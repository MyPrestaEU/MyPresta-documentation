---
title: "PayPal login connect - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the PayPal login connect PrestaShop module by MyPresta.eu."
sidebar:
  label: "PayPal login connect - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy PayPal login connect Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/paypal-login-connect/)
>
> ---


# PayPal login connect

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “PayPal login connect” module to access its settings.

#### **PayPal API Credentials**

These settings connect your store to your PayPal developer account, allowing the module to securely authenticate users.

- **What this setting does:** These fields require your unique Client ID and Client Secret obtained from your PayPal Developer account. These credentials are vital for your store to communicate with PayPal’s login service.
- **Effect of changing this setting:**
  - *When correctly entered:* The “Login with PayPal” button will function, allowing customers to log in.
  - *When incorrect or empty:* The module will not be able to connect to PayPal, and the login feature will fail or not appear.
- **Recommended value:** Enter the exact Client ID and Client Secret provided by PayPal.
- **Merchant scenario / example:** You’ve created a PayPal Developer account and set up a “Login with PayPal” app. PayPal provides you with a Client ID (a long string of characters) and a Client Secret (another long, secure string). You copy and paste these into the respective fields here.

#### **Enable PayPal Login**

This is the master switch for the module’s functionality.

- **What this setting does:** Controls whether the “Login with PayPal” feature is active and visible on your store.
- **Effect of changing this setting:**
  - *When enabled (YES):* The PayPal login buttons will appear in the selected locations, and the functionality will be active.
  - *When disabled (NO):* The PayPal login buttons will be hidden, and customers will not be able to use this feature.
- **Recommended value:** YES
- **Merchant scenario / example:** You’ve finished setting up the module and want to make it live for your customers. You set this to YES. If you need to temporarily disable it for maintenance, you can set it to NO.

#### **Display Button In**

This section allows you to choose where the “Login with PayPal” button will appear in your store.

- **What this setting does:** Determines the specific locations (hooks) where the PayPal login button will be rendered on your front office.
- **Effect of changing this setting:**
  - *When a location is checked:* The PayPal login button will appear in that specific area of your store.
  - *When a location is unchecked:* The button will not be displayed in that area.
- **Recommended value:** Select locations that are most relevant for customer login/registration, such as `displayNav` (top navigation), `displayCustomerLoginFormAfter` (after the standard login form), and `createAccountForm` (on the registration page).
- **Merchant scenario / example:** You want the button to be easily accessible in the header and on the main login page. You would check `displayNav` and `displayCustomerLoginFormAfter`. If your theme has a custom pop-up login, you might also check `displayPopUpLogin`.

#### **Button Style**

Customize the visual appearance of the PayPal login button.

- **What this setting does:** Allows you to select from different pre-defined styles for the “Login with PayPal” button to match your store’s design or PayPal’s branding guidelines.
- **Effect of changing this setting:** Changes the visual look (e.g., color, size, text) of the PayPal login buttons across your store.
- **Recommended value:** Choose a style that best integrates with your store’s design while remaining clearly identifiable as a PayPal button.
- **Merchant scenario / example:** Your store uses a dark theme, so you might choose a white PayPal button with dark text for better contrast. Or you might prefer the standard blue PayPal button for maximum brand recognition.

#### **Redirect URL After Login**

Specify where customers are sent after successfully logging in with PayPal.

- **What this setting does:** Defines the page a customer is redirected to immediately after they successfully authenticate with PayPal and return to your store.
- **Effect of changing this setting:**
  - *When set to “My Account”:* Customers land on their personal account dashboard.
  - *When set to “Homepage”:* Customers are taken back to your store’s main page.
  - *When set to “Previous Page”:* Customers are returned to the page they were on before initiating the login.
