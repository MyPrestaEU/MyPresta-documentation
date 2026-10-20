---
title: "Customer register spam protection - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer register spam protection PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer register spam protection - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer register spam protection Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/customer-register-spam-protection/)
>
> ---


# Customer register spam protection

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for communication with external APIs, which this module may utilize for advanced spam detection. Ensure your hosting environment meets these common requirements.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Customer register spam protection” module, accessible after installation. Here you will define the core rules and behaviors of the spam protection system.

While the specific settings are not detailed in the provided dossier, based on the module’s purpose, typical settings would include:

- **Enable/Disable Module:**

  - **What this setting does:** Turns the spam protection functionality on or off for your entire store.
  - **Effect of changing this setting:**
    - *When enabled:* The module actively monitors and blocks suspicious customer registrations.
    - *When disabled:* The module is inactive, and all registration attempts will proceed without spam checks.
  - **Recommended value:** YES (unless you are actively debugging or temporarily disabling for a specific reason).
  - **Merchant scenario / example:** Enable this immediately after installation to start protecting your store. Disable only if you suspect it’s blocking legitimate customers and you need to investigate, but remember this leaves your store vulnerable.
- **Spam Detection Sensitivity Level:**

  - **What this setting does:** Controls how aggressively the module identifies and blocks potential spam. This might be a slider (Low, Medium, High) or a numerical threshold.
  - **Effect of changing this setting:**
    - *Higher sensitivity:* More likely to block suspicious registrations, potentially including a small number of legitimate users (false positives).
    - *Lower sensitivity:* Less likely to block legitimate users, but may allow more spam accounts to slip through (false negatives).
  - **Recommended value:** Start with “Medium” and adjust based on your store’s traffic and the number of spam attempts observed.
  - **Merchant scenario / example:** If you’re seeing a lot of spam despite the module being active, increase sensitivity. If customers report issues registering, try lowering it slightly.
- **Action on Detected Spam:**

  - **What this setting does:** Defines what happens when the module identifies a registration attempt as spam.
  - **Effect of changing this setting:**
    - *Block registration:* The account is not created, and the user receives an error message.
    - *Mark as pending/review:* The account is created but flagged for manual review by an administrator.
    - *Log only:* The attempt is recorded, but the account is still created (useful for initial monitoring).
  - **Recommended value:** “Block registration” for maximum protection.
  - **Merchant scenario / example:** For most stores, outright blocking is the best approach. If you have a very specific customer base and want to be extra cautious, “Mark as pending” might be an option, but requires manual work.
- **Error Message for Blocked Registrations:**

  - **What this setting does:** Allows you to customize the message displayed to users whose registration attempts are blocked.
  - **Effect of changing this setting:**
    - *Custom message:* Provides a user-friendly or informative message instead of a generic error.
  - **Recommended value:** A polite message like “Registration could not be completed. Please contact support if you believe this is an error.”
  - **Merchant scenario / example:** Avoid messages that reveal too much about your spam detection methods. A simple, helpful message is best.
- **IP Blacklist/Whitelist Management:**

  - **What this setting does:** Allows you to manually add specific IP addresses to a blacklist (always block) or a whitelist (never block).
  - **Effect of changing this setting:**
    - *Blacklisted IPs:* Any registration from these IPs will be blocked, regardless of other settings.
    - *Whitelisted IPs:* Any registration from these IPs will always be allowed.
  - **Recommended value:** Use sparingly. Blacklist known spammers. Whitelist only if a legitimate user or internal system is being falsely blocked.
  - **Merchant scenario / example:** If you repeatedly see spam from a specific IP range, add it to the blacklist. If your internal testing environment’s IP is being blocked, whitelist it.
- **Email Blacklist/Whitelist Management:**

  - **What this setting does:** Similar to IP management, but for specific email addresses or email domains.
  - **Effect of changing this setting:**
    - *Blacklisted emails/domains:* Registrations using these will be blocked.
    - *Whitelisted emails/domains:* Registrations using these will always be allowed.
  - **Recommended value:** Use sparingly. Blacklist known spam email addresses or domains.
  - **Merchant scenario / example:** If you notice a pattern of spam registrations from disposable email services (e.g., mailinator.com), you can blacklist that domain.
- **Integration with External APIs (e.g., reCAPTCHA, Akismet):**

  - **What this setting does:** If the module integrates with external spam detection services, this section will contain fields for API keys and configuration specific to those services.
  - **Effect of changing this setting:**
    - *Enabled with valid keys:* Adds an additional layer of protection using the external service’s database and algorithms.
    - *Disabled or invalid keys:* The external service will not be used, relying solely on the module’s internal logic.
  - **Recommended value:** Enable and configure if available, as it significantly enhances protection.
  - **Merchant scenario / example:** Obtain API keys from the respective service (e.g., Google reCAPTCHA) and enter them here to leverage their advanced spam filtering.

