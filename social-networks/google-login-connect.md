---
title: "Google Login Connect - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google Login Connect PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google Login Connect Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for secure communication with Google's API.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Google Login Connect)

This is the main configuration screen where you will set up your Google API credentials and decide where the "Sign in with Google" button appears in your store.

#### **Google API Credentials**

Before configuring the module, you need to create a Google API Project and obtain your Client ID. This is crucial for the module to communicate securely with Google.

**How to get your Google Client ID:**
1.  Go to the [Google Cloud Console](https://console.cloud.google.com/).
2.  Create a new project or select an existing one.
3.  Navigate to **APIs & Services > Credentials**.
4.  Click **"Create Credentials"** and choose **"OAuth client ID"**.
5.  Select **"Web application"** as the application type.
6.  Under **"Authorized JavaScript origins"**, add your store's URL (e.g., `https://www.yourstore.com`).
7.  Under **"Authorized redirect URIs"**, add your store's URL followed by the module's callback path (e.g., `https://www.yourstore.com/module/glogin/index`).
8.  After creation, Google will provide you with a **Client ID**. Copy this value.

-   **Google Client ID (ggl_appid)**
    -   **What this setting does:** This is the unique identifier for your application (your PrestaShop store) that Google uses to recognize your login requests. It's essential for the "Sign in with Google" functionality to work.
    -   **Effect of changing this setting:**
        -   *When correctly entered:* Your Google login buttons will function, allowing customers to authenticate via Google.
        -   *When incorrect or empty:* The Google login buttons will not work, or customers will encounter errors when trying to sign in with Google.
    -   **Recommended value:** The Client ID obtained from your Google Cloud Console.
    -   **Merchant scenario / example:** You've just created your Google API project and received `1234567890-abcdefg.apps.googleusercontent.com`. You must paste this exact string here.

#### **Customer Account Settings**

-   **Customer Group for Google Users (glogin_groupid)**
    -   **What this setting does:** Determines which customer group new users who register via Google will be automatically assigned to.
    -   **Effect of changing this setting:**
        -   *When set to "Customer" (default):* New Google users will be standard customers.
        -   *When set to "Visitor" or another custom group:* New Google users will be assigned to that specific group, potentially affecting their access to discounts, special prices, or content.
    -   **Recommended value:** "Customer" (or your default customer group).
    -   **Merchant scenario / example:** You want all new Google sign-ups to be part of your "Wholesale Customers" group to automatically grant them B2B pricing. You would select "Wholesale Customers" from the dropdown.

-   **Send Welcome Email to New Google Users (glogin_semail)**
    -   **What this setting does:** Controls whether PrestaShop sends a standard welcome email to customers who register using their Google account.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* New Google users will receive the standard PrestaShop welcome email, confirming their account creation.
        -   *When disabled (NO):* New Google users will not receive a welcome email.
    -   **Recommended value:** YES (to confirm account creation and provide a good first impression).
    -   **Merchant scenario / example:** You want to ensure new customers feel welcomed and have their account details confirmed, so you enable this.

#### **Display Options**

-   **Display Google Login Button Style (glogin_button_style)**
    -   **What this setting does:** Allows you to choose the visual style of the "Sign in with Google" button. Options typically include different sizes, shapes, or color schemes provided by Google.
    -   **Effect of changing this setting:** Changes the appearance of all Google login buttons across your store.
    -   **Recommended value:** Choose the style that best fits your store's design.
    -   **Merchant scenario / example:** Your theme uses large, rounded buttons. You would select a button style that matches this aesthetic for consistency.

-   **Display Google Login Button in Pop-up (ggl_popuplogin)**
    -   **What this setting does:** If enabled, when a customer clicks a login link, a pop-up window will appear with the Google login option, instead of redirecting them to a full login page.
    -   **Effect of changing this setting:**
        -   *When enabled (YES):* Provides a quicker, less disruptive login experience via a modal pop-up.
        -   *When disabled (NO):* Customers will be redirected to the standard login page.
    -   **Recommended value:** YES (for a modern, seamless user experience).
    -   **Merchant scenario / example:** You want to keep customers on the current page as much as possible, so you enable the pop-up login.

#### **Button Placement (Hook Selection)**

These settings control where the "Sign in with Google" button appears in your store. You can enable or disable the button for various PrestaShop display hooks.

-   **Display in Header (ggl_top)**
    -   **What this setting does:** Controls the visibility of the Google login button in your store's header section.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears in the header (e.g., near "My Account" or "Login").
        -   *Disabled:* Button is hidden from the header.
    -   **Recommended value:** YES (for easy access from any page).

-   **Display in Navigation Bar (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **What these settings do:** Control the visibility of the Google login button in different navigation bar positions, depending on your PrestaShop version and theme. `displayNav` is common for older themes, while `displayNav1` and `displayNav2` are often used in PrestaShop 1.7+ for top-of-page navigation.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears in the selected navigation bar.
        -   *Disabled:* Button is hidden from that navigation bar.
    -   **Recommended value:** Enable one or two that fit your theme best, avoiding redundancy.

-   **Display in Shopping Cart (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **What these settings do:** Control the visibility of the Google login button on the shopping cart page. `ggl_shoppingCart` is typically for the main cart content, while `ggl_shoppingCartExtra` might be for additional blocks or summaries.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears on the shopping cart page, allowing quick login before checkout.
        -   *Disabled:* Button is hidden from the shopping cart page.
    -   **Recommended value:** YES (to encourage quick login and reduce abandonment).

-   **Display in Left Column (ggl_leftcolumn)**
    -   **What this setting does:** Controls the visibility of the Google login button in your store's left sidebar.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears in the left column.
        -   *Disabled:* Button is hidden from the left column.
    -   **Recommended value:** YES (if your theme uses a left column and you want prominent placement).

-   **Display in Right Column (ggl_rightoclumn)**
    -   **What this setting does:** Controls the visibility of the Google login button in your store's right sidebar.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears in the right column.
        -   *Disabled:* Button is hidden from the right column.
    -   **Recommended value:** YES (if your theme uses a right column and you want prominent placement).

-   **Display on Homepage (ggl_home)**
    -   **What this setting does:** Controls the visibility of the Google login button on your store's homepage.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears on the homepage.
        -   *Disabled:* Button is hidden from the homepage.
    -   **Recommended value:** YES (for maximum visibility and quick access for new visitors).

-   **Display After Customer Login Form (ggl_displayCustomerLoginFormAfter)**
    -   **What this setting does:** Controls the visibility of the Google login button directly after the standard PrestaShop customer login form (e.g., on the `/my-account` page).
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears below the traditional login form.
        -   *Disabled:* Button is hidden from this position.
    -   **Recommended value:** YES (this is a primary location for social login buttons).

-   **Display on Create Account Form (ggl_createAccountForm, ggl_createAccountTop)**
    -   **What these settings do:** Control the visibility of the Google login button on the customer account creation page. `ggl_createAccountForm` typically places it within or near the form, while `ggl_createAccountTop` places it at the very top of the account creation page.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears on the account creation page, offering a quick registration alternative.
        -   *Disabled:* Button is hidden from this page.
    -   **Recommended value:** YES (to simplify new customer registration).

-   **Display in Top Column (ggl_topColumn)**
    -   **What this setting does:** Controls the visibility of the Google login button in the `displayTopColumn` hook, often used for banners or content just below the header.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears in the top column.
        -   *Disabled:* Button is hidden from the top column.
    -   **Recommended value:** Consider based on your theme's layout; often less critical than other positions.

-   **Display Personal Information Top (ggl_displayPersonalInformationTop)**
    -   **What this setting does:** Controls the visibility of the Google login button on the "My Personal Information" page, usually when a customer is already logged in. This might be less common for a login button but could be used for account linking.
    -   **Effect of changing this setting:**
        -   *Enabled:* Button appears on the personal information page.
        -   *Disabled:* Button is hidden from this page.
    -   **Recommended value:** NO (typically not a primary login point).

#### **Other Settings (Internal/Legacy)**

-   **mypresta_updates, update_, updatev_**: These are internal settings used by MyPresta.eu for module update checks and version management. You should not modify these.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING**: These are standard PrestaShop configuration variables that the module might reference but typically doesn't allow direct modification through its interface. They reflect your store's core settings.
-   **glogin_identity**: This is likely an internal identifier used by the module. Do not modify.
-   **ggl_**: Any other settings starting with `ggl_` that are not explicitly listed above are likely internal flags or legacy options. It's best to leave them at their default values unless instructed otherwise by support.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Google Client ID | Your Google Client ID | Essential for Google login functionality. |
| Module Configuration | Customer Group for Google Users | Customer | Assigns new Google users to a specific customer group. |
| Module Configuration | Send Welcome Email to New Google Users | YES | Sends a welcome email to new Google sign-ups. |
| Module Configuration | Display Google Login Button Style | (Choose best fit) | Changes the visual appearance of the button. |
| Module Configuration | Display Google Login Button in Pop-up | YES | Enables pop-up login for a smoother UX. |
| Module Configuration | Display in Header (ggl_top) | YES | Shows button in the store's header. |
| Module Configuration | Display in Navigation Bar (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | YES (as needed) | Shows button in various navigation bars. |
| Module Configuration | Display in Shopping Cart (ggl_shoppingCart, ggl_shoppingCartExtra) | YES | Shows button on the shopping cart page. |
| Module Configuration | Display in Left Column (ggl_leftcolumn) | YES (if applicable) | Shows button in the left sidebar. |
| Module Configuration | Display in Right Column (ggl_rightoclumn) | YES (if applicable) | Shows button in the right sidebar. |
| Module Configuration | Display on Homepage (ggl_home) | YES | Shows button on the store's homepage. |
| Module Configuration | Display After Customer Login Form (ggl_displayCustomerLoginFormAfter) | YES | Shows button below the standard login form. |
| Module Configuration | Display on Create Account Form (ggl_createAccountForm, ggl_createAccountTop) | YES | Shows button on the account creation page. |
| Module Configuration | Display in Top Column (ggl_topColumn) | NO (or as needed) | Shows button in the top column hook. |
| Module Configuration | Display Personal Information Top (ggl_displayPersonalInformationTop) | NO | Shows button on the personal information page (less common). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The Google login button appears, but nothing happens when I click it, or I get an error.**
A: This is almost always an issue with your Google Client ID or the Authorized Redirect URIs in your Google Cloud Console.
    *   **Check Client ID:** Double-check that the `Google Client ID` entered in the module configuration is exactly what Google provided, with no extra spaces.
    *   **Check Authorized Redirect URIs:** In your Google Cloud Console, ensure you have added `https://www.yourstore.com/module/glogin/index` (replace `yourstore.com` with your actual domain) to the "Authorized redirect URIs" list. It must be an exact match, including `https://` if your store uses SSL.
    *   **Check Authorized JavaScript origins:** Also ensure your main store URL (e.g., `https://www.yourstore.com`) is listed under "Authorized JavaScript origins".

**Q: New customers are registering with Google, but they aren't receiving a welcome email.**
A: Check the "Send Welcome Email to New Google Users" setting in the module configuration. Ensure it is set to "YES". Also, verify that your PrestaShop store's general email settings are correctly configured and that other transactional emails (like order confirmations) are being sent successfully.

**Q: The Google login button doesn't appear in a specific location (e.g., the header) even though I enabled it.**
A:
    *   **Clear Cache:** First, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear Cache**).
    *   **Module Position:** Go to **Design > Positions** (or **Modules > Positions** in older versions). Search for the `glogin` module. Ensure it is hooked into the `displayHeader`, `displayNav`, or other relevant hooks you've enabled. Sometimes, themes might override default hook behaviors.
    *   **Theme Conflicts:** Your theme might have custom templates that don't explicitly call all standard PrestaShop hooks. If the button doesn't appear after clearing cache and checking module positions, you might need a webmaster to inspect your theme's `.tpl` files.

**Q: Can customers link an existing PrestaShop account to their Google account?**
A: This module primarily facilitates new registrations and logins. If a customer logs in with Google and an account with that email already exists in your PrestaShop store, the module will typically log them into their existing account. It doesn't usually offer a separate "link existing account" feature post-login, but it intelligently matches by email.

**Q: I want to change the text or appearance of the button beyond the module's options.**
A: The module provides standard Google button styles. For advanced customization (e.g., changing text, adding custom icons), you would need custom CSS and potentially JavaScript modifications, which should be handled by a web developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the Google Login Connect module.

### 4.1 Architecture Overview
The `Google Login Connect` module follows a standard PrestaShop module architecture, primarily leveraging front controllers for OAuth 2.0 callback handling and various display hooks for button injection. It relies on PrestaShop's `Configuration` class for settings storage and `Customer` `ObjectModel` for user management. The module integrates with Google's JavaScript API for client-side authentication, which then sends the token to a module front controller for server-side verification and user session creation.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    *   `glogin/controllers/front/index.php`
        *   **Class name & parent class**: `GloginIndexModuleFrontController` extends `ModuleFrontController`
        *   **Responsibility**: This is the primary callback endpoint for Google's OAuth 2.0 flow. After a user authenticates with Google, Google redirects to this controller. It receives the Google ID token, verifies it, extracts user information (email, name), and then either logs in an existing PrestaShop customer or creates a new one. It handles session management and redirects the user back to the store.
    *   `glogin/controllers/front/loginloader.php`
        *   **Class name & parent class**: `GloginLoginloaderModuleFrontController` extends `ModuleFrontController`
        *   **Responsibility**: This controller likely serves a small piece of JavaScript or initializes the Google API client on pages where the login button is displayed. It might be used to dynamically load the Google Platform Library (`platform.js`) or to provide configuration variables (like the `ggl_appid`) to the front-end JavaScript.

-   **Back-Office Admin Controllers**:
    *   None. All configuration is handled via the main module's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
-   No custom `ObjectModel` classes are defined within the `classes/` directory. The module directly interacts with PrestaShop's core `Customer` `ObjectModel` and `Configuration` class.
-   The main module file `glogin/glogin.php` acts as the primary class, extending `Module` and containing all installation, uninstallation, and configuration logic.

### 4.4 JavaScript Assets (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Scope**: Front-office.
    *   **Responsibility**: This script is responsible for initializing the Google Sign-In client library. It likely includes:
        *   Loading the Google Platform Library (`https://apis.google.com/js/platform.js`).
        *   Rendering the "Sign in with Google" button using `gapi.signin2.render()`.
        *   Handling the `onSignIn` callback function, which is triggered after a successful Google login. This callback extracts the ID token and sends it via AJAX to the module's front controller (`index.php`) for server-side processing.
        *   Potentially manages the pop-up login functionality (`ggl_popuplogin`), dynamically displaying the Google button within a modal.
        *   Event listeners for click events on Google login buttons.

### 4.5 CSS Stylesheets (`views/css/`)

-   `glogin/css.css`
    *   **Scope**: Front-office.
    *   **Responsibility**: General styling for the Google login buttons and potentially any custom containers or pop-ups introduced by the module. May contain basic layout adjustments.
-   `glogin/views/css/glogin.css`
    *   **Scope**: Front-office.
    *   **Responsibility**: Similar to `css.css`, likely contains core styling for the Google login buttons, ensuring they are properly aligned and sized within various PrestaShop themes.
-   `glogin/views/css/glogin17-new.css`
    *   **Scope**: Front-office.
    *   **Responsibility**: Specific CSS rules tailored for PrestaShop 1.7+ themes, addressing potential layout differences or styling overrides required for newer versions. This might include Flexbox or Grid adjustments.
-   `glogin/views/css/glogin17.css`
    *   **Scope**: Front-office.
    *   **Responsibility**: Another stylesheet specifically for PrestaShop 1.7.x, potentially containing additional or alternative styles compared to `glogin17-new.css`, depending on the exact theme structure.

### 4.6 Smarty Template Structure (`views/templates/`)

The module leverages numerous templates to inject the Google login button into various PrestaShop hooks. Most of these templates will contain a call to the Google Sign-In button rendering logic (e.g., `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) and potentially some surrounding HTML for styling.

-   **Hook templates (`views/templates/hook/`)**:
    *   `glogin/views/templates/createAccountForm.tpl`: Renders the Google button within the customer account creation form.
    *   `glogin/views/templates/createAccountTop.tpl`: Renders the Google button at the top of the account creation page.
    *   `glogin/views/templates/dashboardZoneOne.tpl`: Renders the Google button in the `dashboardZoneOne` hook (less common for login, possibly for admin dashboard integration or a specific theme).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl`: Renders the Google button directly after the standard customer login form.
    *   `glogin/views/templates/displayNav.tpl`: Renders the Google button in the `displayNav` hook (often top navigation).
    *   `glogin/views/templates/displayNav1.tpl`: Renders the Google button in the `displayNav1` hook (PrestaShop 1.7+ navigation).
    *   `glogin/views/templates/displayNav2.tpl`: Renders the Google button in the `displayNav2` hook (PrestaShop 1.7+ navigation).
    *   `glogin/views/templates/displayPopUpLogin.tpl`: Contains the HTML structure for the pop-up login modal, including the Google button.
    *   `glogin/views/templates/footer.tpl`: Renders the Google button in the `displayFooter` hook.
    *   `glogin/views/templates/glogin.tpl`: A generic template, possibly used as a fallback or for internal rendering logic.
    *   `glogin/views/templates/header.tpl`: Renders the Google button in the `displayHeader` hook.
    *   `glogin/views/templates/home.tpl`: Renders the Google button in the `displayHome` hook.
    *   `glogin/views/templates/leftcolumn.tpl`: Renders the Google button in the `displayLeftColumn` hook.
    *   `glogin/views/templates/rightcolumn.tpl`: Renders the Google button in the `displayRightColumn` hook.
    *   `glogin/views/templates/shoppingCart.tpl`: Renders the Google button in the `displayShoppingCart` hook.
    *   `glogin/views/templates/shoppingCartExtra.tpl`: Renders the Google button in the `displayShoppingCartExtra` hook.
    *   `glogin/views/templates/top.tpl`: Renders the Google button in the `displayTop` hook.
    *   `glogin/views/templates/topColumn.tpl`: Renders the Google button in the `displayTopColumn` hook.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module does not create any custom SQL tables.
    *   Configuration settings are stored in the `ps_configuration` table using keys like `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE`, and various `GGL_DISPLAY[HOOK_NAME]` flags.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section or at the very beginning of the `<body>` | Inject CSS, JS, and potentially the Google button in the header. |
| `displayFooter` | At the end of the `<body>` | Inject the Google button in the footer. |
| `displayHome` | On the homepage content area | Inject the Google button on the homepage. |
| `displayShoppingCart` | On the shopping cart page | Inject the Google button on the cart page. |
| `displayRightColumn` | In the right sidebar | Inject the Google button in the right column. |
| `displayCustomerLoginFormAfter` | After the standard customer login form | Inject the Google button for alternative login. |
| `displayNav` | In the main navigation bar (older themes) | Inject the Google button in the navigation. |
| `displayCreateAccountTop` | At the top of the account creation page | Inject the Google button for quick registration. |
| `displayTop` | In the top section of the page (often above header) | Inject the Google button in the very top section. |
| `displayNav2` | In a secondary navigation bar (PS 1.7+) | Inject the Google button in the navigation. |
| `displayShoppingCartExtra` | Additional content area on the shopping cart page | Inject the Google button on the cart page. |
| `displayTopColumn` | In the content area below the header (often for banners) | Inject the Google button in the top column. |
| `displayNav1` | In a primary navigation bar (PS 1.7+) | Inject the Google button in the navigation. |
| `dashboardZoneOne` | In the first zone of the admin dashboard | Potentially for admin-side information or a specific button. |
| `displayLeftColumn` | In the left sidebar | Inject the Google button in the left column. |

## 5. Official Support & Updates
For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Ensure you are running the latest compatible version of the module for your PrestaShop store.
