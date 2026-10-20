---
title: "Login protection pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Login protection pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Login protection pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Login protection pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you define the core rules for login protection.

- **Menu Location:** Back Office > Modules > Module Manager > Login protection pro > Configure

#### Settings & Options:

1. **Enable Login Protection:**

   - **What this setting does:** This is the master switch for the module. It turns the entire login protection system on or off.
   - **Effect of changing this setting:**
     - *When enabled:* The module will start monitoring login attempts, applying the rules you set below.
     - *When disabled:* The module will be inactive, and no login attempts will be monitored or blocked. Your store will rely on PrestaShop’s default security, which does not include brute-force protection.
   - **Recommended value:** **YES**
   - **Merchant scenario / example:** Always keep this enabled to ensure your store is protected. Disable only for specific debugging if instructed by support.
2. **Max Failed Attempts:**

   - **What this setting does:** Defines the maximum number of incorrect login attempts allowed from a single IP address within a specific timeframe (defined by “Attempt Time Window”) before that IP is temporarily blocked.
   - **Effect of changing this setting:**
     - *Setting a lower number (e.g., 3):* Makes the protection more aggressive, blocking suspicious IPs faster. This might accidentally block legitimate users who genuinely forget their password multiple times.
     - *Setting a higher number (e.g., 10):* Makes the protection less aggressive, allowing more failed attempts. This reduces the chance of blocking legitimate users but gives hackers more tries.
   - **Recommended value:** **5**
   - **Merchant scenario / example:** If you notice many legitimate customers getting blocked, you might increase this. If you see a lot of brute-force attempts in your logs, you might decrease it. 5 is a good balance.
3. **Attempt Time Window (minutes):**

   - **What this setting does:** Specifies the duration (in minutes) during which the “Max Failed Attempts” count is active. If an IP makes `Max Failed Attempts` within this window, it gets blocked. After this window, the count resets.
   - **Effect of changing this setting:**
     - *Setting a shorter window (e.g., 5 minutes):* An IP must make the `Max Failed Attempts` very quickly to be blocked. This is good for rapid brute-force attacks.
     - *Setting a longer window (e.g., 60 minutes):* An IP can make `Max Failed Attempts` over a longer period to be blocked. This catches slower, more distributed attacks but might also block legitimate users who try to log in, get distracted, and try again later.
   - **Recommended value:** **15**
   - **Merchant scenario / example:** A 15-minute window is usually sufficient to catch automated attacks without unduly penalizing a human user who might be trying to remember their password over a few minutes.
4. **Ban Duration (minutes):**

   - **What this setting does:** Determines how long an IP address remains blocked once it exceeds the `Max Failed Attempts` within the `Attempt Time Window`.
   - **Effect of changing this setting:**
     - *Setting a shorter duration (e.g., 30 minutes):* The IP is unblocked sooner. This is less disruptive for legitimate users who might have been accidentally blocked but gives hackers a quicker retry.
     - *Setting a longer duration (e.g., 1440 minutes = 24 hours):* The IP remains blocked for a significant period. This is very effective against automated attacks but can be frustrating for legitimate users who are blocked.
   - **Recommended value:** **60** (1 hour)
   - **Merchant scenario / example:** A 60-minute ban is usually enough to deter automated bots, as they will likely move on. For a human, it provides a reasonable cool-down period.
5. **Protect Admin Login:**

   - **What this setting does:** This switch specifically applies the login protection rules to the PrestaShop Back Office (admin panel) login page.
   - **Effect of changing this setting:**
     - *When enabled:* Your admin login page is protected. If an attacker tries to guess your admin password too many times, their IP will be blocked.
     - *When disabled:* Only customer login attempts are monitored. Your admin login page remains vulnerable to brute-force attacks.
   - **Recommended value:** **YES**
   - **Merchant scenario / example:** It is absolutely critical to protect your admin login, as unauthorized access here can compromise your entire store. Always keep this enabled.
6. **Protect Customer Login:**

   - **What this setting does:** This switch specifically applies the login protection rules to the customer login page (front office).
   - **Effect of changing this setting:**
     - *When enabled:* Customer login attempts are protected. If an attacker tries to guess customer passwords, their IP will be blocked.
     - *When disabled:* Only admin login attempts are monitored. Customer accounts remain vulnerable to brute-force attacks.
   - **Recommended value:** **YES**
   - **Merchant scenario / example:** Protecting customer accounts is vital for data security and maintaining customer trust. Always keep this enabled.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Enable Login Protection | YES | Master switch for module functionality. **Always YES.** |
