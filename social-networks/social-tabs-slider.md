---
title: "Social tabs slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Social tabs slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Social tabs slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Social tabs slider Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/social-tabs-slider/)
>
> ---


# Social tabs slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and ensure proper communication with social media APIs.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you will set up all the options for your Social tabs slider.

#### General Settings

- **Template:**

  - **What this setting does:** This allows you to choose the visual style and design of your social tabs. The module comes with several pre-designed templates.
  - **Effect of changing this setting:**
    - *When set to Template 1, 2, 3, etc.:* The appearance of the social icons, the tab design, and potentially the animation style will change on your front office.
  - **Recommended value:** Experiment to find the one that best matches your store’s theme.
  - **Merchant scenario / example:** If your store has a minimalist design, you might choose a template with clean, flat icons. If you prefer a more vibrant look, another template might offer colorful, glossy icons.
- **Position:**

  - **What this setting does:** Determines where the social tabs slider will appear on your website.
  - **Effect of changing this setting:**
    - *When set to “Left”:* The slider will be fixed to the left side of the browser window.
    - *When set to “Right”:* The slider will be fixed to the right side of the browser window.
  - **Recommended value:** “Left” or “Right” depending on your theme’s layout and where it causes less interference with other elements.
  - **Merchant scenario / example:** If your theme has a left sidebar, you might choose “Right” to avoid clutter. If your theme is wide and centered, either “Left” or “Right” could work well.
- **Last tab opened by default:**

  - **What this setting does:** Controls whether one of the social tabs should automatically open when a visitor first lands on your page.
  - **Effect of changing this setting:**
    - *When set to “YES”:* The last social tab that was opened by a previous visitor (or a default one if no history) will automatically slide out when a new visitor arrives.
    - *When set to “NO”:* All social tabs will remain closed until the visitor actively clicks or hovers over one.
  - **Recommended value:** “NO” to avoid potentially annoying visitors with an automatically opening tab.
  - **Merchant scenario / example:** You might set it to “YES” temporarily if you’re running a special campaign on one social network and want to draw immediate attention to it, but generally, “NO” provides a better user experience.

#### Facebook Like Box Settings

- **Display Facebook Like Box:**

  - **What this setting does:** Toggles the visibility of the Facebook tab and its embedded Like Box.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The Facebook tab will appear in the slider, and when opened, it will display your Facebook Fan Page Like Box.
    - *When disabled (NO):* The Facebook tab will not be shown in the slider.
  - **Recommended value:** “YES” if you have an active Facebook page you want to promote.
  - **Merchant scenario / example:** If Facebook is a primary channel for customer interaction and marketing, you’ll definitely want this enabled.
- **Facebook Like Box Height:**

  - **What this setting does:** Sets the vertical size of the Facebook Like Box content area when the tab is open.
  - **Effect of changing this setting:**
    - *When set to a higher value (e.g., 500px):* More content (posts, faces) from your Facebook page will be visible within the tab.
    - *When set to a lower value (e.g., 200px):* Less content will be visible, requiring scrolling if the feed is long.
  - **Recommended value:** Start with `280px` and adjust based on how much content you want to show and how it looks on your site.
  - **Merchant scenario / example:** If you post frequently and want visitors to see more of your recent activity, increase the height.
- **Facebook Like Box Color Scheme:**

  - **What this setting does:** Changes the color theme of the Facebook Like Box itself (not the tab icon).
  - **Effect of changing this setting:**
    - *When set to “Light”:* The Like Box background and text will use lighter colors.
    - *When set to “Dark”:* The Like Box background and text will use darker colors.
  - **Recommended value:** Choose “Light” or “Dark” to best match your store’s overall design.
  - **Merchant scenario / example:** If your website has a dark background, a “Dark” color scheme for the Like Box might integrate better visually.
