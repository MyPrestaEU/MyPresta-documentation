---
title: "Twitter widget free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Twitter widget free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Twitter widget free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Twitter widget free Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/twitter-widget-free/)
>
> ---


# Twitter widget free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Twitter widget free” module. Here you will define how your Twitter timeline appears and functions on your store.

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Twitter Username** | `mypresta` (example) | **What this setting does:** This is the most crucial setting. It specifies the Twitter (X) account whose public tweets will be displayed. You need to enter your account’s username (e.g., `mypresta`, `yourstorename`).   **Effect of changing this setting:**   *When set to your username:* The widget will fetch and display tweets from your specified account.   *When left empty or incorrect:* The widget will either not display any tweets or display an error message, as it won’t know which account to pull data from.   **Recommended value:** Your official Twitter (X) username, without the ”@” symbol.   **Merchant scenario / example:** If your Twitter handle is `@MyAwesomeStore`, you would enter `MyAwesomeStore` here. |
| **Widget ID** | `(empty)` | **What this setting does:** This is an advanced setting for specific Twitter widget configurations. Twitter allows you to create custom widgets on their platform, which generate a unique ID. This ID can be used to display a highly customized timeline (e.g., a timeline of specific lists, search results, or collections).   **Effect of changing this setting:**   *When left empty:* The module will generate a standard timeline based on your “Twitter Username.” This is usually sufficient for most merchants.   *When a valid Widget ID is entered:* The module will display the specific, customized timeline associated with that ID, overriding the default user timeline.   **Recommended value:** Leave empty unless you have created a custom widget on Twitter’s developer platform and specifically want to use its ID.   **Merchant scenario / example:** You might create a custom Twitter widget that only shows tweets containing a specific hashtag related to a campaign. You would then get that widget’s ID from Twitter and enter it here. |
| **Theme** | `light` | **What this setting does:** Controls the visual theme of the Twitter widget.   **Effect of changing this setting:**   *When set to `light` (default):* The widget will have a light background and dark text, suitable for most light-themed PrestaShop stores.   *When set to `dark` (if available):* The widget will have a dark background and light text, ideal for dark-themed stores or to create a contrast.   **Recommended value:** `light` for most stores. Choose `dark` if your store’s design uses a dark color scheme.   **Merchant scenario / example:** If your website has a clean, white background, `light` theme will blend in perfectly. If your site uses a sophisticated dark grey or black background, `dark` theme would be more appropriate. |
| **Link Color** | `(empty)` | **What this setting does:** Allows you to customize the color of links within the Twitter widget (e.g., hashtags, mentions, URLs).   **Effect of changing this setting:**   *When left empty:* The widget will use Twitter’s default link color (typically a shade of blue).   *When a valid hex color code is entered (e.g., `#FF0000` for red):* All links within the widget will display in that custom color.   **Recommended value:** Leave empty for default, or enter a hex color code that matches your store’s branding.   **Merchant scenario / example:** If your brand’s primary color is green, you could enter `#008000` to make the links in the widget match your brand. |
| **Border Color** | `(empty)` | **What this setting does:** Allows you to customize the color of the border around the Twitter widget.   **Effect of changing this setting:**   *When left empty:* The widget will use Twitter’s default border color.   *When a valid hex color code is entered:* The widget’s border will display in that custom color.   **Recommended value:** Leave empty for default, or enter a hex color code that matches your store’s branding or blends with your layout.   **Merchant scenario / example:** To make the widget stand out with a subtle frame, you might use a light grey border `#CCCCCC`. |
| **Tweet Limit** | `20` | **What this setting does:** Determines the maximum number of tweets that will be displayed in the timeline.   **Effect of changing this setting:**   *When set to a lower number (e.g., `3`):* Only the most recent few tweets will be visible, making the widget shorter.   *When set to a higher number (e.g., `20`):* More tweets will be loaded, making the widget longer and allowing more scrolling.   **Recommended value:** `3` to `7` for side columns to keep it concise, `10` to `20` for wider areas like the footer or main content.   **Merchant scenario / example:** If you place the widget in a narrow left column, you might set it to `3` to avoid making the column too long. In the footer, you might set it to `10` to show more activity. |
| **Height** | `300` | **What this setting does:** Sets the fixed height of the Twitter widget in pixels.   **Effect of changing this setting:**   *When set to a lower number (e.g., `200`):* The widget will be shorter, potentially requiring more scrolling to see all tweets (up to the Tweet Limit).   *When set to a higher number (e.g., `500`):* The widget will be taller, displaying more tweets at once without scrolling.   **Recommended value:** `280` to `400` pixels, depending on the placement and available space.   **Merchant scenario / example:** For a right column, a height of `300px` is often a good balance. For a footer placement, you might increase it to `400px` if you have ample vertical space. |
| **Width** | `(empty)` | **What this setting does:** Sets the fixed width of the Twitter widget in pixels.   **Effect of changing this setting:**   *When left empty:* The widget will attempt to automatically adjust its width to fit the container it’s placed in (responsive behavior). This is generally recommended.   *When set to a specific number (e.g., `250`):* The widget will maintain that fixed width, which might cause overflow or empty space if the container is larger or smaller.   **Recommended value:** Leave empty for responsive behavior, or set a specific width if you need precise control and understand the implications for different screen sizes.   **Merchant scenario / example:** Leaving it empty ensures it looks good on mobile. If you absolutely need a fixed width for a very specific layout, you might set it to `280px` for a narrow column. |
| **Language** | `en` | **What this setting does:** Determines the language in which the Twitter widget interface (e.g., “View on Twitter” button, timestamps) is displayed.   **Effect of changing this setting:**   *When set to `en` (English):* The widget interface will be in English.   *When set to another valid language code (e.g., `fr` for French, `es` for Spanish):* The widget interface will be localized to that language.   **Recommended value:** The primary language of your store.   **Merchant scenario / example:** If your store primarily serves customers in France, setting this to `fr` will make the widget more user-friendly for them. |
| **Display Header** | `YES` | **What this setting does:** Controls whether the header section of the Twitter widget (showing your account name and “Tweets” label) is visible.   **Effect of changing this setting:**   *When enabled (YES):* The header will be displayed, providing clear context about whose tweets are being shown.   *When disabled (NO):* The header will be hidden, resulting in a more compact widget, but potentially less clear context.   **Recommended value:** `YES` for clarity, unless you need a very minimalist design.   **Merchant scenario / example:** If the widget is in a prominent location, `YES` is good. If it’s a small widget in a crowded area, `NO` might save space. |
| **Display Footer** | `YES` | **What this setting does:** Controls whether the footer section of the Twitter widget (typically showing “View on Twitter” link) is visible.   **Effect of changing this setting:**   *When enabled (YES):* The footer will be displayed, providing a direct link for users to visit your full Twitter profile.   *When disabled (NO):* The footer will be hidden, making the widget more compact.   **Recommended value:** `YES` to encourage users to follow you on Twitter.   **Merchant scenario / example:** Keeping `YES` helps drive traffic to your Twitter profile. |
| **Display Border** | `YES` | **What this setting does:** Controls whether a border is displayed around the Twitter widget.   **Effect of changing this setting:**   *When enabled (YES):* A border will frame the widget, helping it stand out from surrounding content.   *When disabled (NO):* The widget will have no visible border, blending more seamlessly with the background.   **Recommended value:** `YES` for better visual separation, especially in columns.   **Merchant scenario / example:** If your page has a lot of content, a border helps define the widget’s space. If you want a very clean, integrated look, `NO` might be preferred. |
| **Display Scrollbar** | `YES` | **What this setting does:** Controls whether a scrollbar appears within the widget if the content (tweets) exceeds the set height.   **Effect of changing this setting:**   *When enabled (YES):* A scrollbar will appear, allowing users to scroll through all loaded tweets within the fixed height.   *When disabled (NO):* No scrollbar will appear. If tweets exceed the height, they will be cut off, or the widget might expand (depending on other settings and browser behavior). This is generally not recommended as it hides content.   **Recommended value:** `YES` to ensure all tweets are accessible.   **Merchant scenario / example:** Always keep `YES` unless you only ever want to show 1-2 tweets and never want scrolling. |
| **Transparent Background** | `YES` | **What this setting does:** Controls whether the background of the Twitter widget is transparent.   **Effect of changing this setting:**   *When enabled (YES):* The widget’s background will be transparent, allowing your store’s background color or image to show through.   *When disabled (NO):* The widget will have a solid background (white for `light` theme, dark for `dark` theme), potentially creating a boxy appearance.   **Recommended value:** `YES` for better integration with your theme.   **Merchant scenario / example:** If your store has a textured background or a specific background color, `YES` will make the widget look like a natural part of your design. |
| **Show Replies** | `YES` | **What this setting does:** Controls whether replies to tweets are included in the timeline.   **Effect of changing this setting:**   *When enabled (YES):* Replies will be shown, providing a more complete conversation context.   *When disabled (NO):* Only original tweets and retweets will be shown, making the timeline potentially cleaner but less conversational.   **Recommended value:** `YES` for a more active and engaging feed.   **Merchant scenario / example:** If you frequently engage with customers via replies, `YES` is important to showcase that interaction. If your feed is purely for announcements, `NO` might be preferred. |
| **Autoplay Videos** | `NO` | **What this setting does:** Controls whether videos embedded in tweets within the widget will automatically play.   **Effect of changing this setting:**   *When enabled (YES):* Videos will start playing automatically when they appear in the viewport. This can be engaging but might consume bandwidth and annoy some users.   *When disabled (NO):* Videos will require a user click to play.   **Recommended value:** `NO` to avoid surprising customers with sound or consuming their data without consent.   **Merchant scenario / example:** Generally, `NO` is better for user experience. If you have a very specific, silent, short video you want to highlight, you might consider `YES`, but proceed with caution. |
| **Hide Scrollbar** | `NO` | **What this setting does:** This setting is likely redundant or conflicting with “Display Scrollbar”. In general, if “Display Scrollbar” is YES, this setting should be NO.   **Effect of changing this setting:**   *When enabled (YES):* Attempts to hide the scrollbar. This can lead to content being inaccessible if the height is fixed and tweets exceed it.   *When disabled (NO):* Allows the scrollbar to be visible if “Display Scrollbar” is also YES.   **Recommended value:** `NO` to ensure content is always accessible.   **Merchant scenario / example:** Always keep `NO` in conjunction with `Display Scrollbar: YES`. |
| **Place in hook** | `displayRightColumn` | **What this setting does:** Determines where in your PrestaShop store the Twitter widget will be displayed.   **Effect of changing this setting:**   *When set to `displayRightColumn` (default):* The widget will appear in the right sidebar.   *When set to `displayLeftColumn` (if available):* The widget will appear in the left sidebar.   *When set to `displayFooter` (if available):* The widget will appear in the footer section.   *When set to `displayHeader` (if available):* The widget will appear in the header section.   *When set to `displayProductButtons` or similar (if available):* The widget will appear on product pages.   **Recommended value:** `displayRightColumn` or `displayLeftColumn` for general visibility, `displayFooter` for a less intrusive placement. Choose based on your theme’s layout and where you want to draw attention.   **Merchant scenario / example:** If your theme has a prominent right sidebar, `displayRightColumn` is a good choice. If you want it to be visible on every page but not take up much space, `displayFooter` is suitable. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| Module Configuration | Twitter Username | Your X username | Specifies the account to display tweets from. |
| Module Configuration | Widget ID | Empty | Advanced: Use for custom Twitter-generated widgets. |
| Module Configuration | Theme | `light` | Visual theme of the widget (light/dark). |
| Module Configuration | Link Color | Empty | Customizes link colors within the widget. |
| Module Configuration | Border Color | Empty | Customizes the widget’s border color. |
| Module Configuration | Tweet Limit | `20` | Maximum number of tweets to display. |
| Module Configuration | Height | `300` | Fixed height of the widget in pixels. |
| Module Configuration | Width | Empty | Fixed width of the widget in pixels (leave empty for responsive). |
| Module Configuration | Language | `en` | Language of the widget interface. |
| Module Configuration | Display Header | `YES` | Show/hide the widget header (account name). |
| Module Configuration | Display Footer | `YES` | Show/hide the widget footer (View on Twitter link). |
| Module Configuration | Display Border | `YES` | Show/hide the widget’s outer border. |
| Module Configuration | Display Scrollbar | `YES` | Show/hide the internal scrollbar for tweets. |
| Module Configuration | Transparent Background | `YES` | Make the widget background transparent. |
| Module Configuration | Show Replies | `YES` | Include/exclude replies in the timeline. |
| Module Configuration | Autoplay Videos | `NO` | Autoplay videos in tweets. |
| Module Configuration | Hide Scrollbar | `NO` | (Redundant with Display Scrollbar) Keep NO. |
| Module Configuration | Place in hook | `displayRightColumn` | Where the widget appears in your store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My Twitter widget isn’t showing up on my store. What should I do?**
A:

1. **Check Configuration:** Go to **Modules > Module Manager > Twitter widget free > Configure**. Ensure you have entered your correct “Twitter Username” and saved the settings.
2. **Check Hook Placement:** Verify that the “Place in hook” setting is set to a hook that is actually rendered by your theme (e.g., `displayRightColumn`). Some themes might not display all standard hooks.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache prevents new module content from appearing immediately.
4. **Theme Compatibility:** While the module is broadly compatible, very heavily customized themes might require minor adjustments. If the issue persists, contact MyPresta.eu support.

**Q: The widget appears, but it’s empty or shows an error message.**
A:

1. **Incorrect Username:** Double-check your “Twitter Username” in the module configuration. Even a small typo will prevent it from fetching tweets.
2. **Private Account:** Ensure your Twitter account is public. The widget cannot display tweets from private (protected) accounts.
3. **Twitter API Issues:** Occasionally, there might be temporary issues with Twitter’s own API. Wait a little while and check again.

**Q: How do I change the language of the widget?**
A: In the module configuration, find the “Language” setting and select the appropriate two-letter language code (e.g., `fr` for French, `es` for Spanish).

**Q: The widget looks too wide/narrow or too tall/short.**
A:

1. **Width:** For responsive behavior, leave the “Width” setting empty. If you’ve set a specific pixel value, try removing it.
2. **Height:** Adjust the “Height” setting (in pixels) to make the widget taller or shorter.
3. **Tweet Limit:** Reduce the “Tweet Limit” to make the widget shorter if you have a fixed height and want fewer tweets displayed.

