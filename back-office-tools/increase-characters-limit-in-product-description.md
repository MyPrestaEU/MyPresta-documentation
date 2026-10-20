---
title: "Increase characters limit in product description - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Increase characters limit in product description PrestaShop module by MyPresta.eu."
sidebar:
  label: "Increase characters limit in product description - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Increase characters limit in product description Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Increase characters limit in product description

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5 (Always extending to PHP 8.5 for future-proofing)
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings. This is the main and only configuration screen for this module.

#### Settings & Options:

1. **Product description length**

   - **What this setting does:** This field controls the maximum number of characters allowed in the main “Description” field for all your products in the PrestaShop Back Office. The default PrestaShop limit is 21,844 characters.
   - **Effect of changing this setting:**
     - *When set to a higher number:* You will be able to enter more characters into the product description field when editing products. This allows for more detailed content.
     - *When set to a lower number (not recommended):* You would restrict your ability to add detailed content, potentially truncating existing longer descriptions.
   - **Recommended value:** A significantly higher number like `65535` or `16777215` (which corresponds to MySQL’s `MEDIUMTEXT` or `LONGTEXT` limits, effectively removing practical limits for most content). You can also set it to `0` or leave it empty to remove the limit entirely and use the maximum possible.
   - **Merchant scenario / example:** You sell high-tech gadgets and need to include extensive technical specifications, compatibility lists, and user guides directly in the product description. Setting this to `65535` ensures you have ample space.
2. **Product name length**

   - **What this setting does:** This field controls the maximum number of characters allowed for the “Product Name” field for all your products. The default PrestaShop limit is typically 128 or 255 characters, depending on the version.
   - **Effect of changing this setting:**
     - *When set to a higher number:* You can use longer product names, which can be useful for very specific products, including model numbers, or for SEO purposes where longer, descriptive titles are beneficial.
     - *When set to a lower number (not recommended):* You would restrict product naming, potentially causing issues with existing products or making it harder to differentiate items.
   - **Recommended value:** A higher number like `512` or `1024` if you need very long product names. For most stores, the default is sufficient, but if you have specific needs (e.g., including full part numbers or detailed model descriptions), increasing this is helpful.
   - **Merchant scenario / example:** You sell industrial equipment, and product names often include manufacturer, model, specific features, and version numbers (e.g., “XYZ Corp. Heavy Duty Industrial Mixer Model 5000-A with Variable Speed Control and Stainless Steel Hopper”). Increasing this limit to `512` allows you to fit the full, descriptive name.
3. **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (This is a standard PrestaShop setting, not directly controlled by the module, but often relevant for content editing)

   - **What this setting does:** This PrestaShop core setting determines whether employees can select the language for a form field directly within the form, or if the form language is determined by the employee’s back office language. It’s not a module setting but is often visible or relevant when dealing with multi-language content.
   - **Effect of changing this setting:**
     - *When enabled:* Employees can switch the language for text fields (like product descriptions) directly on the product edit page, allowing them to enter content for different languages without changing their entire back office language.
     - *When disabled:* The language of the text fields will match the employee’s current back office language. To edit content in another language, the employee must change their back office language.
   - **Recommended value:** Generally **YES** for multi-language stores with multiple content editors, as it improves workflow.
   - **Merchant scenario / example:** You have a French-speaking content editor and an English-speaking content editor. If this is enabled, the French editor can write the French description and then switch the language dropdown to English to write the English description, all on the same product page.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Product description length | `65535` or `0` (no limit) | Increases max characters for product descriptions. Allows for more detailed content and better SEO. |
