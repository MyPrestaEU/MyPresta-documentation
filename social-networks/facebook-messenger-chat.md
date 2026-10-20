---
title: "Facebook Messenger chat - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Messenger chat PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Messenger chat - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Messenger chat Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-messenger-chat/)
>
> ---


# Facebook Messenger chat

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on all modern hosting environments. No special extensions are needed for this module beyond standard PrestaShop requirements.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for your Facebook Messenger chat module. You’ll find all options here to customize how the chat appears and functions on your store.

- **What this setting does:** This is a general setting for MyPresta.eu modules to check for updates.
- **Effect of changing this setting:**
  - *When enabled (On):* The module will periodically check MyPresta.eu for new versions.
  - *When disabled (Off):* The module will not check for updates.
- **Recommended value:** **On** (It’s always good to stay updated for security and new features).
- **Merchant scenario / example:** Keeping this on ensures you’re notified when a new version with bug fixes or new features is available, helping your store stay current and secure.

---

- **What this setting does:** This option allows you to choose between two types of Facebook chat integration: a simple Facebook Page chat or the more advanced Facebook Messenger chat.
- **Effect of changing this setting:**
  - *When set to “Facebook Page Chat”:* A simpler chat widget will appear, primarily for sending messages to your Facebook Page.
  - *When set to “Facebook Messenger Chat”:* The full-featured Facebook Messenger chat widget will appear, offering a richer conversation experience, including greeting messages and potentially more advanced features from Facebook.
- **Recommended value:** **Facebook Messenger Chat** (Offers a better user experience and more features).
- **Merchant scenario / example:** If you want the full, interactive Messenger experience with greeting messages, choose “Facebook Messenger Chat”. If you prefer a very basic, lightweight message sender, “Facebook Page Chat” might be sufficient.

---

- **What this setting does:** This setting helps improve your store’s performance scores on tools like Google PageSpeed Insights by preventing the Facebook chat from loading immediately, which can sometimes block the rendering of your page.
- **Effect of changing this setting:**
  - *When enabled (On):* The Facebook chat script will load with a slight delay or in a non-blocking way, which can improve your Google PageSpeed scores.
  - *When disabled (Off):* The Facebook chat script will load normally, which might slightly impact page load performance metrics.
- **Recommended value:** **On** (Recommended for better SEO and user experience).
- **Merchant scenario / example:** If you’re concerned about your store’s performance metrics and want to ensure the chat doesn’t negatively impact them, enable this.

---

- **What this setting does:** This controls whether the Facebook Application SDK (Software Development Kit) is included on your website. The SDK is necessary for the full functionality of the Facebook Messenger chat, especially for features like identifying logged-in users.
- **Effect of changing this setting:**
  - *When enabled (On):* The Facebook SDK will be loaded, enabling all Messenger chat features.
  - *When disabled (Off):* Some advanced Messenger features, particularly those related to user identification and personalized greetings, might not work correctly.
- **Recommended value:** **On** (Required for full Messenger chat functionality).
- **Merchant scenario / example:** If you want the chat to recognize if a customer is logged into Facebook and display a personalized greeting, you must enable this.

---

- **What this setting does:** This is your unique identifier for your Facebook Application. You need to create a Facebook App on the Facebook Developers website to get this ID. It links your website to your Facebook Page for advanced Messenger features.
- **Effect of changing this setting:**
  - *When correctly entered:* Enables the full functionality of the Facebook Messenger chat, including personalized greetings and potentially more accurate user identification.
  - *When incorrect or empty:* The Messenger chat might not function correctly or at all.
