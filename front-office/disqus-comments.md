---
title: "DISQUS comments - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the DISQUS comments PrestaShop module by MyPresta.eu."
sidebar:
  label: "DISQUS comments - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy DISQUS comments Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/disqus-comments/)
>
> ---


# DISQUS comments

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop and for communication with external services like Disqus.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > DISQUS comments)

This is the main configuration screen where you will set up how Disqus integrates with your store.

#### **1. Site shortname**

- **What this setting does:** This is the unique identifier for your Disqus website. You get this from your Disqus account when you register your website. It tells Disqus which comment threads belong to your store.
- **Effect of changing this setting:**
  - *When set correctly:* Disqus comments will load and save correctly for your products.
  - *When incorrect or empty:* Disqus will not be able to load comments, or it might load comments from a different site, leading to errors or missing comments.
- **Recommended value:** Your unique Disqus shortname (e.g., `yourstorename`).
- **Merchant scenario / example:** If you registered your website on Disqus as “My Awesome Store,” your shortname might be “myawesomestore.” Enter that exact string here.

#### **2. Comments widget position**

- **What this setting does:** This controls where the main Disqus comment section appears on your product pages.
- **Effect of changing this setting:**
  - *When set to “Product Tab section”:* Comments will appear in a new tab on the product page (e.g., next to “Description” or “Data sheet”). Customers click the tab to see comments.
  - *When set to “Product Footer section”:* Comments will appear at the bottom of the product page, below the main product information. Customers will see them as they scroll down.
- **Recommended value:** “Product Tab section” for a cleaner product page layout, or “Product Footer section” if you want comments to be immediately visible without clicking a tab.
- **Merchant scenario / example:** If your product pages are already very long, putting comments in a tab keeps the initial view tidy. If you want to emphasize customer feedback, placing them in the footer makes them more prominent.

#### **3. Testimonials page**

- **What this setting does:** This enables or disables a dedicated page on your store that aggregates all Disqus comments from across your products.
- **Effect of changing this setting:**
  - *When “Enabled”:* A new page will be created at a URL like `yourstore.com/testimonials` (or similar, depending on your friendly URLs) showing all comments.
  - *When “Disabled”:* No such page will be available.
- **Recommended value:** “Enabled” to provide a central hub for customer feedback.
- **Merchant scenario / example:** Enabling this allows you to link to a “Customer Reviews” or “What Our Customers Say” page from your footer, showcasing all positive feedback in one place.

#### **4. Testimonials link appearance**

- **What this setting does:** If the “Testimonials page” is enabled, this controls where a link to that page appears in your store’s layout.
- **Effect of changing this setting:**
  - *When “Hide”:* The testimonials page will exist, but no automatic link will be added by the module. You would need to manually add a link (e.g., in your theme’s footer menu).
  - *When “Left column”:* A link to the testimonials page will appear in the left column of your store.
  - *When “Right column”:* A link to the testimonials page will appear in the right column of your store.
- **Recommended value:** “Right column” or “Left column” to make the testimonials page easily discoverable.
- **Merchant scenario / example:** If your store uses a left column for categories, placing the testimonials link in the right column might be more appropriate.

#### **5. Homepage recent comments**

- **What this setting does:** This controls whether a block displaying the most recent Disqus comments appears on your store’s homepage.
- **Effect of changing this setting:**
  - *When “Enabled”:* A block with recent comments will be displayed on your homepage.
  - *When “Disabled”:* No recent comments block will appear on the homepage.
- **Recommended value:** “Enabled” to keep your homepage dynamic and highlight recent customer activity.
- **Merchant scenario / example:** Showing recent comments on the homepage can encourage visitors to explore products that have active discussions, potentially leading to more sales.

#### **6. Right column recent comments**

- **What this setting does:** This controls whether a block displaying the most recent Disqus comments appears in the right column of your store.
- **Effect of changing this setting:**
  - *When “Enabled”:* A block with recent comments will be displayed in the right column on pages where the right column is active.
  - *When “Disabled”:* No recent comments block will appear in the right column.
- **Recommended value:** “Enabled” to maintain engagement across your site.
- **Merchant scenario / example:** If your store has a right column, displaying recent comments there can provide a constant stream of fresh content and encourage exploration.

#### **7. Left column recent comments**

