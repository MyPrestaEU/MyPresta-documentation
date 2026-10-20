---
title: "Cart protection pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cart protection pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cart protection pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cart protection pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for external API integrations (like CleanTalk or StopForumSpam) if you choose to enable them. Most modern hosting environments already provide these.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main control panel for “Cart protection pro,” where you define how the module detects and responds to suspicious cart activity.

#### General Settings

- **Enabled**:

  - **What this setting does:** This is the master switch for the module.
  - **Effect of changing this setting:**
    - *When enabled:* The module actively monitors cart activity and applies your chosen protection rules.
    - *When disabled:* The module is inactive and will not protect your store from fake cart attacks.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Always keep this enabled to ensure your store is protected. Disable only for troubleshooting or maintenance.
- **Protection type**:

  - **What this setting does:** Determines the method the module uses to identify and block suspicious activity.
  - **Effect of changing this setting:**
    - *When set to “IP address”:* The module tracks cart attempts based on the visitor’s IP address. If an IP exceeds the allowed attempts, it will be blocked.
    - *When set to “Cookie”:* The module tracks cart attempts using a browser cookie. If a browser (identified by cookie) exceeds attempts, it will be blocked. This is less reliable as cookies can be cleared.
    - *When set to “IP address + Cookie”:* Combines both methods for stronger protection. An IP or a cookie exceeding limits will trigger a block.
    - *When set to “CleanTalk”:* Uses the external CleanTalk anti-spam service to verify requests. Requires a CleanTalk API key.
    - *When set to “StopForumSpam”:* Uses the external StopForumSpam database to check if an IP is known for spam. Requires a StopForumSpam key.
  - **Recommended value:** “IP address + Cookie” for robust local protection, or “CleanTalk” / “StopForumSpam” if you have accounts with these services for advanced external checks.
  - **Merchant scenario / example:** If you’re experiencing a high volume of fake carts, start with “IP address + Cookie”. If the problem persists or you want more advanced checks, consider integrating with CleanTalk or StopForumSpam.
- **Time frame**:

  - **What this setting does:** Defines the duration (in minutes) within which the module counts cart attempts from a single source (IP or cookie).
  - **Effect of changing this setting:**
    - *A shorter time frame (e.g., 5 minutes):* More aggressive protection. A user/bot will be blocked faster if they make many attempts in a short burst.
    - *A longer time frame (e.g., 60 minutes):* Less aggressive. Allows more attempts over a longer period before blocking.
  - **Recommended value:** 10 minutes
  - **Merchant scenario / example:** If bots are rapidly creating carts, a shorter time frame will catch them quicker. If you find legitimate users are being blocked (rare), you might slightly increase this.
- **Number of attempts**:

  - **What this setting does:** Sets the maximum number of cart additions allowed from a single source (IP or cookie) within the defined “Time frame” before a block is triggered.
  - **Effect of changing this setting:**
    - *A lower number (e.g., 3):* Very aggressive. A user/bot will be blocked after only a few cart additions.
    - *A higher number (e.g., 10):* Less aggressive. Allows more cart additions before blocking.
  - **Recommended value:** 5
  - **Merchant scenario / example:** A normal customer rarely adds more than 5 items to their cart within a 10-minute window. Bots, however, often try to add dozens or hundreds. Setting this to 5 helps differentiate.
- **Title of email to merchant**:

  - **What this setting does:** Specifies the subject line for the email notification sent to you (the merchant) when a cart protection ban occurs.
  - **Effect of changing this setting:** Changes the subject line of the alert emails you receive.
  - **Recommended value:** “Cart Protection Pro - Ban Alert!”
  - **Merchant scenario / example:** Customize this to make the alerts easily recognizable in your inbox, e.g., “URGENT: Bot Blocked on [Your Store Name]”.
