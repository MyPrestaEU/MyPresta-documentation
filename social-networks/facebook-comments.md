---
title: "Facebook Comments - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Comments PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Comments - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Comments Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-comments/)
>
> ---


# Facebook Comments

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and any module interacting with external APIs like Facebook.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s settings. This is where you’ll control how the Facebook Comments box appears and functions on your product pages.

#### 2.1.1 Facebook App ID

- **What this setting does:** This is a unique identifier for your Facebook App. While the module can function without it, providing an App ID gives you access to Facebook’s moderation tools and insights for the comments on your site.
- **Effect of changing this setting:**
  - *When provided:* You gain access to Facebook’s comment moderation panel (developers.facebook.com/tools/comments) where you can review, approve, or delete comments. It also helps Facebook attribute the comments to your specific site.
  - *When left empty:* Comments will still appear, but you won’t have the advanced moderation capabilities through Facebook’s developer tools. You’ll rely on Facebook’s default spam filtering.
- **Recommended value:** It’s highly recommended to create a Facebook App and enter your App ID here for better control and moderation.
- **Merchant scenario / example:** You want to ensure that all comments are appropriate and on-topic. By setting up a Facebook App ID, you can easily moderate comments directly from Facebook’s developer dashboard, removing spam or inappropriate content.

#### 2.1.2 Number of Comments

- **What this setting does:** This controls how many comments are initially displayed in the Facebook Comments box before users need to click “View more comments” or “Load more” to see older ones.
- **Effect of changing this setting:**
  - *When set to a low number (e.g., 5):* The comments section will be more compact, requiring users to click to see more. This can be good for pages with limited space or if you want to keep the initial page load lighter.
  - *When set to a higher number (e.g., 20):* More comments will be visible immediately, providing more social proof at a glance. However, it might make the product page longer.
- **Recommended value:** 5-10 comments is a good starting point to balance visibility and page length. Adjust based on your product page design and typical comment volume.
- **Merchant scenario / example:** For popular products with many comments, you might set this to 5 to keep the page tidy. For newer products, setting it to 10 might encourage more interaction by showing more existing comments.

#### 2.1.3 Width of Comments Box

- **What this setting does:** This determines the width of the Facebook Comments box in pixels.
- **Effect of changing this setting:**
  - *When set to a specific pixel value (e.g., 600px):* The comments box will maintain that fixed width, potentially creating empty space or overflowing if your theme’s content area is narrower or wider.
  - *When left empty or set to 100% (if supported by the module):* The comments box will try to automatically adjust to the available width of its parent container, making it responsive.
- **Recommended value:** Leave empty for auto-detect or set to 100% if the module supports it, to ensure responsiveness. If you need a fixed width, ensure it fits your theme’s content area.
- **Merchant scenario / example:** Your product page has a main content column that is 700px wide. You might set the width to 700px to perfectly fill that space. If you want it to adapt to mobile, leaving it empty is usually best.

#### 2.1.4 Language of Comments Box

- **What this setting does:** This allows you to specify the language for the Facebook Comments plugin interface (e.g., “Write a comment…”, “View more comments”).
- **Effect of changing this setting:**
  - *When set to a specific language code (e.g., “en\_US” for English, “fr\_FR” for French):* The Facebook plugin’s text will be displayed in that language, regardless of the user’s browser language or your PrestaShop store’s active language.
  - *When left empty:* Facebook will typically try to detect the user’s preferred language or the language of your PrestaShop store.
- **Recommended value:** It’s generally best to leave this empty so Facebook can automatically detect the user’s language, or set it to your store’s primary language if you want consistency.
- **Merchant scenario / example:** If your store primarily targets customers in Germany, you might set this to “de\_DE” to ensure all Facebook plugin text is in German, even if a user’s browser is set to English.

#### 2.1.5 Position of Comments Box

- **What this setting does:** This determines where on the product page the Facebook Comments box will be displayed. You can choose from various PrestaShop hooks.
- **Effect of changing this setting:**
  - *When set to `displayProductButtons` (or similar):* The comments box might appear near the “Add to Cart” button or other product actions.
  - *When set to `displayFooterProduct` (or similar):* The comments box will appear further down the product page, often below the main product details, which is a common and usually preferred location.
  - *When set to `displayRightColumn` or `displayLeftColumn` (if available):* The comments box would appear in one of your store’s side columns, which is less common for comments and might not be ideal visually.
- **Recommended value:** `displayFooterProduct` or a similar hook that places the comments section below the main product information is usually the most natural and effective placement.
- **Merchant scenario / example:** You want the comments to be visible but not distract from the primary goal of adding the product to the cart. Placing it in `displayFooterProduct` ensures customers see all product details first, then can engage with comments.

#### 2.1.6 Enable Facebook Comments

- **What this setting does:** This is a simple ON/OFF switch to activate or deactivate the entire Facebook Comments functionality.
- **Effect of changing this setting:**
  - *When enabled (YES):* The Facebook Comments box will appear on your product pages according to your other settings.
  - *When disabled (NO):* The Facebook Comments box will be completely hidden from your product pages, and the module will not load any Facebook-related scripts.
- **Recommended value:** YES, if you want to use the feature.
- **Merchant scenario / example:** You’ve finished setting up the module and want to make it live on your store. You switch this to YES. Later, if you decide to temporarily disable comments for maintenance, you can switch it to NO.

