---
title: "Shoutbox - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Shoutbox PrestaShop module by MyPresta.eu."
sidebar:
  label: "Shoutbox - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Shoutbox Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Shoutbox module, accessible directly after installation or by navigating to **Modules > Module Manager**, searching for “Shoutbox”, and clicking “Configure”.

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enable Shoutbox** | This is the master switch to turn the entire Shoutbox feature on or off in your store. | *When enabled:* The Shoutbox will appear on your front office in the chosen hook locations. Customers can see and interact with it.   *When disabled:* The Shoutbox will be completely hidden from your store, and no messages will be displayed or accepted. | **YES** | You want to activate the community chat feature on your store. If you need to temporarily hide it for maintenance or content review, you would set this to NO. |
| **Shoutbox Title** | This sets the heading text that appears at the top of the Shoutbox widget in your store’s front office. | *When set to “Community Chat”:* Your customers will see “Community Chat” as the title of the box.   *When set to “Ask Us Anything”:* The title changes to “Ask Us Anything”. | **Community Chat** | You want to clearly label the chat box for your customers. You might change it to “Product Discussions” if you place it on product pages. |
| **Number of Messages to Display** | This controls how many of the most recent messages are shown in the Shoutbox at any given time. Older messages will be hidden. | *When set to 10:* Only the last 10 messages will be visible in the chat box.   *When set to 20:* The last 20 messages will be shown. | **10** | To keep the chat concise and prevent it from becoming too long, showing the most recent 10-15 messages is usually best. If you have a very active community, you might increase this. |
| **Refresh Interval (seconds)** | This determines how often the Shoutbox automatically checks for and loads new messages without the customer having to refresh the page. | *When set to 5:* New messages will appear every 5 seconds.   *When set to 15:* New messages will appear every 15 seconds. | **10** | A shorter interval (e.g., 5 seconds) makes the chat feel more real-time but uses more server resources. A longer interval (e.g., 15-20 seconds) reduces server load but messages appear less instantly. 10 seconds is a good balance. |
| **Allow Guests to Post** | This option controls whether visitors who are not logged into a customer account can post messages in the Shoutbox. | *When enabled:* Anyone visiting your store can post messages, even if they haven’t registered or logged in. They will typically post as “Guest”.   *When disabled:* Only registered and logged-in customers can post messages. Guests will see the chat but cannot contribute. | **NO** | If you want to encourage registration and prevent anonymous spam, disable this. If you want maximum interaction and don’t mind anonymous posts, enable it. |
| **Display Shoutbox In** | This crucial setting determines where the Shoutbox widget will appear on your store’s front office. You can select one or more locations. | *When “Left Column” is selected:* The Shoutbox will appear in the left sidebar of your store.   *When “Footer” is selected:* The Shoutbox will appear at the bottom of your store pages. | **Left Column** (or a location that fits your theme) | You want the Shoutbox to be easily visible but not interfere with your main product content. Placing it in a column or the footer is often a good choice. |
| **Moderation Required** | If enabled, new messages will not appear in the Shoutbox until an administrator manually approves them in the Back Office. | *When enabled:* All new messages go into a pending queue. You must approve each message before it becomes visible to other customers.   *When disabled:* Messages appear instantly after being posted. | **NO** (unless you anticipate spam) | If you are concerned about spam, inappropriate content, or want to maintain strict control over the conversation, enable moderation. For a more fluid, real-time chat, disable it. |
| **Clear All Messages** | This is a button (not a toggle) that, when clicked, will permanently delete all existing messages from the Shoutbox. | *When clicked:* All historical messages in the Shoutbox are removed from your database and will no longer be displayed. This action is irreversible. | **N/A** (Use with caution) | You might use this if the chat has accumulated too many old messages, or if you want to start a fresh conversation for a new promotion or event. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Shoutbox | YES | Activates/deactivates the entire Shoutbox feature. |
| Module Configuration | Shoutbox Title | Community Chat | Sets the visible title of the Shoutbox widget. |
| Module Configuration | Number of Messages to Display | 10 | Controls how many recent messages are shown. |
| Module Configuration | Refresh Interval (seconds) | 10 | How often the chat updates with new messages. |
| Module Configuration | Allow Guests to Post | NO | Determines if non-logged-in users can post messages. |
| Module Configuration | Display Shoutbox In | Left Column | Selects the front-office location(s) for the Shoutbox. |
| Module Configuration | Moderation Required | NO | Requires admin approval for messages before they appear. |
| Module Configuration | Clear All Messages | N/A | Permanently deletes all messages from the Shoutbox. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Shoutbox isn’t appearing on my store, even though I’ve enabled it.**
**A1:**