- **Facebook Like Box Show Faces:**

  - **What this setting does:** Determines if the profile pictures of people who like your page are displayed in the Like Box.
  - **Effect of changing this setting:**
    - *When enabled (YES):* A row of profile pictures of your page’s fans will be shown.
    - *When disabled (NO):* The profile pictures will not be displayed.
  - **Recommended value:** “YES” as it adds a social proof element, showing that real people like your page.
  - **Merchant scenario / example:** Showing faces can encourage others to like your page, as it demonstrates popularity.
- **Facebook Like Box Border Color:**

  - **What this setting does:** Sets the color of the border around the Facebook Like Box.
  - **Effect of changing this setting:**
    - *When set to a specific color (e.g., #CCCCCC):* The border will appear in that color.
  - **Recommended value:** A color that complements your website’s design or is transparent/invisible if you prefer.
  - **Merchant scenario / example:** You might use your brand’s primary color for the border to reinforce branding.
- **Facebook Like Box Show Stream:**

  - **What this setting does:** Controls whether your recent Facebook posts (the “stream”) are displayed within the Like Box.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Your latest Facebook posts will be visible in the tab.
    - *When disabled (NO):* Only the “Like” button and potentially faces will be shown, without the post stream.
  - **Recommended value:** “YES” to provide fresh content and encourage engagement.
  - **Merchant scenario / example:** If you regularly share news, promotions, or product updates on Facebook, showing the stream keeps visitors informed.
- **Facebook Like Box Show Header:**

  - **What this setting does:** Toggles the visibility of the “Find us on Facebook” header at the top of the Like Box.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The header will be displayed.
    - *When disabled (NO):* The header will be hidden, making the Like Box more compact.
  - **Recommended value:** “YES” for clarity, or “NO” if you want a cleaner look and assume users understand it’s Facebook.
  - **Merchant scenario / example:** If space is limited, hiding the header can save vertical room.
- **Facebook Fan Page URL:**

  - **What this setting does:** This is the most crucial setting for Facebook. You must enter the full URL of your Facebook Fan Page.
  - **Effect of changing this setting:**
    - *When correctly entered:* The Facebook tab will display the Like Box for your specified page.
    - *When incorrect or empty:* The Facebook tab may not display correctly or will show an error.
  - **Recommended value:** Your exact Facebook Fan Page URL (e.g., `https://www.facebook.com/MyPresta`).
  - **Merchant scenario / example:** Copy and paste the URL directly from your browser when viewing your Facebook page to ensure accuracy.

#### Google+ Settings

- **Display Google+ Follow:**

  - **What this setting does:** Toggles the visibility of the Google+ tab and its embedded follow button/profile.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The Google+ tab will appear in the slider.
    - *When disabled (NO):* The Google+ tab will not be shown.
  - **Recommended value:** “YES” if you actively use Google+ (though its usage has declined, it might still be relevant for some niches).
  - **Merchant scenario / example:** If your business has a strong presence on Google My Business or specific local SEO strategies involving Google+, this can be beneficial.
- **Google+ Profile ID:**

  - **What this setting does:** You need to provide your Google+ Profile ID (a numerical string) for the module to display the correct profile.
  - **Effect of changing this setting:**
    - *When correctly entered:* The Google+ tab will display the follow button/profile for your specified ID.
    - *When incorrect or empty:* The Google+ tab may not display correctly.
  - **Recommended value:** Your Google+ Profile ID.
  - **Merchant scenario / example:** Find your Google+ ID by navigating to your Google+ profile page and looking at the URL (it’s usually a long string of numbers).

#### Twitter Settings

- **Display Twitter User Timeline:**

  - **What this setting does:** Toggles the visibility of the Twitter tab and its embedded user timeline widget.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The Twitter tab will appear in the slider, showing your recent tweets.
    - *When disabled (NO):* The Twitter tab will not be shown.
  - **Recommended value:** “YES” if you have an active Twitter account for your business.
  - **Merchant scenario / example:** If you use Twitter for customer service, announcements, or flash sales, this is a great way to keep visitors updated.
- **Twitter Username:**

  - **What this setting does:** Specifies the Twitter account whose timeline will be displayed.
  - **Effect of changing this setting:**
    - *When correctly entered (e.g., MyPresta):* The Twitter tab will show tweets from that username.
    - *When incorrect or empty:* The Twitter tab may not display correctly.
  - **Recommended value:** Your Twitter username (without the ”@” symbol).
  - **Merchant scenario / example:** Enter `MyPresta` if your Twitter handle is `@MyPresta`.
- **Twitter Widget ID:**

  - **What this setting does:** This is a unique ID generated by Twitter when you create an embedded timeline widget. It’s crucial for the widget to function.
  - **Effect of changing this setting:**
    - *When correctly entered:* The Twitter timeline will load and display correctly.
    - *When incorrect or empty:* The Twitter tab will likely show an error or remain blank.
  - **Recommended value:** Your Twitter Widget ID.
  - **Merchant scenario / example:** To get this, go to [Twitter Publish](https://publish.twitter.com/), select “Embedded Timeline,” enter your profile URL, and copy the `data-widget-id` from the generated code.

#### YouTube Settings

- **Display YouTube Account:**

  - **What this setting does:** Toggles the visibility of the YouTube tab and its embedded channel/user feed.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The YouTube tab will appear in the slider.
    - *When disabled (NO):* The YouTube tab will not be shown.
  - **Recommended value:** “YES” if you have a YouTube channel with product videos, tutorials, or brand content.
  - **Merchant scenario / example:** If you sell products that benefit from video demonstrations, this is an excellent way to showcase them.
- **YouTube Username:**

  - **What this setting does:** Specifies the YouTube channel or user whose videos will be displayed.
  - **Effect of changing this setting:**
    - *When correctly entered:* The YouTube tab will display content from that channel/user.
    - *When incorrect or empty:* The YouTube tab may not display correctly.
  - **Recommended value:** Your YouTube channel’s custom URL name or legacy username.
  - **Merchant scenario / example:** If your YouTube channel URL is `youtube.com/user/MyPrestaVideos`, your username would be `MyPrestaVideos`. If it’s `youtube.com/c/MyPresta`, you might need to find the legacy username or channel ID.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Template** | (Choose best fit) | Changes the visual style of the social tabs. |
|  | **Position** | Right | Determines if tabs appear on the Left or Right side of the browser. |
|  | **Last tab opened by default** | NO | Controls if a tab automatically opens on page load. |
|  | **Display Facebook Like Box** | YES | Shows/hides the Facebook tab. |
|  | **Facebook Like Box Height** | 280px | Sets the height of the Facebook content area. |
|  | **Facebook Like Box Color Scheme** | Light | Changes the Facebook Like Box’s color theme. |
|  | **Facebook Like Box Show Faces** | YES | Displays profile pictures of fans. |
|  | **Facebook Like Box Border Color** | (empty/transparent) | Sets the border color of the Like Box. |
|  | **Facebook Like Box Show Stream** | YES | Displays recent Facebook posts. |
|  | **Facebook Like Box Show Header** | YES | Shows/hides the “Find us on Facebook” header. |
|  | **Facebook Fan Page URL** | (Your Facebook URL) | **CRITICAL:** URL of your Facebook Fan Page. |
|  | **Display Google+ Follow** | NO | Shows/hides the Google+ tab. |
|  | **Google+ Profile ID** | (Your Google+ ID) | **CRITICAL:** Your Google+ numerical Profile ID. |
|  | **Display Twitter User Timeline** | YES | Shows/hides the Twitter tab. |
|  | **Twitter Username** | (Your Twitter handle) | **CRITICAL:** Your Twitter username (e.g., `MyPresta`). |
|  | **Twitter Widget ID** | (Your Twitter Widget ID) | **CRITICAL:** Unique ID for your Twitter timeline widget. |
|  | **Display YouTube Account** | YES | Shows/hides the YouTube tab. |
|  | **YouTube Username** | (Your YouTube username) | **CRITICAL:** Your YouTube channel’s username or legacy ID. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The social tabs are not appearing on my store, or only some of them are showing.**
**A1:**

- **Check Module Status:** Go to **Modules > Module Manager** and ensure “Social tabs slider” is installed and enabled.
- **Verify Configuration:** Go to the module’s configuration page. Make sure “Display Facebook Like Box,” “Display Google+ Follow,” etc., are set to “YES” for the tabs you want to show.
- **Correct IDs/URLs:** Double-check that your Facebook Fan Page URL, Google+ Profile ID, Twitter Username/Widget ID, and YouTube Username are entered *exactly* as required. A single typo will prevent the tab from loading.
- **Theme Compatibility:** Some highly customized themes might have issues with module hooks. Try temporarily switching to the default PrestaShop theme to see if the tabs appear. If they do, your theme might require minor adjustments.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached files prevent new module content from appearing.

**Q2: My Facebook/Twitter/YouTube tab is showing an error or is blank when opened.**
**A2:**

- **Incorrect IDs/URLs:** This is the most common reason. Re-verify every single character of your Facebook Fan Page URL, Google+ Profile ID, Twitter Username, Twitter Widget ID, and YouTube Username. Even a missing slash or extra space can cause issues.
- **API Changes:** Social media platforms occasionally update their APIs or embed codes. Ensure your module version is up-to-date from MyPresta.eu.
- **Privacy Settings:** Ensure your social media pages/profiles are public and accessible. If they are set to private, the module won’t be able to display their content.
- **Network Issues:** Temporarily disable any ad blockers or browser extensions that might interfere with social media widgets.

**Q3: The social tabs look strange or misaligned on my mobile device.**
**A3:**

- **Theme Responsiveness:** While the module is designed to be responsive, its appearance can be affected by your PrestaShop theme’s overall responsiveness.
- **CSS Conflicts:** Your theme’s CSS might be overriding the module’s styling. If you have a webmaster, they can inspect the elements using browser developer tools to identify conflicts.
- **Module Template:** Try switching to a different “Template” in the module configuration to see if one adapts better to mobile.
- **Clear Cache:** Always clear your PrestaShop cache after making configuration changes.

**Q4: How do I get my Twitter Widget ID?**
**A4:**

1. Go to [Twitter Publish](https://publish.twitter.com/).
2. Select “Embedded Timeline.”
3. Enter the full URL of your Twitter profile (e.g., `https://twitter.com/MyPresta`).
4. Click the arrow, then select “Embedded Timeline.”
5. Twitter will generate a code. Look for `data-widget-id="YOUR_WIDGET_ID_HERE"` within that code. Copy only the numerical ID.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Social tabs slider” module is a classic PrestaShop module implemented as a single PHP file (`socialslider.php`) following the PrestaShop module structure. It leverages PrestaShop’s hook system to inject its CSS, JavaScript, and HTML content into the front office. Configuration is managed through the `getContent()` method in the main module class, storing settings in `ps_configuration`. The module uses external JavaScript libraries (jscolor) and custom scripts to handle the sliding animation and social media widget loading.

### 4.2 Controllers (`controllers/`)

This module does **not** utilize custom Front-Office or Back-Office Admin Controllers. All logic is encapsulated within the main module file.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or extend `ObjectModel`. All core logic resides within the `Socialslider` class in `socialslider.php`. Configuration values are stored directly in the `ps_configuration` table using `Configuration::get()` and `Configuration::updateValue()`.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files to manage its functionality:

- `socialslider/jscolor/jscolor.js`
  - **Scope:** Back-office (used in `getContent()` for color picker input).
  - **Responsibility:** Provides a JavaScript color picker functionality for input fields, specifically for the Facebook border color setting.
- `socialslider/left.js`
  - **Scope:** Front-office.
  - **Responsibility:** Contains the JavaScript logic for the sliding animation and tab interaction when the slider is positioned on the **left** side of the screen. It handles opening/closing tabs, loading social media content dynamically, and potentially managing cookies for the “last tab opened” feature.
- `socialslider/right.js`
  - **Scope:** Front-office.
  - **Responsibility:** Contains the JavaScript logic for the sliding animation and tab interaction when the slider is positioned on the **right** side of the screen. Similar to `left.js` but adapted for right-side positioning.

### 4.5 CSS Stylesheets (`views/css/`)

The module uses a template-based approach for its styling, with separate CSS files for each template and position.

- `socialslider/templates/1/css/left.css`
  - **Scope:** Front-office (for Template 1, Left position).
  - **Responsibility:** Defines the visual styles for the social tabs, icons, and slider container when Template 1 is selected and the slider is on the left.
  - **Key Selectors:** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/1/css/right.css`
  - **Scope:** Front-office (for Template 1, Right position).
  - **Responsibility:** Defines the visual styles for the social tabs, icons, and slider container when Template 1 is selected and the slider is on the right.
  - **Key Selectors:** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/2/css/left.css`
  - **Scope:** Front-office (for Template 2, Left position).
  - **Responsibility:** Styling for Template 2, Left position.
- `socialslider/templates/2/css/right.css`
  - **Scope:** Front-office (for Template 2, Right position).
  - **Responsibility:** Styling for Template 2, Right position.
- `socialslider/templates/3/css/left.css`
  - **Scope:** Front-office (for Template 3, Left position).
  - **Responsibility:** Styling for Template 3, Left position.
- `socialslider/templates/3/css/right.css`
  - **Scope:** Front-office (for Template 3, Right position).
  - **Responsibility:** Styling for Template 3, Right position.
- `socialslider/templates/4/css/left.css`
  - **Scope:** Front-office (for Template 4, Left position).
  - **Responsibility:** Styling for Template 4, Left position.
- `socialslider/templates/4/css/right.css`
  - **Scope:** Front-office (for Template 4, Right position).
  - **Responsibility:** Styling for Template 4, Right position.
- `socialslider/templates/5/css/left.css`
  - **Scope:** Front-office (for Template 5, Left position).
  - **Responsibility:** Styling for Template 5, Left position.
- `socialslider/templates/5/css/right.css`
  - **Scope:** Front-office (for Template 5, Right position).
  - **Responsibility:** Styling for Template 5, Right position.
- `socialslider/templates/6/css/left.css`
  - **Scope:** Front-office (for Template 6, Left position).
  - **Responsibility:** Styling for Template 6, Left position.
- `socialslider/templates/6/css/right.css`
  - **Scope:** Front-office (for Template 6, Right position).
  - **Responsibility:** Styling for Template 6, Right position.

Developers can override these styles in their theme’s `custom.css` or by creating a child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for rendering its front-office content and for the back-office configuration form.

- **Hook templates (`views/templates/hook/`)**:
  - `socialslider/header.tpl`
    - **Hook:** `displayHeader`
    - **Output:** This template is responsible for including the necessary CSS and JavaScript files dynamically based on the module’s configuration (e.g., loading `left.js` or `right.js`, and the correct template-specific CSS). It also includes the Facebook, Twitter, and Google+ SDKs/widgets if enabled.
  - `socialslider/top.tpl`
    - **Hook:** `displayTop`
    - **Output:** This is the main template that renders the HTML structure of the social tabs slider itself. It generates the `div` elements for the slider container, individual tabs (Facebook, Google+, Twitter, YouTube), and their respective content areas, populating them with configuration values.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table.

  - `ps_configuration` (or `_configuration` with your prefix): Stores key-value pairs for module settings, e.g., `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects module’s CSS and JavaScript files, and social media platform SDKs/widget scripts (Facebook SDK, Twitter widget script, Google+ script). |
| `displayTop` | Typically at the very top of the content area, below the main header. | Renders the main HTML structure of the social tabs slider (the fixed container, individual tabs, and their content areas). |
| `header` | (Alias for `displayHeader` in some PrestaShop versions, or used for older themes) | Same as `displayHeader`, ensures compatibility for injecting assets. |

## 5. Official Support & Updates

For official updates, bug fixes, and developer support for the “Social tabs slider” module, please refer to your MyPresta.eu customer account. You can download the latest versions and access support resources directly from your order history.
