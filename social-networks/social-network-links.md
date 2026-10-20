---
title: "Social Network Links - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Social Network Links PrestaShop module by MyPresta.eu."
sidebar:
  label: "Social Network Links - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Social Network Links Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/social-network-links/)
>
> ---


# Social Network Links

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Social Network Links)

This is the main and only configuration screen for the “Social Network Links” module. Here you will define which social networks to display and where they appear on your store.

**Access:** Navigate to **Modules > Module Manager**, search for “Social Network Links”, and click “Configure”.

#### **General Settings**

- **Facebook URL:**

  - **What this setting does:** This is where you enter the full web address (URL) of your Facebook page.
  - **Effect of changing this setting:**
    - *When filled:* A Facebook icon will appear in the module block, linking directly to the URL you provided.
    - *When empty:* No Facebook icon will be displayed.
  - **Recommended value:** Your official Facebook page URL (e.g., `https://www.facebook.com/yourstorename`).
  - **Merchant scenario / example:** If your Facebook page is `https://www.facebook.com/MyAwesomeShop`, enter that URL here. Customers clicking the Facebook icon will be taken to your page.
- **Twitter URL:**

  - **What this setting does:** Enter the full web address (URL) of your Twitter profile.
  - **Effect of changing this setting:**
    - *When filled:* A Twitter icon will appear, linking to your Twitter profile.
    - *When empty:* No Twitter icon will be displayed.
  - **Recommended value:** Your official Twitter profile URL (e.g., `https://twitter.com/yourstorename`).
  - **Merchant scenario / example:** If your Twitter handle is `@MyAwesomeShop`, your URL might be `https://twitter.com/MyAwesomeShop`.
- **YouTube URL:**

  - **What this setting does:** Enter the full web address (URL) of your YouTube channel.
  - **Effect of changing this setting:**
    - *When filled:* A YouTube icon will appear, linking to your channel.
    - *When empty:* No YouTube icon will be displayed.
  - **Recommended value:** Your official YouTube channel URL (e.g., `https://www.youtube.com/channel/yourchannelid`).
  - **Merchant scenario / example:** If you have product review videos or tutorials on YouTube, link your channel here.
- **Google+ URL:**

  - **What this setting does:** Enter the full web address (URL) of your Google+ profile or page.
  - **Effect of changing this setting:**
    - *When filled:* A Google+ icon will appear, linking to your profile.
    - *When empty:* No Google+ icon will be displayed.
  - **Recommended value:** Your official Google+ profile/page URL (e.g., `https://plus.google.com/+YourStoreName`).
  - **Merchant scenario / example:** While Google+ is largely deprecated, if you still maintain a presence or have legacy content, you can link it here. Otherwise, leave it empty.
- **RSS URL:**

  - **What this setting does:** Enter the full web address (URL) of your RSS feed. This is typically used for blogs or news sections to allow users to subscribe to updates.
  - **Effect of changing this setting:**
    - *When filled:* An RSS icon will appear, linking to your feed.
    - *When empty:* No RSS icon will be displayed.
  - **Recommended value:** If your store has a blog or news section with an RSS feed, enter its URL (e.g., `https://yourstore.com/blog/feed`). Otherwise, leave empty.
  - **Merchant scenario / example:** If you regularly publish blog posts about your products or industry, providing an RSS feed allows tech-savvy customers to get updates directly.

#### **Display Settings**

- **Display in Header:**

  - **What this setting does:** Controls whether the social network links block appears in the header section of your store.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The social links block will be visible at the top of your website.
    - *When disabled (No):* The block will not appear in the header.
  - **Recommended value:** **Yes**, if you want high visibility for your social links.
  - **Merchant scenario / example:** Enable this if you want customers to immediately see your social presence upon landing on your site.
- **Display in Left Column:**

  - **What this setting does:** Controls whether the social network links block appears in the left sidebar of your store.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The social links block will be visible in the left column (if your theme has one).
    - *When disabled (No):* The block will not appear in the left column.
  - **Recommended value:** **No**, unless you have a specific reason to place it there and your theme supports a left column. Often, the right column or footer is preferred.
  - **Merchant scenario / example:** If your theme has a prominent left column and you want to keep the links visible as customers browse categories, enable this.
