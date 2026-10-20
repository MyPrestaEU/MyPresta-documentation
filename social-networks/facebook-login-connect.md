---
title: "Facebook Login Connect - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Login Connect PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Login Connect Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for communication with Facebook’s API. These are almost always available on any modern web hosting.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you will set up how the Facebook Login button behaves and where it appears.

#### General Settings

- **Facebook Application ID (App ID):**
  - **What this setting does:** This is a unique identifier provided by Facebook for your specific application. It’s crucial for your store to communicate with Facebook’s login system.
  - **Effect of changing this setting:** Without a valid App ID, the Facebook login button will not work, as your store cannot authenticate with Facebook.
  - **Recommended value:** The App ID you obtain from your Facebook Developer account. This field cannot be empty.
  - **Merchant scenario / example:** You must create a Facebook App at [developers.facebook.com](https://developers.facebook.com/) to get this ID. Follow Facebook’s instructions to set up a basic app and enable Facebook Login.
- **Default Customer Group for New Accounts:**
  - **What this setting does:** When a new customer registers using Facebook, they will automatically be assigned to this customer group.
  - **Effect of changing this setting:**
    - *When set to “Customer” (default):* New Facebook users become regular customers, subject to your store’s standard pricing and discounts.
    - *When set to a custom group (e.g., “Wholesale”):* New Facebook users could immediately access special pricing or content if that group has specific rules.
  - **Recommended value:** `Customer` (or your default customer group for new registrations).
  - **Merchant scenario / example:** If you have a “VIP” customer group with special discounts, you might consider assigning new Facebook users to a standard “Customer” group first, then manually upgrading them if they meet VIP criteria.
- **Send Welcome Email to New Customers:**
  - **What this setting does:** Controls whether PrestaShop sends its standard welcome email to customers who register via Facebook.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* New Facebook users receive an email confirming their account creation.
    - *When disabled (No):* No welcome email is sent.
  - **Recommended value:** `Yes`. It’s good practice to welcome new customers and provide them with their login details (even if they use Facebook, they might want to set a password later).
  - **Merchant scenario / example:** Keeping this enabled ensures new customers feel welcomed and have a record of their account, even if they don’t need to remember a password immediately.
- **Enable In-App Browser Login (for mobile apps):**
  - **What this setting does:** This setting is primarily for stores accessed via a dedicated mobile app (not just a mobile browser). It optimizes the Facebook login flow for in-app browsers.
  - **Effect of changing this setting:**
    - *When enabled:* Improves the login experience for users accessing your store through a WebView within a mobile app.
    - *When disabled:* Standard browser login flow is used, which might be less seamless in a dedicated app.
  - **Recommended value:** `No`, unless you have a specific mobile application that embeds your PrestaShop store.
  - **Merchant scenario / example:** If you’ve developed a native iOS or Android app that displays your PrestaShop store content, enabling this might be necessary for a smooth Facebook login experience within that app.
- **Display Facebook Login in Pop-up Window:**
  - **What this setting does:** If your theme uses a pop-up window for login, this option allows the Facebook login button to appear within that pop-up.
  - **Effect of changing this setting:**
    - *When enabled:* The Facebook login button will be available inside your theme’s login pop-up.
    - *When disabled:* The button will only appear on standard login pages or other hook positions.
  - **Recommended value:** `Yes`, if your theme uses a login pop-up.
  - **Merchant scenario / example:** Many modern themes use a quick login pop-up accessible from the header. Enabling this makes the Facebook login option immediately visible there.
- **Facebook Login Button Language:**
  - **What this setting does:** Allows you to specify the language for the Facebook login button and related messages.
  - **Effect of changing this setting:** The button text and any Facebook-generated prompts will appear in the selected language.
  - **Recommended value:** `Default PrestaShop Language` (to match your store’s primary language) or `Auto-detect` if available.
  - **Merchant scenario / example:** If your store operates in multiple languages, you might want to set this to match the current front-office language for a consistent user experience.
- **Allow Facebook to identify users (Advanced):**
  - **What this setting does:** This is an advanced setting related to Facebook’s identity tracking. It allows Facebook to potentially track users across your site for advertising purposes.
  - **Effect of changing this setting:**
    - *When enabled:* May provide more data for Facebook advertising but could have privacy implications depending on local regulations (e.g., GDPR).
    - *When disabled:* Limits Facebook’s ability to track users on your site.
  - **Recommended value:** `No`, unless you have a specific marketing strategy that requires this and have addressed privacy compliance.
  - **Merchant scenario / example:** Consult with your marketing team and legal counsel before enabling this, especially if you operate in regions with strict data privacy laws.

#### Display Options (Where to show the Facebook Login Button)

These settings control in which specific areas (hooks) of your PrestaShop store the Facebook Login button will be displayed. You can enable or disable each hook individually.

- **Display in Top (fbl\_displayTop):**
  - **What this setting does:** Shows the button in the very top section of your store, often near the search bar or logo.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the header.
    - *Disabled:* Button is hidden from the header.
  - **Recommended value:** `Yes`, for high visibility.
- **Display in Top Column (fbl\_displaytopColumn):**
  - **What this setting does:** Shows the button in the main content area, usually above the main product listings or content on the homepage.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the top content area.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `No`, unless you want a very prominent button on the homepage.
- **Display on Homepage (fbl\_displayHome):**
  - **What this setting does:** Shows the button specifically on your store’s homepage.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears on the homepage.
    - *Disabled:* Button is hidden from the homepage.
  - **Recommended value:** `Yes`, to encourage immediate registration.
- **Display in Navigation (fbl\_displayNav):**
  - **What this setting does:** Shows the button within the main navigation bar, often alongside “My Account” or “Contact Us” links.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the navigation.
    - *Disabled:* Button is hidden from the navigation.
  - **Recommended value:** `Yes`, for easy access from any page.
- **Display in Navigation 1 (fbl\_displayNav1):**
  - **What this setting does:** Similar to `displayNav`, but targets a specific navigation hook that some themes use (often for the very top bar).
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the first navigation area.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, if your theme uses this hook and you want the button there.
- **Display in Navigation 2 (fbl\_displayNav2):**
  - **What this setting does:** Similar to `displayNav`, but targets a second navigation hook that some themes use (often for the main navigation bar).
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the second navigation area.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, if your theme uses this hook and you want the button there.
- **Display in Shopping Cart (fbl\_displayShoppingCart):**
  - **What this setting does:** Shows the button on the shopping cart summary page.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears on the cart page, allowing quick login before checkout.
    - *Disabled:* Button is hidden from the cart page.
  - **Recommended value:** `Yes`, to simplify checkout for returning customers.
- **Display After Customer Login Form (fbl\_displayCustomerLoginFormAfter):**
  - **What this setting does:** Shows the button directly below the standard PrestaShop login form.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears as an alternative login method on the login page.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, this is a prime location for alternative login options.
- **Display in Personal Information Top (fbl\_displayPersonalInformationTop):**
  - **What this setting does:** Shows the button at the top of the “Personal Information” section during account creation or editing.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears on the personal information page.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, to offer Facebook login as an alternative to filling out the form.
- **Display in Shopping Cart Extra (fbl\_displayShoppingCartExtra):**
  - **What this setting does:** Shows the button in an additional area on the shopping cart page, often used for extra modules or information.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the extra cart area.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `No`, unless your theme specifically uses this hook for login options.
- **Display in Left Column (fbl\_displayLeftColumn):**
  - **What this setting does:** Shows the button in the left sidebar of your store (if your theme has one).
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the left column.
    - *Disabled:* Button is hidden from the left column.
  - **Recommended value:** `No`, unless you want it prominently displayed in the sidebar.
- **Display in Right Column (fbl\_displayRightColumn):**
  - **What this setting does:** Shows the button in the right sidebar of your store (if your theme has one).
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the right column.
    - *Disabled:* Button is hidden from the right column.
  - **Recommended value:** `No`, unless you want it prominently displayed in the sidebar.
- **Display in Create Account Form (fbl\_displayCreateAccountForm):**
  - **What this setting does:** Shows the button directly within the standard PrestaShop account creation form.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears as an alternative registration method on the account creation page.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, this is a crucial location to simplify registration.
- **Display in Create Account Top (fbl\_displayCreateAccountTop):**
  - **What this setting does:** Shows the button at the very top of the account creation page, above the form fields.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears at the top of the account creation page.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `Yes`, for maximum visibility on the registration page.
- **Display in Footer (fbl\_displayFooter):**
  - **What this setting does:** Shows the button in the footer section of your store.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the footer.
    - *Disabled:* Button is hidden from the footer.
  - **Recommended value:** `No`, generally not a primary location for login buttons.
- **Display in Header (fbl\_displayHeader):**
  - **What this setting does:** Shows the button in the header section of your store. This is a very common and effective placement.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in the header.
    - *Disabled:* Button is hidden from the header.
  - **Recommended value:** `Yes`, for high visibility across all pages.
- **Display in Dashboard Zone One (fbl\_displayDashboardZoneOne):**
  - **What this setting does:** This hook is typically for displaying content on the customer’s account dashboard.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears on the customer’s dashboard.
    - *Disabled:* Button is hidden from this area.
  - **Recommended value:** `No`, as customers are already logged in when they see their dashboard.
- **Display in Pop-up Login (fbl\_popuplogin):**
  - **What this setting does:** Specifically targets themes that use a pop-up modal for login.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears within the login pop-up.
    - *Disabled:* Button is hidden from the login pop-up.
  - **Recommended value:** `Yes`, if your theme uses a login pop-up.
- **Display Facebook Login (fbl\_fblogin):**
  - **What this setting does:** This is a generic hook for the Facebook login button. It might be used by the module internally or by themes for custom placement.
  - **Effect of changing this setting:**
    - *Enabled:* Button appears in this generic hook.
    - *Disabled:* Button is hidden from this hook.
  - **Recommended value:** `Yes`, if other specific hooks don’t work or if you want a fallback.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook Application ID (App ID) | *Your Facebook App ID* | Essential for connecting to Facebook; button won’t work without it. |
| Module Configuration | Default Customer Group for New Accounts | Customer | Assigns new Facebook users to a specific customer group. |
| Module Configuration | Send Welcome Email to New Customers | Yes | Determines if new Facebook registrations receive a welcome email. |
| Module Configuration | Enable In-App Browser Login | No | Optimizes login for dedicated mobile apps (not mobile browsers). |
| Module Configuration | Display Facebook Login in Pop-up Window | Yes (if theme uses pop-up) | Shows button in theme’s login pop-up. |
| Module Configuration | Facebook Login Button Language | Default PrestaShop Language | Sets the language for the Facebook button and prompts. |
| Module Configuration | Allow Facebook to identify users | No | Advanced tracking option; consult legal/marketing. |
| Module Configuration | Display in Top (fbl\_displayTop) | Yes | Shows button in the header. |
| Module Configuration | Display in Top Column (fbl\_displaytopColumn) | No | Shows button in the main content area, usually above listings. |
| Module Configuration | Display on Homepage (fbl\_displayHome) | Yes | Shows button specifically on the homepage. |
| Module Configuration | Display in Navigation (fbl\_displayNav) | Yes | Shows button in the main navigation bar. |
| Module Configuration | Display in Navigation 1 (fbl\_displayNav1) | Yes (if theme uses) | Shows button in a specific top navigation area. |
| Module Configuration | Display in Navigation 2 (fbl\_displayNav2) | Yes (if theme uses) | Shows button in a specific main navigation area. |
| Module Configuration | Display in Shopping Cart (fbl\_displayShoppingCart) | Yes | Shows button on the shopping cart summary page. |
| Module Configuration | Display After Customer Login Form | Yes | Shows button below the standard login form. |
| Module Configuration | Display in Personal Information Top | Yes | Shows button at the top of the personal information page. |
| Module Configuration | Display in Shopping Cart Extra | No | Shows button in an additional cart area. |
| Module Configuration | Display in Left Column (fbl\_displayLeftColumn) | No | Shows button in the left sidebar. |
| Module Configuration | Display in Right Column (fbl\_displayRightColumn) | No | Shows button in the right sidebar. |
| Module Configuration | Display in Create Account Form | Yes | Shows button within the account creation form. |
| Module Configuration | Display in Create Account Top | Yes | Shows button at the top of the account creation page. |
| Module Configuration | Display in Footer (fbl\_displayFooter) | No | Shows button in the footer. |
| Module Configuration | Display in Header (fbl\_displayHeader) | Yes | Shows button in the header section. |
| Module Configuration | Display in Dashboard Zone One | No | Shows button on the customer’s account dashboard. |
| Module Configuration | Display in Pop-up Login (fbl\_popuplogin) | Yes (if theme uses pop-up) | Shows button within the login pop-up modal. |
| Module Configuration | Display Facebook Login (fbl\_fblogin) | Yes | Generic hook for Facebook login button. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook login button appears, but nothing happens when I click it, or it shows an error.**
A1: This almost always indicates an issue with your Facebook App ID or the Facebook App configuration itself.
- **Check your Facebook App ID:** Go to your module configuration in PrestaShop and verify that the “Facebook Application ID” is correctly entered.
- **Check your Facebook App settings:** Log in to [developers.facebook.com](https://developers.facebook.com/).
- Ensure your app is “Live” (not in Development Mode).
- Go to “Facebook Login” > “Settings” and make sure “Client OAuth Login” and “Web OAuth Login” are enabled.
- Under “Valid OAuth Redirect URIs”, you *must* add your store’s full domain (e.g., `https://www.yourstore.com/`). Sometimes, you might also need to add `https://www.yourstore.com/module/fblogin/index` or `https://www.yourstore.com/module/fblogin/loginloader` depending on your PrestaShop version and URL structure.
- Ensure your “Privacy Policy URL” and “Terms of Service URL” are set in your Facebook App’s “Basic Settings”.
- **Clear Cache:** After making any changes, clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).

**Q2: New customers register via Facebook, but their names or emails aren’t appearing correctly.**
A2: The module pulls public profile information from Facebook.
- Ensure the customer has granted permission for your app to access their basic profile and email.
- Facebook’s API provides the first name, last name, and email. If these are missing or incorrect, it’s usually an issue on the customer’s Facebook profile privacy settings or a rare API glitch.
- The module creates a new account if no matching email is found. If an email already exists in your PrestaShop database, the module should attempt to log the user into that existing account.

**Q3: The Facebook button doesn’t appear in the location I expect, even after enabling the hook.**
A3:
- **Clear Cache:** Always clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) after changing hook settings.
- **Theme Compatibility:** Some custom themes might override standard PrestaShop hooks or have unique structures. If the button doesn’t appear, your theme might not be actively displaying that specific hook. You may need to consult your theme developer or a webmaster to integrate it manually into your theme’s `.tpl` files.
- **Check Module Positions:** Go to Design > Positions (or Modules > Positions in older versions) and search for `fblogin`. Ensure the module is “hooked” to the desired positions. If it’s not, you can manually “Transplant a module” to the correct hook.

