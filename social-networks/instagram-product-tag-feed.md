---
title: "Instagram product tag feed - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Instagram product tag feed PrestaShop module by MyPresta.eu."
sidebar:
  label: "Instagram product tag feed - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Instagram product tag feed Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/instagram-product-tag-feed/)
>
> ---


# Instagram product tag feed

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for API communication, which are almost universally available on modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s settings, go to **Modules > Module Manager** in your PrestaShop Back Office, search for “Instagram product tag feed”, and click the “Configure” button.

Here you will find the main configuration options to control how your Instagram feeds are displayed.

#### General Settings

- **Instagram Access Token:**

  - **What this setting does:** This is a unique code that grants your PrestaShop store permission to access your Instagram account’s public data (like photos associated with specific tags). You need to generate this token from Instagram’s developer tools or a third-party tool that simplifies the process.
  - **Effect of changing this setting:**
    - *When correctly entered:* Your module will be able to fetch and display Instagram photos.
    - *When incorrect or empty:* The module will not be able to connect to Instagram, and no photos will be displayed, resulting in an empty feed or an error message.
  - **Recommended value:** Your valid Instagram Access Token.
  - **Merchant scenario / example:** You’ve just set up your Instagram Business account. You’ll need to follow Instagram’s instructions (or use a helper tool) to get this token and paste it here. Without it, the module can’t “see” your Instagram photos.
- **Instagram User ID:**

  - **What this setting does:** This is the unique numerical identifier for your Instagram account. It’s often required alongside the Access Token to correctly fetch data.
  - **Effect of changing this setting:**
    - *When correctly entered:* Ensures the module fetches data from your specific Instagram account.
    - *When incorrect or empty:* May lead to errors in fetching data or fetching data from the wrong account, resulting in an empty or incorrect feed.
  - **Recommended value:** Your valid Instagram User ID.
  - **Merchant scenario / example:** Similar to the Access Token, you’ll obtain this ID when setting up your Instagram API access. It tells the module *whose* Instagram feed to look at.
- **Number of photos to display:**

  - **What this setting does:** Controls how many Instagram photos are fetched and displayed in a single feed instance.
  - **Effect of changing this setting:**
    - *When set to a higher number (e.g., 10):* More photos will be loaded and potentially shown in the feed, making it richer but possibly slower to load.
    - *When set to a lower number (e.g., 3):* Fewer photos will be displayed, resulting in a more concise feed and faster loading times.
  - **Recommended value:** Start with 6-9 photos for a good balance of content and performance. Adjust based on your layout and page speed tests.
  - **Merchant scenario / example:** For a product page tab, you might want 6 photos. For a homepage carousel, you might want 12 to give more variety as users scroll.
- **Display on Homepage:**

  - **What this setting does:** A simple switch to enable or disable the Instagram feed on your store’s homepage.
  - **Effect of changing this setting:**
    - *When enabled:* The module will attempt to display an Instagram feed on your homepage (usually via the `displayHome` hook).
    - *When disabled:* No Instagram feed will appear on your homepage.
  - **Recommended value:** YES, if you want to showcase your Instagram content prominently. NO, if you prefer a cleaner homepage or only want feeds on product pages.
  - **Merchant scenario / example:** You want to show off your latest lifestyle shots on the homepage to engage visitors immediately. You’d enable this.
- **Display on Product Page:**

  - **What this setting does:** A simple switch to enable or disable the Instagram feed on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The module will attempt to display a product-specific Instagram feed on your product pages (usually via `displayProductTab` or `displayProductExtraContent` hooks).
    - *When disabled:* No Instagram feed will appear on product pages.
  - **Recommended value:** YES, as this is one of the module’s core features and a powerful conversion tool.
  - **Merchant scenario / example:** You sell shoes, and you want to show Instagram photos of people wearing *that specific shoe model* on its product page. You’d enable this.
- **Display on Left Column:**

  - **What this setting does:** Controls whether the Instagram feed appears in your store’s left sidebar column.
  - **Effect of changing this setting:**
    - *When enabled:* A feed will be rendered in the left column on pages where it’s hooked.
    - *When disabled:* No feed in the left column.
  - **Recommended value:** NO, unless you have a very specific design need. Columns can become cluttered.
  - **Merchant scenario / example:** You want a small, persistent feed visible as customers browse categories.
