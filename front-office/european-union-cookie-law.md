---
title: "European Union Cookie Law - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the European Union Cookie Law PrestaShop module by MyPresta.eu."
sidebar:
  label: "European Union Cookie Law - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy European Union Cookie Law Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/european-union-cookie-law/)
>
> ---


# European Union Cookie Law

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the European Union Cookie Law module. You’ll find all settings here to customize your cookie notification.

#### **Enable / Disable Module**

- **What this setting does:** This is the master switch to turn the cookie notification on or off across your entire store.
- **Effect of changing this setting:**
  - *When enabled:* The cookie notification bar will appear on your front office according to your other settings.
  - *When disabled:* The cookie notification bar will not be displayed to any visitors.
- **Recommended value:** YES (unless you have another method for cookie compliance).
- **Merchant scenario / example:** You’ve just installed the module and want to activate the cookie notice. Set this to “YES”. If you temporarily need to hide it for maintenance or testing, you can set it to “NO”.

#### **Cookie Text**

- **What this setting does:** This is the actual message that will be displayed to your customers regarding cookie usage. It supports multiple languages, allowing you to provide a localized message for each language enabled in your store.
- **Effect of changing this setting:** The text you enter here will be shown in the cookie notification bar. You can use the rich text editor to format the text, add links (e.g., to your full privacy policy page), and emphasize important information.
- **Recommended value:** A clear, concise message that informs users about cookies and ideally includes a link to your full privacy policy or cookie policy page.
- **Merchant scenario / example:** You might write: “This website uses cookies to ensure you get the best experience on our website. [Link to Privacy Policy]”. Make sure to translate this into all active languages of your store.

#### **Button Text**

- **What this setting does:** This defines the text displayed on the button that customers click to acknowledge or accept the cookie policy. Like the cookie text, it supports multiple languages.
- **Effect of changing this setting:** The button will display the text you specify. Clicking this button will dismiss the cookie notification for the user.
- **Recommended value:** “I understand”, “Accept”, “Got it”, “Continue”, or “OK”.
- **Merchant scenario / example:** To make it clear that users are acknowledging the policy, you might set this to “I understand and accept”.

#### **Position**

- **What this setting does:** Determines where the cookie notification bar appears on your website.
- **Effect of changing this setting:**
  - *Top:* The bar will appear fixed at the top of the browser window.
  - *Bottom:* The bar will appear fixed at the bottom of the browser window.
- **Recommended value:** Bottom (often less intrusive than the top, which can sometimes interfere with header elements).
- **Merchant scenario / example:** You want the cookie notice to be visible but not obstruct your main navigation or logo. Choosing “Bottom” is usually a good compromise.

#### **Background Color**

- **What this setting does:** Allows you to choose the background color of the cookie notification bar. This helps integrate the bar visually with your store’s design.
- **Effect of changing this setting:** The background of the cookie bar will change to the selected color. A color picker tool is usually provided for easy selection.
- **Recommended value:** A color that contrasts well with your text color and complements your store’s branding.
- **Merchant scenario / example:** Your store uses a lot of blue. You might choose a light blue or a subtle grey for the background to match your theme.

#### **Text Color**

- **What this setting does:** Allows you to choose the color of the text within the cookie notification bar.
- **Effect of changing this setting:** The text in the cookie bar will change to the selected color.
- **Recommended value:** A color that provides good contrast against your chosen background color for readability.
- **Merchant scenario / example:** If your background color is dark, choose a light text color (e.g., white, light grey). If your background is light, choose a dark text color (e.g., black, dark grey).

#### **Link Color**

- **What this setting does:** Allows you to choose the color of any links included in your “Cookie Text” (e.g., a link to your privacy policy).
- **Effect of changing this setting:** All `<a>` tags within the cookie bar’s text will display in this color.
- **Recommended value:** A color that stands out from the main text color but still fits your brand.
- **Merchant scenario / example:** You want the link to your privacy policy to be easily noticeable. You might choose your brand’s accent color for the link.

#### **Button Background Color**