**Q4: Can customers who registered with Facebook set a password later to log in directly?**
A4: Yes. Once an account is created via Facebook, it’s a standard PrestaShop customer account.
- Customers can use the “Forgot Password” link on your store’s login page. They will receive an email to set a new password, allowing them to log in directly with their email and the new password, even without Facebook.

**Q5: Does this module support multiple languages for the button?**
A5: Yes, the module has a setting for “Facebook Login Button Language”. You can set it to match your store’s default language, or in some cases, Facebook’s SDK might auto-detect the user’s browser language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Facebook Login Connect` module integrates Facebook’s JavaScript SDK to facilitate user authentication. It primarily operates by hooking into various front-office display points to render the Facebook login button. Upon a successful Facebook login, a front controller handles the callback, retrieves user data from Facebook, and either logs in an existing PrestaShop customer or creates a new one. The module leverages PrestaShop’s `Module` class for configuration and hook management, with minimal custom classes, relying heavily on the main `fblogin.php` file for core logic.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - **Class Name:** `FbloginIndexModuleFrontController`
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller acts as the primary callback endpoint for Facebook’s authentication process. After a user successfully logs in via Facebook, Facebook redirects to this controller. It handles the retrieval of the Facebook access token, fetches user profile data (name, email), and then either logs in an existing PrestaShop customer or creates a new one. It then redirects the user to their account page or the homepage.
  - `controllers/front/loginloader.php`
    - **Class Name:** `FbloginLoginloaderModuleFrontController`
    - **Parent Class:** `ModuleFrontController`
    - **Responsibility:** This controller is likely a fallback or an alternative entry point for the Facebook login process, potentially used for specific scenarios or older PrestaShop versions. It would perform similar authentication and user management tasks as `index.php`.
- **Back-Office Admin Controllers**:

  - None. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom `ObjectModel` classes or other core business logic classes in the `classes/` directory. All core logic is encapsulated within the `Fblogin` class in `fblogin.php`.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/fblogin4.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script is responsible for initializing the Facebook JavaScript SDK. It loads the SDK, sets up the `FB.init` configuration (including the App ID and desired permissions), and handles the `FB.login` call when the Facebook login button is clicked. It likely listens for the `auth.statusChange` event to detect login/logout states and redirects the user to the appropriate PrestaShop front controller (`index.php` or `loginloader.php`) upon successful authentication. It also manages the display of the Facebook login button and its interaction.

### 4.5 CSS Stylesheets (`views/css/`)

- `css.css`
  - **Scope:** Front-office.
  - **Responsibility:** This is likely a generic stylesheet for the module, providing basic styling for the Facebook login button and any related UI elements.
- `views/css/fblogin.css`
  - **Scope:** Front-office.
  - **Responsibility:** Provides specific styling rules for the Facebook login button and its container, ensuring consistent appearance across different themes. It might include styles for button size, color, hover effects, and alignment.
- `views/css/fblogin17.css`
  - **Scope:** Front-office.
  - **Responsibility:** This stylesheet likely contains specific overrides or additional styles tailored for PrestaShop 1.7.x and newer versions, addressing potential layout or styling differences in newer theme structures.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `createAccountForm.tpl`: Renders the Facebook login button within the standard account creation form.
  - `createAccountTop.tpl`: Renders the Facebook login button at the top of the account creation page.
  - `dashboardZoneOne.tpl`: Renders the Facebook login button in the customer dashboard’s zone one (less common for login, but available).
  - `displayCustomerLoginFormAfter.tpl`: Renders the Facebook login button directly after the standard customer login form.
  - `displayNav.tpl`: Renders the Facebook login button in the main navigation bar.
  - `displayPersonalInformationTop.tpl`: Renders the Facebook login button at the top of the personal information page.
  - `displayPopUpLogin.tpl`: Renders the Facebook login button within a theme’s pop-up login modal.
  - `fblogin.tpl`: A generic template for the Facebook login button, potentially used by `displayfblogin` or as a fallback.
  - `footer.tpl`: Renders the Facebook login button in the store’s footer.
  - `header.tpl`: Renders the Facebook login button in the store’s header.
  - `home.tpl`: Renders the Facebook login button on the homepage.
  - `leftcolumn.tpl`: Renders the Facebook login button in the left sidebar.
  - `rightcolumn.tpl`: Renders the Facebook login button in the right sidebar.
  - `shoppingCart.tpl`: Renders the Facebook login button on the shopping cart page.
  - `shoppingCartExtra.tpl`: Renders the Facebook login button in an extra area of the shopping cart page.
  - `top.tpl`: Renders the Facebook login button in the very top section of the store.
  - `topColumn.tpl`: Renders the Facebook login button in the main content area, typically above product listings.
- **Admin templates (`views/templates/admin/`)**:

  - None. The module configuration is rendered directly via `getContent()` in `fblogin.php` using standard PrestaShop form helpers.
- **Front-office templates (`views/templates/front/`)**:

  - None. All front-office display is handled via hook templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table using keys like `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayRightColumn` | Renders content in the right sidebar. | Displays Facebook login button in the right column. |
| `displaypopuplogin` | Renders content within a theme’s login pop-up. | Displays Facebook login button in the login pop-up. |
| `displayCreateAccountForm` | Renders content within the customer account creation form. | Displays Facebook login button as an alternative registration method. |
| `displayPersonalInformationTop` | Renders content at the top of the personal information page. | Displays Facebook login button for quick registration/login. |
| `displayTop` | Renders content in the very top section of the store. | Displays Facebook login button in the header’s top bar. |
| `displayCreateAccountTop` | Renders content at the top of the account creation page. | Displays Facebook login button above the registration form. |
| `displayHeader` | Renders content in the `<head>` section of the HTML and potentially visible header elements. | Injects Facebook SDK JavaScript and displays the login button in the header. |
| `displayNav` | Renders content in the main navigation bar. | Displays Facebook login button in the navigation. |
| `displayDashboardZoneOne` | Renders content in the first zone of the customer dashboard. | Displays Facebook login button (less common for logged-in users). |
| `displayNav2` | Renders content in a secondary navigation bar (theme-dependent). | Displays Facebook login button in the secondary navigation. |
| `displayShoppingCart` | Renders content on the shopping cart summary page. | Displays Facebook login button for quick login before checkout. |
| `displayTopColumn` | Renders content in the main content area, typically above listings. | Displays Facebook login button in the top content column. |
| `displayFooter` | Renders content in the store’s footer. | Displays Facebook login button in the footer. |
| `displayfblogin` | A custom hook defined by the module itself. | Provides a flexible point for themes to integrate the Facebook login button. |
| `displayHome` | Renders content on the store’s homepage. | Displays Facebook login button on the homepage. |
| `displayLeftColumn` | Renders content in the left sidebar. | Displays Facebook login button in the left column. |
| `displayCustomerLoginFormAfter` | Renders content directly after the standard customer login form. | Displays Facebook login button as an alternative login method. |
| `displayShoppingCartExtra` | Renders content in an extra area of the shopping cart page. | Displays Facebook login button in an additional cart area. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Facebook Login Connect” module.