- **Check Hook Selection:** Go to the module configuration and ensure you’ve selected at least one “Display Shoutbox In” location (e.g., Left Column, Footer).
- **Clear Cache:** PrestaShop’s cache can sometimes prevent new modules from appearing. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Theme Compatibility:** Some highly customized themes might not correctly render standard module hooks. If clearing cache doesn’t work, try switching to the default PrestaShop theme temporarily to see if the Shoutbox appears. If it does, your theme likely needs a small adjustment (contact your theme developer or a webmaster).

**Q2: New messages aren’t appearing in real-time; I have to refresh the page.**
**A2:**

- **Check Refresh Interval:** In the module configuration, ensure “Refresh Interval (seconds)” is set to a reasonable number (e.g., 5-15 seconds) and not 0 or a very high number.
- **JavaScript Conflicts:** Another module or your theme’s JavaScript might be causing a conflict. Check your browser’s developer console (F12 key, then look at the “Console” tab) for any JavaScript errors. If errors appear, try disabling other recently installed modules one by one to identify the culprit.

**Q3: I’m getting a lot of spam messages in the Shoutbox.**
**A3:**

- **Enable Moderation:** Go to the module configuration and set “Moderation Required” to YES. This will put all new messages into a pending state, allowing you to approve them before they go live.
- **Disable Guest Posting:** If spam is coming from anonymous users, set “Allow Guests to Post” to NO. This will require users to be logged into a customer account to post, which often reduces spam.

**Q4: How do I translate the Shoutbox title or other texts into different languages?**
**A4:**

- Navigate to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations”, choose your theme, and then select your language.
- Find the “Shoutbox” module in the list and you’ll be able to edit the translatable strings, including the Shoutbox title.

**Q5: The Shoutbox looks a bit off or doesn’t match my theme’s styling.**
**A5:**

- The module uses basic styling. For custom appearance, you’ll need a webmaster or developer to add custom CSS rules to your theme’s stylesheet. They can target the Shoutbox’s elements and adjust colors, fonts, borders, etc., to perfectly match your brand.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Shoutbox module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The Shoutbox module follows a classic PrestaShop module structure, leveraging front controllers for AJAX interactions and the main module file (`index.php`) for configuration and hook registration. It’s a lightweight module, primarily focused on displaying and submitting messages via AJAX without complex object models or dedicated database tables beyond `ps_configuration` for settings. The core functionality relies on direct database interaction for message storage and retrieval.

### 4.2 Controllers (`controllers/`)

The module utilizes front controllers to handle AJAX requests for loading and inserting messages, ensuring a dynamic user experience without full page reloads.

- **Front-Office Controllers**:

  - `controllers/front/ajaxload.php`
    - **Class Name**: `ShoutboxAjaxloadModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller handles the AJAX request for loading existing messages. It typically fetches a specified number of the most recent messages from the database and returns them, likely as JSON or raw HTML, to be displayed in the Shoutbox widget. This is the endpoint for the auto-refresh mechanism.
  - `controllers/front/index.php`
    - **Class Name**: `ShoutboxIndexModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller might serve as a fallback or a direct access point to the Shoutbox if it were to have a dedicated page. Given the module’s nature, it’s more likely a placeholder or handles initial rendering logic if the Shoutbox is embedded directly rather than via a hook. In most cases, the Shoutbox is rendered via `shoutbox.tpl` in a hook.
  - `controllers/front/insert.php`
    - **Class Name**: `ShoutboxInsertModuleFrontController` (extends `ModuleFrontController`)
    - **Responsibility**: This controller handles the AJAX request for submitting new messages. It receives the message content (and potentially user ID/name) from the front-end, performs any necessary validation (e.g., guest posting, moderation), stores the message in the database, and returns a success/failure response.
