---
title: "Multistore localization settings - language and currency - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Multistore localization settings - language and currency PrestaShop module by MyPresta.eu."
sidebar:
  label: "Multistore localization settings - language and currency - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Multistore localization settings - language and currency Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Multistore localization settings - language and currency

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your hosting environment must support the PrestaShop Multistore feature.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module introduces a new menu item in your PrestaShop Back Office to manage the localization rules for each of your shops.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you first click “Configure” after installation, you’ll land on a basic configuration page. This page primarily serves as an entry point to the main management interface.

- **What this setting does:** This screen will likely contain a simple message or a button directing you to the dedicated management area for Multistore localization rules. It might also include information about the module version or a link to support.
- **Effect of changing this setting:** Clicking any button or link here will navigate you to the main interface where you define your shop-specific language and currency rules.
- **Recommended value:** Follow the instructions on the screen, usually by clicking a button to proceed to the main configuration.
- **Merchant scenario / example:** After installing, you’ll see a message like “Click here to manage your Multistore localization rules.” You’ll click this to access the core functionality.

### 2.2 Dedicated Admin Screen: Multistore Localization Rules (Back Office > Multistore Localization Rules)

This is the main control panel for the module. You’ll find this new menu item under **Shop Parameters > Multistore Localization Rules** (or similar, depending on your PrestaShop version and menu structure).

Upon entering this screen, you will see a list (grid) of your existing shops. For each shop, you will be able to define its specific language and currency settings.

**Available Actions & Settings:**

1. **Shop List / Grid View:**

   - **Purpose:** This table displays all the shops you have configured in your PrestaShop Multistore setup.
   - **Columns:** You’ll typically see columns like “Shop Name” and potentially “Actions” or “Configure.”
   - **Effect of changes:** This view allows you to quickly see which shops are configured and provides the entry point to edit their localization settings.
2. **Edit/Configure Button for Each Shop:**

   - **What this button does:** Clicking this button (often a pencil icon) next to a shop name will open a detailed configuration form specifically for that shop.
   - **Effect of changing this setting:** This is where you define the specific languages and currencies for the selected shop.

**Inside the Shop-Specific Configuration Form:**

When you click to edit a shop, you will see two main sections: **Languages** and **Currencies**.

#### 2.2.1 Languages Configuration for [Shop Name]

- **Available Languages List:**

  - **What this setting does:** This section presents a list of all languages installed in your PrestaShop store. For each language, you’ll typically see a checkbox.
  - **Effect of changing this setting:**
    - *When checked:* The language will be available for selection by customers in the front office of this specific shop.
    - *When unchecked:* The language will NOT be shown in the language selector for this shop, and customers will not be able to switch to it.
  - **Recommended value:** Check only the languages relevant to the target audience of this specific shop.
  - **Merchant scenario / example:** For your “French Store,” you would check “Français (French)” and uncheck all other languages.
- **Default Language for [Shop Name]:**

  - **What this setting does:** A dropdown or radio button selection allowing you to choose one of the *enabled* languages as the default for this shop.
  - **Effect of changing this setting:** When a customer first visits this shop, it will automatically load in the selected default language. If the customer has previously selected a language, their preference might be remembered, but for new visitors, this default applies.
  - **Recommended value:** Set the primary language for the shop’s target audience.
  - **Merchant scenario / example:** For your “French Store,” you would set “Français (French)” as the default language.

#### 2.2.2 Currencies Configuration for [Shop Name]

- **Available Currencies List:**

  - **What this setting does:** This section presents a list of all currencies installed in your PrestaShop store. For each currency, you’ll typically see a checkbox.
  - **Effect of changing this setting:**
    - *When checked:* The currency will be available for selection by customers in the front office of this specific shop. Prices will be displayed in this currency if selected.
    - *When unchecked:* The currency will NOT be shown in the currency selector for this shop, and customers will not be able to view prices in it.
  - **Recommended value:** Check only the currencies relevant to the target audience of this specific shop.
  - **Merchant scenario / example:** For your “US Store,” you would check “US Dollar ($)” and uncheck “Euro (€)” and other currencies.