| Module Config | Max Failed Attempts | 5 | Number of incorrect logins before an IP is blocked. |
| Module Config | Attempt Time Window (minutes) | 15 | Duration over which failed attempts are counted. |
| Module Config | Ban Duration (minutes) | 60 | How long a blocked IP remains banned. |
| Module Config | Protect Admin Login | YES | Applies protection to the Back Office login. **Always YES.** |
| Module Config | Protect Customer Login | YES | Applies protection to the Front Office customer login. **Always YES.** |

### 2.2 Dedicated Admin Screens & Controller Views

The module provides two dedicated screens in your PrestaShop Back Office to manage and review login attempts and bans.

#### 2.2.1 AdminLproAttemptsController: Login Attempts Log

This screen allows you to view a detailed log of all failed login attempts recorded by the module.

- **Screen Name & Menu Location:** Back Office > Modules > Login Protection Pro > **Login Attempts** (or similar, depending on PrestaShop version and menu customization).
- **Available Actions & Settings:**
  - **Listing Table:** You will see a table displaying:
    - **IP Address:** The IP address from which the failed attempt originated.
    - **Attempt Time:** The exact date and time of the failed attempt.
    - **Login Type:** Whether it was an ‘Admin’ or ‘Customer’ login attempt.
    - **Username/Email:** The username or email address that was attempted.
    - **Status:** Indicates if the attempt led to a ban or was just a failed attempt.
  - **Filtering & Sorting:** You can typically filter by IP address, login type, or date range to find specific attempts.
  - **No direct actions:** This screen is primarily for monitoring and review. You cannot directly ban or unban IPs from here, but it helps you identify suspicious patterns.
- **Effect of changes:** Viewing this log helps you understand the frequency and source of attacks. If you notice a particular IP address making many attempts, you can manually add it to the ban list via the “Banned IPs” screen.
- **Recommended workflow for daily store management:** Regularly check this log, especially if you suspect an attack or if customers report issues logging in. Look for patterns of repeated failed attempts from the same IP or range of IPs.

#### 2.2.2 AdminLproBansController: Banned IPs Management

This screen allows you to view, add, and remove IP addresses from the module’s ban list.

- **Screen Name & Menu Location:** Back Office > Modules > Login Protection Pro > **Banned IPs** (or similar, depending on PrestaShop version and menu customization).
- **Available Actions & Settings:**
  - **Listing Table:** Displays all currently banned IP addresses, including:
    - **IP Address:** The blocked IP.
    - **Ban Reason:** (If applicable, e.g., “Automatic ban due to failed attempts”).
    - **Ban Start Time:** When the ban was initiated.
    - **Ban End Time:** When the ban is scheduled to expire (if temporary).
    - **Actions:** Usually includes an option to “Delete” or “Unban” a specific IP.
  - **“Add New IP” Button:** Allows you to manually add an IP address to the ban list. This is useful if you identify a malicious IP from your server logs or the “Login Attempts” screen that hasn’t been automatically banned yet.
    - When adding, you might be able to specify the IP, a reason, and an optional expiry time for the ban.
- **Effect of changes:**
  - *Adding an IP:* Immediately blocks all login attempts from that IP address for the specified duration (or permanently if no duration is set).
  - *Removing an IP:* Unblocks the IP address, allowing login attempts from it again. Use this cautiously, ensuring you’re not unblocking a known attacker.
- **Recommended workflow for daily store management:**
  - Review this list periodically.
  - If a legitimate customer reports being unable to log in, and you’ve confirmed their IP address (e.g., by asking them to visit a “what is my IP” site), you might temporarily unban their IP here.
  - If you identify a persistent threat, you can manually add their IP to ensure they remain blocked.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

