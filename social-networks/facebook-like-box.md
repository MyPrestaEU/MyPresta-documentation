---
title: "Facebook Like Box - Merchant Manual & Configuration Guide"
description: ""
sidebar:
  label: "Facebook Like Box - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Like Box Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and any module interacting with external APIs like Facebook.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for your Facebook Like Box module. Here you will define how your Like Box looks and behaves on your store.

**Screen Name & Menu Location:** Back Office > Modules > Module Manager > Facebook Like Box > Configure

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Facebook Page URL** | This is the direct link to your official Facebook Page. | *When set:* The Like Box will display content from this specific Facebook page. *When empty:* The module will not function correctly as it won’t know which page to display. | Your Facebook Page URL (e.g., `https://www.facebook.com/myprestaeu`) | You want to promote your main business Facebook page. |
| **App ID (Facebook)** | Your Facebook App ID, required for some advanced features and API integrations. | *When set:* Enables the module to interact with Facebook’s Graph API using your application. *When empty:* May result in “App not configured” errors if the module requires API access. | Your Facebook App ID (e.g., `123456789012345`) | You need to resolve an “App not configured” error or enable advanced Facebook API features. |
| **Width** | Controls the width of the Facebook Like Box in pixels. | *When set to a specific value (e.g., 280):* The Like Box will maintain that exact width. *When left empty or set to 0:* The Like Box will attempt to be responsive and adjust its width automatically to fit its container. | Leave empty for auto-detect (responsive behavior) or set a specific value like `280` if you need a fixed width. | You want the Like Box to fit perfectly into a narrow column, so you set it to `280`. |
| **Height** | Controls the height of the Facebook Like Box in pixels. | *When set to a specific value (e.g., 500):* The Like Box will maintain that exact height. *When left empty or set to 0:* The Like Box will attempt to be responsive and adjust its height automatically. | Leave empty for auto-detect (responsive behavior) or set a specific value like `500` if you want to show more of the post stream. | You want to display more recent posts from your Facebook page, so you increase the height to `500`. |
| **Show Faces** | Determines whether the profile pictures of people who have liked your page are displayed. | *When enabled (YES):* Small profile pictures of some of your Facebook fans will appear below the Like button, adding social proof. *When disabled (NO):* Only the Like button and page information will be shown, without individual faces. | YES | You want to show that real people like your page, encouraging others to join. |
| **Show Stream** | Controls whether recent posts from your Facebook page are displayed within the Like Box. | *When enabled (YES):* Your latest Facebook posts will scroll within the Like Box, providing fresh content. *When disabled (NO):* Only the page cover, profile, and Like button will be visible, making the box more compact. | YES | You frequently post updates on Facebook and want to share them directly on your store. |
| **Show Header** | Controls whether the “Facebook” header is shown at the top of the Like Box. | *When enabled (YES):* A small “Facebook” title will appear at the top of the widget. *When disabled (NO):* The header will be hidden, making the widget look cleaner and more integrated. | NO | You prefer a minimalist look for the Like Box and don’t need the explicit “Facebook” header. |
| **Small Header** | Uses a smaller version of the header. | *When enabled (YES):* The header will be more compact. *When disabled (NO):* The standard header size will be used. | NO | You want to save vertical space in your layout. |
| **Hide Cover** | Hides the cover photo of your Facebook page. | *When enabled (YES):* Only your page’s profile picture and name will be visible, making the widget more compact. *When disabled (NO):* Your Facebook page’s cover photo will be displayed at the top of the widget. | NO | You have a very narrow space and want to prioritize the Like button and posts over the cover photo. |
| **Adapt to container width** | Allows the Like Box to automatically adjust its width to fit the parent container it’s placed in. | *When enabled (YES):* The widget will resize itself to fill the available width, making it responsive. *When disabled (NO):* The widget will stick to the specified `Width` setting, potentially causing overflow or empty space. | YES | You want the Like Box to look good on all devices and screen sizes without manual adjustments. |
| **Custom CSS** | Allows you to add custom CSS rules to further style the Like Box. | *When filled with CSS code:* Your custom styles will be applied, overriding default styles. *When empty:* The module will use its default styling or Facebook’s default styling. | Leave empty unless you have specific styling needs. | You want to change the font size or color of the text within the Like Box to match your brand’s theme. |
| **Hook to display module** | Selects where in your store the Like Box will appear. | *When a hook is selected:* The module will render its content in that specific location (e.g., `displayRightColumn`, `displayFooter`). *When no hook is selected:* The module will not be visible on your front office. | `displayRightColumn` or `displayLeftColumn` are common, but choose based on your theme’s layout. | You want the Like Box to be visible on the side of your product listings, so you choose `displayRightColumn`. |
| **Background Color** | Sets the background color of the Like Box. | *When a color is selected:* The Like Box will have that background color. *When left empty:* The Like Box will typically inherit the background color of its parent container or use Facebook’s default. | Leave empty or match your theme’s background color. | Your theme has a dark background, and you want the Like Box to blend in, so you set a dark background color. |
| **Border Color** | Sets the color of the border around the Like Box. | *When a color is selected:* The Like Box will have a border of that color. *When left empty:* The Like Box will typically have no border or a default Facebook border. | Leave empty or match your theme’s border colors. | You want a subtle grey border around the Like Box to separate it from other content. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook Page URL | Your Facebook Page URL | Links the widget to your specific Facebook page. |
| Module Configuration | App ID (Facebook) | Empty (if not required) | Your Facebook App ID for API integration. |
| Module Configuration | Width | Empty (Responsive) | Controls widget width; empty for auto-adjust. |
| Module Configuration | Height | Empty (Responsive) | Controls widget height; empty for auto-adjust. |
| Module Configuration | Show Faces | YES | Displays profile pictures of likers for social proof. |
| Module Configuration | Show Stream | YES | Displays recent posts from your Facebook page. |
| Module Configuration | Show Header | NO | Hides the “Facebook” title for a cleaner look. |
| Module Configuration | Small Header | NO | Uses a smaller header if `Show Header` is YES. |
| Module Configuration | Hide Cover | NO | Shows your Facebook page’s cover photo. |
| Module Configuration | Adapt to container width | YES | Ensures the widget is responsive to its parent container. |
| Module Configuration | Custom CSS | Empty | Allows advanced styling with custom CSS rules. |
| Module Configuration | Hook to display module | `displayRightColumn` (or relevant column) | Determines where the module appears on your store. |
| Module Configuration | Background Color | Empty | Sets the background color of the widget. |
| Module Configuration | Border Color | Empty | Sets the border color of the widget. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook Like Box isn’t showing up on my store. What should I do?**
A1:

- **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Facebook Like Box” module is installed and enabled.
- **Verify Hook Selection:** In the module’s configuration, make sure you have selected a “Hook to display module” (e.g., `displayRightColumn`, `displayFooter`). If your theme doesn’t render the selected hook, it won’t appear. Try a different common hook.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, PrestaShop’s cache prevents new modules from appearing immediately.
- **Facebook Page URL:** Double-check that the “Facebook Page URL” in the module configuration is correct and accessible.

**Q2: The Like Box looks too wide/narrow or doesn’t fit my theme properly.**
A2:

- **Responsive Settings:** In the module configuration, ensure “Adapt to container width” is set to YES, and leave “Width” and “Height” fields empty. This allows Facebook to manage responsiveness.
- **Theme Conflicts:** Your theme’s CSS might be overriding the module’s styles. If you’re comfortable with CSS, use your browser’s developer tools (F12) to inspect the element and see which CSS rules are being applied.
- **Custom CSS:** Use the “Custom CSS” field in the module configuration to add specific rules to adjust its size or appearance if necessary. For example: `.fb_iframe_widget { max-width: 100% !important; }`.

**Q3: The Like Box is showing an error or not loading content from my Facebook page.**
A3:

- **Correct URL:** Verify that the “Facebook Page URL” is absolutely correct and points to a public Facebook page (not a personal profile or group).
- **Facebook API Issues:** Occasionally, Facebook’s API might experience temporary issues. Wait a little while and check again.
- **Page Restrictions:** Ensure your Facebook page doesn’t have any country or age restrictions that might prevent the widget from loading for all visitors.