- **Display in Right Column:**

  - **What this setting does:** Controls whether the social network links block appears in the right sidebar of your store.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The social links block will be visible in the right column (if your theme has one).
    - *When disabled (No):* The block will not appear in the right column.
  - **Recommended value:** **Yes**, if you want to display the links in a sidebar.
  - **Merchant scenario / example:** A good option for keeping social links visible without cluttering the header or footer too much.
- **Display in Footer:**

  - **What this setting does:** Controls whether the social network links block appears in the footer section of your store.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The social links block will be visible at the bottom of your website.
    - *When disabled (No):* The block will not appear in the footer.
  - **Recommended value:** **Yes**, as the footer is a standard and expected place for social media links.
  - **Merchant scenario / example:** Enable this to provide a consistent location for social links that customers often look for at the bottom of a page.
- **Display on Product Page:**

  - **What this setting does:** Controls whether the social network links block appears on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The social links block will be visible on every product detail page.
    - *When disabled (No):* The block will not appear on product pages.
  - **Recommended value:** **Yes**, if you want to encourage social sharing or following directly from product pages.
  - **Merchant scenario / example:** If you want customers to easily find your social media while they are considering a purchase, enable this.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook URL | Empty / Your Facebook Page URL | Link to your Facebook profile. Empty = no icon. |
| Module Configuration | Twitter URL | Empty / Your Twitter Profile URL | Link to your Twitter profile. Empty = no icon. |
| Module Configuration | YouTube URL | Empty / Your YouTube Channel URL | Link to your YouTube channel. Empty = no icon. |
| Module Configuration | Google+ URL | Empty / Your Google+ Profile URL | Link to your Google+ profile. Empty = no icon. |
| Module Configuration | RSS URL | Empty / Your RSS Feed URL | Link to your RSS feed. Empty = no icon. |
| Module Configuration | Display in Header | No / Yes | Show social links in the store’s header. |
| Module Configuration | Display in Left Column | No / No | Show social links in the left sidebar. |
| Module Configuration | Display in Right Column | No / Yes | Show social links in the right sidebar. |
| Module Configuration | Display in Footer | No / Yes | Show social links in the store’s footer. |
| Module Configuration | Display on Product Page | No / Yes | Show social links on individual product pages. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: My social icons aren’t showing up after configuration.**

  - **A:** First, double-check that you’ve entered the full URLs for your social networks in the module configuration. Also, ensure you’ve selected at least one “Display in…” option (e.g., “Display in Footer” to Yes). Finally, clear your PrestaShop cache under **Advanced Parameters > Performance** (click “Clear cache” button). Sometimes, theme caching can also prevent changes from appearing immediately.
- **Q: The icons are showing, but they look misaligned or don’t match my theme.**

  - **A:** The module provides basic styling. If your theme has very specific CSS rules, they might override or conflict with the module’s styles.
    - **Solution 1 (Basic):** Try clearing your browser’s cache (Ctrl+F5 or Cmd+R).
    - **Solution 2 (Advanced):** This usually requires a webmaster or developer to inspect your theme’s CSS and potentially add custom CSS rules to your theme’s `custom.css` file to adjust the appearance. The module’s CSS file (`socialnetworklinks.css`) can be a reference.
- **Q: Can I add other social networks not listed (e.g., Instagram, Pinterest)?**

  - **A:** The current version of the module supports Facebook, Twitter, YouTube, Google+, and RSS. To add other networks, it would require custom development to modify the module’s code and add new icons and input fields. Alternatively, look for a more comprehensive social media module if you need a wider range of platforms.
- **Q: The links open in the same tab, but I want them to open in a new tab.**

  - **A:** By default, the module is designed to open links in a new tab (`target="_blank"`). If this is not happening, it might be due to a conflict with your theme’s JavaScript or an older browser. Ensure your PrestaShop and browser are up to date. If the issue persists, a developer would need to inspect the generated HTML.