- **Display on Right Column:**

  - **What this setting does:** Controls whether the Instagram feed appears in your store’s right sidebar column.
  - **Effect of changing this setting:**
    - *When enabled:* A feed will be rendered in the right column on pages where it’s hooked.
    - *When disabled:* No feed in the right column.
  - **Recommended value:** NO, unless you have a very specific design need. Columns can become cluttered.
  - **Merchant scenario / example:** Similar to the left column, for a persistent, smaller feed.
- **Display in Footer:**

  - **What this setting does:** Controls whether the Instagram feed appears in your store’s footer area.
  - **Effect of changing this setting:**
    - *When enabled:* A feed will be rendered in the footer.
    - *When disabled:* No feed in the footer.
  - **Recommended value:** YES, for a subtle yet effective way to showcase your Instagram. It’s less intrusive than columns.
  - **Merchant scenario / example:** You want to add a visually appealing section at the bottom of every page, encouraging visitors to explore your Instagram.
- **Display in Header (Left):**

  - **What this setting does:** Controls whether the Instagram feed appears in the left part of your store’s header.
  - **Effect of changing this setting:**
    - *When enabled:* A feed will be rendered in the header’s left section.
    - *When disabled:* No feed in the header.
  - **Recommended value:** NO, typically headers are reserved for navigation and branding.
  - **Merchant scenario / example:** Very specific design where you want a small, rotating Instagram icon or a single image in the header.
- **Display in Header (Right):**

  - **What this setting does:** Controls whether the Instagram feed appears in the right part of your store’s header.
  - **Effect of changing this setting:**
    - *When enabled:* A feed will be rendered in the header’s right section.
    - *When disabled:* No feed in the header.
  - **Recommended value:** NO, typically headers are reserved for navigation and branding.
  - **Merchant scenario / example:** Similar to Header (Left).
- **Carousel Feature:**

  - **What this setting does:** Enables or disables the carousel (sliding gallery) functionality for the Instagram feeds.
  - **Effect of changing this setting:**
    - *When enabled:* Photos will display in a horizontal, scrollable carousel, saving space and allowing users to browse many images easily.
    - *When disabled:* Photos will likely display in a static grid or list, depending on the template.
  - **Recommended value:** YES, for most placements (homepage, product page) as it’s space-efficient and engaging.
  - **Merchant scenario / example:** You have 9 photos for a product, but only space for 3 at a time. Enabling the carousel allows customers to swipe through all 9.
- **Fancybox Feature:**

  - **What this setting does:** Enables or disables the “Fancybox” effect, which is a popular JavaScript library that displays images in a stylish, overlaying popup when clicked.
  - **Effect of changing this setting:**
    - *When enabled:* Clicking an Instagram photo in the feed will open it in a large, elegant popup window, allowing customers to view details without leaving the page.
    - *When disabled:* Clicking an image might open it directly in a new browser tab or simply do nothing, depending on the theme.
  - **Recommended value:** YES, as it provides a much better user experience for viewing images.
  - **Merchant scenario / example:** A customer sees a great outfit on Instagram in your feed. Clicking it opens a large, clear view of the photo, making it easier to appreciate the details.

#### Product Page Specific Settings (Product Back Office Tab)

After installing the module, you will find a new field or tab when editing a product in your PrestaShop Back Office:

