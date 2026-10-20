---
title: "Free PopUp - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free PopUp PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free PopUp - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free PopUp Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the Free PopUp module. You’ll find all the settings here to control your popup’s content and behavior.

#### **1. Enable / Disable Popup**

- **What this setting does:** This is the master switch for your popup.
- **Effect of changing this setting:**
  - *When enabled (YES):* The popup will appear on your front office according to your other settings.
  - *When disabled (NO):* The popup will not appear on your front office, regardless of other settings.
- **Recommended value:** YES (when you want the popup active), NO (when you want to temporarily hide it).
- **Merchant scenario / example:** Enable it when you have a new promotion running. Disable it during maintenance or if you want to run a different campaign temporarily.

#### **2. Popup Content**

- **What this setting does:** This is where you enter the actual message, offer, or information you want to display inside the popup. It uses a rich text editor (TinyMCE), allowing you to format text, add images, links, and more.
- **Effect of changing this setting:** Whatever you type and format here will be displayed directly to your customers in the popup window.
- **Recommended value:** Your specific promotional message, welcome text, or important announcement.
- **Merchant scenario / example:** “Welcome to our store! Use code WELCOME10 for 10% off your first order!” or “Free shipping on all orders over $50 this week!” You can also add an image of a new product or a brand logo.

#### **3. Cookie Expiration (Days)**

- **What this setting does:** This determines how long the popup remains hidden after a customer closes it. It sets a cookie in the customer’s browser.
- **Effect of changing this setting:**
  - *When set to 0:* The popup will appear on *every* page load, even if the customer just closed it. This is generally not recommended as it can be annoying.
  - *When set to a positive number (e.g., 7):* The popup will appear on the first visit. Once closed, it will not reappear for the next 7 days for that specific customer on that specific browser.
- **Recommended value:** 7 (for weekly promotions), 30 (for monthly welcome messages), or 1 (if you want it to reappear daily).
- **Merchant scenario / example:** If you have a general welcome message, setting it to 30 days is good. If you’re running a weekly sale, 7 days ensures customers see the new offer next week.

#### **4. Test Mode**

- **What this setting does:** This allows you to test your popup’s appearance and content without waiting for the cookie expiration.
- **Effect of changing this setting:**
  - *When enabled (YES):* The popup will appear on every page refresh, even if you’ve just closed it. This overrides the “Cookie Expiration” setting for testing purposes.
  - *When disabled (NO):* The popup will behave normally, respecting the “Cookie Expiration” setting.
- **Recommended value:** YES (while you are setting up and tweaking the popup), NO (once you are satisfied with the setup and want it to function normally for customers).
- **Merchant scenario / example:** You’ve just updated your popup content and want to see how it looks on the front office immediately. Enable Test Mode, refresh your store page, and the popup will show up. Once you’re happy, disable Test Mode.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Enable / Disable Popup | YES | Master switch to show or hide the popup on your store. |
| Module Configuration Page | Popup Content | Your message | The actual text, images, and links displayed inside the popup. |
| Module Configuration Page | Cookie Expiration (Days) | 7 | How many days the popup remains hidden after a customer closes it. |
| Module Configuration Page | Test Mode | NO | Forces the popup to show on every refresh for testing purposes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My popup isn’t showing up on the front office, even after enabling it.**

- **A:** First, check if “Enable / Disable Popup” is set to YES. If it is, try enabling “Test Mode” to see if it appears. If it still doesn’t show, clear your browser cache and PrestaShop’s Smarty cache (Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right). Also, ensure you’ve saved your configuration after making changes.

**Q2: The popup appeared once, but now it won’t show again.**

- **A:** This is normal behavior due to the “Cookie Expiration” setting. The module sets a cookie in your browser to prevent the popup from reappearing for the specified number of days. To force it to show for testing, enable “Test Mode” in the module configuration. To see it as a new visitor, clear your browser’s cookies for your store’s domain or use an incognito/private browsing window.

**Q3: How can I make the popup look different (change colors, fonts, etc.)?**