- **Logs**:

  - **What this setting does:** Controls whether the module records details of cart attempts and bans in your PrestaShop database.
  - **Effect of changing this setting:**
    - *When enabled:* The module stores a history of all attempts and bans, which you can review in the “Attempts” and “Bans” sections of the module. This is crucial for monitoring and understanding attacks.
    - *When disabled:* No logs are kept, making it harder to track or troubleshoot issues.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Always keep logs enabled. They provide valuable insights into the types and frequency of attacks your store faces, helping you fine-tune your settings.

#### CleanTalk Integration

- **Turn on CleanTalk free support**:

  - **What this setting does:** Enables integration with the CleanTalk anti-spam service for real-time spam checks. CleanTalk offers a free plan for basic checks.
  - **Effect of changing this setting:**
    - *When enabled:* The module will send requests to CleanTalk to verify if an IP address or email (if available) is known for spam before allowing cart additions.
    - *When disabled:* CleanTalk checks are not performed.
  - **Recommended value:** NO (unless you have a CleanTalk account and API key)
  - **Merchant scenario / example:** If you already use CleanTalk for other spam protection (e.g., comments, registrations) or want an additional layer of external verification, enable this.
- **Turn on CleanTalk paid support**:

  - **What this setting does:** Enables integration with the CleanTalk anti-spam service, specifically for features available with a paid CleanTalk subscription.
  - **Effect of changing this setting:** Similar to free support, but potentially with more advanced checks if your CleanTalk plan allows.
  - **Recommended value:** NO (unless you have a CleanTalk paid account and API key)
  - **Merchant scenario / example:** Choose this if you have a paid CleanTalk subscription and want to leverage its full capabilities for cart protection.
- **Clean talk API key**:

  - **What this setting does:** This is the unique key provided by CleanTalk that authenticates your store with their service.
  - **Effect of changing this setting:** Without a valid API key, CleanTalk integration will not work, even if enabled.
  - **Recommended value:** Your actual CleanTalk API key (leave empty if not using CleanTalk).
  - **Merchant scenario / example:** After signing up for CleanTalk, you’ll receive an API key. Enter it here to activate their service.

#### StopForumSpam Integration

- **Turn on StopForumSpam support**:

  - **What this setting does:** Enables integration with the StopForumSpam database, which lists IPs, emails, and usernames known for spamming forums and websites.
  - **Effect of changing this setting:**
    - *When enabled:* The module will query StopForumSpam to check if the visitor’s IP address is listed as a known spammer.
    - *When disabled:* StopForumSpam checks are not performed.
  - **Recommended value:** NO (unless you have a StopForumSpam key)
  - **Merchant scenario / example:** This is a good additional layer of protection if you want to block IPs that are globally recognized as spammers, even if they haven’t yet triggered your local cart limits.
- **StopForumSpam key**:

  - **What this setting does:** This is the unique key provided by StopForumSpam that authenticates your store with their service.
  - **Effect of changing this setting:** Without a valid key, StopForumSpam integration will not work, even if enabled.
  - **Recommended value:** Your actual StopForumSpam API key (leave empty if not using StopForumSpam).
  - **Merchant scenario / example:** After registering with StopForumSpam, you’ll receive an API key. Enter it here to activate their service.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Cart Protection Pro > Attempts (Back Office > Modules > Cart Protection Pro > Attempts)

- **Screen Name & Menu Location:** You can find this screen by navigating to **Modules > Module Manager**, then clicking “Configure” on “Cart protection pro”, and then selecting the “Attempts” tab (or a similar menu item if the module adds its own top-level menu).
- **Available Actions & Settings:** This screen displays a list (grid view) of all recorded cart attempts that triggered the module’s logging. It shows details like:
  - **IP Address:** The IP address of the visitor.
  - **Cookie ID:** The unique cookie identifier (if “Cookie” protection is enabled).
  - **Attempts:** The number of cart additions made by this source within the configured time frame.
  - **Timestamp:** When the attempt was recorded.
  - **Status:** Whether it led to a ban or was just an attempt.
