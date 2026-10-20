---
title: "Remove language ISO code from urls - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Remove language ISO code from urls PrestaShop module by MyPresta.eu."
sidebar:
  label: "Remove language ISO code from urls - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Remove language ISO code from urls Module on MyPresta.eu](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/remove-language-iso-code-from-urls/)
>
> ---


# Remove language ISO code from urls

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond what PrestaShop itself requires.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name “Remove language ISO code from urls” to access its settings.

The configuration page for this module is intentionally simple, as its core function is straightforward.

**Screen Name:** Remove language ISO code from urls Configuration
**Menu Location:** Back Office > Modules > Module Manager > Remove language ISO code from urls > Configure

On this screen, you will typically find a single, crucial setting:

- **Setting Name:** Enable / Disable module
  - **What this setting does:** This is the master switch for the module’s functionality. It controls whether the module actively removes the language ISO code from your default language URLs or not.
  - **Effect of changing this setting:**
    - **When enabled (YES):** The module will become active. For your store’s default language, the language ISO code (e.g., `/en/` if English is default) will be removed from all generated URLs. URLs for other languages will remain unchanged.
    - **When disabled (NO):** The module will be inactive. All URLs, including those for your default language, will continue to display the language ISO code (e.g., `/en/`, `/fr/`).
  - **Recommended value:** **YES**. The primary purpose of installing this module is to utilize its functionality, so enabling it is the standard recommendation.
  - **Merchant scenario / example:**
    - You’ve just installed the module and want your English (default) URLs to look like `www.yourstore.com/my-product`. You would set this to **YES**.
    - If you later decide you prefer the language ISO code to be present in all URLs for some reason (e.g., a specific SEO strategy change), you could set this to **NO** to revert the behavior without uninstalling the module.

**Important Note after Configuration:**
After enabling or disabling the module, it is highly recommended to:

1. **Clear your PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
2. **Regenerate your `.htaccess` file:** Go to **Shop Parameters > Traffic & SEO**, scroll down to the “Set up URLs” section, and click “Save” (even if you don’t change anything). This ensures that the URL rewriting rules are correctly updated.
3. **Test your URLs:** Browse your store in your default language and verify that the language ISO code is indeed removed from the URLs. Also, test other languages to ensure their URLs still contain the ISO code.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable module | YES | Controls whether the module removes the language ISO code from default language URLs. **YES** for cleaner URLs, **NO** to keep ISO codes for all languages. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but the language ISO code is still showing in my default language URLs. What should I do?**
A: This is usually a caching issue or `.htaccess` not being regenerated.
1. Go to **Advanced Parameters > Performance** and click “Clear cache”.
2. Go to **Shop Parameters > Traffic & SEO**, scroll to “Set up URLs”, and click “Save”.
3. Check your browser cache as well, or try browsing in an incognito/private window.

**Q: Will this module affect my non-default language URLs?**
A: No, the module is specifically designed to only remove the language ISO code for your *default* language. All other language versions will continue to display their respective ISO codes (e.g., `/fr/`, `/de/`).

**Q: Will this module break my existing SEO or create 404 errors for old URLs?**
A: The module works by overriding PrestaShop’s core URL generation and dispatching. It should handle redirects internally. However, for maximum safety, especially on established stores, it’s always a good idea to:
1. **Backup your database and files** before installation.
2. **Test thoroughly** on a staging environment first.
3. After enabling, monitor your server access logs and Google Search Console for any 404 errors. If you find any, you might need to manually add 301 redirects for specific old URLs to their new, cleaner versions in your `.htaccess` file, though this is rarely needed with this module.

**Q: My custom theme has some issues after installing the module. What could be wrong?**
A: This module primarily affects URL generation and routing, not visual display. It’s unlikely to directly cause theme issues. However, if your theme has very specific, hardcoded URL structures or relies on JavaScript that parses URLs in an unusual way, there’s a very small chance of conflict.
\* First, clear your Smarty cache (**Advanced Parameters > Performance**).
\* If the issue persists, temporarily disable the module to see if the problem disappears. If it does, contact MyPresta.eu support with details of the issue.

**Q: Does this module support all languages installed in PrestaShop?**
A: Yes, it supports all languages. It identifies your *default* language and removes its ISO code, while leaving the ISO codes for all other installed languages intact.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical implementation of the “Remove language ISO code from urls” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Remove language ISO code from urls” module achieves its functionality by overriding core PrestaShop classes responsible for URL generation (`Link`) and URL dispatching (`Dispatcher`). This allows it to intercept and modify how URLs are constructed and interpreted by PrestaShop, specifically targeting the removal of the language ISO code for the default language. It leverages PrestaShop’s override system to inject its custom logic without directly modifying core files.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. Its logic is primarily implemented through class overrides.

### 4.3 Core Classes & Models (`classes/`)