- **Recommended value:** Your actual **Facebook App ID**. (Leave empty if “Include facebook application sdk” is Off).
- **Merchant scenario / example:** To use the advanced Messenger chat features, you’ll need to go to [developers.facebook.com](https://developers.facebook.com/), create an app, link it to your Facebook Page, and then copy the App ID here.

---

- **What this setting does:** This allows you to specify the language for the Facebook Messenger chat interface.
- **Effect of changing this setting:**
  - *When a language code is selected:* The chat widget will display text (like “Send us a message”) in the chosen language.
  - *When left empty or incorrect:* The chat might default to English or the browser’s language.
- **Recommended value:** Select the primary language of your store, e.g., `en_US` for English (United States), `fr_FR` for French (France), `es_ES` for Spanish (Spain).
- **Merchant scenario / example:** If your store primarily serves customers in Germany, setting this to `de_DE` will ensure the chat interface is in German, making it more user-friendly for your local customers.

---

- **What this setting does:** This is the URL to your Facebook Fan Page. This is crucial as it tells the chat widget where to send messages.
- **Effect of changing this setting:**
  - *When correctly entered:* Messages sent through the chat widget will go directly to your Facebook Page’s inbox.
  - *When incorrect or empty:* The chat widget will not be able to connect to your page, and messages will not be delivered.
- **Recommended value:** The full URL to your Facebook Fan Page, e.g., `https://www.facebook.com/MyPresta.eu`.
- **Merchant scenario / example:** If your Facebook Page is `https://www.facebook.com/MyAwesomeStore/`, you would enter that URL here so customers can reach you.

---

- **What this setting does:** This is the initial message displayed to customers who are already logged into Facebook when they open the chat.
- **Effect of changing this setting:**
  - *When set:* Logged-in customers will see this personalized greeting, making the interaction more welcoming.
  - *When empty:* A default Facebook greeting might be used, or no greeting will appear.
- **Recommended value:** A friendly, concise greeting, e.g., “Hi [Customer Name], how can we help you today?”
- **Merchant scenario / example:** You could set this to “Welcome back! How can we assist you with your shopping today?” to make returning customers feel valued.

---

- **What this setting does:** This is the initial message displayed to customers who are NOT logged into Facebook when they open the chat.
- **Effect of changing this setting:**
  - *When set:* Unlogged customers will see this greeting, encouraging them to start a conversation.
  - *When empty:* A default Facebook greeting might be used, or no greeting will appear.
- **Recommended value:** A clear, inviting message, e.g., “Hello! We’re here to help. Ask us anything!”
- **Merchant scenario / example:** For new visitors, you might use “Hi there! Have a question about our products? Chat with us!”

---

- **What this setting does:** This is the numerical ID of your Facebook Page. You can find this in your Facebook Page’s “About” section or by using a Facebook Page ID finder tool. It’s essential for linking the chat widget to your specific page.
- **Effect of changing this setting:**
  - *When correctly entered:* The chat widget will correctly identify and connect to your Facebook Page.
  - *When incorrect or empty:* The chat widget will not function, as it won’t know which page to connect to.
- **Recommended value:** Your actual **Facebook Page ID**.
- **Merchant scenario / example:** If your Facebook Page ID is `123456789012345`, you would enter that number here. This is distinct from the App ID.

---

- **What this setting does:** This controls the position of the chat widget on your website.
- **Effect of changing this setting:**
  - *When set to “Left”:* The chat icon/panel will appear on the bottom-left side of your screen.
  - *When set to “Right”:* The chat icon/panel will appear on the bottom-right side of your screen.
- **Recommended value:** **Right** (This is a common and often less intrusive position, as many websites have navigation or other elements on the left).
- **Merchant scenario / example:** If your website’s main navigation or a crucial banner is on the left, you’d choose “Right” to avoid obscuring it.

---

- **What this setting does:** This is the text that appears as the title of the chat window or the sliding panel before a conversation starts.
- **Effect of changing this setting:**
  - *When set:* Customers will see this title, clearly indicating what the chat is for.
  - *When empty:* A default title might be used, or no title will appear, which can be confusing.
- **Recommended value:** A clear and inviting title, e.g., “Chat with us!”, “Customer Support”, or “Questions?”.
- **Merchant scenario / example:** Setting this to “Need Help?” makes it clear to customers that they can get assistance through the chat.

---

- **What this setting does:** This allows you to customize the color of the text within the Facebook Chat widget.
- **Effect of changing this setting:**
  - *When a color code is entered:* The text in the chat widget will display in the chosen color.
  - *When empty:* The default Facebook Messenger text color will be used.
- **Recommended value:** Choose a color that contrasts well with your background color and matches your brand. Use a hexadecimal color code (e.g., `#FFFFFF` for white, `#000000` for black).
- **Merchant scenario / example:** If your brand colors are dark blue and white, you might set the font color to `#FFFFFF` (white) if your background color is dark blue.

---

- **What this setting does:** This allows you to customize the background color of the Facebook Chat widget.
- **Effect of changing this setting:**
  - *When a color code is entered:* The background of the chat widget will display in the chosen color.
  - *When empty:* The default Facebook Messenger background color will be used.
- **Recommended value:** Choose a color that complements your store’s design. Use a hexadecimal color code (e.g., `#F0F2F5` for light gray, `#3B5998` for Facebook blue).
- **Merchant scenario / example:** To integrate the chat seamlessly with your store’s design, you might set the background color to a subtle gray or a color from your brand palette.

---

- **What this setting does:** This allows you to customize the main accent color of the Facebook Messenger chat, such as the send button or active elements.
- **Effect of changing this setting:**
  - *When a color code is entered:* Key interactive elements in the chat widget will display in the chosen color.
  - *When empty:* The default Facebook Messenger accent color (typically Facebook blue) will be used.
- **Recommended value:** Choose a color that aligns with your brand’s primary or secondary accent color. Use a hexadecimal color code (e.g., `#1877F2` for Facebook blue, or your brand’s call-to-action color).
- **Merchant scenario / example:** If your store’s call-to-action buttons are green, setting this to a similar green (`#28A745`) will make the chat widget feel more integrated with your site.

---

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | MyPresta.eu Updates | On | Enables module update checks for security and features. |
| Module Configuration | Type of chat | Facebook Messenger Chat | Selects between basic Facebook Page chat and full Messenger experience. |
| Module Configuration | Disable chat for Google Insights | On | Improves PageSpeed scores by delaying chat script loading. |
| Module Configuration | Include facebook application sdk | On | Enables advanced Messenger features like personalized greetings. |
| Module Configuration | Your APP ID | Your Facebook App ID | Links your website to your Facebook App for full Messenger functionality. |
| Module Configuration | Facebook APP language codes | `en_US` (or your store’s language) | Sets the language for the chat interface. |
| Module Configuration | Url to Facebook fanpage (messages receiver) | Your Facebook Page URL | Directs customer messages to your Facebook Page inbox. |
| Module Configuration | Greeting message for logged | “Hi [Customer Name], how can we help you today?” | Personalized greeting for logged-in Facebook users. |
| Module Configuration | Greeting message for unlogged | “Hello! We’re here to help. Ask us anything!” | Inviting message for users not logged into Facebook. |
| Module Configuration | Your facebook page ID | Your Facebook Page ID | Identifies your specific Facebook Page for the chat connection. |
| Module Configuration | Where to dispaly? | Right | Positions the chat widget on the left or right side of the screen. |
| Module Configuration | Title of sliding panel | “Chat with us!” | Text displayed as the chat window title. |
| Module Configuration | Facebook Chat font color | `#000000` (black) or your brand color | Customizes the text color within the chat widget. |
| Module Configuration | Facebook Chat background color | `#F0F2F5` (light gray) or your brand color | Customizes the background color of the chat widget. |
| Module Configuration | Facebook Messenger color | `#1877F2` (Facebook blue) or your brand color | Customizes the accent color of interactive chat elements. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The chat widget isn’t appearing on my store. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Facebook Messenger chat” module is installed and enabled.
2. **Verify Configuration:** Double-check all settings in the module’s configuration page, especially “Your APP ID”, “Url to Facebook fanpage”, and “Your facebook page ID”. Even a single incorrect character can prevent it from working.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached files prevent new modules from displaying.
4. **Theme Compatibility:** If you’re using a highly customized theme, there might be a conflict. Temporarily switch to the default PrestaShop theme to see if the chat appears. If it does, your theme might require a small adjustment.

**Q: My greeting messages aren’t showing up, or the chat isn’t recognizing logged-in users.**
A:

1. **Enable SDK:** Make sure “Include facebook application sdk” is set to **On**.
2. **Provide APP ID:** Ensure “Your APP ID” is correctly entered. You need to create a Facebook App and link it to your page to get this.
3. **Facebook Login:** The customer must be logged into Facebook in their browser for the personalized greeting to work.

**Q: The chat widget looks out of place or doesn’t match my store’s design.**
A:

1. **Use Color Settings:** Go to the module configuration and adjust “Facebook Chat font color”, “Facebook Chat background color”, and “Facebook Messenger color” to match your brand’s palette.
2. **Positioning:** Experiment with the “Where to display?” setting (Left/Right) to find the least intrusive position for your site.

**Q: How do I find my Facebook Page ID and App ID?**
A:

- **Facebook Page ID:** Go to your Facebook Page, click on “About” in the left menu. Scroll down, and you should see “Page ID”.
- **Facebook App ID:** You need to create a Facebook Developer account and then create a new App. Once created, the App ID will be visible in your App Dashboard. Make sure to link this App to your Facebook Page.

**Q: Will this module slow down my website?**
A: Facebook’s SDK can sometimes impact page load times. However, the module includes a “Disable chat for Google Insights” option. Enabling this can help mitigate performance impacts by loading the script in a non-blocking way, improving your PageSpeed scores.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The `Facebook Messenger chat` module (`fbchat`) is a standard PrestaShop module following an MVC-like pattern within the module’s scope. It primarily leverages PrestaShop’s hook system to inject JavaScript and HTML into the front-office. Configuration is managed via the `getContent()` method in the main module class, storing settings in `ps_configuration`. The module integrates directly with the Facebook Messenger Platform SDK, relying on external Facebook resources for its core functionality.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is handled within the main module file (`fbchat.php`) and injected via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or `ObjectModel` instances in the `classes/` directory. All data handling is done directly through `Configuration` class for settings.

### 4.4 JavaScript Assets (`views/js/`)

- **`fbchat/jscolor/jscolor.js`**

  - **Scope:** Back-office (Admin configuration page).
  - **Purpose:** This is a third-party JavaScript library for a color picker. It’s used on the module’s configuration page to provide a user-friendly interface for selecting colors for the chat widget (e.g., font color, background color).
  - **Interaction:** It attaches color picker functionality to specific input fields on the admin form.
- **`fbchat/js/fbchat.js`**

  - **Scope:** Front-office.
  - **Purpose:** This custom JavaScript handles the dynamic loading and initialization of the Facebook Messenger chat widget. It contains logic to conditionally load the Facebook SDK and the Messenger chat based on module settings and potentially performance optimization flags.
  - **Interaction:**
    - Checks `fbchat_hack` configuration to determine if delayed loading for Google Insights is enabled.
    - Dynamically creates and appends the Facebook SDK script (`sdk.js`) to the `<body>` if `fbchat_appsdk` is enabled.
    - Initializes the `FB.CustomerChat` plugin with parameters fetched from module configuration (e.g., `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
    - Handles the positioning of the chat widget based on `fbchat_side`.

### 4.5 CSS Stylesheets (`views/css/`)

- **`fbchat/css.css`**

  - **Scope:** Back-office (Admin configuration page).
  - **Purpose:** Contains styling specific to the module’s configuration form in the PrestaShop Back Office. This might include styles for input fields, buttons, or custom layout elements within the `getContent()` output.
  - **Key Selectors:** Likely targets elements within the module’s configuration form.
- **`fbchat/css/fbchat_left.css`**

  - **Scope:** Front-office.
  - **Purpose:** Provides styling adjustments for the Facebook Messenger chat widget when its position is set to the “Left” side of the screen. This might include `right` or `left` CSS properties to control its fixed position.
  - **Key Selectors:** Targets the main chat container or its wrapper to ensure correct left-side alignment.
- **`fbchat/css/fbchat_right.css`**

  - **Scope:** Front-office.
  - **Purpose:** Provides styling adjustments for the Facebook Messenger chat widget when its position is set to the “Right” side of the screen. This might include `right` or `left` CSS properties to control its fixed position.
  - **Key Selectors:** Targets the main chat container or its wrapper to ensure correct right-side alignment.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`fbchat/admin-script.tpl`**

  - **Scope:** Back-office (Admin configuration page).
  - **Purpose:** This template is likely used to inject JavaScript code (e.g., for the color picker initialization from `jscolor.js`) or specific styling into the module’s configuration page. It’s rendered within the `getContent()` method.
  - **Variables:** May receive configuration variables to dynamically set initial color picker values.
- **`fbchat/fbchat.tpl`**

  - **Scope:** Front-office.
  - **Purpose:** This is the main front-office template responsible for rendering the necessary HTML structure and JavaScript initialization for the Facebook Messenger chat widget. It’s typically hooked into `displayFooter` or `displayHeader`.
  - **Variables:** Receives all necessary configuration variables from the module’s `hookDisplayFooter` or `hookDisplayHeader` methods, such as `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
  - **Output:** Generates the `<div class="fb-customerchat">` element and the `<script>` tag for the Facebook SDK initialization.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - All configuration settings are stored in the `ps_configuration` table using keys like `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to include CSS files (`fbchat_left.css`, `fbchat_right.css`) and potentially some initial JavaScript if needed early in the page load. |
| `displayFooter` | Executed just before the closing `</body>` tag of every front-office page. | This is the primary hook for rendering the `fbchat.tpl` template, which includes the Facebook Messenger chat HTML and initializes the `fbchat.js` script. Placing it here ensures the main page content loads first, improving perceived performance. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Facebook Messenger chat” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality or integration.