- **What this setting does:** This controls whether a block displaying the most recent Disqus comments appears in the left column of your store.
- **Effect of changing this setting:**
  - *When “Enabled”:* A block with recent comments will be displayed in the left column on pages where the left column is active.
  - *When “Disabled”:* No recent comments block will appear in the left column.
- **Recommended value:** “Enabled” to maintain engagement across your site.
- **Merchant scenario / example:** Similar to the right column, using the left column for recent comments can be effective if your theme primarily uses the left column for navigation or other blocks.

#### **8. Show disqus only for logged users that purchased product**

- **What this setting does:** This is a powerful setting to restrict who can see and interact with Disqus comments on product pages.
- **Effect of changing this setting:**
  - *When “Enabled”:* Only customers who are logged into their account AND have previously purchased the specific product will see the Disqus comment section. All other visitors will not see it.
  - *When “Disabled”:* All visitors (logged in or guest, purchasers or not) will see the Disqus comment section.
- **Recommended value:** “Disabled” for maximum engagement and SEO benefits. “Enabled” if you want to ensure only verified buyers can comment, which can increase the credibility of reviews but reduce the volume of comments.
- **Merchant scenario / example:** If you’re struggling with spam or irrelevant comments, enabling this can filter out non-buyers. However, if your goal is broad discussion and SEO, keep it disabled.

#### **9. How many recent comments to show?**

- **What this setting does:** This determines the number of recent comments displayed in the “Recent Comments” blocks (on homepage, left, or right columns).
- **Effect of changing this setting:**
  - *When set to a number (e.g., 5):* The blocks will display that many of the most recent comments.
  - *When set to 0 or empty:* No recent comments will be displayed in the blocks, even if the blocks are enabled.
- **Recommended value:** 3 to 5 comments for a compact block, or up to 10 for a more prominent display.
- **Merchant scenario / example:** Showing 5 comments provides a good balance between displaying activity and not making the block too long.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Site shortname | Your Disqus shortname | Unique identifier for your Disqus account; essential for comments to load. |
| Module Configuration | Comments widget position | Product Tab section | Where the main comment section appears on product pages (tab or footer). |
| Module Configuration | Testimonials page | Enabled | Creates a dedicated page aggregating all comments. |
| Module Configuration | Testimonials link appearance | Right column | Where a link to the testimonials page appears (if enabled). |
| Module Configuration | Homepage recent comments | Enabled | Displays a block of recent comments on the homepage. |
| Module Configuration | Right column recent comments | Enabled | Displays a block of recent comments in the right column. |
| Module Configuration | Left column recent comments | Enabled | Displays a block of recent comments in the left column. |
| Module Configuration | Show disqus only for logged users that purchased product | Disabled | Restricts comment visibility/interaction to verified buyers. |
| Module Configuration | How many recent comments to show? | 5 | Number of comments to display in recent comments blocks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Disqus comments are not appearing on product pages. What should I do?**

- **A:** First, double-check your “Site shortname” in the module configuration. It must exactly match the shortname from your Disqus account. Also, ensure you have set “Comments widget position” to either “Product Tab section” or “Product Footer section.” Finally, clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.

**Q2: The “Recent Comments” blocks are not showing up in my columns/homepage.**

- **A:** Verify that you have enabled “Homepage recent comments,” “Right column recent comments,” or “Left column recent comments” in the module configuration. Also, ensure that “How many recent comments to show?” is set to a number greater than 0. If your theme doesn’t display left/right columns on certain pages, the blocks won’t appear there. Clear cache after making changes.

**Q3: I enabled the “Testimonials page,” but I can’t find a link to it.**

- **A:** If you set “Testimonials link appearance” to “Hide,” the module won’t automatically add a link. You’ll need to manually add a link to the page (e.g., in your theme’s footer menu). The URL for the testimonials page is typically `yourstore.com/module/disqus/testimonials` (or a friendly URL version if enabled). If you chose “Left column” or “Right column,” ensure those columns are active on the pages you’re viewing.

**Q4: Only some users can see the comments, or I can’t see them as a guest.**

- **A:** Check the setting “Show disqus only for logged users that purchased product.” If this is enabled, only logged-in customers who have bought the specific product will see the comments. Disable this setting if you want all visitors to see and interact with comments.

**Q5: My custom theme’s styling is clashing with the Disqus comments.**

