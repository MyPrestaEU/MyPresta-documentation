---
title: "Geolocation pro - currency and language by country - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Geolocation pro - currency and language by country PrestaShop module by MyPresta.eu."
sidebar:
  label: "Geolocation pro - currency and language by country - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Geolocation pro - currency and language by country Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Geolocation pro - currency and language by country

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required and usually available on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Geolocation pro - currency and language by country)

This is the main configuration screen where you enable or disable the module’s core functionality and access diagnostic tools.

- **Enable Geolocation Pro:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively detect customer locations and apply your defined currency and language rules.
    - *When disabled:* The module will be inactive, and your store will revert to its default currency and language settings for all visitors, regardless of their location.
  - **Recommended value:** YES (to utilize the module’s features).
  - **Merchant scenario / example:** You’ve finished setting up all your rules and are ready to go live with personalized experiences. Enable this switch. If you need to temporarily disable the feature for maintenance, switch it off.
- **Show banner with country choice:**

  - **What this setting does:** Determines if a small banner or pop-up appears to inform customers about the detected country and offer them a choice to change it.
  - **Effect of changing this setting:**
    - *When enabled:* A banner will appear (usually at the top or bottom of the screen) showing the detected country and potentially allowing the customer to manually override the detected location, currency, or language. This can be useful for customers using VPNs or those who prefer a different region’s settings.
    - *When disabled:* No banner will be shown. The module will silently apply the rules based on IP detection.
  - **Recommended value:** YES (initially, to give customers control, then consider NO if you prefer a completely seamless experience and trust the IP detection).
  - **Merchant scenario / example:** A customer from the USA is visiting your store, and the module correctly detects their location. If this setting is enabled, a banner might say “You are browsing from the United States. [Change country?]” This gives them a chance to correct it if they’re using a VPN or prefer to shop from a different region.
- **Diagnostics & Tools:**

  - **What this setting does:** This section provides tools to test the module’s functionality and verify IP detection. It’s not a setting to change, but a utility.
  - **Effect of changing this setting:** Clicking on the diagnostic tools will open new views or pop-ups that show you information about your current IP address, detected country, and how the module would apply rules.
  - **Recommended value:** Use this whenever you are setting up new rules or troubleshooting.
  - **Merchant scenario / example:** You’ve created a rule for Germany. You can use the diagnostic tool to simulate a visit from Germany and see if the correct currency and language are applied, ensuring your rules work as expected.

### 2.2 Dedicated Admin Screen: Geo Rules (Back Office > Modules > Geolocation pro > Geo Rules)

This screen allows you to define and manage the core rules for currency and language based on country.

- **Screen Name & Menu Location:** **Back Office > Modules > Geolocation pro - currency and language by country > Geo Rules** (or similar path under the module’s main menu item).
- **Available Actions & Settings:**
  - **Listing Table:** Displays all your existing geo-rules, showing the country, the assigned currency, and the assigned language.
  - **Add New Geo Rule:** A button to create a new rule.
  - **Edit/Delete Actions:** Icons next to each rule to modify or remove it.
- **Effect of changes:**
  - **Adding a new rule:** When you add a rule (e.g., for “Germany” to use “EUR” and “German”), any visitor detected as being from Germany will automatically have their currency and language set to these values.
  - **Editing a rule:** Modifying an existing rule will instantly change how the module behaves for visitors from that specific country.
  - **Deleting a rule:** Removing a rule means that visitors from that country will no longer have a specific currency or language applied by this module and will revert to your store’s default settings.
- **Recommended workflow for daily store management:**
  1. **Identify target countries:** Decide which countries you want to target with specific currencies and languages.
  2. **Ensure currencies/languages are enabled:** Make sure the currencies and languages you want to assign are already enabled in your PrestaShop store (Back Office > International > Currencies / Languages).
  3. **Create rules:** For each country, click “Add New Geo Rule,” select the country from the dropdown, then select the desired currency and language. Save the rule.
  4. **Test with diagnostics:** Use the module’s diagnostic tools to verify your rules are working as intended.

### 2.3 Dedicated Admin Screen: Language Rules (Back Office > Modules > Geolocation pro > Language Rules)

This screen appears to be a duplicate or an alternative interface for managing language-specific rules, potentially offering more granular control or a different view. Given the module’s description, the “Geo Rules” screen is likely the primary interface for country-based assignments. This screen might be for more advanced, language-specific overrides not tied directly to a country.

