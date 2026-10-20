---
title: "CMS pages for logged only - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the CMS pages for logged only PrestaShop module by MyPresta.eu."
sidebar:
  label: "CMS pages for logged only - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy CMS pages for logged only Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/cms-pages-for-logged-only/)
>
> ---


# CMS pages for logged only

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “CMS pages for logged only” module. You will see a single configuration screen.

![CMS pages for logged only configuration screen example](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

This screen presents a list of all your existing CMS pages. For each page, you will see a simple switch to enable or disable the “logged only” restriction.

- **Setting Name:** `cmsp` (This is the internal identifier, you’ll see the actual CMS page titles).
- **What this setting does:** This setting allows you to select which specific CMS pages will be restricted to logged-in customers only. Each row represents one of your store’s CMS pages.
- **Effect of changing this setting:**
  - *When enabled (switch is ON/green):* The selected CMS page will only be accessible to customers who are logged into their accounts. If an unlogged customer tries to visit this page, they will be redirected to the login page. After successful login, they will be sent back to this specific CMS page.
  - *When disabled (switch is OFF/red):* The selected CMS page will be publicly accessible to all visitors, whether they are logged in or not. This is the default behavior for all CMS pages in PrestaShop.
- **Recommended value:** This depends entirely on your business needs. Enable it for any CMS page that contains sensitive, exclusive, or members-only information.
- **Merchant scenario / example:**
  - You have a “Wholesale Terms & Conditions” CMS page. You would enable the switch next to this page so only your registered wholesale clients can view it.
  - You create a “Premium Content Guide” CMS page for loyal customers. You would enable the switch for this page to encourage registration and reward existing customers.
  - You have a standard “About Us” page. You would leave the switch disabled, as this page should be publicly visible to all visitors.

After making your selections, remember to click the **“Save”** button at the bottom of the page to apply your changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Individual CMS Page Switches | Disabled (OFF) | Controls whether a specific CMS page requires a customer to be logged in to view it. Enabling redirects unlogged users to the login page, then back to the CMS page after successful login. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the restriction for a CMS page, but unlogged users can still see it. What’s wrong?**
A:

1. **Clear Cache:** The most common reason is caching. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” in older versions). Your browser cache might also need clearing.
2. **Save Configuration:** Ensure you clicked the “Save” button on the module’s configuration page after enabling the restriction for the specific CMS page.
3. **Check CMS Page URL:** Double-check that you are testing the correct URL for the CMS page you restricted.

**Q: After logging in, the customer is redirected to the homepage instead of the restricted CMS page. Why?**
A: This module is designed to redirect the customer back to the original restricted CMS page after successful login. If this isn’t happening, it might be due to:

1. **Custom Login Redirects:** Another module or a custom theme modification might be overriding PrestaShop’s default login redirection behavior. Temporarily disable other modules that affect login/redirection to test.
2. **PrestaShop Version Specifics:** While the module is compatible with many versions, very specific theme or core overrides in older/newer PrestaShop versions might interfere. Ensure your PrestaShop core files are standard.

**Q: Can I restrict categories or products instead of CMS pages?**
A: No, this module is specifically designed for CMS pages only. It does not provide functionality to restrict categories, products, or other types of content. You would need a different module for those purposes.

**Q: Does this module affect SEO?**
A: When a page is restricted, search engine crawlers (like Googlebot) will typically be redirected to the login page, just like a human user. This means the content of the restricted CMS page will not be indexed by search engines. If the content is meant to be public and indexed, do not restrict it with this module. For content that should be hidden from search engines but still accessible to logged-in users, this behavior is desired.

**Q: How do I translate the module’s text (if any)?**
A: This module has very little front-office text, as it primarily handles redirection. Any messages related to login are handled by PrestaShop’s core authentication page. If there were any module-specific texts, you would translate them via **International > Translations** in your Back Office. Select “Installed modules translations,” choose your theme, and then find “CMS pages for logged only” in the list.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “CMS pages for logged only” module (`privatecms`) primarily operates by overriding the core `CmsController` to intercept requests for CMS pages. It checks if a requested CMS page is configured for “logged only” access and, if the user is not logged in, triggers a redirection to the authentication page. Upon successful login, PrestaShop’s default redirection mechanism (which the module leverages) sends the user back to the originally requested page. Configuration is managed through a standard `getContent()` method in the main module file, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `override/controllers/front/CmsController.php`
    - **Class Name:** `CmsController` (overrides the core PrestaShop `CmsController`)
    - **Parent Class:** `CmsControllerCore`
    - **Responsibility:** This override is the core of the module’s functionality. It intercepts the `init()` method of the `CmsController`. Before the CMS page is rendered, it checks if the current CMS page ID (`$this->cms->id`) is present in the list of restricted pages stored in the module’s configuration. If the page is restricted and the customer is not logged in (`$this->context->customer->isLogged()`), it redirects the user to the authentication page (`$this->context->link->getPageLink('authentication')`). It also includes a `back` parameter in the redirection URL, ensuring that PrestaShop redirects the user back to the original CMS page after successful login.
- **Back-Office Admin Controllers**: None. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

None. The module does not define any custom classes or `ObjectModel` entities. It directly interacts with existing PrestaShop core classes like `Configuration`, `Cms`, `Customer`, and `Link`.

### 4.4 JavaScript Assets (`views/js/`)

None. The module does not include any custom JavaScript files. Its functionality is purely server-side (PHP-based redirection).

### 4.5 CSS Stylesheets (`views/css/`)

- `privatecms/css.css`
  - **Scope:** Back-office admin form styling.
  - **Main UI components and containers it styles:** This stylesheet likely contains minimal styling for the module’s configuration form in the PrestaShop Back Office, ensuring the layout and elements (like the list of CMS pages and switches) are displayed correctly and consistently with the PrestaShop admin theme.
  - **Key CSS class selectors developers can override:** Specific selectors would be found within the file, typically targeting elements within the `admin.tpl` template.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - `privatecms/admin.tpl`
    - **Purpose:** This template is rendered by the `getContent()` method of the main module file (`privatecms.php`). It displays the list of all available CMS pages in the Back Office, along with a toggle switch for each page, allowing the administrator to enable or disable the “logged only” restriction. It iterates through the CMS pages and displays their titles and the current status of the restriction (checked/unchecked).

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom SQL tables.
  - Configuration is stored in the `ps_configuration` table (or `_configuration` prefix).
    - **Key:** `cmsp`
    - **Value:** A serialized array (or JSON string, depending on PrestaShop version and module implementation) containing the IDs of the CMS pages that are selected for “logged only” access.
- **Registered Hooks Table**:
  The module does not explicitly register any standard PrestaShop hooks in its `install()` method. Its core functionality relies on overriding the `CmsController`, which is a more direct way to intercept CMS page requests.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | During `CmsController` initialization | Intercepts CMS page requests to check for logged-in status and redirect if necessary. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “CMS pages for logged only” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions regarding the module’s functionality and compatibility.
