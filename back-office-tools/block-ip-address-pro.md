---
title: "Block IP address Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Block IP address Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Block IP address Pro"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Block IP address Pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/block-ip-address-pro/)
>
> ---


# Block IP address Pro

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) typically available on any modern web hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Block IP address Pro)

This is the main configuration screen for the module, where you define the global behavior for blocked visitors.

-   **Menu Location:** Back Office > Modules > Module Manager > Block IP address Pro > Configure

#### Settings & Options:

1.  **Display Update Notifications**
    -   **What this setting does:** Controls whether you receive notifications in your PrestaShop back office when a new version of the "Block IP address Pro" module is available.
    -   **Effect of changing this setting:**
        -   *When enabled:* You will see alerts or messages in your admin panel if an update is released, helping you keep your module current.
        -   *When disabled:* You will not receive these notifications, and you'll need to manually check for updates on MyPresta.eu.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** Keeping this enabled ensures you're always aware of new features, bug fixes, or security improvements for the module.

2.  **Message for Blocked Users (`banippro_msg`)**
    -   **What this setting does:** This is the custom message that will be displayed to users whose IP address has been blocked, *if* you choose not to redirect them.
    -   **Effect of changing this setting:**
        -   *When filled:* Blocked users will see this specific text on a blank page instead of your store content.
        -   *When empty:* If redirection is also disabled, blocked users might see a generic error or a blank page without a specific message.
    -   **Recommended value:** "Access to this store has been denied for your IP address." (or a similar polite but firm message).
    -   **Merchant scenario / example:** You might want to display "We're sorry, but access from your location has been restricted due to unusual activity." to inform the user without giving too much detail.

3.  **Redirect Blocked Users (`banippro_redirect`)**
    -   **What this setting does:** Determines whether blocked users are shown a message or automatically sent to a different web page.
    -   **Effect of changing this setting:**
        -   *When enabled:* Blocked users will be immediately redirected to the URL specified in the "Redirect URL" setting.
        -   *When disabled:* Blocked users will see the "Message for Blocked Users" you defined.
    -   **Recommended value:** YES (Redirection is often a cleaner user experience than a blank page with a message).
    -   **Merchant scenario / example:** If you want to send spammers away from your site entirely, or direct a problematic customer to a customer service page, enable this.

4.  **Redirect URL (`banippro_url`)**
    -   **What this setting does:** The specific web address (URL) where blocked users will be redirected if the "Redirect Blocked Users" setting is enabled.
    -   **Effect of changing this setting:**
        -   *When filled with a valid URL:* Blocked users will be sent to this exact page.
        -   *When empty:* If redirection is enabled but no URL is provided, the module's behavior might be unpredictable, or it might default to showing the message.
    -   **Recommended value:** Your store's homepage URL (e.g., `https://www.yourstore.com/`), or a specific "Contact Us" page, or even an external site like Google.
    -   **Merchant scenario / example:** You could redirect them to `https://www.yourstore.com/contact-us` if you want them to reach out, or to `https://www.google.com` to simply remove them from your site.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Display Update Notifications | YES | Shows alerts for new module versions. |
| Module Configuration | Message for Blocked Users | "Access to this store has been denied for your IP address." | Text displayed to blocked users if not redirected. |
| Module Configuration | Redirect Blocked Users | YES | If enabled, sends blocked users to a specified URL. |
| Module Configuration | Redirect URL | Your store's homepage URL | The destination for redirected blocked users. |

### 2.2 Dedicated Admin Screen: IP Address Management (Back Office > Modules > Block IP address Pro > Manage IP Addresses)

This is the core management screen where you add, edit, activate, and deactivate specific IP addresses to be blocked.