- **Screen Name & Menu Location:** **Back Office > Modules > Geolocation pro - currency and language by country > Language Rules** (or similar path).
- **Available Actions & Settings:**
  - **Listing Table:** Shows existing language rules.
  - **Add New Language Rule:** Button to create a new rule.
  - **Edit/Delete Actions:** Icons to modify or remove rules.
- **Effect of changes:** These rules would likely override or complement the country-based rules for language. For example, you might have a general rule for “English” for all non-specified countries, and then use this screen for exceptions or specific language behaviors.
- **Recommended workflow for daily store management:** Use this screen if you need to manage language settings independently of country-specific geo-rules, or if you encounter scenarios where a country rule isn’t sufficient for language handling. Otherwise, focus on the “Geo Rules” screen.

### 2.4 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Geolocation Pro | YES | Master switch for module functionality. YES activates country-based currency/language detection. |
|  | Show banner with country choice | YES | Displays a banner informing customers of detected country and allowing manual override. |
|  | Diagnostics & Tools | N/A | Utility to test IP detection and rule application. |
| **Geo Rules** | Add/Edit Geo Rule (Country, Currency, Language) | N/A | Defines which currency and language are automatically set for visitors from a specific country. |
| **Language Rules** | Add/Edit Language Rule | N/A | (Potentially) Defines language overrides or specific language behaviors, possibly independent of country. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are still seeing the wrong currency/language even after I set up rules. What’s wrong?**
A1:

- **Is the module enabled?** Double-check the “Enable Geolocation Pro” setting on the main configuration page.
- **Are your rules correct?** Go to “Geo Rules” and ensure the country, currency, and language are correctly assigned.
- **Are the currencies/languages enabled in PrestaShop?** Make sure the currencies and languages you’re trying to assign are active in your PrestaShop (International > Currencies / Languages).
- **Clear your browser cache:** Sometimes your browser might cache old settings. Ask customers to clear their browser cache or try an incognito window.
- **Clear PrestaShop cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
- **Test with Diagnostics:** Use the module’s built-in diagnostic tools to simulate a visit from a specific country and see what currency/language it applies. This helps pinpoint if the issue is with detection or rule application.

**Q2: The module detects the wrong country for some customers. Why?**
A2:

- **VPNs and Proxies:** Customers using Virtual Private Networks (VPNs) or proxy servers will appear to be browsing from the location of their VPN/proxy, not their actual physical location. The module relies on IP address detection, which can be spoofed.
- **IP Database Accuracy:** Geolocation databases are generally very accurate but not 100% perfect. Some IP ranges might be misidentified.
- **“Show banner with country choice”:** If this setting is enabled, customers can manually correct the detected country, which is the best solution for these edge cases.

**Q3: How do I add a new currency or language to my store so I can use it in a geo-rule?**
A3:

- **Adding a Currency:** Go to **International > Currencies** in your PrestaShop Back Office. Click “Add new currency,” fill in the details, and enable it.
- **Adding a Language:** Go to **International > Languages** in your PrestaShop Back Office. Click “Add new language,” fill in the details, and enable it. Remember to also install language packs and translate your content for the new language.

**Q4: Will this module slow down my website?**
A4: The module performs a quick IP lookup and rule application, which is generally very fast and optimized. It should not noticeably impact your website’s loading speed. If you experience any performance issues, ensure your PrestaShop cache is enabled and regularly cleared.

**Q5: I want to style the country choice banner to match my theme. How can I do that?**
A5: The banner uses specific CSS classes. While direct modification of module files is not recommended (as updates would overwrite them), a web developer can use your theme’s custom CSS file to override the default styles. They would inspect the banner using browser developer tools to identify the relevant CSS selectors (e.g., classes like `.progeo-banner`, `.progeo-choice`) and then apply their own styles.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Geolocation pro - currency and language by country” module (`progeo`) is designed to integrate deeply with PrestaShop’s core internationalization features. It primarily leverages overrides to modify how PrestaShop determines the active `Configuration`, `Currency`, and `Language` based on the visitor’s IP address. It follows a standard PrestaShop module structure, utilizing front and admin controllers, custom classes (especially for `ObjectModel` entities), and Smarty templates for both configuration and front-office display (e.g., the country choice banner). The module’s core logic resides in its `index.php` (main module file) and the overridden core classes.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `progeo/controllers/front/choice.php`
  - **Class name & parent class:** `ProgeoChoiceModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller handles AJAX requests related to the country choice banner. When a customer interacts with the banner (e.g., selects a different country, currency, or language), this controller processes the request, updates session variables or cookies, and potentially redirects the user to apply the new settings. It’s crucial for the interactive aspect of the banner.
- `progeo/controllers/front/index.php`
  - **Class name & parent class:** `ProgeoIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a fallback or a simple entry point for front-office module actions, though `choice.php` is more specific to the banner’s interactivity. In many modules, `index.php` in `controllers/front` is a placeholder or handles very basic, non-specific front-office requests.