| Module Config | Product name length | `512` or `1024` | Increases max characters for product names. Useful for highly specific or descriptive product titles. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve increased the character limit, but my product descriptions still seem to be cut off on the front office. What’s wrong?**
A: This is usually a theme-related issue, not a module issue.
- **Check your theme’s display settings:** Some themes might have their own CSS or JavaScript that truncates long text to fit a specific design layout. You might need to consult your theme documentation or a web developer to adjust these.
- **Clear Smarty Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office, scroll down to “Clear cache” and click “Clear cache.” Sometimes old template files are cached.
- **Verify in Back Office:** Double-check that the full description is saved correctly in the product edit page in your Back Office. If it’s cut off there, then the module might not have applied correctly (though this is rare).

**Q: Does this module affect SEO?**
A: Indirectly, yes, in a very positive way. By allowing you to write longer, more detailed, and keyword-rich product descriptions, you provide more content for search engines to crawl and index. This can lead to better rankings for relevant search queries and attract more organic traffic to your product pages.

**Q: Will this module slow down my store?**
A: No, this module has a negligible impact on store performance. It primarily modifies database column definitions during installation/configuration. Once configured, it doesn’t add any complex processing or front-office scripts that would slow down page load times. The only potential “slowdown” could be if you write extremely long descriptions that take longer to load from the database, but this is usually minimal and offset by the SEO benefits.

**Q: I changed the limits, but I don’t see the change in the product edit page. What should I do?**
A:
- **Save the module configuration:** Ensure you clicked the “Save” button after changing the character limits in the module’s configuration page.
- **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.”
- **Refresh your browser:** Sometimes the browser caches old forms. Do a hard refresh (Ctrl+F5 or Cmd+Shift+R).
- **Log out and back in:** For some administrative changes, logging out and back into the Back Office can ensure all session data is refreshed.

**Q: Is there a maximum limit I can set?**
A: While the module allows you to set virtually any number, the practical limit is determined by your database’s capabilities. For `TEXT` fields in MySQL, the maximum is `65,535` characters. For `MEDIUMTEXT`, it’s `16,777,215` characters, and for `LONGTEXT`, it’s `4,294,967,295` characters. Setting `0` or leaving the field empty will typically default to the largest possible `TEXT` type, effectively removing any practical limit for most content. For product names, `255` or `512` characters are usually more than enough.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Increase characters limit in product description” module is a lightweight PrestaShop module primarily designed to modify the database schema for product-related text fields. It operates by altering the `type` and `size` of specific columns in the `ps_product_lang` table (for descriptions) and `ps_product` / `ps_product_lang` tables (for names) during its installation and configuration. It does not introduce any front-office controllers, custom classes, or complex JavaScript/CSS. Its core functionality is executed via the `install()` and `getContent()` methods of the main module class.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin controllers. All configuration is handled directly within the module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** introduce any custom classes or `ObjectModel` definitions. It directly interacts with existing PrestaShop core database tables and configuration settings.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does **not** include any custom Smarty template files. The configuration form is rendered directly within the `getContent()` method using PrestaShop’s standard `HelperForm` components.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module primarily interacts with the following core PrestaShop tables:

- `ps_product_lang`:
  - **`description` column**: Modified to a larger `TEXT` type (e.g., `MEDIUMTEXT` or `LONGTEXT`) to accommodate more characters.
  - **`description_short` column**: Not directly modified by this module, but often related.
  - **`name` column**: Modified to a larger `VARCHAR` type (e.g., `VARCHAR(512)`) to accommodate more characters.
- `ps_configuration`:
  - `chr_max_description_length`: Stores the configured maximum length for product descriptions.
  - `chr_max_name_length`: Stores the configured maximum length for product names.
  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: A standard PrestaShop configuration key, not created by the module, but often referenced in the context of content editing.

The module’s `install()` method contains SQL queries to alter these table columns. The `uninstall()` method attempts to revert these changes, though manual verification might be needed depending on the database state.

#### Registered Hooks Table

This module does **not** register any front-office or back-office display hooks. Its functionality is entirely backend-driven by modifying database schema.

The module’s `install()` method might implicitly use `Configuration::updateValue()` which doesn’t directly register hooks but stores values.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Increase characters limit in product description” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