- **Back-Office Admin Controllers**:

  - None. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes or `ObjectModel`s in the `classes/` directory. Message storage and retrieval are handled directly within the module’s PHP files, likely using `Db::getInstance()` for SQL queries. This implies messages are stored in a custom table created during installation or directly in `ps_configuration` if messages are very few and simple (though a dedicated table is more likely for chat messages).

### 4.4 JavaScript Assets (`views/js/`)

The module relies on JavaScript for its AJAX functionality and dynamic updates.

- `js/advajax.js`
  - **Scope**: Front-office.
  - **Details**: This file likely contains a generic AJAX utility or wrapper functions used by the module. It might provide cross-browser compatibility for AJAX requests or simplify the process of sending and receiving data from the front controllers. It could be a custom implementation or a lightweight library.
- `js/script.js`
  - **Scope**: Front-office.
  - **Details**: This is the main JavaScript file for the Shoutbox’s front-end logic.
    - **Event Listeners**: Binds to form submission events for posting new messages, and potentially click events for actions like clearing messages (if exposed to front-end).
    - **AJAX Calls**: Initiates AJAX requests to `ajaxload.php` for refreshing messages at the specified interval and to `insert.php` for submitting new messages.
    - **DOM Manipulation**: Updates the Shoutbox display with new messages, scrolls to the bottom of the chat, and handles input field clearing.
    - **Timers**: Sets up `setInterval` for periodic message loading based on the “Refresh Interval” setting.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not explicitly list any custom CSS files in the `views/css/` directory. This suggests that:

1. The module relies on inline styles or basic default browser styles.
2. It might be designed to inherit styling directly from the active PrestaShop theme, requiring minimal custom CSS.
3. Any styling is embedded directly within the `shoutbox.tpl` file or the main module PHP.
   Developers wishing to style the Shoutbox will need to inspect the generated HTML and add custom CSS rules to their theme’s stylesheet, targeting the specific IDs and classes used by the Shoutbox elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `shoutbox/shoutbox.tpl`
    - **Hook(s) Rendered**: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (or similar product page hook). The actual hook depends on the merchant’s configuration in the Back Office.
    - **Visual Block Output**: This template renders the complete HTML structure of the Shoutbox widget. This includes:
      - The main container for the chat box.
      - The title (e.g., “Community Chat”).
      - The area where messages are displayed (a scrollable div).
      - The input field for typing new messages.
      - The “Send” button.
      - Conditional rendering for guest posting capabilities.
      - It will also include the necessary JavaScript and potentially inline CSS.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not explicitly declare a custom `ObjectModel` or SQL file. Message storage is likely handled directly via `Db::getInstance()` in the main module file or front controllers. A common pattern for such modules is to create a table like `ps_shoutbox_messages` with fields such as `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
  - **Configuration Records**: Module settings (e.g., `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content in the `<head>` section of the HTML or at the very top of the `<body>`. | Used to inject CSS, JavaScript files, or the Shoutbox widget itself if configured for header display. |
| `displayLeftColumn` | Renders content in the left sidebar of the store. | Common hook for displaying the Shoutbox widget as a sidebar element. |
| `displayRightColumn` | Renders content in the right sidebar of the store. | Common hook for displaying the Shoutbox widget as a sidebar element. |
| `displayFooter` | Renders content in the footer section of the store. | Used to display the Shoutbox widget at the bottom of the page. |
| `displayProductButtons` (or similar product page hook) | Renders content on the product page, often near the add-to-cart button or product description. | Used to display the Shoutbox specifically on product pages for product-related discussions. |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media (CSS/JS). | Used to register module-specific JavaScript (`advajax.js`, `script.js`) and any potential CSS files to be loaded on the front office. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Shoutbox module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our dedicated support team is ready to assist you with any issues or questions you may have.