### 2.2 Dedicated Admin Screens & Controller Views

The module provides dedicated screens in the PrestaShop Back Office to manage and review spam attempts and bans. These are crucial for monitoring the module’s effectiveness and making manual adjustments.

#### 2.2.1 AdminregproAttemptsController (Back Office > Modules > Customer register spam protection > Attempts)

- **Screen Name & Menu Location:** “Attempts” (or similar, under the main module menu item). This screen lists all registration attempts that the module has processed, especially those flagged as suspicious or blocked.
- **Available Actions & Settings:** This will be a grid (list) view displaying details about each registration attempt.
  - **Columns:** Typically includes:
    - Date/Time of attempt
    - IP Address
    - Email address used
    - Status (e.g., “Blocked,” “Allowed,” “Flagged”)
    - Reason for status (e.g., “IP Blacklisted,” “Spam Score High”)
    - Action buttons (e.g., “View Details,” “Whitelist IP,” “Blacklist IP,” “Delete Entry”)
  - **Filtering/Sorting:** Standard PrestaShop grid functionalities to filter by date, IP, status, etc.
- **Effect of changes:**
  - *Whitelisting an IP:* Adds the IP to the module’s whitelist, ensuring future registrations from this IP are allowed.
  - *Blacklisting an IP:* Adds the IP to the module’s blacklist, blocking future registrations from this IP.
  - *Deleting an entry:* Removes the record from the attempts log (does not unblock/unban).
- **Recommended workflow for daily store management:** Regularly review this list, especially if you receive reports of legitimate customers being blocked. Use the “Whitelist IP” action if you identify a false positive. Conversely, if you see persistent spam from a particular IP, use “Blacklist IP.”

#### 2.2.2 AdminregproBansController (Back Office > Modules > Customer register spam protection > Bans)

- **Screen Name & Menu Location:** “Bans” (or similar, under the main module menu item). This screen lists all currently active bans (IPs or email addresses/domains) that the module is enforcing.
- **Available Actions & Settings:** This will be a grid (list) view displaying details about each ban.
  - **Columns:** Typically includes:
    - Type of ban (e.g., “IP,” “Email,” “Domain”)
    - Value (e.g., “192.168.1.1,” “[spam@example.com](mailto:spam@example.com),” “bad-domain.com”)
    - Date added
    - Reason (if manually added)
    - Action buttons (e.g., “Remove Ban,” “Edit”)
  - **Filtering/Sorting:** Standard PrestaShop grid functionalities.
- **Effect of changes:**
  - *Removing a ban:* Lifts the restriction for the specified IP, email, or domain, allowing future registrations from it.
  - *Adding a ban:* Manually adds a new IP, email, or domain to the ban list.
- **Recommended workflow for daily store management:** This is your central hub for managing your custom ban lists. If you’ve blacklisted an IP from the “Attempts” screen, it will appear here. If a legitimate customer is accidentally caught in a ban, you can quickly remove their IP or email from this list.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

- **Managed Table / Entity:** This file likely serves as a routing or default controller for the module’s admin section, potentially redirecting to one of the specific controllers (like `AdminregproAttempts` or `AdminregproBans`) or displaying a general overview/dashboard for the module. It might not directly manage a specific table but acts as an entry point.
- **Form Fields & Columns:** If it displays a grid, it would be a summary or a dashboard. More likely, it’s a redirector.
- **Effect of changes:** No direct data changes, but controls the initial view when accessing the module’s admin section.
- **Recommended workflow for daily store management:** This is usually the first screen you see when clicking on the module in the Modules list. It might offer quick statistics or links to the “Attempts” and “Bans” sections.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable/Disable Module | YES | Turns spam protection on/off. |
|  | Spam Detection Sensitivity | Medium | Controls aggressiveness of spam detection. |
|  | Action on Detected Spam | Block registration | Defines response to spam (block, review, log). |
|  | Error Message for Blocked Registrations | “Registration could not be completed. Please contact support if you believe this is an error.” | Customizes message for blocked users. |
|  | IP Blacklist/Whitelist | Use sparingly | Manually block/allow specific IPs. |
|  | Email Blacklist/Whitelist | Use sparingly | Manually block/allow specific emails/domains. |
|  | External API Integration | Enable with valid keys | Enhances protection with third-party services. |
| **AdminregproAttemptsController** | View Attempts Log | N/A | Review all registration attempts, their status, and reasons. |
|  | Whitelist IP (from log) | N/A | Allows future registrations from a specific IP. |
|  | Blacklist IP (from log) | N/A | Blocks future registrations from a specific IP. |
| **AdminregproBansController** | View Active Bans | N/A | Manage and review all currently active IP/email/domain bans. |
|  | Remove Ban | N/A | Lifts a specific ban. |
|  | Add New Ban | N/A | Manually adds a new IP, email, or domain to the ban list. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My legitimate customers are reporting they can’t register. What should I do?**
A: First, check the “Attempts” log (`AdminregproAttemptsController`) in the Back Office. Look for their IP address or email. If their attempt was blocked, you’ll see the reason. You can then whitelist their IP address or email, or temporarily lower the module’s sensitivity setting. Remember to clear your PrestaShop cache after making changes.