- **What this setting does:** Sets the background color of the “Button Text” button.
- **Effect of changing this setting:** The button will have the selected background color.
- **Recommended value:** A color that makes the button stand out and encourages clicks, often matching your store’s primary call-to-action button color.
- **Merchant scenario / example:** Your store’s “Add to Cart” buttons are green. You might choose green for the cookie button’s background to maintain consistency.

#### **Button Text Color**

- **What this setting does:** Sets the color of the text on the “Button Text” button.
- **Effect of changing this setting:** The button text will display in this color.
- **Recommended value:** A color that provides good contrast against the button’s background color for readability.
- **Merchant scenario / example:** If your button background is dark green, choose white or a very light color for the button text.

#### **Cookie Expiration (in days)**

- **What this setting does:** Determines how long the cookie notification remains hidden after a user clicks the “I understand” button. After this period, the notification will reappear for the user.
- **Effect of changing this setting:**
  - *Set to 30:* The notification will be hidden for 30 days for that specific user.
  - *Set to 0:* The notification might reappear on every visit or session, which is generally not recommended as it can be annoying.
- **Recommended value:** 30 to 365 days. A common practice is 90 or 180 days.
- **Merchant scenario / example:** To avoid repeatedly bothering returning customers, you set this to “180” days. This means a customer who accepts the policy won’t see the bar again for six months.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Enable / Disable Module** | YES | Master switch for cookie bar visibility. |
| Module Configuration | **Cookie Text** | Customizable | The main message about cookie usage, supports rich text & multi-language. |
| Module Configuration | **Button Text** | Customizable | Text on the button to dismiss the notice, multi-language. |
| Module Configuration | **Position** | Bottom | Where the bar appears (Top or Bottom of the screen). |
| Module Configuration | **Background Color** | Customizable | Background color of the cookie bar. |
| Module Configuration | **Text Color** | Customizable | Color of the main text in the cookie bar. |
| Module Configuration | **Link Color** | Customizable | Color of any links within the cookie text. |
| Module Configuration | **Button Background Color** | Customizable | Background color of the dismissal button. |
| Module Configuration | **Button Text Color** | Customizable | Color of the text on the dismissal button. |
| Module Configuration | **Cookie Expiration (in days)** | 180-365 days | How long the notice remains hidden after user acceptance. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The cookie bar isn’t showing up on my store.**
A1:

- **Check “Enable / Disable Module”:** Ensure this setting is set to “YES” in the module configuration.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” at the top right. Sometimes, old cached content prevents new module changes from appearing.
- **Check for Conflicts:** Temporarily disable other recently installed modules to see if there’s a conflict.
- **Browser Cache:** Try clearing your browser’s cache or opening your store in an incognito/private browsing window.

**Q2: I’ve updated the text, but it’s not changing on the front office.**
A2:

- **Save Changes:** Make sure you clicked the “Save” button after making changes in the module configuration.
- **Clear PrestaShop Cache:** As mentioned above, clearing the Smarty cache (under **Advanced Parameters > Performance**) is often necessary for template and text changes to take effect.
- **Check Language:** Ensure you are editing the text for the correct language if your store is multilingual.

**Q3: The cookie bar looks strange or doesn’t fit my theme.**
A3:

- **Adjust Colors:** Use the “Background Color”, “Text Color”, “Link Color”, “Button Background Color”, and “Button Text Color” settings to match your theme’s palette.
- **Theme Conflicts:** Some custom themes might have conflicting CSS styles. If adjusting colors doesn’t help, you might need a web developer to inspect the CSS and make minor adjustments.

**Q4: How do I add a link to my Privacy Policy in the cookie text?**
A4:

- In the “Cookie Text” field, use the rich text editor. Type the text you want to be a link (e.g., “Privacy Policy”), select it, and then click the “Link” icon in the editor toolbar. Enter the URL of your Privacy Policy page.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers, webmasters, and agencies working with the European Union Cookie Law module.

### 4.1 Architecture Overview