- **Recommended value:** “Previous Page” or “My Account” for a seamless experience. “Previous Page” is often preferred during checkout.
- **Merchant scenario / example:** A customer is on a product page and clicks “Login with PayPal.” If “Previous Page” is selected, they will return to that product page. If they were in the checkout process, they would return to the checkout step.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | PayPal Client ID | (Empty) / Your PayPal Client ID | Unique identifier for your PayPal app. **Required for module to work.** |
| Module Configuration | PayPal Client Secret | (Empty) / Your PayPal Client Secret | Secret key for your PayPal app. **Required for module to work.** |
| Module Configuration | Enable PayPal Login | YES | Master switch to activate/deactivate the PayPal login feature. |
| Module Configuration | Display Button In: displayNav | YES | Shows button in the main navigation bar. |
| Module Configuration | Display Button In: displayCustomerLoginFormAfter | YES | Shows button after the standard login form. |
| Module Configuration | Display Button In: createAccountForm | YES | Shows button on the customer registration page. |
| Module Configuration | Display Button In: displayFooter | NO | Shows button in the store footer. |
| Module Configuration | Display Button In: displayHome | NO | Shows button on the homepage. |
| Module Configuration | Display Button In: displayLeftColumn | NO | Shows button in the left column. |
| Module Configuration | Display Button In: displayNav1 | NO | Shows button in an alternative navigation hook (theme dependent). |
| Module Configuration | Display Button In: displayNav2 | NO | Shows button in another alternative navigation hook (theme dependent). |
| Module Configuration | Display Button In: displayPopUpLogin | YES | Shows button in pop-up login forms (if your theme uses them). |
| Module Configuration | Display Button In: displayRightColumn | NO | Shows button in the right column. |
| Module Configuration | Display Button In: displayTop | NO | Shows button in the very top section of the page (theme dependent). |
| Module Configuration | Display Button In: header | NO | Shows button in the HTML `<head>` section (less common for visible buttons). |
| Module Configuration | Display Button In: shoppingCart | NO | Shows button within the shopping cart summary. |
| Module Configuration | Display Button In: shoppingCartExtra | NO | Shows button in extra section of shopping cart (theme dependent). |
| Module Configuration | Button Style | (Default PayPal style) | Visual appearance of the PayPal login button. |
| Module Configuration | Redirect URL After Login | Previous Page | Destination page after successful PayPal login. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The PayPal login button isn’t showing up on my store.**
A:

1. **Check “Enable PayPal Login”:** Ensure this setting is set to YES in the module configuration.
2. **Verify “Display Button In” settings:** Make sure you have selected at least one hook (e.g., `displayNav`, `displayCustomerLoginFormAfter`) where you want the button to appear.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and clear your PrestaShop cache (Smarty cache, filesystem cache). Your browser cache might also need clearing.
4. **Theme Compatibility:** Some highly customized themes might require minor adjustments. If the button still doesn’t appear, contact MyPresta.eu support.

**Q: When I click the PayPal button, nothing happens or I get an error.**
A:

1. **Check API Credentials:** Double-check your PayPal Client ID and Client Secret in the module configuration. Even a single incorrect character will prevent the connection.
2. **PayPal App Configuration:** Ensure your “Login with PayPal” app in your PayPal Developer account is correctly configured, especially the “Return URL” or “Redirect URI” which should point to your store’s authentication page (e.g., `https://yourstore.com/authentication?paypal_login=1`).
3. **PHP Compatibility:** Verify your server’s PHP version is within the supported range (PHP 5.6 - 8.5).

**Q: My customers are redirected to the wrong page after logging in.**
A:

1. **Check “Redirect URL After Login”:** Review this setting in the module configuration. Select the desired option (e.g., “My Account,” “Previous Page”).
2. **Clear Cache:** After changing this setting, clear your PrestaShop and browser cache.

**Q: Can I change the text on the PayPal login button?**
A: The module typically uses standard PayPal branding for the button text and style. Direct modification of the text is usually not an option within the module configuration itself, as it’s designed to adhere to PayPal’s guidelines. If you need custom text, it would require theme-level overrides or module customization (see Developer Guide).

**Q: Does this module work with multi-language stores?**
A: Yes, the module is designed to be compatible with PrestaShop’s multi-language features. The PayPal login interface itself is handled by PayPal, which typically adapts to the user’s browser language. Any module-specific texts (if present) can be translated via **International > Translations** in your PrestaShop back office.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “PayPal login connect” module (`plogin`) is a standard PrestaShop module primarily implemented within its main `index.php` file, which acts as the module’s entry point and configuration handler. It leverages PrestaShop’s hook system to inject the “Login with PayPal” button into various front-office locations. The module handles the OAuth 2.0 flow with PayPal for user authentication, creating a customer account if one doesn’t exist, and logging the user in. It does not introduce custom database tables or complex `ObjectModel` structures, relying on PrestaShop’s native `Customer` and `Configuration` classes.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers in the `controllers/` directory. All front-office logic related to the PayPal callback is handled directly within the `index.php` file (the main module class) via `$_GET` parameters, and back-office configuration is managed through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not contain custom classes or models in a `classes/` directory. All core logic, including API interaction and customer handling, is encapsulated within the main `plogin` class defined in `index.php`.

### 4.4 JavaScript Assets (`views/js/`)