#### Back-Office Admin Controllers

- `progeo/controllers/admin/AdminGeorulesController.php`
  - **Tab name and managed entity:** “Geo Rules” (under the module’s main menu). Manages `Georule` entities.
  - **Responsibility:** This is the primary controller for managing country-specific currency and language assignments. It provides the CRUD (Create, Read, Update, Delete) interface for `ps_progeo_georule` records, allowing administrators to define which currency and language should be active for visitors from specific countries. It extends `AdminController` and uses `HelperList` for the grid and `HelperForm` for add/edit forms.
- `progeo/controllers/admin/AdminLangrules.php`
  - **Tab name and managed entity:** “Language Rules” (under the module’s main menu). Manages `Langrule` entities.
  - **Responsibility:** This controller manages language-specific rules. It provides a CRUD interface for `ps_progeo_langrule` records. It’s likely used for more granular language control, potentially overriding or complementing the language set in `AdminGeorulesController`.
- `progeo/controllers/admin/AdminLangrulesController.php`
  - **Tab name and managed entity:** “Language Rules” (under the module’s main menu). Manages `Langrule` entities.
  - **Responsibility:** This appears to be a duplicate or an alternative implementation of `AdminLangrules.php`. In a typical PrestaShop module, `AdminLangrulesController.php` would be the standard naming convention. Developers should verify which file is actually being used by the module’s menu registration.
- `progeo/controllers/admin/index.php`
  - **Tab name and managed entity:** Not a direct tab, but a standard placeholder.
  - **Responsibility:** This file is often present in `controllers/admin` directories but typically empty or contains basic security measures (e.g., `die('Forbidden');`). It doesn’t manage a specific entity or provide a UI.

### 4.3 Core Classes & Models (`classes/`)

The module uses overrides to inject its logic into PrestaShop’s core behavior.

- `progeo/override/classes/Configuration.php`
  - **Responsibility:** Overrides the core `Configuration` class. This is critical for the module to modify global configuration values (like `PS_CURRENCY_DEFAULT` or `PS_LANG_DEFAULT`) on the fly based on geolocation, without actually changing the database values for other visitors. It ensures that when PrestaShop requests a configuration value, the module can intercept and return a localized one.
- `progeo/override/classes/Currency.php`
  - **Responsibility:** Overrides the core `Currency` class. This override allows the module to manipulate which currency is considered “active” or “default” for the current visitor, ensuring that prices are displayed correctly according to the geo-rule.
- `progeo/override/classes/Language.php`
  - **Responsibility:** Overrides the core `Language` class. Similar to `Currency.php`, this override enables the module to set the active language for the current visitor based on geolocation, ensuring content is displayed in the correct language.
- `progeo/override/classes/index.php`
  - **Responsibility:** Standard empty `index.php` file for security in a directory.
- `progeo/override/classes/_Configuration.php`
  - **Responsibility:** This file name suggests a potential backup or an older version of the `Configuration` override. In a production environment, only one `Configuration.php` override should be active. Developers should verify the module’s installation process to ensure the correct override is used.

### 4.4 JavaScript Assets (`views/js/`)

- `progeo/views/js/banner.js`
  - **Scope:** Front-office.
  - **Responsibility:** This script handles the interactive country choice banner.
    - **Event listeners:** Binds events to elements within the banner (e.g., click events on “change country” buttons, select box changes for currency/language).
    - **AJAX calls:** Makes AJAX requests to the `ProgeoChoiceModuleFrontController` (e.g., `choice.php`) to update the user’s selected country, currency, or language.
    - **DOM manipulation:** Shows/hides the banner, updates text content based on user selections, and potentially redirects the browser after a choice is made.
    - **Cookies/Local Storage:** May store user preferences in cookies or local storage to remember their choice across sessions.