The `uecookie` module is a straightforward PrestaShop module primarily designed to inject a front-office template into a display hook, controlled by a standard `getContent()` configuration method. It leverages PrestaShop’s `Module` class for installation, uninstallation, and configuration, and uses Smarty templates for rendering the cookie notification. Client-side logic for dismissing the cookie bar is handled via JavaScript.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All functionality is handled within the main module file and its associated templates and assets.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or `ObjectModel` definitions. All configuration is stored directly in `ps_configuration` using `Configuration::get()` and `Configuration::updateValue()`.

### 4.4 JavaScript Assets (`views/js/`)

- `uecookie/jscolor/jscolor.js`:
  - **Scope:** Back-office.
  - **Purpose:** Provides a JavaScript color picker functionality for the module’s configuration form, allowing administrators to visually select colors for the cookie bar.
- `uecookie/tinymce-original.js`:
  - **Scope:** Back-office.
  - **Purpose:** A full version of the TinyMCE rich text editor, used for the “Cookie Text” field in the module’s configuration. This enables administrators to format text, add links, etc.
- `uecookie/tinymce16.inc.js`:
  - **Scope:** Back-office.
  - **Purpose:** Likely an include or configuration file for TinyMCE, possibly customizing its toolbar or options for PrestaShop 1.6 compatibility or specific module needs.
- `uecookie/views/js/scripts.js`:
  - **Scope:** Front-office.
  - **Purpose:** This script handles the client-side logic for the cookie notification bar.
    - **Event Listeners:** Likely listens for a click event on the “I understand” button.
    - **DOM Manipulation:** Hides the cookie bar element from the DOM upon dismissal.
    - **Cookie Management:** Sets a browser cookie (e.g., `uecookie_accepted`) with an expiration date (determined by the “Cookie Expiration” setting) to prevent the bar from reappearing for the specified duration.
    - **Initial Check:** On page load, it checks for the presence of the `uecookie_accepted` cookie to determine whether to display the bar or not.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** contain any custom CSS files in `views/css/`. Styling for the cookie bar is likely inline or generated dynamically based on the color settings, or relies on minimal default browser styles. Developers wishing to customize the appearance further would need to target the HTML structure output by `top.tpl` using their theme’s custom CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `uecookie/top.tpl`:
    - **Hook:** This template is primarily designed to be rendered in a front-office hook such as `displayHeader`, `displayFooter`, `displayTop`, or `displayBeforeBodyClosingTag`. The module’s `hookDisplayHeader` method is typically responsible for registering and rendering this template.
    - **Output:** It outputs the HTML structure for the cookie notification bar, including the customizable text, button, and dynamic styling based on the module’s configuration settings (background color, text color, etc.). It also includes the necessary JavaScript (`scripts.js`) to handle dismissal and cookie setting.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - All configuration settings are stored in the `ps_configuration` table. Key configuration entries would include:
    - `UECOOKIE_ENABLED` (boolean)
    - `UECOOKIE_TEXT` (multilingual string)
    - `UECOOKIE_BUTTON_TEXT` (multilingual string)
    - `UECOOKIE_POSITION` (string: ‘top’ or ‘bottom’)
    - `UECOOKIE_BG_COLOR` (string: hex color code)
    - `UECOOKIE_TEXT_COLOR` (string: hex color code)
    - `UECOOKIE_LINK_COLOR` (string: hex color code)
    - `UECOOKIE_BUTTON_BG_COLOR` (string: hex color code)
    - `UECOOKIE_BUTTON_TEXT_COLOR` (string: hex color code)
    - `UECOOKIE_EXPIRATION` (integer: days)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to inject the module’s CSS (if any) and JavaScript files, and potentially the initial HTML structure of the cookie bar if positioned at the top. |
| `displayFooter` | Executed at the bottom of every front-office page, before the closing `</body>` tag. | Can be used to inject the cookie bar HTML and JavaScript, especially if positioned at the bottom. |
| `displayTop` | Executed in the header section of the theme, typically above the main content. | Alternative hook for displaying the cookie bar at the top. |
| `displayBeforeBodyClosingTag` | Executed just before the `</body>` tag. | A robust hook for injecting JavaScript and HTML elements that should appear at the very end of the page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “European Union Cookie Law” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
