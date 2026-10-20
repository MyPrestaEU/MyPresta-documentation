---
title: "Sticky Cart Bar PRO - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Sticky Cart Bar PRO PrestaShop module by MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Sticky Cart Bar PRO Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The Sticky Cart Bar PRO module offers a powerful set of configuration options, divided into several key areas for managing your sticky bars and A/B tests.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you first click “Configure” on the module, you’ll land on a dashboard that provides an overview and access to the main sections. This page acts as a central hub.

The main configuration page for Sticky Cart Bar PRO is structured with tabs or sections to manage different aspects of the module.

#### General Settings / Dashboard Overview

This section typically presents a summary of your active bars, A/B tests, and quick links to the main management screens.

- **What this section does:** Provides a high-level overview of your module’s status and quick navigation to create new bars, manage existing ones, or set up A/B tests.
- **Effect of changing this setting:** This is primarily a navigation and informational screen. Changes here involve clicking links to other dedicated management screens.
- **Recommended value:** Review this dashboard regularly to monitor your sticky bars and experiments.

### 2.2 Dedicated Admin Screens & Controller Views

The module features dedicated admin controllers for managing your sticky bars and A/B tests, offering a comprehensive interface for design, targeting, and analysis.

#### 2.2.1 Sticky Cart Bars Management (Back Office > Modules > Sticky Cart Bar PRO > **Manage Bars**)

This screen is where you create, edit, and manage all your sticky cart bars.

- **Screen Name & Menu Location:** You’ll find this under **Modules > Sticky Cart Bar PRO > Manage Bars** (or a similar menu entry directly within the module’s configuration).
- **Available Actions & Settings:**
  - **Bar Listing Table:** Displays all your created sticky bars with key information like name, status (active/inactive), and assigned experiments.
    - *Effect:* Provides an organized view of all your sticky bars.
    - *Recommended:* Keep bar names descriptive for easy identification.
  - **Add New Bar Button:** Initiates the process of creating a new sticky bar.
    - *Effect:* Opens the “Layout Studio” where you design your bar.
    - *Recommended:* Start with a clear goal in mind for your new bar (e.g., “Product Page Bottom Bar - Free Shipping”).
  - **Edit Button (for existing bars):** Allows you to modify an existing sticky bar.
    - *Effect:* Re-opens the Layout Studio with the bar’s current settings.
    - *Recommended:* Regularly review and update bars based on performance or promotions.
  - **Duplicate Button:** Creates an exact copy of an existing bar.
    - *Effect:* Saves time when creating similar bars or variations for A/B testing.
    - *Recommended:* Use this to quickly create a new bar based on a successful design, then make minor adjustments.
  - **Toggle Status (Active/Inactive):** A switch to enable or disable a bar without deleting it.
    - *Effect:* An active bar will appear on your front office according to its targeting rules; an inactive bar will not.
    - *Recommended:* Disable bars that are seasonal or no longer relevant, rather than deleting them, in case you need them again.
  - **Delete Button:** Permanently removes a sticky bar.
    - *Effect:* The bar will no longer appear on your store.
    - *Recommended:* Only delete bars you are certain you will never use again.
  - **Layout Studio (when adding/editing a bar):** This is the core design interface.
    - **Drag-and-Drop Editor:** Allows you to visually build your sticky bar by adding and arranging elements.
      - *Effect:* You can customize the layout, content, and appearance of your bar without coding.
      - *Recommended:* Experiment with different element combinations to find what works best for your products and audience.
    - **Element Options:** Each element (e.g., “Add to Cart button,” “Product Image,” “Countdown Timer,” “Custom Text”) has its own settings for styling, content, and behavior.
      - *Effect:* Fine-tune the look and functionality of each part of your bar.
      - *Recommended:* Pay attention to colors, fonts, and sizes to match your store’s branding.
    - **Presets:** Choose from a library of pre-designed sticky bar layouts.
      - *Effect:* Quickly get started with a professional-looking bar.
      - *Recommended:* Use presets as a starting point and then customize them to fit your specific needs.
    - **Targeting Rules:** Define *where* and *to whom* the sticky bar should be displayed.
      - *Effect:* Ensures your bar is shown only to relevant customers on specific pages.
      - *Recommended:* Target specific product categories, brands, or customer groups for maximum impact. Examples:
        - *Display on:* All product pages, specific product IDs, specific categories.
        - *Customer groups:* Only logged-in customers, new visitors, specific customer groups.
        - *Geographic location:* Only customers from certain countries.
        - *Device type:* Desktop, mobile, or both.
    - **Display Position:** Choose whether the bar appears at the top or bottom of the screen.
      - *Effect:* Controls the visual placement of the sticky bar.
      - *Recommended:* Bottom bars are often less intrusive, while top bars can be more prominent. Test both!
    - **Visibility Settings:** Control when the bar appears (e.g., after scrolling a certain distance, after a delay).
      - *Effect:* Prevents the bar from appearing too early or too late, optimizing user experience.
      - *Recommended:* A slight delay or scroll threshold can make the bar feel less aggressive.