- **`plogin/js/plogin.js`**
  - **Scope:** Front-office.
  - **Purpose:** This script likely handles the client-side interaction for the PayPal login button. This could include:
    - Opening the PayPal authentication window as a pop-up.
    - Handling the redirect after PayPal authentication.
    - Potentially managing AJAX requests for login status or dynamic button rendering.
    - Binding click events to the PayPal login buttons.
    - Ensuring the button’s functionality across different browsers and devices.

### 4.5 CSS Stylesheets (`views/css/`)

- **`plogin/css.css`**

  - **Scope:** Front-office.
  - **Purpose:** This stylesheet likely contains general styling for the PayPal login button and any associated elements. It might define basic layout, padding, margins, and font styles.
  - **Key Selectors:** Developers can inspect this file for class names (e.g., `.paypal-login-button`, `.plogin-container`) to override styles in their theme’s `custom.css` or `theme.css`.
- **`plogin/css/plogin.css`**

  - **Scope:** Front-office.
  - **Purpose:** Similar to `css.css`, this file provides additional or more specific styling for the PayPal login button, potentially including different button styles based on configuration, hover effects, or responsive adjustments.
  - **Key Selectors:** Look for specific button classes (e.g., `.plogin-btn-blue`, `.plogin-btn-white`) to target and customize.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a comprehensive set of Smarty templates to inject the PayPal login button into various PrestaShop hooks.

- **Hook templates (`views/templates/hook/`)**:
  - `plogin/createAccountForm.tpl`: Renders the PayPal button on the customer registration form.
  - `plogin/displayCustomerLoginFormAfter.tpl`: Renders the PayPal button after the standard customer login form.
  - `plogin/displayFooter.tpl`: Renders the PayPal button in the store’s footer.
  - `plogin/displayHome.tpl`: Renders the PayPal button on the homepage.
  - `plogin/displayleftColumn.tpl`: Renders the PayPal button in the left column.
  - `plogin/displayNav.tpl`: Renders the PayPal button in the main navigation bar (common hook for top links).
  - `plogin/displayNav1.tpl`: Renders the PayPal button in an alternative navigation hook (theme-dependent).
  - `plogin/displayNav2.tpl`: Renders the PayPal button in another alternative navigation hook (theme-dependent).
  - `plogin/displayPopUpLogin.tpl`: Renders the PayPal button within a pop-up login form (if used by the theme).
  - `plogin/displayrightColumn.tpl`: Renders the PayPal button in the right column.
  - `plogin/displayTop.tpl`: Renders the PayPal button in the very top section of the page (theme-dependent).
  - `plogin/header.tpl`: This template is likely used to include CSS/JS assets in the `<head>` section when `displayHeader` hook is used, rather than displaying a visible button.
  - `plogin/shoppingCart.tpl`: Renders the PayPal button within the shopping cart summary.
  - `plogin/shoppingCartExtra.tpl`: Renders the PayPal button in an extra section of the shopping cart (theme-dependent).
  - `plogin/top.tpl`: Similar to `displayTop`, for the top section of the page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - Configuration settings (Client ID, Client Secret, enabled status, selected hooks, redirect URL, button style) are stored in PrestaShop’s `ps_configuration` table, typically with keys prefixed by `PLOGIN_` (e.g., `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing / Location | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To include CSS and JavaScript assets globally for the module. |
| `displayNav` | In the main navigation bar, usually at the top of the page. | Displays the PayPal login button in a prominent navigation area. |
| `displayNav1` | Alternative navigation hook (theme-dependent). | Provides flexibility for themes with multiple navigation areas. |
| `displayNav2` | Another alternative navigation hook (theme-dependent). | Provides flexibility for themes with multiple navigation areas. |
| `displayTop` | In the very top section of the page, above the main content. | Displays the PayPal login button in the top bar. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Displays the PayPal login button in the left column. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Displays the PayPal login button in the right column. |
| `displayFooter` | In the store’s footer section. | Displays the PayPal login button in the footer. |
| `displayHome` | On the store’s homepage. | Displays the PayPal login button on the main landing page. |
| `displayCustomerLoginFormAfter` | After the standard login form on the authentication page. | Provides the PayPal login option as an alternative to email/password. |
| `createAccountForm` | On the customer registration page. | Offers PayPal as a quick registration method. |
| `displayPopUpLogin` | Within a pop-up login modal (if implemented by the theme). | Integrates with modern theme login pop-ups. |
| `shoppingCart` | Within the shopping cart summary block. | Offers login/registration during the cart review phase. |
| `shoppingCartExtra` | In an extra section of the shopping cart (theme-dependent). | Provides additional placement flexibility within the cart. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “PayPal login connect” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions regarding module functionality.