- **Default Currency for [Shop Name]:**

  - **What this setting does:** A dropdown or radio button selection allowing you to choose one of the *enabled* currencies as the default for this shop.
  - **Effect of changing this setting:** When a customer first visits this shop, all prices will automatically be displayed in the selected default currency.
  - **Recommended value:** Set the primary currency for the shop’s target audience.
  - **Merchant scenario / example:** For your “US Store,” you would set “US Dollar ($)” as the default currency.

**Recommended workflow for daily store management:**

1. Navigate to **Shop Parameters > Multistore Localization Rules**.
2. Identify the shop you wish to configure from the list.
3. Click the “Edit” or “Configure” button next to that shop.
4. In the “Languages” section, check all languages you want to be available for this specific shop.
5. Select one of the *checked* languages as the “Default Language” for this shop.
6. In the “Currencies” section, check all currencies you want to be available for this specific shop.
7. Select one of the *checked* currencies as the “Default Currency” for this shop.
8. Click “Save” to apply your changes.
9. Repeat for any other shops in your Multistore setup.
10. **Always clear your PrestaShop cache** (Advanced Parameters > Performance) after making changes to ensure they are reflected immediately on the front office.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Multistore Localization Rules (List View)** | Edit/Configure Button | N/A | Access detailed language/currency settings for a specific shop. |
| **Shop-Specific Configuration (Languages)** | Available Languages (checkboxes) | Check relevant | Controls which languages appear in the front office selector for this shop. |
| **Shop-Specific Configuration (Languages)** | Default Language | Primary language for shop’s audience | Sets the initial language for new visitors to this shop. |
| **Shop-Specific Configuration (Currencies)** | Available Currencies (checkboxes) | Check relevant | Controls which currencies appear in the front office selector for this shop. |
| **Shop-Specific Configuration (Currencies)** | Default Currency | Primary currency for shop’s audience | Sets the initial currency for new visitors to this shop. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the languages/currencies, but they’re not changing on my front office.**
A: The most common reason for this is cache. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and click “Clear cache” (or “Clear Smarty cache” and “Clear cache” for all caches). Also, try clearing your browser’s cache.

**Q: My custom theme doesn’t seem to respect the module’s settings for language/currency selectors.**
A: This module controls *which* options are available, but your theme dictates *how* those options are displayed. If your theme has heavily customized language/currency selectors, it might be overriding PrestaShop’s standard behavior.
\* **Solution:** Check your theme’s documentation or contact your theme developer. You might need to make minor adjustments to your theme’s `.tpl` files to ensure they are using PrestaShop’s standard `languages` and `currencies` variables, which this module modifies.

**Q: Can I set different default languages/currencies for different customer groups?**
A: No, this module sets the default language and currency *per shop*, not per customer group. The default applies to all visitors to that specific shop. Customers can then manually change it if other options are available.

**Q: What happens if I disable a language/currency that is currently set as default for a shop?**
A: The module should prevent you from doing this or automatically revert to the next available language/currency. Always ensure your chosen default is one of the *enabled* options for that shop. If you encounter issues, re-enable a suitable default and clear your cache.

**Q: I only have one shop. Do I need this module?**
A: No, this module is specifically designed for PrestaShop’s Multistore feature. If you only have a single shop, PrestaShop’s default localization settings (under International > Localization) are sufficient.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical implementation of the “Multistore localization settings - language and currency” module for developers and webmasters.

### 4.1 Architecture Overview

The module primarily extends PrestaShop’s core localization behavior by overriding `Currency` and `Language` classes. It introduces a custom administration controller (`AdminMultirulesController`) to manage shop-specific localization rules, which are stored in a custom database table. The module leverages PrestaShop’s MVC pattern for its Back Office interface and uses overrides to inject its logic into the front office language and currency selection process.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not include any dedicated front-office controllers. Its front-office logic is injected via class overrides and hooks.
- **Back-Office Admin Controllers**:

  - `multishoplang/controllers/admin/AdminMultirules.php`
    - **Class Name & Parent Class**: `AdminMultirulesController` extends `ModuleAdminController`.
    - **Responsibility**: This controller manages the listing and editing of localization rules for each shop. It is responsible for displaying the grid of shops, handling the form for selecting available languages and currencies for a specific shop, and saving these settings to the database. It likely uses `HelperList` for the shop grid and `HelperForm` for the shop-specific configuration.
    - **Tab Name**: “Multistore Localization Rules” (or similar, defined in `installTab()` method).
  - `multishoplang/controllers/admin/index.php`
    - **Class Name & Parent Class**: This is typically an empty file or a file containing a security `die()` statement to prevent direct access to the directory. It does not represent an active controller.