- **Recommended workflow for daily store management:**
  1. **Plan:** Decide on the purpose of your new sticky bar (e.g., promote a specific product, offer free shipping, reduce cart abandonment).
  2. **Create:** Use the “Add New Bar” button and the Layout Studio to design your bar. Start with a preset if unsure.
  3. **Target:** Carefully set the targeting rules to ensure the bar appears for the right audience on the right pages.
  4. **Activate:** Set the bar to “Active” once you’re satisfied with its design and targeting.
  5. **Monitor:** Use the analytics dashboard (see next section) to track its performance.
  6. **Optimize:** Based on analytics, edit the bar to improve its effectiveness.

#### 2.2.2 A/B Testing Management (Back Office > Modules > Sticky Cart Bar PRO > **A/B Tests**)

This screen allows you to set up and manage A/B tests for your sticky bars, comparing different versions to see which performs best.

- **Screen Name & Menu Location:** You’ll find this under **Modules > Sticky Cart Bar PRO > A/B Tests**.
- **Available Actions & Settings:**
  - **Experiment Listing Table:** Shows all your active and completed A/B tests, including their status, start/end dates, and performance metrics.
    - *Effect:* Provides an overview of your testing efforts.
    - *Recommended:* Regularly check the status of your experiments.
  - **Add New Experiment Button:** Starts the process of creating a new A/B test.
    - *Effect:* Guides you through selecting a control bar and one or more variant bars.
    - *Recommended:* Have at least two sticky bars ready (one control, one variant) before starting an experiment.
  - **Experiment Configuration (when adding/editing):**
    - **Name:** A descriptive name for your A/B test.
      - *Effect:* Helps you identify the experiment later.
      - *Recommended:* Use names like “Product Page Bottom Bar - Button Color Test” or “Top Bar vs. Bottom Bar.”
    - **Control Bar:** The original or default sticky bar you want to test against.
      - *Effect:* This is your baseline for comparison.
      - *Recommended:* Choose your currently best-performing bar or a standard design.
    - **Variant Bars:** One or more alternative sticky bars you want to test.
      - *Effect:* These are the versions with changes you believe might improve performance.
      - *Recommended:* Focus on testing one major change per variant (e.g., different button color, different message, different position).
    - **Traffic Distribution:** Define what percentage of your audience sees each bar (control vs. variants).
      - *Effect:* Ensures a fair comparison by distributing traffic evenly or as desired.
      - *Recommended:* Start with an even distribution (e.g., 50/50 for two bars, 33/33/33 for three).
    - **Goal:** Define the metric you want to optimize (e.g., “Add to Cart” clicks, conversion rate, revenue).
      - *Effect:* The module will track this metric for each bar.
      - *Recommended:* Choose a clear, measurable goal directly related to your business objective.
    - **Targeting Rules:** Similar to bar targeting, but for the experiment itself. Ensures the A/B test runs only for specific segments.
      - *Effect:* Allows you to run targeted experiments without affecting your entire audience.
      - *Recommended:* If testing a bar for a specific category, apply the same targeting to the experiment.
  - **View Analytics Button:** Accesses detailed performance data for a specific experiment.
    - *Effect:* Shows which bar performed best based on your defined goal.
    - *Recommended:* Let experiments run long enough to gather statistically significant data before making decisions.
  - **Stop Experiment Button:** Ends an active A/B test.
    - *Effect:* The module will stop showing the variant bars and you can choose to make the winning bar permanent.
      *Recommended:* Stop an experiment once a clear winner is identified or if it’s not yielding useful results.
- **Recommended workflow for daily store management:**
  1. **Hypothesize:** Identify an area for improvement (e.g., “I think a red ‘Add to Cart’ button will perform better than a green one”).
  2. **Create Variants:** Duplicate your existing sticky bar and make the specific change you want to test (e.g., change button color).
  3. **Set Up Experiment:** Go to the A/B Tests screen, click “Add New Experiment,” and configure your control, variants, traffic, and goal.
  4. **Launch & Monitor:** Start the experiment and regularly check the analytics dashboard for progress.
  5. **Analyze & Implement:** Once the experiment concludes or a clear winner emerges, implement the winning bar as your default.

#### 2.2.3 Analytics Dashboard (Back Office > Modules > Sticky Cart Bar PRO > **Analytics**)

This screen provides detailed performance metrics for your sticky bars and A/B tests.

- **Screen Name & Menu Location:** You’ll find this under **Modules > Sticky Cart Bar PRO > Analytics**.
- **Available Actions & Settings:**
  - **Dashboard View:** Displays charts and graphs showing key metrics like impressions, clicks, click-through rates (CTR), and conversions for your sticky bars.
    - *Effect:* Gives you a clear visual representation of how your bars are performing.
    - *Recommended:* Use this data to understand which bars are effective and which need improvement.
  - **Filter Options:** Filter data by date range, specific sticky bar, or experiment.
    - *Effect:* Allows you to drill down into specific periods or compare individual bar performance.
    - *Recommended:* Compare performance before and after a major change or promotion.
  - **A/B Test Results:** For active or completed experiments, this section will clearly show which variant is performing better against the control, often with statistical significance indicators.
    - *Effect:* Provides the evidence needed to make data-driven decisions about your sticky bar designs.
    - *Recommended:* Don’t make decisions based on small sample sizes; wait for statistical significance.
- **Recommended workflow for daily store management:**
  1. **Regular Review:** Check the analytics dashboard weekly or monthly to understand overall performance trends.
  2. **Deep Dive:** If a bar is underperforming, use the filters to investigate specific periods or compare it to other bars.
  3. **Decision Making:** Use the A/B test results to confidently choose winning designs and implement them across your store.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

This controller manages the A/B testing experiments. It handles the creation, editing, listing, and deletion of `stickycartbar_experiment` entities.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

This controller manages the individual sticky cart bars themselves. It handles the creation, editing, listing, and deletion of `stickycartbar_bar` entities, including access to the Layout Studio for design.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

This is a placeholder file, typically used to prevent direct directory listing and does not represent a configurable screen itself.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Manage Bars** | Bar Name | Descriptive | Identifies the bar in the back office. |
|  | Layout Studio | N/A | Drag-and-drop editor for bar content and styling. |
|  | Element Options | Varies | Customizes individual elements (buttons, text, images). |
|  | Presets | N/A | Quick-start templates for bar design. |
|  | Targeting Rules | All Product Pages | Defines where and to whom the bar is shown. |
|  | Display Position | Bottom | Controls if bar is at top or bottom of screen. |
|  | Visibility Settings | After scroll | Controls when the bar appears (delay, scroll). |
|  | Status (Active/Inactive) | Inactive (initially) | Enables/disables bar display on front office. |
| **A/B Tests** | Experiment Name | Descriptive | Identifies the A/B test. |
|  | Control Bar | Existing Bar | The baseline bar for comparison. |
|  | Variant Bars | New/Modified Bar(s) | The alternative versions being tested. |
|  | Traffic Distribution | Evenly split | How audience is divided between bars. |
|  | Goal | Add to Cart Clicks | The metric to optimize (e.g., clicks, conversions). |
|  | Targeting Rules | All Product Pages | Defines where the experiment runs. |
|  | Status (Active/Stopped) | Active | Controls if the experiment is running. |
| **Analytics** | Date Range Filter | Last 30 days | Filters performance data by time. |
|  | Bar/Experiment Filter | All | Filters data for specific bars or tests. |
|  | Metrics Display | Impressions, Clicks, CTR | Shows performance data for bars/experiments. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My sticky bar isn’t showing up on my product pages. What should I check?**
**A1:**

- **Is the bar “Active”?** Go to **Modules > Sticky Cart Bar PRO > Manage Bars** and ensure the toggle switch for your bar is set to “Active.”
- **Check Targeting Rules:** Edit your bar and review the “Targeting Rules.” Make sure it’s set to display on the correct pages (e.g., “All Product Pages” or specific categories/products) and for the correct customer groups.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache prevents new module changes from appearing immediately.
- **Module Position:** Ensure the module is hooked correctly. While the module usually handles this, if you’ve manually unhooked it, it won’t appear. Check **Design > Positions** and search for “Sticky Cart Bar PRO” to ensure it’s hooked to `displayHeader` or `displayFooter` (depending on your bar’s position).