- **Effect of changes:** This is a read-only log. You cannot directly modify attempts here. Its purpose is to provide transparency and data for you to understand potential attacks. You can usually filter and sort the list to analyze patterns.
- **Recommended workflow for daily store management:** Regularly check this log, especially if you suspect bot activity. Look for patterns:
  - Many attempts from the same IP or cookie.
  - Attempts concentrated within a short period.
  - Unusual IP ranges or geographic locations.
    This data helps you fine-tune your “Time frame” and “Number of attempts” settings.

#### 2.2.2 Cart Protection Pro > Bans (Back Office > Modules > Cart Protection Pro > Bans)

- **Screen Name & Menu Location:** Similar to the Attempts screen, this is accessible via **Modules > Module Manager > Configure “Cart protection pro” > Bans** tab/menu item.
- **Available Actions & Settings:** This screen displays a list (grid view) of all IP addresses or cookie IDs that have been blocked by the module. It typically shows:
  - **IP Address:** The blocked IP.
  - **Cookie ID:** The blocked cookie (if applicable).
  - **Reason:** Why the ban occurred (e.g., “Too many attempts”).
  - **Ban Start/End Time:** When the ban was initiated and if it’s temporary.
  - **Actions:** Often includes options to manually “Unban” an entry.
- **Effect of changes:**
  - *Unbanning an entry:* Removes the block for that specific IP or cookie, allowing them to access your cart functionality again. Use with caution!
- **Recommended workflow for daily store management:**
  - Periodically review the list of bans. If you notice a legitimate IP address (e.g., your own, or a known partner) has been accidentally banned, you can unban it here.
  - Look for recurring IP addresses or patterns in bans, which might indicate persistent attacks.
  - This screen is crucial for ensuring that the module is effectively blocking malicious traffic without inadvertently affecting real customers.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enabled | YES | Master switch for module functionality. |
| Module Configuration | Protection type | IP address + Cookie | Method to identify and block suspicious activity (IP, Cookie, both, CleanTalk, StopForumSpam). |
| Module Configuration | Time frame | 10 minutes | Duration (minutes) for counting cart attempts. |
| Module Configuration | Number of attempts | 5 | Max cart additions within the time frame before a block. |
| Module Configuration | Title of email to merchant | Cart Protection Pro - Ban Alert! | Subject line for merchant notification emails. |
| Module Configuration | Logs | YES | Enables/disables logging of attempts and bans. |
| Module Configuration | Turn on CleanTalk free support | NO | Activates CleanTalk free anti-spam checks. |
| Module Configuration | Turn on CleanTalk paid support | NO | Activates CleanTalk paid anti-spam checks. |
| Module Configuration | Clean talk API key | (empty) | Your unique CleanTalk API key. |
| Module Configuration | Turn on StopForumSpam support | NO | Activates StopForumSpam IP database checks. |
| Module Configuration | StopForumSpam key | (empty) | Your unique StopForumSpam API key. |
| AdminCproAttempts | Grid / Management view | N/A | Displays a log of all cart attempts. |
| AdminCproBans | Grid / Management view | N/A | Displays a list of all blocked IPs/cookies, with unban option. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are complaining they can’t add items to the cart, but I’m not seeing any bans.**
A1: First, check if the “Cart protection pro” module is “Enabled” in its configuration. If it is, navigate to the “Bans” section within the module’s configuration. See if any legitimate customer IPs are listed there. If so, you might have set the “Number of attempts” or “Time frame” too aggressively. Try increasing the “Number of attempts” slightly (e.g., from 3 to 5 or 7) or extending the “Time frame” (e.g., from 5 to 10-15 minutes). Also, ensure your theme or other modules aren’t interfering with the cart process.