#### 2.1.7 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook App ID | (Empty) / Recommended: Your App ID | Enables Facebook moderation tools for comments. |
| Module Configuration | Number of Comments | 5-10 | Sets how many comments are initially visible. Affects page length. |
| Module Configuration | Width of Comments Box | (Empty) / Auto-detect (Responsive) | Defines the width of the comments section. Empty for responsiveness. |
| Module Configuration | Language of Comments Box | (Empty) / Auto-detect | Sets the language of the Facebook plugin interface. Empty for user/store language. |
| Module Configuration | Position of Comments Box | `displayFooterProduct` | Determines where on the product page the comments box appears. |
| Module Configuration | Enable Facebook Comments | YES | Turns the entire Facebook Comments feature ON or OFF. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The Facebook Comments box isn’t showing up on my product pages. What should I do?**
A:

1. **Check “Enable Facebook Comments”:** Ensure this setting in the module configuration is set to YES.
2. **Verify Position:** Make sure the “Position of Comments Box” setting is set to a hook that is actually present and rendered by your theme on product pages (e.g., `displayFooterProduct`). Some custom themes might not use all standard hooks.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache”). Sometimes, old cached content prevents new modules from appearing.
4. **Theme Compatibility:** If you’re using a heavily customized theme, it might override standard product page templates or remove the necessary hooks. Contact your theme developer or a PrestaShop expert for assistance.
5. **Browser Issues:** Try clearing your browser’s cache and cookies, or test in an incognito window.

**Q: How do I moderate the comments?**
A: If you have set up a Facebook App ID and entered it into the module configuration, you can moderate comments directly through Facebook’s developer tools. Go to [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). You’ll need to be logged in with the Facebook account associated with your App ID.

**Q: Can I change the styling (colors, fonts) of the Facebook Comments box?**
A: The styling of the Facebook Comments plugin is largely controlled by Facebook itself to maintain a consistent brand experience. You have very limited control over its internal appearance. You can control the width and its placement, but not its internal CSS.

**Q: Will Facebook Comments slow down my website?**
A: The Facebook Comments plugin loads external scripts from Facebook. While Facebook optimizes these, any external script can add a slight delay to page load. The module is designed to load these scripts efficiently. You can use tools like Google PageSpeed Insights to monitor your site’s performance.

**Q: Do I need a Facebook Business Page for this module to work?**
A: No, you don’t strictly need a Facebook Business Page. However, if you want to use the advanced moderation tools, you will need a Facebook Developer account and to create a basic Facebook App, which is a separate entity from a Business Page.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Facebook Comments module (`facebook-comments`) is a straightforward PrestaShop module primarily designed to inject the Facebook Comments social plugin’s HTML and JavaScript SDK into the front-office product pages. It follows a standard PrestaShop module structure, leveraging hooks for content injection and `Configuration` class for settings storage. It does not introduce custom controllers, models, or complex AJAX interactions.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or `ObjectModel` definitions. All logic is encapsulated within the main `facebook-comments.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- This module does **not** contain any custom JavaScript files. The Facebook JavaScript SDK is loaded directly from Facebook’s CDN by the module’s template.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** contain any custom CSS files. The styling of the Facebook Comments plugin is handled by Facebook’s own stylesheets.

### 4.6 Smarty Template Structure (`views/templates/`)

This module primarily uses a single template file to render the Facebook Comments box.

- **Hook templates (`views/templates/hook/`)**:
  - `facebook-comments.tpl`: This is the main template file.
    - **Purpose:** Renders the `div` element that Facebook’s JavaScript SDK transforms into the comments box. It also includes the necessary JavaScript SDK initialization code.
    - **Variables:**
      - `{$facebook_app_id}`: The Facebook App ID from module configuration.
      - `{$facebook_comments_number}`: The number of comments to display.
      - `{$facebook_comments_width}`: The width of the comments box.
      - `{$facebook_comments_lang}`: The language code for the plugin.
      - `{$product_link}`: The URL of the current product page, used by Facebook to identify the comment thread.
    - **Hooks:** This template is rendered via the hook specified in the module’s configuration (e.g., `displayFooterProduct`).

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does **not** create any custom database tables. All configuration settings are stored in the `ps_configuration` table using standard PrestaShop `Configuration::get()` and `Configuration::updateValue()` methods.

  - Configuration keys typically include:
    - `FACEBOOK_COMMENTS_APP_ID`
    - `FACEBOOK_COMMENTS_NUMBER`
    - `FACEBOOK_COMMENTS_WIDTH`
    - `FACEBOOK_COMMENTS_LANG`
    - `FACEBOOK_COMMENTS_POSITION`
    - `FACEBOOK_COMMENTS_ENABLED`
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to include the Facebook JavaScript SDK once per page, ensuring it’s available before the comments box is rendered. |
| `displayProductButtons` | Near the “Add to Cart” button on product pages. | Optional hook for rendering the comments box, if configured by the merchant. |
| `displayFooterProduct` | At the bottom of the product page content. | Common and recommended hook for rendering the comments box, if configured by the merchant. |
| `displayLeftColumn` | In the left sidebar of pages. | Optional hook for rendering the comments box, if configured by the merchant. (Less common for comments). |
| `displayRightColumn` | In the right sidebar of pages. | Optional hook for rendering the comments box, if configured by the merchant. (Less common for comments). |
| `displayFooter` | In the store’s footer section. | Optional hook for rendering the comments box, if configured by the merchant. (Less common for product-specific comments). |

The module dynamically registers itself to the hook chosen by the merchant in the configuration. The `displayHeader` hook is always used to load the Facebook SDK.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Facebook Comments module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the module’s functionality.