### 4.3 Core Classes & Models (`classes/`)

The module heavily relies on overrides to modify PrestaShop’s core behavior.

- `multishoplang/override/classes/Currency.php`
  - **Class Name & Parent Class**: `Currency` (overrides PrestaShop’s core `Currency` class).
  - **Responsibility**: This override intercepts calls related to currency retrieval and selection. It modifies methods like `getCurrencies()` or `getDefaultCurrency()` to filter the list of available currencies based on the current shop’s configuration as defined by the module. It ensures that only currencies enabled for the active shop are presented in the front office.
- `multishoplang/override/classes/Language.php`
  - **Class Name & Parent Class**: `Language` (overrides PrestaShop’s core `Language` class).
  - **Responsibility**: Similar to the `Currency` override, this class intercepts language-related calls. It modifies methods like `getLanguages()` or `getDefaultLanguage()` to filter the list of available languages based on the current shop’s configuration. It ensures that only languages enabled for the active shop are presented in the front office.
- `multishoplang/override/classes/index.php`
  - **Class Name & Parent Class**: This is typically an empty file or a file containing a security `die()` statement to prevent direct access to the directory. It does not represent an active class.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All interactions in the Back Office are handled by PrestaShop’s standard `HelperForm` and `HelperList` JavaScript, and front-office behavior is managed by the class overrides.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. Its Back Office interface relies on PrestaShop’s default admin theme styling. Front-office display is controlled by the active theme.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly listed, but the module’s logic primarily operates through class overrides rather than direct hook templates.
- **Admin templates (`views/templates/admin/`)**:
  - `multishoplang/views/advert.tpl`
    - **Purpose**: Likely a template for displaying promotional messages or information about other MyPresta.eu modules within the module’s configuration interface.
  - `multishoplang/views/currenciesForm.tpl`
    - **Purpose**: This template is used within the `AdminMultirulesController` to render the form section for configuring available currencies and the default currency for a specific shop. It will contain checkboxes for currencies and a dropdown for the default.
  - `multishoplang/views/languagesForm.tpl`
    - **Purpose**: This template is used within the `AdminMultirulesController` to render the form section for configuring available languages and the default language for a specific shop. It will contain checkboxes for languages and a dropdown for the default.
- **Front-office templates (`views/templates/front/`)**: None.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_multirule`: This is the custom table created by the module to store the localization rules. It likely contains fields such as:
    - `id_shop`: Foreign key referencing `ps_shop.id_shop`.
    - `id_lang_default`: The default language ID for that shop.
    - `id_currency_default`: The default currency ID for that shop.
    - `available_languages`: A serialized array or comma-separated string of `id_lang` values enabled for the shop.
    - `available_currencies`: A serialized array or comma-separated string of `id_currency` values enabled for the shop.
  - Configuration records are stored in `ps_configuration` for general module settings (if any).
- **Registered Hooks Table**:
  The module primarily operates through class overrides rather than direct hook execution in the front office. However, it will register standard Back Office hooks for its administration interface.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | When an admin controller is loaded | To load module-specific CSS/JS (though none are present in this module). |
| `displayBackOfficeHeader` | In the header of the Back Office | Potentially for displaying module-specific alerts or notices. |
| `moduleRoutes` | During URL routing initialization | If the module defined custom front-office routes (not applicable here). |
| `actionObjectLanguageAddAfter` | After a new language is added | To potentially update module’s internal data for new languages. |
| `actionObjectCurrencyAddAfter` | After a new currency is added | To potentially update module’s internal data for new currencies. |
| `actionShopDataDuplication` | When a shop is duplicated | To ensure localization rules are copied for the new shop. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continued enhancement of your PrestaShop modules.
