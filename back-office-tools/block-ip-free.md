---
title: "Block IP free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Block IP free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Block IP free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Block IP free Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/block-ip-free/)
>
> ---


# Block IP free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Block IP free)

This is the main and only configuration screen for the “Block IP free” module. You will find all settings here to manage your blocked IP addresses and the message displayed to them.

**Screen Name & Menu Location:**

- **Menu Path:** Back Office > Modules > Module Manager > Block IP free > Configure

#### Settings & Options:

1. **IP Address (Input Field)**

   - **What this setting does:** This is where you enter the IP address you wish to block from accessing your store.
   - **Effect of changing this setting:**
     - *When an IP is added to the list:* Any visitor attempting to access your store from this specific IP address will be denied access and shown the “Blocked Access Message”.
     - *When an IP is removed from the list:* Visitors from that IP address will regain full access to your store.
   - **Recommended value:** Enter the exact IP address you want to block. You can add multiple IPs, one at a time, by entering each and clicking “Add”.
   - **Merchant scenario / example:** If you notice a specific IP address (e.g., `192.168.1.100`) is repeatedly attempting fraudulent orders or scraping your product data, you would enter `192.168.1.100` here and click “Add” to block it.
2. **Blocked Access Message (Textarea)**

   - **What this setting does:** This allows you to customize the message that blocked visitors will see when they try to access your store.
   - **Effect of changing this setting:**
     - *When a custom message is entered:* Blocked visitors will see your personalized message instead of a default one. This allows you to be polite, informative, or firm.
     - *When left as default:* A standard “Access Denied” message will be shown.
   - **Recommended value:** A clear and concise message. Something like: “Access to this store has been blocked from your IP address. If you believe this is an error, please contact support.”
   - **Merchant scenario / example:** You might want to display a message like “Due to suspicious activity, access from your IP address has been temporarily restricted. Please contact our support team if you believe this is an error.” This provides a better user experience than a generic error.

#### Managing the Blocked IP List:

Below the “IP Address” input field, you will see a list of all currently blocked IP addresses.

- **To add an IP:** Type the IP address into the “IP Address” field and click the “Add” button.
- **To remove an IP:** Next to each listed IP address, there will be a “Delete” button (often represented by a trash can icon). Click this button to unblock that specific IP.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | IP Address | Empty (add IPs as needed) | Adds/removes specific IP addresses from the block list. Blocked IPs cannot access the store. |
| Module Configuration Page | Blocked Access Message | “Access Denied” (or similar) | Customizes the message displayed to visitors from blocked IP addresses. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I blocked an IP, but the user can still access my store. Why?**
A:

1. **Caching:** Your PrestaShop store or server might have caching enabled. Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) and any server-side cache (like Varnish, LiteSpeed cache, Cloudflare) if applicable.
2. **Dynamic IP:** The user might have a dynamic IP address that has changed since you blocked the previous one.
3. **Proxy/VPN:** The user might be using a VPN or proxy server, which masks their real IP address. You would need to block the IP of the VPN/proxy server if you can identify it.
4. **Incorrect IP:** Double-check that you entered the correct IP address.

**Q: I accidentally blocked my own IP address and now I can’t access my Back Office! What do I do?**
A: This is a critical situation but fixable. You need to access your server directly:

1. **Via FTP/SFTP:** Connect to your store’s server using an FTP client (like FileZilla).
2. **Navigate to the modules folder:** Go to `your_prestashop_root/modules/`.
3. **Rename the module folder:** Find the `banipfree` folder and rename it to something like `banipfree_DISABLED`. This will effectively disable the module.
4. **Access Back Office:** You should now be able to log into your PrestaShop Back Office.
5. **Re-enable and configure:** Rename the folder back to `banipfree`, then go to **Modules > Module Manager**, find “Block IP free”, and click “Configure” to remove your IP from the blocked list.

