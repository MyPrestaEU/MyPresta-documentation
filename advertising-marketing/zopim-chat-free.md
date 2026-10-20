---
title: "Zopim Chat Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Zopim Chat Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Zopim Chat Free Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and any external API integrations, including Zendesk Chat.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Zopim Chat Free)

This is the main and only configuration screen for the Zopim Chat Free module. Here you will input your Zendesk Chat (Zopim) account key and decide where the chat widget script should be loaded on your store.

#### **Zopim Account Key**

- **What this setting does:** This is the most crucial setting. It’s where you enter the unique identifier provided by Zendesk Chat (Zopim) for your live chat widget. This key tells the module which chat widget to load on your website. You can find this key within your Zendesk Chat dashboard (usually under Settings > Widget > Embed Code).
- **Effect of changing this setting:**
  - *When a valid key is entered:* The Zopim chat widget associated with your Zendesk Chat account will appear on your store’s front-office, allowing customers to initiate chats.
  - *When left empty or an invalid key is entered:* The Zopim chat widget will not appear on your store, and live chat functionality will be unavailable.
- **Recommended value:** Your unique Zendesk Chat (Zopim) account key.
- **Merchant scenario / example:** After signing up for Zendesk Chat, you’ll receive a snippet of code. Within that code, you’ll find a specific string (e.g., `zopim.setAndDefer('account', 'YOUR_ACCOUNT_KEY');`). Copy `YOUR_ACCOUNT_KEY` and paste it here.

#### **Load Zopim Chat in Hook**

- **What this setting does:** This option determines where in your PrestaShop store’s code the Zopim chat script will be injected. While the chat widget itself usually floats on the screen, the placement of the script can sometimes affect loading speed or compatibility with specific themes.
- **Effect of changing this setting:**
  - *When set to `displayHeader` (Header):* The chat script will load very early, typically before most of your page content. This can make the chat widget appear quickly.
  - *When set to `displayRightColumn` (Right Column):* The script will load with the content of the right column. This is less common for chat widgets and might not be ideal if your theme doesn’t always show a right column.
  - *When set to `displayLeftColumn` (Left Column):* Similar to the right column, the script loads with the left column content.
  - *When set to `displayProductButtons` (Product Page Buttons):* The script will load specifically on product pages, near the “Add to Cart” button area. This might be useful if you primarily want chat support on product pages.
  - *When set to `displayFooter` (Footer):* The script will load at the very end of your page content. This can improve initial page load speed perceived by the user, as the main content loads first, and the chat widget loads afterward.
- **Recommended value:** `displayHeader` or `displayFooter`. For most stores, `displayHeader` ensures the chat loads quickly. If you experience any conflicts or want to prioritize content loading, `displayFooter` is a good alternative.
- **Merchant scenario / example:** If your customers frequently ask questions *before* they even start browsing products, loading the chat in the `displayHeader` ensures it’s available immediately. If you notice your page loading slowly and suspect the chat script, switching to `displayFooter` might help, as the chat will load after the main page content.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Zopim Account Key | Your unique Zendesk Chat key | Connects your store to your Zendesk Chat account. Essential for the widget to appear. |
| Module Configuration Page | Load Zopim Chat in Hook | `displayHeader` or `displayFooter` | Determines where the chat script is injected (Header, Columns, Product, Footer). Affects loading order and potential theme compatibility. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Zopim chat widget isn’t appearing on my store. What should I do?**
A1:

1. **Check your Zopim Account Key:** Go to the module configuration page and ensure your Zopim Account Key is correctly entered. Even a single typo will prevent it from loading.
2. **Verify Zendesk Chat Status:** Log in to your Zendesk Chat dashboard. Is your widget active? Are your agents online?
3. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached files prevent new module changes from appearing.
4. **Check for Theme Conflicts:** Temporarily switch to the default PrestaShop theme (e.g., Classic) and see if the widget appears. If it does, your custom theme might be causing a conflict. Contact your theme developer or a webmaster.
5. **Inspect Browser Console:** Open your browser’s developer tools (F12) and check the “Console” tab for any JavaScript errors. This can provide clues if the script is failing to load.

