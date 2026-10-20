---
title: "Account activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Account activation by email link Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/account-activation-by-email-link/)
>
> ---


# Account activation by email link

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Account activation by email link” module. You can access it by navigating to **Modules > Module Manager** and clicking “Configure” next to the module name.

#### **General Settings**

- **Send email with account activation link to admin:**

  - **What this setting does:** Controls whether an email notification is also sent to the store administrator (you) every time a new customer registers and needs to activate their account.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* You will receive an email notification to your store’s primary contact email address (usually `PS_SHOP_EMAIL`) whenever a new customer registers and is awaiting activation. This can be useful for monitoring new registrations.
    - *When disabled (“Off”):* No email notification will be sent to the administrator upon new customer registration.
  - **Recommended value:** “Off” for most stores to avoid email clutter, unless you specifically need to monitor every new registration.
  - **Merchant scenario / example:** If you run a small, niche store and want to personally welcome or review every new customer, enabling this can keep you informed. For larger stores, it’s usually unnecessary.
- **Title of email to admin:**

  - **What this setting does:** Defines the subject line of the email sent to the administrator when a new account is registered (if “Send email with account activation link to admin” is enabled).
  - **Effect of changing this setting:** Changes the subject line of the admin notification email.
  - **Recommended value:** “New customer registration awaiting activation - {shop\_name}” (or similar, using `{shop_name}` for your store’s name).
  - **Merchant scenario / example:** You might want to include your store’s name in the title for easy identification in your inbox, e.g., “New Customer at My Awesome Store - Activation Pending.”
- **Auto log-in customer after activation:**

  - **What this setting does:** Determines whether a customer is automatically logged into their account immediately after they click the activation link in their email.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* After clicking the activation link, the customer is seamlessly logged into their newly activated account and typically redirected to their account dashboard or the homepage. This provides a smoother user experience.
    - *When disabled (“Off”):* After clicking the activation link, the customer’s account is activated, but they are *not* automatically logged in. They will be redirected to the login page and prompted to enter their credentials manually.
  - **Recommended value:** “On” for a better customer experience, reducing friction.
  - **Merchant scenario / example:** Enabling this makes the activation process feel more complete and user-friendly, as the customer doesn’t have an extra step to take after verifying their email.
- **Activate account on specific page:**

  - **What this setting does:** Allows you to define a specific page on your store where the customer will be redirected *after* their account is successfully activated.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The module will use the URL specified in the “Specific activation page link” field for redirection after activation.
    - *When disabled (“Off”):* The customer will be redirected to the default page (usually the homepage or their customer account page) after activation.
  - **Recommended value:** “Off” by default, unless you have a specific marketing or onboarding strategy.
  - **Merchant scenario / example:** You might want to redirect new customers to a “Welcome” page with special offers, a guide to your store, or a specific product category to encourage their first purchase.
- **Specific activation page link:**

  - **What this setting does:** This field appears only if “Activate account on specific page” is enabled. It’s where you enter the full URL of the page you want to redirect customers to after activation.
  - **Effect of changing this setting:** Defines the exact destination URL for post-activation redirection.
  - **Recommended value:** Leave empty if “Activate account on specific page” is “Off”. If enabled, provide a full, valid URL (e.g., `https://yourstore.com/content/1-delivery`).
  - **Merchant scenario / example:** If you have a “New Customer Welcome” page at `https://yourstore.com/welcome-new-customers`, you would enter that URL here.

#### **Email Content Settings**

- **Title of email to customer:**
  - **What this setting does:** Defines the subject line of the activation email sent to the customer.
  - **Effect of changing this setting:** Changes the subject line customers see in their inbox for the activation email.
  - **Recommended value:** “Activate your account at {shop\_name}” or “Please verify your email for {shop\_name}” (using `{shop_name}` for your store’s name).
  - **Merchant scenario / example:** A clear and concise subject line helps customers identify the email and encourages them to open it, reducing the chance of it being marked as spam.

#### **Other Settings (Internal / Technical)**

- **mypresta\_updates, update\_, updatev\_:** These are internal settings used by MyPresta.eu modules for update checks and version management. You should generally **not** modify these.
- **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** These are standard PrestaShop configuration values that the module might read or display for context but are not directly configurable within the module itself. They reflect your general PrestaShop settings.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Send email with account activation link to admin | Off | Controls admin notification for new registrations. |
| Module Configuration | Title of email to admin | “New customer registration awaiting activation - {shop\_name}” | Subject line for admin notification email. |
| Module Configuration | Auto log-in customer after activation | On | Automatically logs customer in after successful activation. |
| Module Configuration | Activate account on specific page | Off | Enables redirection to a custom page after activation. |
| Module Configuration | Specific activation page link | (Empty if disabled) | URL for post-activation redirection (if enabled). |
| Module Configuration | Title of email to customer | “Activate your account at {shop\_name}” | Subject line for customer activation email. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving the activation email. What should I do?**

- **A:**
  1. **Check Spam/Junk Folders:** Advise customers to check their spam or junk mail folders.
  2. **Verify Store Email Settings:** Go to **Shop Parameters > Contact > Stores** (or **Advanced Parameters > E-mail** in older versions) in your PrestaShop Back Office. Ensure your store’s email configuration is correct and that emails are being sent successfully (test by sending a test email).
  3. **Server Mail Functionality:** Contact your hosting provider to ensure your server’s mail function (PHP `mail()` or SMTP) is working correctly and not being blocked.
  4. **Module Configuration:** Double-check the “Title of email to customer” in the module settings. A very generic or suspicious-looking title might trigger spam filters.
  5. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes caching issues can prevent emails from being sent.