- **Instagram Hashtag (per product):**
  - **What this setting does:** This field allows you to specify a unique Instagram hashtag for each individual product. The module will then use this hashtag to fetch relevant photos from your Instagram account.
  - **Effect of changing this setting:**
    - *When a hashtag is entered (e.g., #myproductname):* The Instagram feed on that specific product page will display photos from your Instagram account that are tagged with `#myproductname`.
    - *When left empty:* No product-specific Instagram feed will be displayed for that product, even if “Display on Product Page” is enabled.
  - **Recommended value:** A unique, descriptive hashtag for each product. Ensure you are consistently using this hashtag on your Instagram posts.
  - **Merchant scenario / example:** For a product called “Summer Breeze Dress,” you might enter `#SummerBreezeDress` or `#MyBrandSummerDress`. Then, when you post photos of this dress on Instagram, you include that hashtag. The module will then pull those photos onto the dress’s product page.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Instagram Access Token | Your valid token | Connects to Instagram API to fetch photos. **CRITICAL.** |
| Module Config | Instagram User ID | Your valid User ID | Identifies your Instagram account for data fetching. |
| Module Config | Number of photos to display | 6-9 | Controls how many photos are shown in a feed instance. |
| Module Config | Display on Homepage | YES | Shows a general feed on your store’s homepage. |
| Module Config | Display on Product Page | YES | Shows a product-specific feed on product pages. |
| Module Config | Display on Left Column | NO | Shows a feed in the left sidebar. Can clutter layout. |
| Module Config | Display on Right Column | NO | Shows a feed in the right sidebar. Can clutter layout. |
| Module Config | Display in Footer | YES | Shows a feed in the store’s footer. Good for subtle promotion. |
| Module Config | Display in Header (Left) | NO | Shows a feed in the left header. Generally not recommended. |
| Module Config | Display in Header (Right) | NO | Shows a feed in the right header. Generally not recommended. |
| Module Config | Carousel Feature | YES | Displays photos in a sliding gallery, saving space. |
| Module Config | Fancybox Feature | YES | Opens photos in a stylish popup for better viewing. |
| Product Edit Page | Instagram Hashtag | Unique per product | Defines the hashtag to pull photos for *this specific product*. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My Instagram feed is not showing any photos. What should I do?**
A:

1. **Check your Instagram Access Token and User ID:** These are the most common culprits. Ensure they are correctly entered in the module configuration and are still valid. Instagram tokens can expire, so you might need to regenerate them.
2. **Verify Hashtags:** For product pages, ensure the “Instagram Hashtag” field is filled in for the specific product and that you actually have posts on Instagram using that exact hashtag.
3. **Public Account:** Ensure your Instagram account is public. The module cannot fetch photos from private accounts.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and clear the Smarty cache (and optionally, all caches). Sometimes old cached data prevents new content from appearing.
5. **Check for API Limits:** Instagram has API rate limits. If you’re fetching too frequently or have a very large number of products, you might hit these limits temporarily.

**Q: The images are showing, but they look strange or break my theme’s layout.**
A:

1. **Theme Conflicts:** Your custom PrestaShop theme might have conflicting CSS styles. This is a common issue with third-party modules.
2. **Module CSS:** The module includes its own CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Your webmaster or developer can inspect the page to identify conflicting styles and write custom CSS overrides in your theme’s stylesheet.
3. **Image Dimensions:** Ensure the images you post on Instagram are of reasonable quality and aspect ratio. While the module tries to adapt, extremely wide or tall images might cause display issues.

**Q: How do I get an Instagram Access Token and User ID?**
A: Instagram’s API access has changed over time. You typically need an Instagram Business Account and a Facebook Developer Account. The process involves creating a Facebook App, connecting it to your Instagram Business Account, and then generating a token. There are also third-party tools (search for “Instagram Access Token Generator”) that can simplify this process, but always use reputable ones.

**Q: Can I display different feeds on different pages (e.g., a general feed on the homepage and product-specific feeds)?**
A: Yes, absolutely! That’s the core functionality. Use the “Display on Homepage” setting for a general feed (which will typically pull from a default hashtag or your main user feed), and then use the “Instagram Hashtag” field on individual product pages for product-specific feeds.

**Q: The carousel or Fancybox isn’t working.**
A:

1. **Enable the Features:** Double-check that “Carousel Feature” and “Fancybox Feature” are enabled in the module’s configuration.
2. **JavaScript Conflicts:** Another module or your theme might be loading conflicting JavaScript libraries (e.g., another carousel script or lightbox). Your webmaster would need to debug this using the browser’s developer console (look for JavaScript errors).
3. **jQuery:** Ensure jQuery is correctly loaded on your store, as many JavaScript features rely on it.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Instagram product tag feed` module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for configuration and `Hook` system for front-office display. It integrates a custom class for Instagram API interaction and utilizes external JavaScript libraries (lightslider, fancybox) for enhanced UI/UX. The module’s core logic resides within its main `index.php` file, handling configuration, installation, and hook registration. Front-office rendering is achieved by passing data to Smarty templates registered to various display hooks.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any dedicated front-office or back-office controllers. All configuration is handled via the `getContent()` method in the main module file, and front-office display is managed directly through registered hooks.

### 4.3 Core Classes & Models (`classes/`)

- `instagramfeed/classes/index.php`:

  - This is typically an empty file or a file containing `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` to prevent direct directory listing. It does not contain any functional class logic.
- `instagramfeed/classes/instagram_class.php`:

  - **Class Name**: `Instagram`
  - **Parent Class**: None (standalone utility class)
  - **Responsibility**: This class encapsulates the logic for interacting with the Instagram API. It’s responsible for making HTTP requests to fetch media based on user ID and hashtags, handling access tokens, and parsing the JSON responses from Instagram.
  - **Key Public Methods**:
    - `__construct($access_token, $user_id)`: Constructor, initializes with the Instagram access token and user ID.
    - `getMediaByHashtag($hashtag, $count)`: Fetches a specified number of media items from the Instagram API that are tagged with the given hashtag and associated with the configured user ID. Returns an array of media objects.
    - `getMediaByUser($count)`: Fetches a specified number of media items directly from the user’s feed (if supported by the API version and token scope).
    - (Potentially other helper methods for API calls, error handling, etc.)

### 4.4 JavaScript Assets (`views/js/`)

- `instagramfeed/js/if_carousell.js`:
  - **Scope**: Front-office.
  - **Description**: This script likely initializes and configures the `lightslider` carousel functionality for the Instagram feeds. It binds to specific DOM elements (e.g., `ul` with a certain class) and applies the carousel behavior, including settings for responsiveness, auto-play, navigation, etc.
  - **Dependencies**: Relies on `lightslider.js` and jQuery.
- `instagramfeed/js/if_fancybox.js`:
  - **Scope**: Front-office.
  - **Description**: This script initializes and configures the Fancybox lightbox functionality. It targets image links within the Instagram feed (e.g., `a` tags wrapping `img` tags) and enables them to open in a Fancybox popup when clicked, providing a larger, more immersive view of the image.
  - **Dependencies**: Relies on Fancybox library (not included in this module, but expected to be loaded by the theme or another module) and jQuery.
- `instagramfeed/js/if_sliding.js`:
  - **Scope**: Front-office.
  - **Description**: This file might be an alternative or supplementary script for sliding functionality, possibly for older PrestaShop versions or specific layouts. Given `if_carousell.js` and `lightslider.js`, it could be a legacy script or a wrapper for specific sliding behaviors not covered by the main carousel.
  - **Dependencies**: Likely jQuery.
- `instagramfeed/js/ps14.js`:
  - **Scope**: Front-office (specifically for PrestaShop 1.4 compatibility).
  - **Description**: This script likely contains compatibility fixes or polyfills for older PrestaShop 1.4 environments, addressing potential JavaScript differences or missing jQuery versions/features compared to newer PrestaShop releases.
  - **Dependencies**: jQuery.
- `instagramfeed/lib/src/js/lightslider.js`:
  - **Scope**: Front-office.
  - **Description**: This is the core `lightslider` jQuery plugin library. It provides the functionality for creating responsive, touch-enabled content carousels and sliders. `if_carousell.js` would typically call methods from this library.
  - **Dependencies**: jQuery.

### 4.5 CSS Stylesheets (`views/css/`)

- `instagramfeed/css/css.css`:
  - **Scope**: Front-office customer styling.
  - **Description**: Contains custom CSS rules specific to the Instagram feed’s layout, image sizing, spacing, and general appearance within the various hooks. It defines classes for the feed container, individual image items, and potentially captions or links.
  - **Key CSS class selectors**: Developers can inspect the generated HTML to find classes like `.instagram-feed-container`, `.instagram-item`, `.instagram-image`, etc., which can be overridden in the theme’s `custom.css` or `theme.css`.
- `instagramfeed/lib/src/css/lightslider.css`:
  - **Scope**: Front-office customer styling.
  - **Description**: This is the default stylesheet for the `lightslider` jQuery plugin. It provides the essential styling for the carousel’s navigation arrows, pagination dots, slide transitions, and responsive behavior.
  - **Key CSS class selectors**: Classes like `.lightSlider`, `.lSAction`, `.lSPager`, etc., which can be customized to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `instagramfeed/views/templates/admin/instagram_feed.tpl`: This template is rendered by the `getContent()` method in the main module file. It displays the module’s back-office configuration form, including input fields for the Instagram Access Token, User ID, number of photos, and various display toggles (homepage, product page, columns, footer, header, carousel, fancybox). It typically uses PrestaShop’s helper form components.
- **Hook templates (`views/templates/hook/`)**:

  - `instagramfeed/views/templates/hook/column-feed.tpl`: Renders the Instagram feed when hooked into `displayLeftColumn` or `displayRightColumn`. It typically displays a more compact version of the feed.
  - `instagramfeed/views/templates/hook/feed.tpl`: A general-purpose feed template, likely used for the main homepage or footer display. It contains the core structure for displaying Instagram images, potentially wrapped in a carousel container.
  - `instagramfeed/views/templates/hook/header-left.tpl`: Renders the feed when hooked into `displayHeaderLeft`.
  - `instagramfeed/views/templates/hook/header-right.tpl`: Renders the feed when hooked into `displayHeaderRight`.
  - `instagramfeed/views/templates/hook/homepage-feed.tpl`: Specifically designed for the `displayHome` hook, often featuring a more prominent or wider layout for the homepage.
  - `instagramfeed/views/templates/hook/tab.tpl`: Renders the tab title for the Instagram feed on the product page (e.g., “Instagram Photos”). This is typically hooked into `displayProductTab` (PrestaShop 1.6) or `displayProductExtraContent` (PrestaShop 1.7+).
  - `instagramfeed/views/templates/hook/tabcontents.tpl`: Renders the actual content of the Instagram feed within the product page tab. This template will contain the logic to display the images fetched using the product-specific hashtag, often utilizing the carousel and fancybox features.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings (Access Token, User ID, display options, etc.) are stored in the `ps_configuration` table using keys like `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS`, etc.
  - The product-specific Instagram hashtag is stored in the `ps_product_lang` table (or a similar product-related table) as a new field added by the module during installation. This field would typically be named `instagram_hashtag` or similar.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to load CSS and JavaScript assets (lightslider, fancybox, custom scripts) required for the Instagram feeds. |
| `displayHome` | On the store’s homepage. | Renders the general Instagram feed on the homepage. |
| `displayLeftColumn` | In the left sidebar of pages where it’s enabled. | Renders a compact Instagram feed in the left column. |
| `displayRightColumn` | In the right sidebar of pages where it’s enabled. | Renders a compact Instagram feed in the right column. |
| `displayFooter` | In the store’s footer section. | Renders a general Instagram feed in the footer. |
| `displayHeaderLeft` | In the left part of the store’s header. | Renders a small Instagram feed in the header. |
| `displayHeaderRight` | In the right part of the store’s header. | Renders a small Instagram feed in the header. |
| `displayProductTab` (PS 1.6) | On the product page, for adding new tabs. | Renders the title of the Instagram feed tab on the product page. |
| `displayProductTabContent` (PS 1.6) | On the product page, for adding content to tabs. | Renders the content (the actual Instagram feed) within the product page tab. |
| `displayProductExtraContent` (PS 1.7+) | On the product page, for adding extra content blocks. | Alternative hook for PrestaShop 1.7+ to display the Instagram feed on product pages, often as a new block below the main product info. |
| `actionProductUpdate` | After a product is updated in the Back Office. | Used to save the `instagram_hashtag` field value for the product. |
| `actionProductAdd` | After a new product is added in the Back Office. | Used to save the `instagram_hashtag` field value for the new product. |
| `displayAdminProductsExtra` | In the product editing page in the Back Office. | Renders the input field for the “Instagram Hashtag” on the product configuration page. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing assistance and ensuring your module functions optimally.
