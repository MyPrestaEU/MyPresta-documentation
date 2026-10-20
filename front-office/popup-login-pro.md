---
title: "PopUp Login Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the PopUp Login Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy PopUp Login Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store and this module does not have unusual requirements beyond that.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > PopUp Login Pro)

This is the main configuration screen for the PopUp Login Pro module. Here you can customize how the pop-up appears and behaves on your storefront.

#### General Settings

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
| --- | --- | --- | --- | --- |
| **Enable PopUp Login** | This switch controls whether the pop-up login functionality is active on your store. | *When enabled:* The module will intercept clicks on login links and display the pop-up. *When disabled:* Your store will revert to the default PrestaShop login page redirects. | YES | You want to use the pop-up login feature. |
| **PopUp Form Type** | This option allows you to select from several pre-designed visual styles for your login pop-up form. | *When set to Option A:* The pop-up will display with the design of Option A. *When set to Option B:* The pop-up will display with the design of Option B. Each option offers a distinct look and feel. | Choose the one that best matches your store’s design. | You want a minimalist login form (Option 1) or a more visually engaging one with an image (Option 3). |
| **PopUp Width (pixels)** | Defines the width of the pop-up window in pixels. | *When set to 400px:* The pop-up will be 400 pixels wide. *When set to 600px:* The pop-up will be 600 pixels wide. A smaller width might look better on mobile, while a larger one can accommodate more content or a specific design. | 400-500px (adjust based on selected form type) | Your chosen form type looks cramped at 400px, so you increase it to 500px for better readability. |
| **PopUp Height (pixels)** | Defines the height of the pop-up window in pixels. | *When set to 300px:* The pop-up will be 300 pixels tall. *When set to 500px:* The pop-up will be 500 pixels tall. Ensure it’s tall enough to show all form fields without scrolling. | 300-450px (adjust based on selected form type) | Your chosen form type has many fields, and at 300px, customers have to scroll. You increase it to 450px to show everything. |
| **PopUp Background Color** | Sets the background color of the pop-up window. You can usually use a color picker or enter a hexadecimal color code (e.g., #FFFFFF for white). | *When set to #FFFFFF:* The pop-up background will be white. *When set to #F0F0F0:* The pop-up background will be light grey. This helps match the pop-up to your store’s color scheme. | #FFFFFF (White) or a color that complements your theme. | Your store uses a dark theme, so you set the background to a dark grey (#333333) for consistency. |
| **PopUp Border Color** | Sets the color of the border around the pop-up window. | *When set to #CCCCCC:* The pop-up border will be light grey. *When set to transparent:* No visible border will be displayed. | #CCCCCC (Light Grey) or transparent | You want a subtle border to define the pop-up, so you choose a light grey. |
| **PopUp Border Radius (pixels)** | Controls the roundness of the pop-up window’s corners. A value of 0 means sharp corners, higher values create rounder corners. | *When set to 0:* The pop-up will have sharp, square corners. *When set to 10:* The pop-up will have slightly rounded corners. | 5-10px | You prefer a softer, modern look, so you set the border radius to 8px. |
| **Overlay Background Color** | Sets the color of the dimmed background that appears behind the pop-up. This helps focus attention on the pop-up. | *When set to #000000:* The overlay will be black. *When set to #FFFFFF:* The overlay will be white. | #000000 (Black) | You want a dark, transparent overlay to clearly separate the pop-up from the main content. |
| **Overlay Opacity (0-1)** | Controls the transparency of the overlay background. 0 is fully transparent, 1 is fully opaque. | *When set to 0.5:* The overlay will be 50% transparent. *When set to 0.8:* The overlay will be 80% opaque. | 0.7-0.8 | You want the background content to be slightly visible but still clearly dimmed, so you set it to 0.7. |
| **Close Button Color** | Sets the color of the ‘X’ (close) button for the pop-up. | *When set to #000000:* The close button will be black. *When set to #FF0000:* The close button will be red. | #000000 (Black) | Your store uses a red accent color, so you make the close button red for consistency. |
| **Close Button Background Color** | Sets the background color of the ‘X’ (close) button. | *When set to #FFFFFF:* The close button background will be white. *When set to transparent:* No background color will be applied. | transparent | You want the close button to blend into the pop-up, so you set its background to transparent. |
| **Enable Google reCAPTCHA** | Activates Google reCAPTCHA for the login and registration forms within the pop-up, helping to prevent spam and bot registrations. | *When enabled:* reCAPTCHA will appear on the forms, requiring users to verify they are not robots. *When disabled:* No reCAPTCHA will be present. | YES (if you have reCAPTCHA keys) | You are experiencing a lot of spam registrations, so you enable reCAPTCHA to filter them out. |
| **reCAPTCHA Site Key** | Your public reCAPTCHA site key, obtained from Google. Required if reCAPTCHA is enabled. | *When correctly entered:* reCAPTCHA will function. *When incorrect or empty:* reCAPTCHA will not work, potentially blocking legitimate users or failing to prevent bots. | Your actual Google reCAPTCHA site key | You’ve registered your site with Google reCAPTCHA and paste the provided site key here. |
| **reCAPTCHA Secret Key** | Your private reCAPTCHA secret key, obtained from Google. Required if reCAPTCHA is enabled. | *When correctly entered:* reCAPTCHA will function. *When incorrect or empty:* reCAPTCHA will not work. | Your actual Google reCAPTCHA secret key | You’ve registered your site with Google reCAPTCHA and paste the provided secret key here. |

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable PopUp Login | YES | Activates/deactivates the pop-up login feature. |
| Module Configuration | PopUp Form Type | (Choose based on design) | Selects the visual style of the login form. |
| Module Configuration | PopUp Width (pixels) | 400-500px | Controls the width of the pop-up window. |
| Module Configuration | PopUp Height (pixels) | 300-450px | Controls the height of the pop-up window. |
| Module Configuration | PopUp Background Color | #FFFFFF | Sets the background color of the pop-up. |
| Module Configuration | PopUp Border Color | #CCCCCC or transparent | Sets the border color of the pop-up. |
| Module Configuration | PopUp Border Radius (pixels) | 5-10px | Controls the roundness of pop-up corners. |
| Module Configuration | Overlay Background Color | #000000 | Sets the color of the dimmed background behind the pop-up. |
| Module Configuration | Overlay Opacity (0-1) | 0.7-0.8 | Controls transparency of the overlay background. |
| Module Configuration | Close Button Color | #000000 | Sets the color of the pop-up’s close button. |
| Module Configuration | Close Button Background Color | transparent | Sets the background color of the close button. |
| Module Configuration | Enable Google reCAPTCHA | YES (if keys available) | Activates reCAPTCHA for bot protection. |
| Module Configuration | reCAPTCHA Site Key | Your actual key | Public key for reCAPTCHA verification. |
| Module Configuration | reCAPTCHA Secret Key | Your actual key | Private key for reCAPTCHA verification. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The pop-up isn’t appearing when I click “Sign In.” What should I do?**
A:

1. **Check Module Status:** Ensure the “Enable PopUp Login” setting is set to YES in the module’s configuration.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes old cached files prevent new module functionality from loading.
3. **Theme Compatibility:** Some highly customized themes might use non-standard ways to handle login links. Check if your theme has specific settings or overrides for login. If issues persist, contact MyPresta.eu support.

**Q2: The pop-up looks strange or doesn’t match my theme’s style.**
A:

1. **Adjust Styling Settings:** Go to the module configuration and experiment with “PopUp Background Color,” “PopUp Border Color,” “PopUp Border Radius,” “Overlay Background Color,” and “Overlay Opacity.”
2. **Form Type:** Try different “PopUp Form Type” options to see if another design integrates better with your theme.
3. **Custom CSS:** If basic settings aren’t enough, your webmaster might need to add custom CSS to your theme to override the module’s default styles (see Section 7.5 for CSS file details).

**Q3: reCAPTCHA isn’t working on the pop-up forms.**
A:

1. **Enable reCAPTCHA:** Make sure “Enable Google reCAPTCHA” is set to YES.
2. **Check Keys:** Double-check that your “reCAPTCHA Site Key” and “reCAPTCHA Secret Key” are correctly entered in the module configuration. These are case-sensitive.
3. **Google reCAPTCHA Setup:** Ensure your domain is correctly registered in your Google reCAPTCHA account.
4. **Clear Cache:** Always clear your PrestaShop cache after making changes to reCAPTCHA settings.

**Q4: The pop-up is too big/small on my mobile phone.**
A:

1. **Adjust Width/Height:** Modify “PopUp Width (pixels)” and “PopUp Height (pixels)” in the module configuration. While these are pixel values, the module is designed to be responsive, so adjusting these will influence its scaling on different devices.
2. **Test Responsiveness:** Use your browser’s developer tools (F12) to simulate different mobile devices and fine-tune the dimensions.

**Q5: How do I translate the text within the pop-up?**
A:

1. **Translate Module:** In your PrestaShop Back Office, go to **International > Translations**.
2. **Select Options:**
   - Type of translation: “Installed modules translations”
   - Select your theme: Your current theme
   - Select your language: The language you want to translate
3. **Find Module:** Search for “PopUp Login Pro” (or `popuplogin`).
4. **Translate Fields:** You will find all translatable strings used by the module. Enter your translations and save.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The PopUp Login Pro module follows a standard PrestaShop module architecture, primarily leveraging front controllers for AJAX requests and hooks for integration into the theme. It uses JavaScript to intercept standard login link clicks and display the pop-up, dynamically loading content via AJAX. Configuration is handled through the main module class’s `getContent()` method, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  - `controllers/front/index.php`
    - **Class Name**: `PopUpLoginIndexModuleFrontController`
    - **Parent Class**: `ModuleFrontController`
    - **Responsibility**: This controller likely serves as a general entry point or handles initial setup for front-office interactions, though its specific methods would define its exact role. It might be responsible for rendering the initial pop-up structure or handling non-login related AJAX calls.
  - `controllers/front/loginbox.php`
    - **Class Name**: `PopUpLoginLoginBoxModuleFrontController`
    - **Parent Class**: `ModuleFrontController`
    - **Responsibility**: This is the core controller for handling the login and registration form logic. It responds to AJAX requests for displaying the login/registration form content, processing login attempts, handling new registrations, and managing “forgot password” requests. It likely returns HTML fragments or JSON responses to the JavaScript for dynamic insertion into the pop-up.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, there are no custom classes or `ObjectModel` definitions within the `classes/` directory. The module likely leverages existing PrestaShop core classes for customer management (`Customer`, `Context`, `Tools`) and standard configuration storage.

### 4.4 JavaScript Assets (`views/js/`)

- `popuplogin/popuplogin.js`
  - **Scope**: Front-office.
  - **Details**: This is the primary JavaScript file for the module’s front-end functionality.
    - **Event Listeners**: It binds event listeners to various elements, most critically to standard login/account links (e.g., `a[href*="controller=authentication"]`, `a[href*="my-account"]`). It intercepts click events on these links.
    - **AJAX Calls**: When a login link is clicked, it prevents the default navigation and initiates an AJAX request to `popuplogin/controllers/front/loginbox.php` (or similar) to fetch the login/registration form HTML.
    - **DOM Manipulation**: It dynamically creates and inserts the pop-up overlay and the login form content into the DOM. It handles showing/hiding the pop-up, managing the overlay, and potentially switching between login and registration views within the pop-up.
    - **Form Submission**: It likely intercepts form submissions within the pop-up (login, registration, forgot password) and sends them via AJAX to the `loginbox.php` controller, processing the responses (e.g., displaying success messages, error messages, or redirecting upon successful login).
    - **UI/UX**: Manages the visual effects of the pop-up (e.g., fade-in/fade-out, centering).
    - **reCAPTCHA Integration**: If reCAPTCHA is enabled, this script is responsible for rendering the reCAPTCHA widget and including its token in AJAX form submissions.

### 4.5 CSS Stylesheets (`views/css/`)

- `popuplogin/css.css`
  - **Scope**: Front-office customer styling.
  - **Details**: This file likely contains general, foundational styles for the pop-up container, overlay, and potentially common form elements. It might include reset styles or basic layout rules.
  - **Key Selectors**: `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
- `popuplogin/popuplogin.css`
  - **Scope**: Front-office customer styling.
  - **Details**: This file probably contains the more specific and detailed styling for the various pop-up form types, including input fields, buttons, error messages, and responsive adjustments. It will define the visual differences between the “PopUp Form Type” options.
  - **Key Selectors**: `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
  - **Developer Override**: Developers can override these styles in their theme’s `custom.css` or by creating a child theme to modify the appearance without editing the module files directly.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `popuplogin/dashboardZoneOne.tpl`
    - **Hook**: Likely `displayDashboardZoneOne` (or similar dashboard hook).
    - **Purpose**: This template is probably for displaying a small informational block or quick statistics related to the PopUp Login Pro module on the PrestaShop Back Office dashboard. It’s an admin-facing template.
  - `popuplogin/displayPopUpLogin.tpl`
    - **Hook**: This template is likely rendered by the `loginbox.php` front controller and contains the actual HTML structure for the login/registration form that appears inside the pop-up. It’s not directly hooked into a `display` hook in the theme, but rather loaded dynamically.
    - **Purpose**: Renders the login, registration, and forgot password forms, including input fields, buttons, and potentially reCAPTCHA placeholders.
  - `popuplogin/header.tpl`
    - **Hook**: Likely `displayHeader`.
    - **Purpose**: This template is responsible for including the module’s CSS and JavaScript files (`popuplogin.js`, `css.css`, `popuplogin.css`) into the `<head>` section of the front-office pages, ensuring they are loaded before the module’s functionality is triggered.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys typically prefixed with `POPUPLOGIN_` (e.g., `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects the module’s CSS and JavaScript files for front-end functionality. |
| `displayDashboardZoneOne` | On the PrestaShop Back Office dashboard. | Displays an informational block or widget for the module in the admin panel. |
| (Implicit Hooks) | Triggered by JavaScript interception of standard login links. | The module’s JavaScript intercepts clicks on elements that would normally lead to `authentication` or `my-account` controllers, and then uses AJAX to dynamically load content from its own front controllers. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the PopUp Login Pro module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions perfectly and integrates seamlessly with your PrestaShop store.