The module’s core functionality resides in its class overrides. These files are placed in `removeiso/override/classes/` to ensure PrestaShop’s override system picks them up.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Class Name:** `Dispatcher` (overrides PrestaShop’s core `Dispatcher` class)
  - **Parent Class:** `DispatcherCore`
  - **Responsibility:** This override is crucial for how PrestaShop *interprets* incoming URLs. It modifies the `dispatch()` method (or a related method) to correctly route requests that no longer contain the default language ISO code. When a URL like `www.yourstore.com/my-product` comes in, this overridden `Dispatcher` ensures PrestaShop understands it belongs to the default language, even without the `/en/` segment. It also likely handles the logic to ensure that if the default language ISO *is* present (e.g., `www.yourstore.com/en/my-product`), it’s redirected to the cleaner URL.
- **`removeiso/override/classes/Link.php`**
  - **Class Name:** `Link` (overrides PrestaShop’s core `Link` class)
  - **Parent Class:** `LinkCore`
  - **Responsibility:** This override is responsible for how PrestaShop *generates* outgoing URLs. It modifies methods like `getLanguageLink()`, `getProductLink()`, `getCategoryLink()`, etc., to prevent the inclusion of the language ISO code when the target language is the shop’s default language. This ensures that all links generated by PrestaShop (e.g., in templates, modules) for the default language are clean.
- **`removeiso/override/classes/Tools.php`**
  - **Class Name:** `Tools` (overrides PrestaShop’s core `Tools` class)
  - **Parent Class:** `ToolsCore`
  - **Responsibility:** The `Tools` class contains many utility functions. This override might be used to modify how certain global parameters or URL-related strings are handled, possibly in conjunction with the `Dispatcher` and `Link` overrides to ensure consistency across various URL manipulation tasks. It could, for instance, affect how `$_SERVER['REQUEST_URI']` is interpreted or how `Tools::redirect()` behaves in specific scenarios related to language codes.
- **`removeiso/override/classes/index.php`**
  - **Class Name:** N/A (empty file)
  - **Parent Class:** N/A
  - **Responsibility:** This is a standard security practice in PrestaShop modules to prevent directory listing if the `index.php` file is accessed directly. It contains no executable code.

### 4.4 JavaScript Assets (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Scope:** Back-office (likely loaded on the module configuration page).
  - **Responsibility:** Given the module’s function, this JS file is likely minimal. It might contain:
    - Simple event listeners for the configuration form (e.g., a “Save” button click).
    - AJAX calls to save configuration settings if the form uses asynchronous submission.
    - Basic UI enhancements or validation for the single “Enable/Disable” switch.
    - It does not appear to have any front-office responsibilities or complex client-side logic related to URL manipulation, as that is handled server-side by the PHP overrides.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. This indicates that its configuration interface relies on PrestaShop’s default Back Office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Scope:** Admin template for the module’s configuration page.
  - **Responsibility:** This template renders the module’s configuration form in the PrestaShop Back Office. It will contain the HTML structure for the “Enable / Disable module” switch and the standard PrestaShop form elements (e.g., `submit` button, `alert` messages). It’s typically rendered by the `getContent()` method of the main module class.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - This module does not create any custom database tables.
  - Its configuration settings (e.g., the “Enable/Disable” status) are stored in the `ps_configuration` table, using keys typically prefixed with `REMOVEISO_` or similar (e.g., `PS_REMOVEISO_ENABLED`).
- **Registered Hooks Table**:
  This module does not explicitly register to many standard PrestaShop hooks for its core functionality, as its primary mechanism is class overriding. The module’s `install()` method might register to `actionModuleInstall` or `actionModuleUninstall` for cleanup, but its runtime behavior is driven by the overridden classes.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content in the `<head>` section of front-office pages. | While not directly used for its core URL logic, a module might hook here to load JS/CSS or perform initial checks. (Not directly used by this module for its core function). |
| `displayRightColumn` / `displayLeftColumn` | Renders content in the side columns. | (Not directly used by this module). |
| `displayProduct` | Renders content on the product page. | (Not directly used by this module). |
| `displayFooter` | Renders content in the footer section. | (Not directly used by this module). |
| `actionDispatcherBefore` | Before the dispatcher processes the request. | The overridden `Dispatcher` class implicitly handles this, but a module could also use this hook for pre-dispatch logic. |
| `actionDispatcherAfter` | After the dispatcher has processed the request. | (Not directly used by this module). |
| `actionModuleInstall` | Executed when the module is installed. | To perform setup tasks like registering overrides, adding configuration to `ps_configuration`. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | To perform cleanup tasks like removing overrides, deleting configuration from `ps_configuration`. |

The core of this module’s operation is its class overrides, which are loaded automatically by PrestaShop’s autoloader system when the module is enabled, rather than relying on explicit hook registrations for its main URL manipulation.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Remove language ISO code from urls” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any technical issues or questions you may have regarding the module’s functionality.