- **A:** The module provides a basic white modal with a 70% overlay. For advanced styling, you would need custom CSS. This is typically handled by a web developer. You can add custom CSS to your theme’s `custom.css` file or directly edit the module’s `front.css` (though the latter is not recommended as updates would overwrite it).

**Q4: Can I have different popups for different pages or customer groups?**

- **A:** The Free PopUp module is designed for a single, shop-wide campaign. It displays the same content to all visitors. For more advanced, targeted popups, you would need a more feature-rich (and likely paid) popup module.

**Q5: My images or links in the popup content aren’t working correctly.**

- **A:** Ensure you’re using full, absolute URLs for images and links (e.g., `https://yourstore.com/img/yourimage.jpg` instead of `/img/yourimage.jpg`). The TinyMCE editor should handle this automatically, but sometimes issues arise if you copy-paste content from external sources. Double-check the HTML source if you’re comfortable with it.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Free PopUp module is a straightforward PrestaShop module following a basic MVC pattern. It primarily uses the `Module` class for its core functionality, configuration management, and hook registration. The front-office display is managed by a single template rendered via a hook, and its behavior is controlled by a simple JavaScript file. Styling is handled by dedicated CSS files for both the admin and front-office.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom front-office or back-office controllers. All configuration is handled within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. All configuration data is stored directly in PrestaShop’s `ps_configuration` table using standard `Configuration::get()` and `Configuration::updateValue()` methods.

### 4.4 JavaScript Assets (`views/js/`)

- **`myfreepopup/js/front.js`**
  - **Scope:** Front-office.
  - **Responsibility:** This script is responsible for the client-side behavior of the popup.
  - **Details:**
    - It checks for the presence of a specific cookie (`myfreepopup_closed`).
    - If the cookie is not found (meaning the user hasn’t closed the popup recently or it’s their first visit), it displays the popup by manipulating CSS properties (e.g., `display: block`).
    - It attaches an event listener to the close button within the popup.
    - When the close button is clicked, it hides the popup and sets the `myfreepopup_closed` cookie with an expiration based on the module’s configuration.
    - It also handles the “Test Mode” logic, ensuring the cookie check is bypassed when test mode is active.

### 4.5 CSS Stylesheets (`views/css/`)

- **`myfreepopup/css/admin.css`**
  - **Scope:** Back-office admin form styling.
  - **Details:** Contains basic styling rules for the module’s configuration page in the PrestaShop back office, ensuring a consistent look and feel within the admin panel.
- **`myfreepopup/css/front.css`**
  - **Scope:** Front-office customer styling.
  - **Details:** Defines the visual appearance of the popup itself. This includes:
    - Styling for the modal overlay (e.g., `position: fixed`, `background-color`, `opacity`, `z-index`).
    - Styling for the main popup content box (e.g., `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` for centering).
    - Styling for the close button (e.g., `position: absolute`, `font-size`, `cursor: pointer`).
    - Responsive adjustments for different screen sizes using media queries.
  - **Key CSS class selectors for overriding:** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`myfreepopup/views/admin_banner.tpl`**
  - **Scope:** Admin template.
  - **Purpose:** Displays a promotional banner or information message within the module’s configuration page in the back office.
- **`myfreepopup/views/admin_locks.tpl`**
  - **Scope:** Admin template.
  - **Purpose:** Likely used for displaying information related to module licensing or additional features, often with a lock icon.
- **`myfreepopup/views/front.tpl`**
  - **Scope:** Front-office hook template.
  - **Purpose:** This is the main template responsible for rendering the HTML structure of the popup on the front office.
  - **Rendered in hook:** `displayHeader` (or similar global hook where JS/CSS can be loaded).
  - **Content:** Contains the HTML for the overlay, the popup content box, the close button, and dynamically inserts the `{$popup_content}` variable (which comes from the TinyMCE editor in the back office). It also includes the necessary JavaScript and CSS files.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - It stores its configuration settings in the standard `ps_configuration` table using keys such as `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to include the module’s CSS and JavaScript files, and to render the initial HTML structure of the popup (`front.tpl`) which is then controlled by JavaScript. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the Free PopUp module.