**Q2: A customer activated their account but still can’t log in.**

- **A:**
  1. **Check Customer Status:** In your PrestaShop Back Office, go to **Customers > Customers**. Find the customer’s account and verify that their “Enabled” status is set to “Yes.” If not, manually enable it.
  2. **Password Reset:** Suggest the customer try the “Forgot password” link on your login page. This can resolve issues if they are misremembering their password.
  3. **Browser Cache/Cookies:** Ask the customer to clear their browser’s cache and cookies, or try logging in from a different browser or incognito window.
  4. **Module Conflict:** Temporarily disable other modules that interact with customer accounts or login processes to rule out conflicts.

**Q3: How can I manually activate a customer’s account if they can’t receive the email?**

- **A:** You can manually activate a customer’s account from the PrestaShop Back Office:
  1. Go to **Customers > Customers**.
  2. Find the customer’s name in the list and click “Edit” (the pencil icon).
  3. On the customer’s details page, locate the “Enabled” switch and set it to “Yes.”
  4. Click “Save.” The customer will now be able to log in.

**Q4: The activation link redirects to the wrong page or shows an error.**

- **A:**
  1. **“Specific activation page link” Check:** If you have “Activate account on specific page” enabled, verify that the URL entered in “Specific activation page link” is absolutely correct and accessible. A typo or an invalid URL will cause redirection issues.
  2. **Friendly URLs:** Ensure your Friendly URLs are enabled and working correctly (**Shop Parameters > Traffic & SEO**).
  3. **Clear Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**).
  4. **Check .htaccess:** If you’ve made any manual changes to your `.htaccess` file, revert them or ensure they are not interfering with URL rewriting.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Account activation by email link” module (`acactiv`) is a standard PrestaShop module primarily designed to intercept the customer registration process. It leverages PrestaShop’s hook system to modify default behavior, specifically `actionCustomerAccountAdd` to mark new accounts as inactive and send activation emails, and `displayHeader` to inject necessary JavaScript. The module does not introduce new database tables or complex `ObjectModel` structures, instead relying on modifying existing `Customer` object properties and using `ps_configuration` for its settings.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers. All logic is handled within the main module file (`acactiv.php`) and its registered hooks. The activation link itself points to the module’s main dispatch, which then handles the activation logic.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in the `classes/` directory. It directly interacts with PrestaShop’s core `Customer` class and `Configuration` class.

### 4.4 JavaScript Assets (`views/js/`)

- **`acactiv/views/acactiv-compat.js`**

  - **Scope:** Front-office.
  - **Purpose:** This script likely contains compatibility fixes or polyfills for older PrestaShop versions or browsers, ensuring the module’s front-end functionality works across a wider range of environments. It might address differences in jQuery versions or DOM manipulation methods.
  - **Event Listeners/DOM Manipulation:** Specifics would require code review, but typically involves ensuring elements are present or adjusting behaviors based on PrestaShop version.
- **`acactiv/views/acactiv.js`**

  - **Scope:** Front-office.
  - **Purpose:** This is the main JavaScript file for front-office interactions. It’s responsible for displaying messages to the user after registration (e.g., “Check your email for activation link”) and potentially handling client-side aspects of the activation process.
  - **Event Listeners/DOM Manipulation:**
    - May listen for form submissions on the registration page to display custom messages.
    - Could manipulate the DOM to show/hide elements, display pop-up notifications, or redirect the user after certain actions.
    - Might use `prestashop.on('updatedProduct', function(event) { ... });` or similar PrestaShop event listeners if it needs to react to dynamic content updates, though less likely for this module’s core function.

### 4.5 CSS Stylesheets (`views/css/`)

- **`acactiv/views/acactiv.css`**
  - **Scope:** Front-office customer styling.
  - **Purpose:** Provides basic styling for any custom messages or elements introduced by the module on the front office. This could include styling for the “account pending activation” message or the “account activated” confirmation.
  - **Key CSS Class Selectors:** Developers should inspect the module’s output HTML to identify specific classes (e.g., `.acactiv-message`, `.acactiv-success`, `.acactiv-error`) that can be overridden in their theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - **`acactiv/views/checkout_notice.tpl`**
    - **Hook:** Not explicitly stated as a hook template, but its name suggests it might be rendered in a context related to checkout or account creation, possibly via `displayCustomerAccountForm` or similar, to show a notice about activation.
    - **Output:** Likely outputs an informational message to the customer after registration, instructing them to check their email for the activation link.
  - **`acactiv/views/displayHeader.tpl`**
    - **Hook:** `displayHeader`
    - **Output:** This template is typically used to include CSS and JavaScript files in the `<head>` section of the front-office pages. It will contain `<link>` tags for `acactiv.css` and `<script>` tags for `acactiv-compat.js` and `acactiv.js`, ensuring these assets are loaded on relevant pages.
- **Admin templates (`views/templates/admin/`)**: None identified. Configuration is handled directly in `getContent()` within `acactiv.php`.
- **Front-office templates (`views/templates/front/`)**: None identified as dedicated standalone pages.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - It modifies the `active` column of the `ps_customer` table (setting it to `0` for new registrations until activated).
  - Configuration settings are stored in the `ps_configuration` table with keys like `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE`.
- **Registered Hooks Table**:
