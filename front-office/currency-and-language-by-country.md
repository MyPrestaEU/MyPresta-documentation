---
title: "Currency and language by country - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Currency and language by country PrestaShop module by MyPresta.eu."
sidebar:
  label: "Currency and language by country - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Currency and language by country Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/currency-and-language-by-country/)
>
> ---


# Currency and language by country

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment. No special extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the “Currency and language by country” module. You’ll find all settings here to define how your store adapts to visitors from specific countries.

**Access:** Back Office > Modules > Module Manager > Search for “Currency and language by country” > Click “Configure”.

#### **1. Select country**

- **What this setting does:** This dropdown allows you to choose the specific country for which you want to apply the automatic language and currency changes.
- **Effect of changing this setting:** When you select a country (e.g., “France”), the module will then apply the language and currency settings you define below *only* for visitors detected as coming from that country. If you don’t select a country, the module won’t apply any geo-localization rules.
- **Recommended value:** Select the country you wish to target first. You can only configure one country at a time with this free version.
- **Merchant scenario / example:** If you want visitors from Germany to see your store in German with Euro currency, you would select “Germany” here.

#### **2. Turn on language change by visitor**

- **What this setting does:** This switch controls whether the module should automatically change the store’s language for visitors from the selected country.
- **Effect of changing this setting:**
  - *When enabled (“Enabled”):* The module will attempt to switch the store’s front-office language to the one you specify in the “Select language” setting below, for visitors from the chosen country.
  - *When disabled (“Disabled”):* The language will not be automatically changed, even if you’ve selected a language below. The visitor will see the store in your default language or their browser’s preferred language (if PrestaShop’s default behavior allows).
- **Recommended value:** “Enabled” if you want to provide a localized language experience.
- **Merchant scenario / example:** If you selected “France” as the country, enabling this setting means you can then choose “French” as the language for French visitors.

#### **3. Select language**

- **What this setting does:** This dropdown appears only if “Turn on language change by visitor” is enabled. It allows you to choose which language will be set for visitors from the selected country.
- **Effect of changing this setting:** The store’s front-office language will automatically switch to the selected language for visitors from the chosen country. Make sure this language is already installed and enabled in your PrestaShop store (Back Office > International > Languages).
- **Recommended value:** The official language of the country you selected.
- **Merchant scenario / example:** If you selected “Spain” as the country and enabled language change, you would select “Spanish” here.

#### **4. Turn on currency change by visitor**

- **What this setting does:** This switch controls whether the module should automatically change the store’s currency for visitors from the selected country.
- **Effect of changing this setting:**
  - *When enabled (“Enabled”):* The module will attempt to switch the store’s front-office currency to the one you specify in the “Select Currency” setting below, for visitors from the chosen country.
  - *When disabled (“Disabled”):* The currency will not be automatically changed. Prices will be displayed in your store’s default currency or the currency manually selected by the customer.
- **Recommended value:** “Enabled” if you want to display prices in the local currency.
- **Merchant scenario / example:** If you selected “United States” as the country, enabling this setting means you can then choose “US Dollar” as the currency for US visitors.

#### **5. Select Currency**

- **What this setting does:** This dropdown appears only if “Turn on currency change by visitor” is enabled. It allows you to choose which currency will be set for visitors from the selected country.
- **Effect of changing this setting:** All prices in the store’s front-office will automatically switch to the selected currency for visitors from the chosen country. Make sure this currency is already installed and enabled in your PrestaShop store (Back Office > International > Currencies).
- **Recommended value:** The official currency of the country you selected.
- **Merchant scenario / example:** If you selected “Japan” as the country and enabled currency change, you would select “Japanese Yen” here.

#### **Important Note on Overrides:**

This module uses PrestaShop’s override system to modify core currency and language behavior. If you have other modules that also use overrides for `Currency.php` or `Language.php`, there might be conflicts. Always test thoroughly after installation.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Select country | Your target country | Defines the country for which rules apply. |
| Module Configuration | Turn on language change by visitor | Enabled | Activates automatic language switching for the selected country. |
| Module Configuration | Select language | Country’s official language | Sets the specific language for visitors from the chosen country. |
| Module Configuration | Turn on currency change by visitor | Enabled | Activates automatic currency switching for the selected country. |
| Module Configuration | Select Currency | Country’s official currency | Sets the specific currency for visitors from the chosen country. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The language/currency isn’t changing for visitors from the selected country. What should I check?**
A:

1. **Module Enabled:** Ensure the “Currency and language by country” module is installed and enabled in Module Manager.
2. **Configuration Saved:** Double-check that you’ve selected a country, enabled the respective language/currency change options, chosen the correct language/currency, and clicked “Save” on the module’s configuration page.
3. **Language/Currency Installed & Enabled:** Verify that the target language and currency are installed and enabled in your PrestaShop Back Office (International > Languages and International > Currencies).
4. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.
5. **Geolocation Accuracy:** Geolocation services aren’t always 100% accurate. Test with a VPN to ensure your IP is correctly identified as coming from the target country.

**Q: Can I configure different languages/currencies for multiple countries?**
A: The free “Currency and language by country” module allows you to configure rules for only one country at a time. If you need advanced multi-country targeting, consider upgrading to the “Geolocation Pro” module by MyPresta.eu, which offers more extensive features.

**Q: My store’s default language/currency is still showing even after configuration.**
A: This module specifically targets visitors from the *selected* country. For all other visitors, your store’s default language and currency will apply, or their browser’s preferred settings if PrestaShop is configured to respect them. Ensure you are testing from the exact country you configured.

**Q: I installed another module, and now the language/currency switching isn’t working.**
A: This module uses PrestaShop’s override system. If another module also overrides `classes/Currency.php` or `classes/Language.php`, there might be a conflict. Check your `app/config/parameters.php` (for PS 1.7+) or `config/settings.inc.php` (for PS 1.6) for `_PS_MODE_DEV_` and set it to `true` to see error messages. You might need to contact support for assistance in resolving override conflicts.

**Q: How does the module detect the visitor’s country?**
A: The module uses the visitor’s IP address to determine their geographical location. This is a standard method for geolocation.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Currency and language by country” module.

### 4.1 Architecture Overview

The “Currency and language by country” module (`freegeo`) is a lightweight PrestaShop module primarily designed to modify the default language and currency based on a visitor’s IP address. It achieves this by leveraging PrestaShop’s override system for core `Currency` and `Language` classes, and by hooking into the `actionDispatcherBefore` event to perform the geolocation logic before the main page content is rendered. The module’s configuration is handled via the standard `getContent()` method in the main module file.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office controllers. Its logic is primarily executed via hooks and class overrides.

### 4.3 Core Classes & Models (`classes/`)

The module utilizes PrestaShop’s override system to inject its logic into core functionalities.

- **`freegeo/override/classes/Currency.php`**

  - **Class name:** `Currency` (overrides the core `Currency` class)
  - **Parent class:** `CurrencyCore`
  - **Responsibility:** This override is crucial for setting the currency based on geolocation. It modifies the behavior of how the active currency is determined. The module’s logic within this override will check if the `FREEGEO_CURRENCY_ON` setting is enabled and if the visitor’s country matches the configured `FREEGEO_COUNTRY`. If so, it will attempt to force the currency to `FREEGEO_CURRENCY`.
  - **Key methods:** The override likely modifies methods related to `getCurrent()` or `getCurrency()` to inject the geo-localized currency ID.
- **`freegeo/override/classes/Language.php`**

  - **Class name:** `Language` (overrides the core `Language` class)
  - **Parent class:** `LanguageCore`
  - **Responsibility:** Similar to the `Currency` override, this class is responsible for setting the language based on geolocation. It checks `FREEGEO_LANGUAGE_ON` and `FREEGEO_COUNTRY` and, if conditions are met, forces the language to `FREEGEO_LANGUAGE`.
  - **Key methods:** The override likely modifies methods related to `getCurrentLanguage()` or `getLanguage()` to inject the geo-localized language ID.
- **`freegeo/override/classes/index.php`**

  - **Purpose:** This is a standard empty `index.php` file, typically placed in directories to prevent directory listing on web servers, enhancing security. It has no functional impact on the module’s logic.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. All its functionality is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Its functionality does not involve any specific front-office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`freegeo/views/advert.tpl`**
  - **Scope:** Back-office (module configuration page).
  - **Purpose:** This template is likely used to display an advertisement or promotional message for the “Geolocation Pro” module by MyPresta.eu on the module’s configuration page. It serves as a marketing element within the admin interface.
  - **Hook:** This template is rendered within the `getContent()` method of the main module file, typically before or after the main configuration form.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. It stores its configuration settings directly in PrestaShop’s `ps_configuration` table.
- **Configuration Records in `ps_configuration`**:

  - `FREEGEO_CURRENCY_ON`: Stores a boolean (0 or 1) indicating if currency change is enabled.
  - `FREEGEO_LANGUAGE_ON`: Stores a boolean (0 or 1) indicating if language change is enabled.
  - `FREEGEO_CURRENCY`: Stores the ID of the currency to be set (e.g., `id_currency`).
  - `FREEGEO_LANGUAGE`: Stores the ID of the language to be set (e.g., `id_lang`).
  - `FREEGEO_COUNTRY`: Stores the ISO code or ID of the country to target.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller sets its media assets (JS/CSS). | While listed, this module likely uses it minimally or for specific admin-side script/style loading if any were present (none detected in inventory). |
| `actionDispatcherBefore` | Executed very early in the PrestaShop request lifecycle, before the dispatcher processes the URL. | **CRITICAL HOOK:** This is where the module’s core geolocation logic resides. It’s used to detect the visitor’s IP, determine their country, and then, based on module settings, potentially override the `Context::getContext()->language` and `Context::getContext()->currency` before the page is rendered. |
| `actionFrontControllerAfterInit` | Executed after a Front Controller has been initialized. | This hook could be used to perform additional checks or adjustments after the main controller is set up, but before rendering. It might serve as a fallback or supplementary point for language/currency adjustments if `actionDispatcherBefore` isn’t sufficient in all scenarios. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Currency and language by country” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