### 4.5 CSS Stylesheets (`views/css/`)

- `progeo/views/css/admin.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides specific styling for the module’s configuration pages and admin controllers (e.g., `AdminGeorulesController`, `AdminLangrulesController`). This ensures a consistent look and feel within the PrestaShop back office and enhances the usability of the module’s forms and lists.
- `progeo/views/css/banner.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Styles the country choice banner that appears on the front office. It defines the banner’s position, colors, fonts, responsiveness, and overall visual presentation. Developers can override these styles in their theme’s custom CSS to integrate the banner seamlessly with the store’s design. Key selectors might include `.progeo-banner`, `.progeo-choice-form`, etc.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `progeo/views/displayHeader.tpl`: This template is likely hooked into `displayHeader` (or `actionFrontControllerSetMedia`) to include necessary CSS and JS files for the front-office banner, or to inject initial JavaScript variables.
- **Admin templates (`views/templates/admin/`)**:
  - `progeo/views/advert.tpl`: Likely used for displaying promotional messages or links to other MyPresta.eu modules within the module’s configuration.
  - `progeo/views/banner.tpl`: This template is probably used within the module’s configuration to preview or manage settings related to the front-office banner.
  - `progeo/views/currenciesForm.tpl`: Template for managing currency-related settings, possibly within the main configuration or a dedicated admin screen.
  - `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl`: These templates are used to render the various diagnostic tools and their output, helping the admin troubleshoot IP detection and rule application.
  - `progeo/views/languagesForm.tpl`: Template for managing language-related settings, similar to `currenciesForm.tpl`.
  - `progeo/views/tabs.tpl`: Used for rendering navigation tabs within the module’s configuration interface, allowing the admin to switch between different settings sections (e.g., “Geo Rules”, “Language Rules”, “Configuration”).
  - `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl`: Templates for displaying hints or general tools within the module’s back-office interface.
- **Front-office templates (`views/templates/front/`)**:
  - `progeo/views/banner.tpl`: This is the actual template for the front-office country choice banner, rendered to the customer. It contains the HTML structure for displaying the detected country, currency, language, and options for manual selection.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_progeo_georule`: Stores the main geolocation rules.
    - `id_progeo_georule` (Primary Key)
    - `id_country` (Foreign key to `ps_country`)
    - `id_currency` (Foreign key to `ps_currency`)
    - `id_lang` (Foreign key to `ps_lang`)
  - `ps_progeo_langrule`: Stores language-specific rules (details would depend on its specific implementation, but likely similar structure for language overrides).
    - `id_progeo_langrule` (Primary Key)
    - `id_lang` (Foreign key to `ps_lang`)
    - (Potentially other fields for specific language behaviors)
  - Configuration records in `ps_configuration`:
    - `PROGEO_ENABLED`: (1 or 0) Master switch for the module.
    - `PROGEO_SHOW_BANNER`: (1 or 0) Whether to display the country choice banner.
    - (Other configuration keys as defined in `getContent()` and `install()`)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | To include CSS and JavaScript assets (`banner.css`, `banner.js`) for the front-office banner, and potentially to inject initial JavaScript variables or render the banner itself. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media assets. | Similar to `displayHeader`, used for adding CSS and JS files conditionally or in a more modern PrestaShop way. |
| `actionModuleInstall` | During module installation. | To create database tables (`ps_progeo_georule`, `ps_progeo_langrule`), register hooks, and set default configuration values. |
| `actionModuleUninstall` | During module uninstallation. | To remove database tables, unregister hooks, and clean up configuration values. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | To include `admin.css` for module configuration pages and potentially admin-specific JavaScript. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media assets. | Similar to `displayBackOfficeHeader`, for adding admin CSS and JS. |
| `actionDispatcherBefore` | Before the dispatcher processes a request. | Crucial for the module’s core logic: to detect the visitor’s IP, apply the geo-rule, and set the correct `Context` currency and language *before* PrestaShop renders the page. This is where the overrides are effectively triggered. |
| `displayBanner` (Custom Hook) | Potentially a custom hook for rendering the front-office banner. | If `displayBanner` is a custom hook, the module would register itself to render `banner.tpl` in this specific location. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Geolocation pro - currency and language by country” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions optimally and integrates seamlessly with your PrestaShop store.