**Q: Can I block a range of IP addresses instead of just one?**
A: The current version of the “Block IP free” module allows blocking individual IP addresses. For blocking entire ranges (e.g., `192.168.1.0/24`), you would typically need server-level configuration (e.g., `.htaccess` rules or firewall settings) or a more advanced security module.

**Q: Will this module slow down my store?**
A: No, the module is very lightweight. It checks the visitor’s IP address very early in the PrestaShop loading process. If the IP is blocked, the store content is not loaded at all, which can actually save server resources by preventing unwanted traffic from fully processing requests.

**Q: How do I find the IP address of a problematic visitor?**
A: You can find IP addresses in several places:

- **Server Access Logs:** Your web hosting control panel (cPanel, Plesk) usually provides access to raw access logs, which list every visitor’s IP address.
- **PrestaShop Order Details:** For orders, the customer’s IP address is usually recorded in the order details page in the Back Office.
- **Analytics Tools:** Some advanced analytics tools might show visitor IP addresses, though often anonymized.
- **Third-party Security Modules:** Other security modules might log suspicious activity with IP addresses.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Block IP free” module.

### 4.1 Architecture Overview

The “Block IP free” module is a simple, single-file PrestaShop module (`banipfree.php`) that primarily leverages the `actionDispatcher` hook. This hook is executed very early in the PrestaShop request lifecycle, allowing the module to check the visitor’s IP address before any significant processing or rendering of the store’s content occurs. If the IP is found in the blocked list, the module immediately terminates the request and displays a custom message, effectively acting as an early-stage firewall. Configuration is handled via the standard `getContent()` method, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office controllers. All logic is encapsulated within the main module file.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or `ObjectModel` definitions in the `classes/` directory. All data handling is direct via `Configuration::get()` and `Configuration::updateValue()`.

### 4.4 JavaScript Assets (`views/js/`)

- This module does **not** contain any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** contain any custom CSS files. The blocked access message is displayed with minimal, inline styling or default browser styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- This module does **not** contain any custom Smarty template files. The blocked access message is output directly as raw HTML/text within the `hookActionDispatcher` method.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table:

- `BANIPFREE_LIST`: Stores a comma-separated string of blocked IP addresses.
- `BANIPFREE_MSG`: Stores the custom message displayed to blocked users.
- `mypresta_updates`, `update_`, `updatev_`: Internal keys used by MyPresta.eu for module update checks.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionDispatcher` | Executed very early in the PrestaShop request lifecycle, before controller dispatch. | This is the primary hook used by the module. It retrieves the visitor’s IP address, checks it against the `BANIPFREE_LIST`, and if a match is found, it outputs the `BANIPFREE_MSG` and terminates the script execution (`die()`), preventing further store loading. |

### 4.8 Main Module File (`banipfree/banipfree.php`)

This is the core of the module.

- **`__construct()`**: Initializes module metadata (name, tab, version, author, etc.).
- **`install()`**:
  - Calls `parent::install()`.
  - Registers the `actionDispatcher` hook.
  - Sets initial configuration values for `BANIPFREE_LIST` (empty) and `BANIPFREE_MSG` (default message).
- **`uninstall()`**:
  - Calls `parent::uninstall()`.
  - Unregisters the `actionDispatcher` hook.
  - Deletes configuration values (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
- **`getContent()`**:
  - Handles form submission for saving IP addresses and the custom message.
  - Retrieves and displays the current list of blocked IPs.
  - Renders the configuration form using standard PrestaShop `HelperForm` elements (text input for IP, textarea for message, list for blocked IPs with delete buttons).
- **`hookActionDispatcher()`**:
  - This is the critical method for blocking.
  - It retrieves the visitor’s IP address (`$_SERVER['REMOTE_ADDR']`).
  - It fetches the `BANIPFREE_LIST` from `Configuration`.
  - It checks if the current IP is present in the comma-separated list.
  - If the IP is blocked, it retrieves `BANIPFREE_MSG`, outputs a simple HTML page with the message, and calls `die()` to stop further execution.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Block IP free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