- **A:** The Disqus widget itself is largely self-contained and styled by Disqus. However, the container or tab that holds the widget might be affected by your theme’s CSS. You may need a web developer to inspect the elements using browser developer tools and add custom CSS to your theme to adjust spacing, fonts, or colors around the Disqus widget.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the DISQUS comments module for developers and webmasters.

### 4.1 Architecture Overview

The DISQUS comments module follows a standard PrestaShop module architecture, primarily leveraging hooks for front-office display and a `getContent()` method for back-office configuration. It integrates the Disqus Universal Embed Code dynamically. The module uses a custom front controller for the testimonials page, and another for AJAX calls (though currently, the AJAX controller appears to be a placeholder or not heavily utilized for core Disqus functionality). Configuration is stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - **Class Name:** `DisqusIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** This controller is likely a default or fallback for the module’s front-office routing. In the context of Disqus, it might be used for general module-related front-end actions, though the primary Disqus embed is usually handled via hooks. It might serve as a base for future AJAX functionalities or simple page displays if needed.
  - `controllers/front/testimonials.php`
    - **Class Name:** `DisqusTestimonialsModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility:** This controller is responsible for rendering the dedicated “Testimonials” page. It retrieves the necessary configuration (e.g., `disqus_shortname`) and passes it to the `testimonials.tpl` template, which then embeds the Disqus Universal Embed Code configured to display all comments for the given shortname. This controller handles the route `module/disqus/testimonials`.
- **Back-Office Admin Controllers**: None explicitly defined in the provided inventory. All configuration is handled via the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are present in the `classes/` directory according to the inventory. The module relies on PrestaShop’s `Configuration` class to store its settings.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are present in the `views/js/` directory according to the inventory. The module directly embeds the Disqus Universal Embed Code (usually a `<script>` tag with `DISQUS.init()` or similar logic) into the relevant Smarty templates. This means Disqus’s own JavaScript is loaded from `disqus.com` directly.

### 4.5 CSS Stylesheets (`views/css/`)

No custom CSS files are present in the `views/css/` directory according to the inventory. The styling of the Disqus comment widget itself is handled by Disqus. Any integration-specific styling (e.g., for the recent comments blocks or the testimonials page layout) would either be minimal, inherited from the theme, or inline within the templates.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `last-comments.tpl`: This template is used to display the “Recent Comments” block. It iterates through a list of recent comments (fetched from Disqus via JavaScript or a server-side call if implemented) and displays them. This template is likely rendered in `displayHome`, `displayLeftColumn`, and `displayRightColumn` hooks.
  - `leftColumn.tpl`: This template is likely a wrapper or specific content for the `displayLeftColumn` hook, potentially including `last-comments.tpl` or the testimonials link.
  - `productfooter.tpl`: This template is rendered in the `displayProductFooter` hook. It contains the Disqus Universal Embed Code for product comments when the “Comments widget position” is set to “Product Footer section.”
  - `rightColumn.tpl`: Similar to `leftColumn.tpl`, this is for the `displayRightColumn` hook, potentially including `last-comments.tpl` or the testimonials link.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**:

  - `testimonials.tpl`: This template is rendered by the `DisqusTestimonialsModuleFrontController`. It contains the Disqus Universal Embed Code configured to display all comments for the site shortname, effectively creating the aggregated testimonials page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom SQL tables. All configuration settings are stored in the `ps_configuration` table using keys like `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Potentially used to include global Disqus configuration variables or CSS/JS if needed, though the main embed is in specific content hooks. |
| `displayProductExtraContent` | Within the product page, often used for tabs or additional content blocks. | Used to display the Disqus comment section within a product tab when “Comments widget position” is set to “Product Tab section.” |
| `displayRightColumn` | In the right column of pages. | Used to display the “Recent Comments” block or the “Testimonials link” if configured. |
| `displayProductFooter` | At the bottom of the product page content. | Used to display the Disqus comment section when “Comments widget position” is set to “Product Footer section.” |
| `displayLeftColumn` | In the left column of pages. | Used to display the “Recent Comments” block or the “Testimonials link” if configured. |
| `displayHome` | On the homepage. | Used to display the “Recent Comments” block on the homepage. |
| `actionValidateOrder` | After an order has been successfully validated. | This hook is listed in the module’s `install()` method, suggesting a potential future feature or a check for purchased products. It’s likely used in conjunction with the “Show disqus only for logged users that purchased product” setting to verify purchase history. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the DISQUS comments module.