This file typically serves as a placeholder or a redirector within the admin controllers directory. In PrestaShop, `index.php` files within controller directories often prevent direct directory listing or act as a default entry point if no specific controller is requested. It does not represent a configurable screen or managed entity itself.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are complaining they can’t log in, but they are using the correct password. What should I do?**
A1: This is likely due to the module blocking their IP address after too many failed attempts (perhaps from a previous session or a shared network).
1. Ask the customer for their current IP address (they can find it by searching “what is my IP” on Google).
2. Go to **Back Office > Modules > Login Protection Pro > Banned IPs**.
3. Search for their IP address in the list.
4. If found, delete/unban their IP.
5. Advise the customer to try logging in again. You might also suggest they reset their password.

**Q2: I’m locked out of my own admin panel! How can I regain access?**
A2: This can happen if you’ve made too many failed attempts.
1. If you have FTP access to your store, you can temporarily disable the module. Go to `modules/lpro/` and rename the `index.php` file (e.g., to `index.php.bak`). This will disable the module.
2. Log into your admin panel.
3. Go to **Modules > Module Manager**, find “Login protection pro”, and click “Configure”.
4. Go to **Banned IPs** and remove your IP address from the list.
5. Rename `index.php.bak` back to `index.php` in the `modules/lpro/` directory.
6. Re-enable the module if you disabled it in the module manager.
7. Adjust the `Max Failed Attempts` or `Ban Duration` settings if you find yourself frequently locked out.

**Q3: The module doesn’t seem to be blocking any IPs, even after many failed attempts. What could be wrong?**
A3:
1. **Check “Enable Login Protection”:** Ensure the main switch in the module configuration is set to **YES**.
2. **Check “Protect Admin Login” / “Protect Customer Login”:** Make sure the relevant protection (admin or customer) is enabled.
3. **Review Settings:** Verify that `Max Failed Attempts`, `Attempt Time Window`, and `Ban Duration` are set to reasonable values. If the `Attempt Time Window` is too short, or `Max Failed Attempts` is too high, it might take a very aggressive attack to trigger a ban.
4. **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache”. Sometimes, module settings don’t apply immediately due to caching.
5. **Check Server Logs:** Your hosting provider’s server access logs might show if the module is encountering any PHP errors.

**Q4: Will this module slow down my store?**
A4: The module is designed to be lightweight. It only performs checks during login attempts, which are relatively infrequent compared to page views. The performance impact should be negligible. If you notice any slowdown, ensure your PrestaShop installation and server meet the minimum requirements.

**Q5: How do I translate the module’s messages into other languages?**
A5: While this module primarily works in the background, any potential front-office messages (like “Too many failed attempts”) or back-office labels can be translated:
1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations”.
3. Choose your theme.
4. Select the language you want to translate.
5. Find the “Login protection pro” module and translate the relevant text strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Login protection pro” module for developers and webmasters.

### 4.1 Architecture Overview

The `Login protection pro` module follows a standard PrestaShop module architecture, primarily leveraging Admin Controllers for its management interface and hooks for its core functionality. It does not introduce complex front-office controllers or custom `ObjectModel` classes, instead relying on PrestaShop’s `Configuration` class for settings and direct database interaction for logging attempts and managing bans. The module’s logic for detecting and blocking attempts is injected via PrestaShop hooks, specifically around the authentication process.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

The module does **not** contain any dedicated front-office controllers. All front-office related logic (monitoring customer login attempts) is handled directly within the main module file (`lpro/index.php`) by hooking into PrestaShop’s authentication process.

#### Back-Office Admin Controllers

The module provides dedicated admin controllers for managing login attempts and bans.

- **`controllers/admin/AdminLproAttempts.php`**

  - **Class Name:** `AdminLproAttemptsController` (extends `ModuleAdminController`)
  - **Responsibility:** This controller is responsible for displaying a list of all recorded failed login attempts. It provides a read-only grid view of the `lattempt` data, allowing administrators to monitor suspicious activity. It typically uses `HelperList` for rendering the table.
  - **Managed Entity:** `lattempt` (represents a failed login attempt record).
  - **Tab Name:** Login Attempts (visible under the module’s main menu entry).
- **`controllers/admin/AdminLproBans.php`**

  - **Class Name:** `AdminLproBansController` (extends `ModuleAdminController`)
  - **Responsibility:** This controller manages the list of banned IP addresses. It provides a grid view of the `lban` data and allows administrators to add new bans, edit existing ones, and delete (unban) IPs. It likely uses `HelperList` for the table and `HelperForm` for add/edit forms.
  - **Managed Entity:** `lban` (represents a banned IP address record).
  - **Tab Name:** Banned IPs (visible under the module’s main menu entry).