**Q2: The sticky bar looks strange or doesn’t match my theme’s design.**
**A2:**

- **Layout Studio Styling:** Go to **Modules > Sticky Cart Bar PRO > Manage Bars**, edit your bar, and use the Layout Studio’s styling options. You can customize colors, fonts, sizes, padding, and more for each element and the bar itself.
- **Theme Conflicts:** Sometimes, your custom theme’s CSS might override the module’s styling. If basic styling options in the Layout Studio don’t fix it, you might need a webmaster to inspect the CSS (see Developer section).
- **Module Compatibility:** Ensure you downloaded the correct module version for your PrestaShop version.

**Q3: How can I translate the text in my sticky bar into other languages?**
**A3:**

- **Module Translations:** For static texts within the module (like button labels if not customized), go to **International > Translations**. Select “Installed modules translations,” choose your theme, select “Sticky Cart Bar PRO,” and then the language you want to translate.
- **Custom Text Elements:** If you’ve added custom text elements using the Layout Studio, you’ll need to edit the bar for each language. When editing the bar, you should see an option to switch languages for text inputs, allowing you to enter translations directly within the Layout Studio.

**Q4: My A/B test isn’t showing clear results or seems stuck.**
**A4:**

- **Duration & Traffic:** A/B tests need sufficient time and traffic to gather statistically significant data. Ensure your experiment has been running long enough (at least a few weeks) and has received enough visitors to draw conclusions.
- **Clear Goal:** Double-check that your A/B test has a clearly defined “Goal” (e.g., “Add to Cart” clicks). Without a goal, the module can’t measure success.
- **No Major Store Changes:** Avoid making significant changes to your store (e.g., new theme, major promotions) while an A/B test is running, as this can skew results.

**Q5: Can I have multiple sticky bars active at the same time?**
**A5:** Yes, you can create and activate multiple sticky bars. However, you must carefully configure their **Targeting Rules** to avoid conflicts. For example, you might have one bar for “All Product Pages” at the bottom, and another specific bar for “Category X Products” at the top. The module will prioritize bars based on their specificity and internal logic, but it’s best practice to ensure your targeting rules don’t overlap in a way that would cause two bars to try and display in the same position on the same page.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Sticky Cart Bar PRO module follows a robust PrestaShop MVC (Model-View-Controller) architecture, heavily leveraging `ObjectModel` for data persistence and `ModuleFrontController`/`AdminController` for request handling. It employs a sophisticated system for layout building, A/B testing, and analytics, with dedicated classes for configuration, styling, targeting, and experiment resolution. The module uses a modular approach, separating concerns into distinct classes for better maintainability and extensibility. Front-office rendering is primarily hook-based, with AJAX for dynamic interactions.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class Name:** `StickyCartBarProAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles all AJAX requests from the front-office sticky bar. This includes:
    - Tracking impressions and clicks for analytics.
    - Updating cart information dynamically (e.g., adding products, changing quantities).
    - Resolving which sticky bar variant to display for A/B tests.
    - Fetching product data for variant pickers or cross-sell suggestions.
    - Returns JSON responses.
- `controllers/front/index.php`
  - **Class Name:** `StickyCartBarProIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder front controller. Typically, it might be used for a default module page, but in this module, front-office rendering is primarily handled via hooks and AJAX. It might serve as a fallback or a base for future features.

#### Back-Office Admin Controllers

- `controllers/admin/AdminStickyCartBarAbController.php`
  - **Class Name:** `AdminStickyCartBarAbController` (extends `AdminController`)
  - **Tab Name:** A/B Tests (within the module’s main menu)
  - **Managed Entity:** `StickyCartBarExperiment` (mapped to `ps_stickycartbar_experiment` table).
  - **Responsibility:** Manages the CRUD operations for A/B testing experiments. This includes:
    - Listing all experiments in a `HelperList`.
    - Providing a `HelperForm` for creating and editing experiment details (name, control bar, variant bars, traffic distribution, goal, targeting rules).
    - Handling experiment activation/deactivation and result viewing.