**Q2: I’ve configured CleanTalk/StopForumSpam, but it doesn’t seem to be working.**
A2: Double-check the following:
1. Ensure “Turn on CleanTalk/StopForumSpam support” is enabled.
2. Verify that your “Clean talk API key” or “StopForumSpam key” is entered correctly and is active with the respective service. Even a single typo will prevent it from working.
3. Confirm that your hosting environment allows outgoing cURL requests, which are necessary for communicating with these external services. Your host can confirm this.
4. Check the module’s “Attempts” and “Bans” logs for any entries indicating a block by these services.

**Q3: My store is still getting a lot of fake carts even with the module enabled.**
A3: This could indicate a sophisticated bot or that your settings are not aggressive enough.
1. **Review your settings:** Try decreasing the “Number of attempts” (e.g., from 5 to 3) and/or shortening the “Time frame” (e.g., from 10 to 5 minutes).
2. **Enable external services:** If you haven’t already, consider enabling and configuring CleanTalk or StopForumSpam for an additional layer of protection.
3. **Check for conflicts:** Temporarily disable other security or caching modules to see if there’s a conflict.
4. **Clear Cache:** Sometimes, PrestaShop’s Smarty cache can prevent new module settings from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache.”

**Q4: Will this module slow down my store?**
A4: The module is designed to be lightweight. The primary checks (IP/Cookie) are very fast. If you enable external services like CleanTalk or StopForumSpam, there will be a slight delay as your server communicates with their APIs. However, these services are optimized for speed, and the impact is usually negligible. The benefit of preventing server overload from fake carts far outweighs any minimal processing time.

**Q5: How do I translate the email title or other module texts?**
A5: For the “Title of email to merchant,” you can simply change the text directly in the module’s configuration. For other module texts (if any were visible to customers, which this module generally isn’t), you would typically go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations,” choose your theme, and then select “Cart protection pro” to find and edit the translatable strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Cart protection pro” module, intended for developers and webmasters who need to understand, debug, or extend its functionality.

### 4.1 Architecture Overview

The “Cart protection pro” module follows a standard PrestaShop module architecture, primarily leveraging hooks for its core functionality and dedicated Admin Controllers for back-office management. It integrates external anti-spam services (CleanTalk, StopForumSpam) via cURL requests. The module’s logic is encapsulated within its main class and helper classes, with configuration stored in `ps_configuration` and logs in custom database tables.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

This module does not explicitly define custom front-office controllers. Its front-office logic is primarily executed via hooks within the main `cpro.php` module file, intercepting cart actions before they are fully processed.

#### Back-Office Admin Controllers

These controllers manage the module’s dedicated administration screens, providing grid views for attempts and bans.

- `cpro/controllers/admin/AdminCproAttempts.php`

  - **Class Name & Parent Class**: `AdminCproAttemptsController` extends `ModuleAdminController`.
  - **Responsibility**: Manages the display and interaction for the “Attempts” log in the PrestaShop Back Office. It fetches data from the `cattempt` database table and renders it in a list format, allowing the administrator to view all recorded cart attempts. It does not allow direct modification of attempts, acting as a read-only log viewer.
- `cpro/controllers/admin/AdminCproBans.php`

  - **Class Name & Parent Class**: `AdminCproBansController` extends `ModuleAdminController`.
  - **Responsibility**: Manages the display and interaction for the “Bans” list in the PrestaShop Back Office. It retrieves data from the `cban` database table and presents it in a list. This controller also handles actions like “Unban,” allowing an administrator to remove a specific IP or cookie from the ban list.
- `cpro/controllers/admin/index.php`

  - **Class Name & Parent Class**: This file typically serves as a security measure in PrestaShop, containing `die('No direct script access');` to prevent direct access to the directory. It does not contain a functional controller class.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. The core logic for handling attempts and bans, including database interactions, is likely managed directly within the main `cpro.php` module file or through direct `Db::getInstance()` calls.

### 4.4 JavaScript Assets (`views/js/`)