- **`controllers/admin/index.php`**

  - **Exact file path:** `lpro/controllers/admin/index.php`
  - **Class name & parent class:** Not a class file.
  - **Responsibility:** This is a standard PrestaShop placeholder file. Its primary purpose is to prevent directory listing if web server configuration allows it, and sometimes it can contain a simple redirect or a security check. It does not contain any functional logic for the module itself.

### 4.3 Core Classes & Models (`classes/`)

The module does **not** contain any custom classes in the `classes/` directory. It likely handles database interactions directly within the main module file (`lpro/index.php`) or its admin controllers, using standard PrestaShop database query methods. This implies that the `lattempt` and `lban` entities are managed without dedicated `ObjectModel` classes, relying on direct SQL or `Db::getInstance()` calls.

### 4.4 JavaScript Assets (`views/js/`)

The module does **not** contain any custom JavaScript files. This suggests that its configuration and management interfaces rely entirely on PrestaShop’s default JavaScript libraries and behaviors (e.g., for form submission, table filtering).

### 4.5 CSS Stylesheets (`views/css/`)

The module does **not** contain any custom CSS files. This indicates that its Back Office interfaces (configuration, attempt logs, ban lists) inherit styling directly from the PrestaShop Back Office theme, ensuring a consistent look and feel without introducing custom visual elements.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - **`lpro/views/templates/admin/main.tpl`**:
    - **Purpose:** This template is likely used for the main module configuration page, rendered by the `getContent()` method in `lpro/index.php`. It contains the HTML structure for the settings described in section 4.1 (Enable Login Protection, Max Failed Attempts, etc.). It would typically include form elements (switches, input fields) and potentially links to the `AdminLproAttempts` and `AdminLproBans` controllers.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module creates custom database tables during its `install()` method (defined in `lpro/index.php`).

- **`ps_lpro_attempt`**:
  - **Purpose:** Stores records of all failed login attempts.
  - **Likely Fields:**
    - `id_lpro_attempt` (Primary Key)
    - `ip_address` (VARCHAR): The IP address of the failed attempt.
    - `attempt_time` (DATETIME): Timestamp of the attempt.
    - `login_type` (VARCHAR): ‘admin’ or ‘customer’.
    - `username` (VARCHAR): The username/email attempted.
    - `is_banned` (TINYINT): Flag indicating if this attempt led to a ban.
- **`ps_lpro_ban`**:
  - **Purpose:** Stores records of currently active IP bans.
  - **Likely Fields:**
    - `id_lpro_ban` (Primary Key)
    - `ip_address` (VARCHAR): The banned IP address.
    - `ban_start_time` (DATETIME): When the ban started.
    - `ban_end_time` (DATETIME): When the ban is scheduled to expire (NULL for permanent bans).
    - `reason` (TEXT): Optional reason for the ban.
    - `is_permanent` (TINYINT): Flag for permanent bans.

#### Registered Hooks Table

The module registers hooks to intercept login attempts and apply its protection logic.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAuthentication` | After a customer attempts to log in (front office). | Checks if the customer login attempt was successful or failed. If failed, records the attempt and checks for ban conditions. |
| `actionAdminLoginController` | After an administrator attempts to log in (back office). | Checks if the admin login attempt was successful or failed. If failed, records the attempt and checks for ban conditions. |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used for including CSS/JS (though none are present) or for early checks, though less likely for core logic. More often for general module initialization. |
| `displayRightColumn` | In the right column of front-office pages. | Not directly relevant for security logic. If used, it would be for displaying a message or block, which is unlikely for this module. |
| `displayLeftColumn` | In the left column of front-office pages. | Same as `displayRightColumn`. |
| `displayFooter` | In the footer of every front-office page. | Not directly relevant for security logic. |
| `displayProductExtraContent` | On the product page, within the “extra content” section. | Not directly relevant for security logic. |

**Note on Hooks:** The core logic for detecting and blocking attempts will primarily reside within the `actionAuthentication` and `actionAdminLoginController` hooks. Other `display` hooks are likely registered by default but not actively used for the module’s core security functionality.

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the “Login protection pro” module.