**Q: Can I display tweets from a specific hashtag or list instead of my main account?**
A: Yes, but this requires an advanced setup. You would need to create a custom embedded timeline widget directly on Twitter’s developer platform (developer.twitter.com), configure it there to show a hashtag or list, and then obtain the unique “Widget ID” it provides. You would then enter this “Widget ID” into the module’s configuration, leaving the “Twitter Username” empty.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Twitter widget free” module is a straightforward PrestaShop module designed to integrate Twitter’s embedded timeline functionality. It primarily leverages PrestaShop’s standard module structure, using the main `index.php` file for both installation/uninstallation and configuration (`getContent()`). The module injects a JavaScript-based Twitter widget into the front-office using a Smarty template and a CSS file for basic styling. It relies on Twitter’s own `widgets.js` for rendering the timeline, which is loaded asynchronously.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office display is handled entirely via hooks and a Smarty template.
- **Back-Office Admin Controllers**: None. All configuration is managed through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in this module. All logic is self-contained within the main `twitterwidget/index.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included directly within the module’s `views/js/` directory.
- The module relies heavily on the official Twitter `widgets.js` script, which is dynamically loaded in the front-office template (`rightcolumn.tpl`) to render the embedded timeline. This script handles all the complex logic of fetching tweets and displaying them.

### 4.5 CSS Stylesheets (`views/css/`)

- `twitterwidget/twitterwidget.css`:
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: This file likely contains minimal styling, primarily to ensure the Twitter widget integrates well with various PrestaShop themes. It might include rules for the `.twitter-widget` container, basic resets, or responsive adjustments.
  - **Key CSS class selectors developers can override**: Developers can inspect this file to identify specific selectors (e.g., `.twitter-widget-container`, `.twitter-timeline`) and override them in their theme’s `custom.css` or `theme.css` to further customize the widget’s appearance.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `twitterwidget/rightcolumn.tpl`:
    - **Hook(s) rendered in**: This template is designed to be rendered in various display hooks, as configured by the merchant (e.g., `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). The module’s `hookDisplay*` methods will call this template.
    - **Visual block output**: This template outputs the HTML structure required for Twitter’s embedded timeline. It typically includes a `<a>` tag with `data-` attributes (e.g., `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`) that Twitter’s `widgets.js` script reads to render the timeline. It also includes the `<script>` tag to load `widgets.js` asynchronously.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - This module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using standard PrestaShop configuration keys (e.g., `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME`, etc.).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Potentially used to load the Twitter widget script globally, or to display the widget in the header area. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Displays the Twitter widget in the right column. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Displays the Twitter widget in the left column. |
| `displayFooter` | In the footer section of every page. | Displays the Twitter widget in the footer. |
| `displayProductButtons` | On the product page, typically near the add-to-cart button or product description. | Displays the Twitter widget on product pages. |
| `actionFrontControllerSetMedia` | After the front controller has set its media, allowing modules to add their own. | Used to register module’s CSS and potentially JS files (though this module loads Twitter’s JS directly in TPL). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Twitter widget free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