The module dossier indicates no custom JavaScript files. Any dynamic behavior in the back office is likely handled by PrestaShop’s core JS or inline scripts within templates.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no custom CSS files. Styling for the back-office screens will rely on PrestaShop’s default admin theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `cpro/views/templates/admin/main.tpl`
    - **Purpose**: This template is likely used for the main configuration page of the module, rendered by the `getContent()` method in `cpro.php`. It contains the HTML structure for all the settings described in Section 4.1, including form fields for “Protection type,” “Time frame,” “Number of attempts,” API keys, and the “Enabled” switch. It might also include navigation tabs or links to the `AdminCproAttempts` and `AdminCproBans` controllers.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_cattempt`: Stores logs of cart attempts.
    - `id_cattempt` (Primary Key)
    - `ip_address` (VARCHAR): IP address of the visitor.
    - `cookie_id` (VARCHAR): Unique identifier from the browser cookie.
    - `attempts` (INT): Number of cart additions.
    - `date_add` (DATETIME): Timestamp of the attempt.
    - `status` (TINYINT): Status, e.g., 0 for attempt, 1 for banned.
  - `ps_cban`: Stores records of banned IPs/cookies.
    - `id_cban` (Primary Key)
    - `ip_address` (VARCHAR): Banned IP address.
    - `cookie_id` (VARCHAR): Banned cookie ID.
    - `reason` (TEXT): Reason for the ban (e.g., “Too many attempts”).
    - `date_add` (DATETIME): When the ban was initiated.
    - `date_expire` (DATETIME): If the ban is temporary.
  - **Configuration Records (in `ps_configuration`)**:
    - `CPRO_PTYPE_5`: Protection type setting (e.g., IP, Cookie, CleanTalk).
    - `CPRO_CTALK_APIKEY`: CleanTalk API key.
    - `CPRO_CTALK`: CleanTalk free support enabled/disabled.
    - `CPRO_CTALK_PAID`: CleanTalk paid support enabled/disabled.
    - `CPRO_ATMPT`: Number of attempts allowed.
    - `CPRO_TIME`: Time frame in minutes.
    - `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4`: Internal flags for protection types.
    - `CPRO_SFS`: StopForumSpam support enabled/disabled.
    - `CPRO_SFS_KEY`: StopForumSpam API key.
    - `CPRO_MTITLE`: Email title for merchant notifications.
    - `CPRO_LOGS`: Logging enabled/disabled.
    - `mypresta_updates`, `update_`, `updatev_`: Internal keys for module updates.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionObjectCartAddAfter` | After a cart object has been added/updated in the database. | Potentially used for logging successful cart additions or post-processing after a cart is saved. |
| `actionCartSave` | After a cart has been saved (inserted or updated). | Similar to `actionObjectCartAddAfter`, used for monitoring or logging cart changes. |
| `actionFrontControllerInitBefore` | Before the front controller initializes. | Early interception point to check for banned IPs/cookies before any page content is rendered, potentially redirecting or displaying a block message. |
| `actionObjectCartAddBefore` | Before a cart object is added/updated in the database. | **CRITICAL**: This is the primary hook for intercepting and validating cart additions. The module will perform its checks (IP, cookie, CleanTalk, StopForumSpam) here and can prevent the cart addition if limits are exceeded or a ban is detected. |
| `displayHeader` | In the `<head>` section of the front-office pages. | Could be used to inject necessary JavaScript (though none detected) or CSS, or to set cookies for tracking. |
| `actionDispatcherBefore` | Before the dispatcher processes the request. | Another early interception point, similar to `actionFrontControllerInitBefore`, allowing the module to perform checks and potentially block requests before they reach a specific controller. |

### 4.8 External API Integrations

- **CleanTalk**: Uses cURL to send IP addresses and potentially other data to CleanTalk’s API for spam verification.
- **StopForumSpam**: Uses cURL to query the StopForumSpam database with IP addresses to check for known spammers.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for your “Cart protection pro” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our team is dedicated to ensuring your module functions optimally and your store remains secure.