- **Q: I’ve enabled “Display in Left/Right Column,” but nothing appears.**

  - **A:** Many modern PrestaShop themes are designed without traditional left or right columns on all pages, especially on product pages or the homepage. If your theme doesn’t render these columns, the module won’t have a place to display its block. Check your theme’s documentation or customize its layout to enable columns where you want the module to appear. The footer and header are generally more reliable display locations across themes.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Social Network Links” module is a straightforward PrestaShop module following a basic MVC-like pattern within the module’s scope. It primarily uses the `Module` class for its core functionality, configuration, and hook registration. It stores its settings directly in PrestaShop’s `ps_configuration` table. The module’s front-office display is handled through a single Smarty template rendered via various display hooks.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** contain any custom classes or `ObjectModel` definitions. All logic is encapsulated within the main `SocialNetworkLinks` class.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** contain any custom JavaScript files. The functionality for opening links in new tabs is handled directly in the template’s HTML using `target="_blank"`.

### 4.5 CSS Stylesheets (`views/css/`)

- **`socialnetworklinks/css/socialnetworklinks.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet provides the basic visual appearance for the social media icons, including their size, spacing, and potentially hover effects. It targets the main container block and individual social link elements.
  - **Key CSS class selectors developers can override in their theme:**
    - `.socialnetworklinks_block`: The main container for the social links block.
    - `.socialnetworklinks_block ul`: The unordered list containing the social icons.
    - `.socialnetworklinks_block li`: Individual list items for each social icon.
    - `.socialnetworklinks_block li a`: The anchor tag for each social link.
    - `.socialnetworklinks_block li a i`: The icon element (e.g., Font Awesome or similar, depending on theme).
    - Specific classes for each social network (e.g., `.facebook`, `.twitter`, etc.) might be present or can be added for custom styling per network.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`socialnetworklinks/views/front/column.tpl`**:
    - **Hook(s) rendered in:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (or similar product page hook depending on PrestaShop version and theme).
    - **Visual block output:** This template renders the HTML structure for the social network links block. It iterates through the configured social network URLs and displays an icon (typically using a font icon library like Font Awesome, which is usually provided by the theme or PrestaShop core) for each active link. Each icon is wrapped in an `<a>` tag with `target="_blank"` to open the link in a new tab.
    - **Variables available:**
      - `$facebook_url`: The configured Facebook URL.
      - `$twitter_url`: The configured Twitter URL.
      - `$youtube_url`: The configured YouTube URL.
      - `$google_url`: The configured Google+ URL.
      - `$rss_url`: The configured RSS URL.
      - `$module_dir`: The base directory of the module, useful for linking to module assets (though not heavily used in this specific template).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All configuration settings are stored in the `ps_configuration` table using keys prefixed with `SOCIALNETWORKLINKS_`.

  - `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
  - `PS_SOCIALNETWORKLINKS_TWITTER_URL`
  - `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
  - `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
  - `PS_SOCIALNETWORKLINKS_RSS_URL`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content within the `<head>` section or at the very top of the `<body>`. | Used to display the social links block in the store’s header. |
| `displayLeftColumn` | Renders content in the left sidebar. | Used to display the social links block in the left column. |
| `displayRightColumn` | Renders content in the right sidebar. | Used to display the social links block in the right column. |
| `displayFooter` | Renders content in the store’s footer. | Used to display the social links block in the footer. |
| `displayProductButtons` (or similar product page hook) | Renders content on the product page, often near the “Add to Cart” button or product description. | Used to display the social links block on individual product pages. |
| `moduleRoutes` | (Implicitly handled by PrestaShop for module configuration) | Not directly used for front-office display, but part of the module’s lifecycle. |
| `actionAdminControllerSetMedia` | (Implicitly handled by PrestaShop for module configuration) | Used to load CSS/JS in the back office for the module’s configuration page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Social Network Links” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