-   **Menu Location:** After installing the module, a new menu item will appear under **Modules > Block IP address Pro** (or similar, depending on PrestaShop version and module's menu registration). Click on "Manage IP Addresses" or "Ban IP Addresses".

#### Available Actions & Settings:

1.  **IP Address Listing Table:**
    -   This table displays all IP addresses you have configured for blocking.
    -   **Columns:**
        -   **ID:** Unique identifier for the blocked IP entry.
        -   **IP address:** The actual IP address being blocked (e.g., `192.168.1.1`, `203.0.113.45`).
        -   **Number of views:** A statistic showing how many times this specific IP address has attempted to access your store and was blocked. This is invaluable for identifying persistent threats.
        -   **Comment:** Your internal note about why this IP was blocked (e.g., "Spammer bot", "Competitor scraping", "Problematic customer").
        -   **Active:** A toggle switch (On/Off) to quickly enable or disable the blocking for this specific IP without deleting the entry.
        -   **Actions:** Buttons to "Edit" or "Delete" individual IP entries.

2.  **Adding a New IP Address:**
    -   Click the "Add new IP address" button (or similar, usually a plus icon or "Add new" button at the top right of the table).
    -   **Form Fields:**
        -   **IP:** Enter the exact IP address you wish to block.
        -   **Comment:** Add a descriptive note for your reference (e.g., "Known spam source from analytics", "Customer 'John Doe' causing issues").
        -   **Active:** Choose "On" to immediately activate the block, or "Off" to save the entry but keep it inactive for now.
    -   **Save:** Click "Save" to add the new IP to your block list.

3.  **Editing an Existing IP Address:**
    -   Click the "Edit" icon next to an IP address in the listing table.
    -   You can modify the "IP", "Comment", and "Active" status.
    -   **Save:** Click "Save" to apply your changes.

4.  **Deleting an IP Address:**
    -   Click the "Delete" icon next to an IP address.
    -   Confirm the deletion. This will permanently remove the IP from your block list.

#### Effect of changes:
-   **Adding an IP:** Once saved and active, any visitor attempting to access your store from that IP address will immediately be blocked or redirected according to your module's global configuration.
-   **Editing an IP:** Changes to the IP address, comment, or active status will take effect immediately.
-   **Deactivating an IP:** The IP address remains in your list, but visitors from that IP will no longer be blocked. This is useful for temporary blocks or if an IP was blocked by mistake.
-   **Deleting an IP:** The IP is permanently removed from the block list, and visitors from that IP will regain full access to your store.

#### Recommended workflow for daily store management:
1.  **Monitor Analytics:** Regularly check your website analytics for suspicious traffic patterns, high bounce rates from specific IPs, or unusual activity.
2.  **Identify Problematic IPs:** If you find an IP address that is consistently causing issues (e.g., repeated failed login attempts, excessive page scraping, spam comments), note it down.
3.  **Add to Block List:** Navigate to the "Manage IP Addresses" screen, click "Add new IP address", enter the IP, add a descriptive comment, and set it to "On".
4.  **Review Statistics:** Periodically check the "Number of views" column for blocked IPs. High numbers indicate persistent attempts, confirming the effectiveness of your block.
5.  **Manage & Refine:** If an IP address is no longer a threat, you can either deactivate it (set "Active" to "Off") or delete it entirely.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| IP Address Management | Add New IP | N/A | Adds a new IP address to the block list. |
| IP Address Management | IP Address (Field) | N/A | The specific IP to block. |
| IP Address Management | Comment (Field) | N/A | Your internal note for the blocked IP. |
| IP Address Management | Active (Toggle) | On | Enables/disables blocking for a specific IP. |
| IP Address Management | Number of views (Column) | 0 | Tracks how many times an IP was blocked. |
| IP Address Management | Edit / Delete Actions | N/A | Modify or remove existing blocked IP entries. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've blocked an IP, but the user can still access my store. What's wrong?**
A:
1.  **Check "Active" status:** Ensure the "Active" toggle for that specific IP in the "Manage IP Addresses" screen is set to "On".
2.  **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" for older versions). This ensures the module's settings are reloaded.
3.  **Verify IP Address:** Double-check that you've entered the correct IP address. Sometimes dynamic IPs change, or you might have a proxy/CDN issue.
4.  **Browser Cache:** Ask the blocked user to clear their browser cache or try accessing from an incognito window.

**Q: My legitimate customer is blocked! How do I fix this?**
A:
1.  **Identify their IP:** Ask the customer for their current IP address (they can find it by searching "what is my IP" on Google).
2.  **Check your block list:** Go to **Modules > Block IP address Pro > Manage IP Addresses** and search for their IP.
3.  **Deactivate or Delete:** If found, either set the "Active" toggle to "Off" for that entry or delete it entirely.
4.  **Clear Cache:** Remember to clear your PrestaShop cache afterward.

**Q: Can I block a range of IP addresses instead of just one?**
A: The current version of the module supports blocking individual IP addresses. For blocking ranges, you would need to enter each IP within the range individually, or consider server-level IP blocking if you have access to your server's firewall (e.g., via `.htaccess` rules).

**Q: What happens if I enable redirection but don't provide a Redirect URL?**
A: If "Redirect Blocked Users" is enabled but "Redirect URL" is empty, the module's behavior might be inconsistent. It's best practice to always provide a valid URL if redirection is active. If you don't want to redirect, disable the "Redirect Blocked Users" option and use the custom message instead.

**Q: Will this module slow down my store?**
A: No, the module is designed to be very lightweight and efficient. It checks the visitor's IP address very early in the PrestaShop loading process. If an IP is blocked, the request is terminated or redirected quickly, often *before* your store even starts loading its full content, which can actually *improve* performance by reducing unwanted server load.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical deep dive into the "Block IP address Pro" module for developers and webmasters.

### 4.1 Architecture Overview
The "Block IP address Pro" module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for installation/uninstallation and configuration, and `AdminController` for back-office management. It uses a custom database table to store blocked IP addresses and hooks into the `actionFrontControllerAfterInit` hook to perform the IP check as early as possible in the request lifecycle.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    The module does not have dedicated front-office controllers. The IP blocking logic is handled directly within the main module file (`banippro.php`) via a hook, ensuring early execution.

-   **Back-Office Admin Controllers**:
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Class Name & Parent Class:** `AdminBanIpProController` extends `ModuleAdminController`.
        *   **Responsibility:** This controller is responsible for managing the list of blocked IP addresses in the PrestaShop Back Office. It provides the standard CRUD (Create, Read, Update, Delete) interface for the `BanIpPro` entity. It handles:
            *   Displaying the list of blocked IPs with their details (IP, views, comment, active status).
            *   Adding new IP addresses to the block list.
            *   Editing existing IP address entries.
            *   Deleting IP addresses from the block list.
            *   Managing the "Active" status toggle for each IP.
            *   The `initContent()`, `renderList()`, `renderForm()` methods are typically overridden here to customize the display and forms.
            *   It maps to the `ban` database table (or similar, as defined by the `BanIpPro` model if it existed).

    2.  `banippro/controllers/admin/index.php`
        *   **Responsibility:** This is a standard empty `index.php` file often found in PrestaShop module subdirectories. Its primary purpose is to prevent directory listing on web servers for security reasons. It does not contain any functional logic for the module.

### 4.3 Core Classes & Models (`classes/`)
The module description indicates no custom classes in the `classes/` directory. The `BanIpPro` entity (for blocked IPs) is likely managed directly within the `AdminBanIpProController` and the main `banippro.php` file, potentially using a simple `Db` class interaction or an internal array structure if not fully `ObjectModel` compliant. If an `ObjectModel` were used, it would typically be named `BanIpPro` and reside in `classes/BanIpPro.php`.

Given the `AdminBanIpProController` manages a "ban" entity, it implies an underlying data structure. If not a dedicated `ObjectModel`, it would be direct database queries.

### 4.4 JavaScript Assets (`views/js/`)
The module description indicates no custom JavaScript files. Any interactive elements in the back office (like toggle switches or form validation) are likely handled by PrestaShop's core JS or inline scripts within templates.

### 4.5 CSS Stylesheets (`views/css/`)
The module description indicates no custom CSS files. The styling for the back-office configuration and IP management screens will rely entirely on PrestaShop's default back-office theme CSS.

### 4.6 Smarty Template Structure (`views/templates/`)
The module description indicates no custom template files.
-   **Hook templates**: The module's front-office behavior (blocking/redirection) is handled programmatically in the hook, not via a template.
-   **Admin templates**: The configuration form for `getContent()` and the list/form views for `AdminBanIpProController` are likely rendered using PrestaShop's default helper classes (`HelperForm`, `HelperList`) which generate HTML directly, or rely on very minimal inline templates if any.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    The module creates at least one custom table during installation to store the blocked IP addresses.
    -   `ps_banippro` (or similar, e.g., `ps_ban_ip_pro`):
        *   `id_banippro` (Primary Key, INT)
        *   `ip_address` (VARCHAR, stores the IP address to be blocked)
        *   `comment` (TEXT, for admin notes)
        *   `views` (INT, counter for how many times this IP was blocked)
        *   `active` (TINYINT(1), 0 or 1, to enable/disable the block)

    Configuration settings (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) are stored in the `ps_configuration` table.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `actionFrontControllerAfterInit` | Executed after the front controller has been initialized but before any content is rendered. | **CRITICAL:** This is where the module performs its core function: checking the visitor's IP against the blocked list. If a match is found, it either displays the custom message or performs a redirection, effectively stopping further page execution. |
| `displayHome` | Renders content on the homepage. | Likely used for update notifications or other module-specific content if the module had a front-office component. In this module's context, it might be a legacy hook or used for very specific, non-blocking logic. |
| `home` | Alias for `displayHome` in some contexts. | Same as `displayHome`. |
| `header` | Renders content within the `<head>` section of the HTML. | Used for adding CSS, JavaScript, or meta tags. In this module, it might be used for update notifications or to ensure early script/style loading if needed. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media (CSS/JS). | Used by the module to add any specific CSS or JavaScript files required for its back-office configuration pages (e.g., for `AdminBanIpProController`). |
| `ActionAdminControllerSetMedia` | (Duplicate of above, case-sensitive difference) | Same as `actionAdminControllerSetMedia`. PrestaShop hooks are generally case-insensitive, but modules sometimes register both for compatibility. |
| `displayHeader` | Renders content within the `<header>` section of the HTML (often in the `<body>` before main content). | Similar to `header`, but typically for visible elements. In this module, it's less likely to have a direct front-office impact given its blocking nature. |

## 5. Official Support & Updates
For the latest module updates, bug fixes, and professional support, please refer to your customer account at MyPresta.eu. Our team is dedicated to providing timely assistance and ensuring your module operates smoothly.
-   **MyPresta.eu Order History & Downloads:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **MyPresta.eu Support Contact:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
