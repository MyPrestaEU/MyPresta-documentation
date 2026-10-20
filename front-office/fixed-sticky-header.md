---
title: "Fixed sticky header - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Fixed sticky header PrestaShop module by MyPresta.eu."
sidebar:
  label: "Fixed sticky header - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Fixed sticky header Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/fixed-sticky-header/)
>
> ---


# Fixed sticky header

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). The module works with default-bootstrap and classic templates and with all themes with similar structure.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Fixed sticky header” module in your Module Manager. This will take you to the module’s main configuration page.

#### General Settings

- **What this setting does:** This section typically includes standard MyPresta.eu module settings related to updates and support.
- **Effect of changing this setting:**
  - *When enabled:* Allows the module to check for available updates from MyPresta.eu and potentially display notifications in your Back Office. This ensures you’re always running the latest, most secure, and feature-rich version of the module.
  - *When disabled:* The module will not automatically check for updates. You would need to manually check for new versions by logging into your MyPresta.eu account.
- **Recommended value:** **YES** (or enabled). Keeping this setting active is highly recommended to ensure you receive timely updates and bug fixes, which are crucial for security and compatibility with future PrestaShop versions.
- **Merchant scenario / example:** You want to be notified if a new version of the module is released that fixes a bug or adds a new feature. Keeping this enabled ensures you’re always informed.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Update Checks (mypresta\_updates, update\_, updatev\_) | Enabled | Allows the module to check for and notify you about available updates from MyPresta.eu, ensuring you have the latest features and security fixes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The header is not sticking, or it’s overlapping other elements. What should I do?**
A1: This often happens due to conflicts with your theme’s CSS or JavaScript, especially if your theme has a very custom header structure.
\* **Clear Cache:** First, try clearing your PrestaShop cache. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
\* **Theme Compatibility:** The module is designed to work with standard PrestaShop themes (like Classic) and themes with similar structures. If you have a heavily customized theme, you might need minor CSS adjustments.
\* **Contact Support:** If the issue persists, gather screenshots and details about your theme, and contact MyPresta.eu support. They can help diagnose and provide custom CSS snippets if needed.

**Q2: My header looks strange or has extra space when it becomes sticky.**
A2: This can be a styling issue.
\* **Inspect Element:** Use your browser’s developer tools (right-click on your header and select “Inspect”) to see what CSS rules are being applied. Look for `position: fixed;` and `top: 0;`.
\* **Theme Styling:** Your theme might have specific padding or margin rules that conflict. You might need to add custom CSS to adjust the sticky header’s appearance. MyPresta.eu support can guide you.

**Q3: Will this module slow down my website?**
A3: The “Fixed sticky header” module is very lightweight, using minimal JavaScript and CSS. It should have a negligible impact on your website’s loading speed and performance. The effect is activated only on scroll, so it doesn’t add overhead to the initial page load.

**Q4: How do I translate the module if it had any visible text?**
A4: While this module primarily provides a visual effect and doesn’t typically have user-facing text, if any future version introduces configurable text, you would translate it via:
\* **International > Translations** in your PrestaShop Back Office.
\* Select “Installed modules translations”, choose your theme, and then select “Fixed sticky header” from the module dropdown.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Fixed sticky header” module is a lightweight front-office feature module designed to enhance user experience by making the main header sticky on scroll. It primarily leverages JavaScript to detect scroll events and apply CSS classes to the header element, which then triggers the `position: fixed` styling. It adheres to the standard PrestaShop module structure, utilizing the `displayHeader` hook to inject its assets.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s functionality is entirely handled via JavaScript injected through a hook.
- **Back-Office Admin Controllers**: None. Configuration is managed directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are used. The module operates by manipulating existing DOM elements.

### 4.4 JavaScript Assets (`views/js/`)

- **`fixedheader/fixedheader.js`**
  - **Scope:** Front-office.
  - **Purpose:** This script is responsible for the core sticky header functionality.
  - **Details:**
    - It listens for the `scroll` event on the `window` object.
    - It determines the scroll position and the initial offset of the header element.
    - When the user scrolls past a certain threshold (the initial height of the header), it adds a specific CSS class (e.g., `fixed-header-active` or similar, as defined in `fixedheader.css`) to the main header container.
    - When the user scrolls back up above the threshold, it removes this class.
    - It likely targets a common header selector (e.g., `#header`, `.header-container`, or similar, depending on the theme structure) to apply the sticky behavior.
    - It may also handle adding a `padding-top` to the `body` or a main content wrapper to prevent content from “jumping” or being hidden behind the fixed header.

### 4.5 CSS Stylesheets (`views/css/`)

- **`fixedheader/fixedheader.css`**
  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides the necessary CSS rules to make the header sticky when the JavaScript adds the activation class.
  - **Details:**
    - It defines styles for the active sticky header state. Key properties will include:
      - `position: fixed;`
      - `top: 0;`
      - `width: 100%;`
      - `z-index: 1000;` (or a high value to ensure it stays above other content).
      - Potentially `box-shadow` or `background-color` to visually distinguish the sticky header.
    - It might also include rules to handle the `body` padding or margin to prevent content overlap.
    - **Key CSS class selectors developers can override:** The primary class added by the JS (e.g., `.fixed-header-active` or similar) and the selector for the header element itself (e.g., `#header`, `.header-container`). Developers can override these styles in their theme’s custom CSS to match their design.

### 4.6 Smarty Template Structure (`views/templates/`)

- No custom `.tpl` files are used. The module injects its JavaScript and CSS directly into the `<head>` section via the `displayHeader` hook.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: No custom database tables are created. Configuration is stored in `ps_configuration` using keys like `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects the module’s CSS (`fixedheader.css`) and JavaScript (`fixedheader.js`) files into the page, ensuring they are loaded before the page content is rendered and are available for immediate execution. |

## 5. Official Support & Updates

For official updates, technical support, and the latest versions of the “Fixed sticky header” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