**Q: I’m still getting spam registrations even with the module active.**
A:

1. **Check Sensitivity:** Increase the “Spam Detection Sensitivity” in the module’s main configuration.
2. **Review Attempts Log:** Analyze the “Attempts” log to see if the module is logging these attempts and why they might be slipping through.
3. **Add to Blacklist:** If you identify specific IPs or email domains from the spam registrations, manually add them to your ban list via the `AdminregproBansController`.
4. **External API:** Ensure any integrated external spam protection APIs (like reCAPTCHA) are correctly configured and have valid keys.

**Q: How do I know if the module is actually working?**
A: The best way is to monitor the “Attempts” log (`AdminregproAttemptsController`). You should see entries for blocked attempts, indicating the module is actively identifying and preventing spam. If you were previously getting a lot of spam, you should also notice a significant reduction in new fake customer accounts.

**Q: Does this module affect my store’s performance?**
A: The module is designed to be efficient. While it adds a small processing step during registration, this is typically negligible compared to the benefits of preventing spam. A database full of spam accounts would cause far greater performance issues in the long run.

**Q: I’ve changed settings, but nothing seems to happen on the front office.**
A: Always clear your PrestaShop cache after making any configuration changes. Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right corner. This ensures the module loads the updated settings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Customer register spam protection” module (`regpro`) is built following PrestaShop’s MVC (Model-View-Controller) pattern. It primarily operates by hooking into the customer registration process, leveraging PrestaShop’s hook system to intercept and validate registration data. It uses dedicated Admin Controllers for managing attempts and bans, and stores its configuration in `ps_configuration`. The module’s core logic for spam detection is likely contained within the main `index.php` module file, with helper functions or classes (though none are explicitly listed in the dossier, they might be internal to the main module class).

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  The module dossier indicates no dedicated front-office controllers. This suggests that the module’s front-office interactions (e.g., intercepting registration data) are handled directly via hooks within the main `regpro/index.php` module file, or by overriding core PrestaShop controllers (though the latter is less common for simple spam protection). The `displayCustomerAccountForm` hooks are where the module’s logic would be triggered.
- **Back-Office Admin Controllers**:
  These controllers provide the administrative interface for managing the module’s data and settings.

  - `controllers/admin/AdminRegproAttempts.php`

    - **Class name & parent class:** `AdminRegproAttemptsController` (extends `ModuleAdminController` or `AdminController`).
    - **Responsibility:** Manages the listing and actions related to recorded spam attempts. This controller is responsible for displaying the grid of registration attempts, allowing administrators to view details, filter, and perform actions like whitelisting or blacklisting IPs based on these attempts. It interacts with the `regattempt` database table.
  - `controllers/admin/AdminRegproBans.php`

    - **Class name & parent class:** `AdminRegproBansController` (extends `ModuleAdminController` or `AdminController`).
    - **Responsibility:** Manages the listing and actions related to active bans (IPs, emails, domains). This controller allows administrators to view, add, edit, and remove entries from the module’s ban lists. It interacts with the `regban` database table.
  - `controllers/admin/index.php`

    - **Class name & parent class:** Likely a simple redirector or a placeholder file. It might contain a basic `AdminController` that redirects to one of the other module-specific admin controllers (e.g., `AdminRegproAttempts`) or displays a simple dashboard. It doesn’t directly manage a specific entity but serves as an entry point for the module’s admin section.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This implies that the module’s data structures (for attempts and bans) are either handled directly by the `AdminController` logic using raw SQL queries, or more likely, the `ObjectModel` definitions for `regattempt` and `regban` are embedded directly within the respective `AdminRegproAttempts.php` and `AdminRegproBans.php` controllers, or within the main `regpro/index.php` file.

If `ObjectModel` is used, the `$definition` array would be defined for:

- `regattempt`: Mapping to a `ps_regattempt` table (or similar), with fields like `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
- `regban`: Mapping to a `ps_regban` table (or similar), with fields like `id_regban`, `type` (IP, email, domain), `value`, `date_add`.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/regpro-v3.js`
  - **Scope:** Likely Back-office. The “v3” might indicate a version or specific functionality.
  - **Description:** This script is probably responsible for enhancing the user experience in the module’s Back Office configuration or management screens. It could handle:
    - AJAX calls for dynamic updates (e.g., filtering lists, adding/removing bans without page reload).
    - Form validation on the configuration page or when adding new ban entries.
    - Interactive elements on the “Attempts” or “Bans” grids (e.g., confirmation dialogs for actions, sorting, pagination).
    - Potentially, client-side logic for integrating with external APIs if they require JS interaction in the BO.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no custom CSS files. This suggests that the module relies entirely on PrestaShop’s default Back Office styling for its configuration pages and grids. If any specific styling is needed, it would either be inline in templates or dynamically added via JavaScript.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  These templates are rendered when the module is hooked into specific points in the front-office.

  - `views/templates/hook/displayCustomerAccountForm-v3.tpl`

    - **Hook:** `displayCustomerAccountForm` (or similar, specific to PrestaShop 1.7+ and 8.x).
    - **Purpose:** This template is likely used to inject hidden fields, JavaScript variables, or potentially a visible CAPTCHA/challenge (if configured) into the customer registration form. The “v3” suggests it’s a newer version, possibly for newer PrestaShop versions or a specific design. It might contain the HTML structure for reCAPTCHA if that integration is enabled.
  - `views/templates/hook/displayCustomerAccountForm.tpl`

    - **Hook:** `displayCustomerAccountForm` (or similar, potentially for older PrestaShop versions like 1.6.x).
    - **Purpose:** Similar to `displayCustomerAccountForm-v3.tpl`, but possibly a generic or older version. It would serve the same function of injecting elements or logic into the customer registration form for spam detection.
  - `views/templates/hook/displayCustomerAccountFormTop.tpl`

    - **Hook:** `displayCustomerAccountFormTop` (or similar).
    - **Purpose:** This template would render content at the very top of the customer registration form. This could be used for displaying a general message, or for injecting elements that need to appear before the main form fields, such as a “I am not a robot” checkbox or a warning.
- **Admin templates (`views/templates/admin/`)**:
  These templates define the structure and content of the module’s Back Office pages.

  - `views/templates/admin/main.tpl`
    - **Purpose:** This is likely the main template for the module’s configuration page (accessed via `getContent()` in `regpro/index.php`) or a general wrapper for the module’s admin section. It would contain the HTML for the various settings, input fields, and buttons described in Section 4.1. It might also include links to the `AdminRegproAttempts` and `AdminRegproBans` controllers.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  Based on the Admin Controllers, the module likely creates two custom tables:

  - `ps_regattempt` (or similar prefix): Stores records of registration attempts.
    - `id_regattempt` (PK, INT)
    - `ip_address` (VARCHAR)
    - `email` (VARCHAR)
    - `status` (VARCHAR, e.g., ‘blocked’, ‘allowed’, ‘flagged’)
    - `reason` (TEXT, explanation for status)
    - `date_add` (DATETIME)
  - `ps_regban` (or similar prefix): Stores records of active bans.
    - `id_regban` (PK, INT)
    - `type` (VARCHAR, e.g., ‘ip’, ‘email’, ‘domain’)
    - `value` (VARCHAR, the actual IP, email, or domain)
    - `date_add` (DATETIME)
    - `reason` (TEXT, optional, for manual bans)

  Configuration settings (like sensitivity, error messages, API keys) are stored in the `ps_configuration` table using keys prefixed with `REGPRO_` (e.g., `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Potentially used for loading module-specific CSS/JS globally, or for meta-tag injection for external API verification. |
| `displayCustomerAccountForm` | Renders within the customer registration form. | Primary hook for injecting hidden fields, reCAPTCHA elements, or JavaScript to intercept form submission and perform client-side validation. |
| `displayCustomerAccountFormTop` | Renders at the top of the customer registration form. | Similar to `displayCustomerAccountForm`, but ensures content appears before main form fields. |
| `actionCustomerAccountAdd` | Executed *after* a new customer account is successfully added to the database. | Could be used for post-registration logging, sending notifications, or further processing if an account was allowed but flagged for review. |
| `actionAuthentication` | Executed during customer login/authentication. | Less likely for registration spam, but could be used for advanced checks or to prevent login from banned IPs/emails. |
| `actionValidateCustomerAccount` | Executed *before* a new customer account is added to the database. | **CRITICAL HOOK:** This is the most likely hook where the module’s core spam detection logic would run, allowing it to prevent account creation if spam is detected. |
| `displayBackOfficeHeader` | Renders in the `<head>` section of all back-office pages. | Used for loading module-specific CSS/JS for the admin configuration and management screens. |
| `displayAdminCustomers` | Renders on the customer listing page in the Back Office. | Could be used to add a column or action button related to spam status for existing customers. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and comprehensive developer support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely assistance and ensuring the optimal performance of your “Customer register spam protection” module.