- `controllers/admin/AdminStickyCartBarProController.php`
  - **Class Name:** `AdminStickyCartBarProController` (extends `AdminController`)
  - **Tab Name:** Manage Bars (within the module’s main menu)
  - **Managed Entity:** `StickyCartBarLayout` (mapped to `ps_stickycartbar_bar` table).
  - **Responsibility:** Manages the CRUD operations for individual sticky cart bars. This controller integrates with the “Layout Studio” for visual design.
    - Listing all sticky bars in a `HelperList`.
    - Providing the interface for the drag-and-drop Layout Studio, including element configuration, styling, and targeting rules.
    - Handles saving and loading bar configurations, including HTML structure, CSS, and JavaScript settings.
- `controllers/admin/index.php`
  - **Class Name:** N/A (placeholder file)
  - **Responsibility:** Prevents direct directory listing for security.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`: Placeholder file to prevent directory listing.
- `classes/ScbpCompatibility.php`: Handles compatibility layers for different PrestaShop versions (e.g., `Context` differences, specific helper methods).
- `classes/StickyCartBarAdminUi.php`: Utility class for generating common UI elements or handling specific UI logic within the admin panel.
- `classes/StickyCartBarAnalytics.php`: Manages the collection, storage, and retrieval of analytics data for sticky bars and A/B tests (impressions, clicks, conversions).
- `classes/StickyCartBarConfig.php`: Handles module-specific configuration settings stored in `ps_configuration` (e.g., global module enable/disable, default settings).
- `classes/StickyCartBarElementStyles.php`: Manages the styling properties and generation of CSS for individual elements within a sticky bar.
- `classes/StickyCartBarExperiment.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_stickycartbar_experiment`
  - **`$definition` fields:** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
  - **Key Public Methods:** CRUD operations, methods to retrieve control/variant bars, calculate experiment results.
- `classes/StickyCartBarExperimentMatcher.php`: Determines if a given experiment’s targeting rules match the current context (customer, page, device).
- `classes/StickyCartBarExperimentResolver.php`: Given a set of active experiments, determines which sticky bar (control or variant) should be displayed to the current visitor based on traffic distribution and experiment rules.
- `classes/StickyCartBarExperimentRule.php`: Represents a single targeting rule within an experiment.
- `classes/StickyCartBarExperimentVariant.php`: Represents a variant sticky bar within an A/B test.
- `classes/StickyCartBarLayout.php`
  - **Extends:** `ObjectModel`
  - **Database Table:** `ps_stickycartbar_bar`
  - **`$definition` fields:** `id_stickycartbar_bar`, `name`, `content` (JSON for elements, styles, settings), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
  - **Key Public Methods:** CRUD operations, methods to render the bar, retrieve its elements, apply styles.
- `classes/StickyCartBarLayoutInstances.php`: Manages instances of sticky bar layouts, potentially for caching or runtime access.
- `classes/StickyCartBarLayoutPreset.php`: Represents a single pre-designed sticky bar layout.
- `classes/StickyCartBarLayoutPresets.php`: Manages the collection of available layout presets.
- `classes/StickyCartBarLayoutPresetsBuiltin.php`: Contains the definitions for the module’s default, built-in layout presets.
- `classes/StickyCartBarListPresenter.php`: Helper class for formatting and presenting data in admin lists (e.g., `HelperList`).
- `classes/StickyCartBarMatcher.php`: Determines if a sticky bar’s targeting rules (for a non-experiment bar) match the current context.
- `classes/StickyCartBarRule.php`: Represents a single targeting rule for a sticky bar.
- `classes/StickyCartBarTargeting.php`: Central class for evaluating all targeting rules (for both bars and experiments) against the current front-office context.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`: Provides autocomplete functionality, likely used in the admin for selecting products, categories, or manufacturers for targeting rules.
- `views/js/admin-ab-dashboard.js`: Handles interactive elements and data visualization on the A/B testing dashboard in the back office.
- `views/js/admin-analytics-dashboard.js`: Manages charts, filters, and data display on the analytics dashboard.
- `views/js/admin-audience-picker.js`: Powers the interactive interface for defining audience targeting rules (e.g., selecting customer groups, countries).
- `views/js/admin-element-editor.js`: Provides the JavaScript logic for editing individual elements within the Layout Studio (e.g., opening modal for text input, color pickers).
- `views/js/admin-layout-builder.js`: The core JavaScript for the drag-and-drop Layout Studio, handling element placement, resizing, and interaction.
- `views/js/admin-layout-preview.js`: Manages the real-time preview of the sticky bar within the Layout Studio.
- `views/js/admin-layout-studio.js`: Orchestrates all components of the Layout Studio, combining builder, editor, and preview functionalities.
- `views/js/admin.js`: General-purpose JavaScript for the module’s back-office pages, including global event listeners, form submissions, and AJAX calls.
- `views/js/front.js`: The main front-office JavaScript for the sticky bar.
  - **Scope:** Front-office.
  - **Event Listeners:** Scrolls (to detect when to show/hide the bar), clicks on “Add to Cart” buttons within the bar, clicks on variant selectors, form submissions.
  - **DOM Manipulation:** Inserts the sticky bar HTML into the DOM, updates cart quantities, changes product variants, shows/hides elements (e.g., FOMO timers).
  - **AJAX Calls:** Communicates with `controllers/front/ajax.php` to track events, update cart, and fetch dynamic content.
  - **Third-party SDKs:** None explicitly listed, but could potentially integrate with analytics platforms if configured.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`: Styles for the autocomplete search tool in the admin.
- `views/css/admin-audience-picker.css`: Styles for the audience targeting interface in the admin.
- `views/css/admin-bars-list.css`: Styles for the list of sticky bars in the admin.
- `views/css/admin-config.css`: General styles for the module’s main configuration page.
- `views/css/admin-dashboard.css`: Styles for the main module dashboard and potentially analytics/A/B test overviews.
- `views/css/admin-element-editor.css`: Styles for the element editing modals/panels within the Layout Studio.
- `views/css/admin-layout-builder.css`: Core styles for the drag-and-drop layout builder interface.
- `views/css/admin-layout-preview.css`: Styles for the real-time preview area in the Layout Studio.
- `views/css/admin-layout-studio.css`: Overall styles for the Layout Studio, combining all its components.
- `views/css/admin-searchtool.css`: Specific styles for the search tool used in the admin.
- `views/css/front-classic.css`: Specific front-office styles for PrestaShop’s “Classic” theme.
  - **Main UI components:** Overrides or adds styles to ensure the sticky bar integrates well with the Classic theme’s default elements.
  - **Key CSS class selectors:** `.scbp-bar`, `.scbp-button`, `.scbp-product-info`, etc., potentially with theme-specific overrides.
- `views/css/front-hummingbird.css`: Specific front-office styles for PrestaShop’s “Hummingbird” theme (PrestaShop 8.1+).
  - **Main UI components:** Similar to `front-classic.css` but tailored for the Hummingbird theme’s structure and design.
  - **Key CSS class selectors:** `.scbp-bar`, `.scbp-button`, etc., with Hummingbird-specific adjustments.
- `views/css/front.css`: General front-office styles for the sticky bar, applied to all themes.
  - **Main UI components:** Base styling for the sticky bar container, its elements (buttons, text, images, timers), and positioning (fixed top/bottom).
  - **Key CSS class selectors:** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Developers can override these classes in their theme’s custom CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `sticky-cart-bar-classic.tpl`: Renders the sticky bar specifically for the Classic theme. This template likely includes theme-specific HTML structure or class names to ensure seamless integration.
  - **Hook:** `displayHeader` or `displayFooter` (depending on bar position and module’s internal logic).
  - **Output:** The main HTML structure for the sticky bar, including placeholders for dynamic content.
- `sticky-cart-bar-element-inner.tpl`: Renders the inner content of a single element within the sticky bar. This is a reusable partial.
  - **Hook:** N/A (included by other templates).
  - **Output:** HTML for a specific element type (e.g., product name, price, quantity input).
- `sticky-cart-bar-element.tpl`: Renders a single element (e.g., button, image, text block) of the sticky bar, wrapping `sticky-cart-bar-element-inner.tpl` with common element wrappers.
  - **Hook:** N/A (included by other templates).
  - **Output:** HTML for a single, styled sticky bar component.
- `sticky-cart-bar-hummingbird.tpl`: Renders the sticky bar specifically for the Hummingbird theme. Similar to `sticky-cart-bar-classic.tpl` but adapted for the newer theme.
  - **Hook:** `displayHeader` or `displayFooter`.
  - **Output:** The main HTML structure for the sticky bar, optimized for Hummingbird.
- `sticky-cart-bar-inner.tpl`: Renders the inner content of the entire sticky bar, containing all the individual elements.
  - **Hook:** N/A (included by `sticky-cart-bar.tpl`).
  - **Output:** The combined HTML of all configured elements for a sticky bar.
- `sticky-cart-bar.tpl`: The main template responsible for rendering the sticky cart bar on the front office. It determines which theme-specific template (classic/hummingbird) to include or uses a generic structure.
  - **Hook:** `displayHeader` or `displayFooter` (module registers itself to these hooks).
  - **Output:** The complete, rendered sticky cart bar, including its container, elements, and necessary data attributes for JavaScript.

#### Admin templates (`views/templates/admin/`)

- `ab-test-dashboard.tpl`: Renders the main dashboard for A/B testing, showing experiment lists and summary data.
- `ab-tests-tab.tpl`: Renders the content for the “A/B Tests” tab within the module’s configuration.
- `analytics-dashboard.tpl`: Renders the analytics dashboard with charts and performance metrics.
- `audience-picker.tpl`: Renders the HTML for the audience targeting selection interface (e.g., country, customer group pickers).
- `bars-tab.tpl`: Renders the content for the “Manage Bars” tab, including the list of sticky bars.
- `configure.tpl`: The main configuration template for the module, acting as the wrapper for all other admin templates and tabs.
- `country-priority-picker.tpl`: Renders a specific UI component for selecting and prioritizing countries in targeting rules.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_stickycartbar_bar`: Stores the configuration for each individual sticky cart bar.
  - `id_stickycartbar_bar` (PK, INT)
  - `name` (VARCHAR)
  - `content` (TEXT, JSON-encoded: contains elements, styles, position, visibility settings)
  - `targeting_rules` (TEXT, JSON-encoded: conditions for display)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_stickycartbar_experiment`: Stores the configuration for each A/B testing experiment.
  - `id_stickycartbar_experiment` (PK, INT)
  - `name` (VARCHAR)
  - `id_control_bar` (INT, FK to `ps_stickycartbar_bar`)
  - `id_variant_bars` (TEXT, JSON-encoded array of FKs to `ps_stickycartbar_bar`)
  - `traffic_distribution` (TEXT, JSON-encoded: percentage for each bar)
  - `goal` (VARCHAR: e.g., ‘add\_to\_cart’, ‘conversion’)
  - `targeting_rules` (TEXT, JSON-encoded)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_stickycartbar_analytics`: Stores analytics data (impressions, clicks, conversions) for bars and experiments.
  - `id_stickycartbar_analytics` (PK, INT)
  - `id_stickycartbar_bar` (INT, FK)
  - `id_stickycartbar_experiment` (INT, FK, NULLABLE)
  - `type` (VARCHAR: ‘impression’, ‘click’, ‘add\_to\_cart’, ‘conversion’)
  - `id_customer` (INT, NULLABLE)
  - `id_guest` (INT, NULLABLE)
  - `date_add` (DATETIME)
- **`ps_configuration`**: Stores global module settings (e.g., `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects CSS and JavaScript files for the sticky bar, and potentially the initial HTML structure if the bar is positioned at the top. |
| `displayFooter` | Before the closing `</body>` tag on every page. | Injects the HTML structure for sticky bars positioned at the bottom, and any necessary JavaScript initialization. |
| `actionFrontControllerSetMedia` | After a front controller has set its media assets. | Allows the module to conditionally add its JS/CSS based on the current page context (e.g., only on product pages). |
| `actionProductUpdate` | After a product is updated in the back office. | Potentially used to clear cache related to product data that might be displayed in sticky bars. |
| `actionObjectProductAddAfter` | After a new product is added. | Similar to `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | After an existing product is updated. | Similar to `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Potentially used to clean up any references to the deleted product in sticky bar configurations. |
| `actionCartSave` | After a cart is saved or updated. | Used to track “Add to Cart” events for analytics and A/B testing goals. |
| `actionValidateOrder` | After an order is successfully validated. | Used to track conversion events for analytics and A/B testing goals. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | Injects CSS and JavaScript for the module’s admin interfaces (Layout Studio, dashboards). |
| `moduleRoutes` | During URL routing initialization. | Registers custom front-office routes for AJAX controllers if needed. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Sticky Cart Bar PRO module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist you with any issues or questions regarding the module’s functionality and compatibility.