:::caution
\*\*“App not configured” Error (Module Version 1.8 and higher)\*\*
If you encounter an “App not configured” error, especially with module version 1.8 or higher, which supports Facebook Graph API v18.0:
1. \*\*Enter your Facebook App ID:\*\* Ensure you have correctly entered your Facebook App ID in the module’s configuration field.
2. \*\*Verify Domain Settings on Facebook:\*\* Log in to your Facebook Developer account ([developers.facebook.com](https://developers.facebook.com/)). Navigate to your app’s settings and confirm that your store’s domain (e.g., `yourstore.com`) is correctly added and verified in the app’s settings.
:::

**Q4: Can I have multiple Facebook Like Boxes on different pages?**
A4: This module is designed to display one Facebook Like Box configured globally. If you need multiple, distinct Like Boxes (e.g., for different Facebook pages or with different settings), you would typically need to install the module multiple times (if supported by PrestaShop’s module system, which is rare for single-instance modules) or use custom code. For this specific module, it’s generally one instance, one configuration.

**Q5: How do I translate the text within the Like Box (e.g., “Like Page”)?**
A5: The text within the Facebook Like Box itself (like “Like Page”, “Follow”, “Share”) is controlled by Facebook based on the user’s browser language settings and Facebook’s own localization. This module does not directly translate these elements. Any text *around* the Like Box that you add in your theme or other modules would be translatable through PrestaShop’s translation system.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Facebook Like Box module (`likebox`) is a standard PrestaShop module following a basic MVC pattern. It primarily uses the `Module` class for installation, uninstallation, and configuration handling. The core functionality involves rendering a Smarty template that embeds the Facebook Page Plugin (formerly Like Box) using Facebook’s official JavaScript SDK. Configuration settings are stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. All logic is contained within the main module file (`likebox/ar.php`).

### 4.4 JavaScript Assets (`views/js/`)

- **`likebox/jscolor/jscolor.js`**

  - **Scope:** Back-office (Admin Configuration Page)
  - **Purpose:** This is a third-party JavaScript library that provides a color picker functionality. It’s used on the module’s configuration page to allow the merchant to visually select “Background Color” and “Border Color” settings.
  - **Interaction:** It binds to specific input fields (likely with a class like `jscolor`) to open a color selection palette.
- **`likebox/script.js`**

  - **Scope:** Back-office (Admin Configuration Page)
  - **Purpose:** This script handles the dynamic updates and live preview functionality on the module’s configuration page. It takes the merchant’s input settings (Facebook Page URL, width, height, show faces, etc.) and dynamically updates an `<iframe>` or a preview area to show how the Facebook Like Box will look.
  - **Interaction:**
    - Listens to `change` and `keyup` events on various input fields (e.g., `#facebook_page_url`, `#width`, `#height`, checkboxes).
    - Constructs the Facebook Page Plugin URL parameters based on the current settings.
    - Updates the `src` attribute of a preview `<iframe>` or dynamically generates the Facebook SDK embed code to reflect changes in real-time.
    - Likely uses `jscolor.js` to get color values for background and border.

### 4.5 CSS Stylesheets (`views/css/`)

- **`likebox/css.css`**

  - **Scope:** Back-office (Admin Configuration Page)
  - **Purpose:** Provides styling for the module’s configuration form in the PrestaShop Back Office. This might include layout adjustments, input field styling, or styling for the live preview area.
  - **Key Selectors:** Likely targets elements within the `getContent()` output, such as form groups, labels, and the preview container.
- **`likebox/css/css.css`**

  - **Scope:** Front-office (Customer-facing store)
  - **Purpose:** Provides minimal styling for the Facebook Like Box widget itself, primarily to ensure it integrates well with the store’s layout. This might include default padding, margins, or basic responsive adjustments.
  - **Key Selectors:** Targets the container element where the Facebook widget is embedded (e.g., `.facebook_like_box_container`) and potentially applies `max-width: 100%` for responsiveness. Developers can override these styles in their theme’s `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

The module’s templates are located directly within the module’s root directory.

- **`likebox/header.tpl`**

  - **Scope:** Front-office
  - **Hook:** `displayHeader`
  - **Purpose:** This template is designed to be hooked into `displayHeader`. Its primary role is to include the Facebook JavaScript SDK, which is necessary for the Facebook Page Plugin to render correctly. It also contains the `div` element where the Like Box will be rendered by the SDK.
  - **Output:**

    ```
    <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // Version might vary, appId added fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
    ```

    (Note: The actual version of the SDK and data attributes might vary slightly based on the module’s exact implementation and Facebook’s API changes.)
- **`likebox/rightcolumn.tpl`**

  - **Scope:** Front-office
  - **Hook:** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc. (depending on module configuration)
  - **Purpose:** This template acts as the wrapper for the Facebook Like Box. It’s designed to be flexible and can be hooked into various positions. It typically includes the `div` element with the `fb-page` class that Facebook’s SDK will transform into the visual Like Box.
  - **Output:**

    ```
    <div class="block facebook\_like\_box\_container"> <h4>{l s='Follow us on Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
    ```

    This template also includes the `<h4>` title and `block_content` structure common for PrestaShop column blocks.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys typically prefixed with `LIKEBOX_` (e.g., `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID`, etc.).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of every page. | Used to include the Facebook JavaScript SDK and the initial `fb-root` div, essential for the Like Box to function. |
| `displayLeftColumn` | Renders content in the left sidebar column. | Displays the Facebook Like Box widget in the left column. |
| `displayRightColumn` | Renders content in the right sidebar column. | Displays the Facebook Like Box widget in the right column. |
| `displayFooter` | Renders content in the store’s footer section. | Displays the Facebook Like Box widget in the footer. |
| `displayHome` | Renders content on the homepage. | Displays the Facebook Like Box widget on the homepage. |
| `displayProductButtons` | Renders content near product action buttons on the product page. | Displays the Facebook Like Box widget on product pages. |
| `displayProductExtraContent` | Renders additional content on the product page, often in a tab or below the main content. | Displays the Facebook Like Box widget on product pages. |
| `displayMyAccountBlock` | Renders content in the customer’s “My Account” block. | Displays the Facebook Like Box widget in the customer account area (less common for this module). |
| `displayMyAccountBlockfooter` | Renders content in the footer of the “My Account” block. | Displays the Facebook Like Box widget in the customer account area. |

(Note: The module’s `install()` method registers these hooks, and the `hook<HookName>()` methods in `ar.php` are responsible for rendering the `rightcolumn.tpl` or `header.tpl` based on the hook.)

## 5. Official Support & Updates

For the latest versions, updates, and dedicated support for the Facebook Like Box module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have.