**Q2: The chat widget loads, but it looks strange or is positioned incorrectly.**
A2: The module injects the Zopim script, but the visual styling and exact positioning of the widget are largely controlled by your Zendesk Chat account settings and your store’s CSS.

1. **Zendesk Chat Dashboard:** Log in to your Zendesk Chat dashboard and review your widget appearance settings (e.g., position, colors, size).
2. **Theme CSS:** Your custom theme’s CSS might be overriding some default Zopim styles. A webmaster can inspect the element using browser developer tools and identify conflicting CSS rules.

**Q3: Can I translate the chat widget’s text into different languages?**
A3: The Zopim Chat Free module itself doesn’t handle translations for the widget’s interface. This functionality is managed directly within your Zendesk Chat account settings. Zendesk Chat supports multiple languages, and you can configure the widget to display in the customer’s preferred language based on their browser settings or your Zendesk Chat setup.

**Q4: Will this module slow down my website?**
A4: The Zopim Chat Free module only injects the necessary Zendesk Chat script. The performance impact primarily depends on the Zendesk Chat service itself and your internet connection. You can try setting the “Load Zopim Chat in Hook” option to `displayFooter` to ensure the main content of your page loads before the chat script, which can improve perceived page load speed.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters working with the Zopim Chat Free module.

### 4.1 Architecture Overview

The `ZopimFree` module is a straightforward PrestaShop module designed to integrate the Zendesk Chat (formerly Zopim) widget. It primarily functions by injecting the Zendesk Chat embed script into the front-office of the PrestaShop store. The module follows a standard PrestaShop module structure, utilizing the `Module` class for installation, uninstallation, and configuration handling via `getContent()`. It registers a single hook (`displayHeader` by default, but configurable) to output the necessary JavaScript.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module directly injects content into hooks.
- **Back-Office Admin Controllers**: None. All configuration is handled within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in this module. All logic resides within the main `zopimfree.php` file.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included in this module. The module outputs the Zendesk Chat embed script directly into the template, which then loads the necessary JS from Zendesk’s CDN.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are included in this module. The styling of the chat widget is handled by the Zendesk Chat service itself, with potential overrides from the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `zopimfree/header-new-widget.tpl`
    - **Hook:** This template is designed to be rendered within a PrestaShop hook, specifically the one chosen in the module’s configuration (e.g., `displayHeader`, `displayFooter`).
    - **Purpose:** It contains the `<script>` tag responsible for embedding the Zendesk Chat widget. It dynamically inserts the `ZOPIMFREE_ACCOUNT_KEY` from the module’s configuration into the Zendesk Chat initialization script.
    - **Output:** Outputs the standard Zendesk Chat embed code, which then loads the chat widget from Zendesk’s servers.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table:
    - `ZOPIMFREE_ACCOUNT_KEY`: Stores the Zendesk Chat account key.
    - `ZOPIMFREE_HOOK`: Stores the name of the hook where the script should be injected (e.g., `displayHeader`, `displayFooter`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every page. | Default hook to inject the Zendesk Chat script early in the page load. |
| `displayRightColumn` | Executed in the right column of pages where it’s active. | Alternative hook for script injection, less common for chat widgets. |
| `displayLeftColumn` | Executed in the left column of pages where it’s active. | Alternative hook for script injection, less common for chat widgets. |
| `displayProductButtons` | Executed on product pages, typically near the add-to-cart button. | Specific hook for injecting chat script only on product pages. |
| `displayFooter` | Executed just before the closing `</body>` tag. | Alternative hook to inject the Zendesk Chat script later in the page load, potentially improving perceived initial page speed. |

The module registers these hooks dynamically based on the `ZOPIMFREE_HOOK` configuration value. The `install()` method registers all potential hooks, and `uninstall()` unregisters them. The `hook{HookName}` method then checks the configuration to decide if it should render the template.

## 5. Official Support & Updates

For official updates, bug fixes, and developer support for the Zopim Chat Free module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Ensure you download the latest version compatible with your PrestaShop installation.
