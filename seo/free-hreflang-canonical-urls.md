---
title: "Free hreflang & canonical urls - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free hreflang & canonical urls PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free hreflang & canonical urls - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free hreflang & canonical urls Module on MyPresta.eu](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/free-hreflang-canonical-urls/)
>
> ---


# Free hreflang & canonical urls

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most hosting environments. No special server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, navigate to **Modules > Module Manager**, search for “Free hreflang & canonical urls”, and click “Configure”. You will be presented with the module’s main configuration screen.

#### **Configuration Options:**

- **Enable hreflang tags:**

  - **What this setting does:** This master switch controls whether the module will generate and add `hreflang` tags to your store’s HTML header.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will actively generate and insert `hreflang` tags for all available language versions of your pages (product pages, category pages, CMS pages, etc.). This is crucial for international SEO.
    - *When disabled (NO):* No `hreflang` tags will be added by this module. If you have a multi-language store, search engines might treat your different language versions as duplicate content, potentially harming your international rankings.
  - **Recommended value:** **YES**. Always enable this if your store supports multiple languages or targets different regions.
  - **Merchant scenario / example:** If you sell products in both English and Spanish, enabling this ensures that a Spanish-speaking customer searching on Google will see the Spanish version of your product page, and an English-speaking customer will see the English version.
- **Enable canonical URLs:**

  - **What this setting does:** This master switch controls whether the module will generate and add `canonical` URL tags to your store’s HTML header.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will actively generate and insert `canonical` tags for all pages, pointing to the preferred version of each page. This helps consolidate SEO signals and prevents duplicate content issues.
    - *When disabled (NO):* No `canonical` tags will be added by this module. Your store might suffer from duplicate content issues if the same content is accessible via multiple URLs (e.g., with or without trailing slashes, with different parameters, or through different category paths).
  - **Recommended value:** **YES**. Canonical tags are fundamental for good SEO on almost any website.
  - **Merchant scenario / example:** A product page might be accessible via `yourstore.com/product-name` and also `yourstore.com/category/product-name`. Enabling canonical URLs tells Google that `yourstore.com/product-name` is the main version, ensuring all SEO credit goes to that single URL.
- **Use x-default hreflang:**

  - **What this setting does:** The `x-default` hreflang attribute specifies a default page that should be shown to users when no other language/region matches their browser settings or location.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will add an `x-default` hreflang tag, typically pointing to your store’s default language or a generic international version. This is useful for users whose language or region isn’t explicitly targeted by your other hreflang tags.
    - *When disabled (NO):* No `x-default` hreflang tag will be added. Users whose language/region doesn’t match any specific hreflang might be shown a less relevant page, or search engines might have to guess which page to show.
  - **Recommended value:** **YES**. It’s generally good practice to include an `x-default` for comprehensive international SEO, especially if you have a global audience.
  - **Merchant scenario / example:** If you have English (US), English (UK), and French versions, but a user from Germany searches in English, the `x-default` can direct them to your general English (US) page, ensuring they still get relevant content.
- **Use language code only (e.g., “en” instead of “en-us”):**

  - **What this setting does:** This controls the format of the language codes used in your `hreflang` tags.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The module will use only the two-letter ISO language code (e.g., `en`, `fr`, `de`). This is simpler and suitable if you target a language globally rather than specific regions.
    - *When disabled (NO):* The module will use both the language and region code (e.g., `en-US`, `en-GB`, `fr-CA`). This is more precise and recommended if you have different content or pricing for specific countries within the same language.
  - **Recommended value:**
    - **NO** if you have specific regional targeting (e.g., different English content for US vs. UK).
    - **YES** if your different language versions are generic and not country-specific (e.g., one “English” version for all English speakers).
  - **Merchant scenario / example:** If you sell in English and have one English version for all countries, choose YES. If you have separate English content/prices for the USA and the UK, choose NO to use `en-US` and `en-GB`.

#### **Saving Your Settings:**

After making your selections, click the **“Save”** button at the bottom of the configuration page to apply your changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable hreflang tags | YES | Activates hreflang tags for international SEO. |
| Module Configuration | Enable canonical URLs | YES | Activates canonical tags to prevent duplicate content. |
| Module Configuration | Use x-default hreflang | YES | Provides a fallback page for unmatched language/region users. |
| Module Configuration | Use language code only (e.g., “en” instead of “en-us”) | NO (depends on strategy) | Determines if hreflang uses language only (`en`) or language-region (`en-US`). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve enabled the module, but I don’t see any visual changes on my website. Is it working?**
A1: Yes, it’s working as intended! This module operates entirely in the background. It adds special code (hreflang and canonical tags) to the `<head>` section of your website’s HTML, which is visible to search engines but not to your customers. To verify it’s working, you can right-click on any page of your store, select “View Page Source” (or similar), and search for “hreflang” or “canonical”. You should see the tags there.

**Q2: After enabling the module, my search rankings haven’t immediately improved. What should I expect?**
A2: SEO changes, especially those related to crawling and indexing, take time to be reflected in search engine results. Google and other search engines need to re-crawl your site, process the new tags, and update their index. This process can take anywhere from a few days to several weeks or even months. Continue to monitor your Google Search Console for any changes in indexing or international targeting reports.

**Q3: My custom theme has some unique URL structures. Will this module still work correctly?**
A3: The module is designed to integrate with PrestaShop’s core URL generation mechanisms. In most cases, it should work seamlessly with custom themes. However, if your theme heavily modifies PrestaShop’s standard URL routing or page rendering, there’s a small chance of conflict. If you suspect an issue, first clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**). If problems persist, contact MyPresta.eu support with details of your theme and any specific pages where you see issues.

**Q4: I have a multi-language store, but some pages don’t have translations for all languages. How does the module handle this?**
A4: The module typically generates `hreflang` tags only for the languages that actually have content available for a given page. If a product or category is not translated into a specific language, the module should not generate an `hreflang` tag for that non-existent translation. Ensure your PrestaShop translations are correctly managed in the Back Office.

**Q5: I’m seeing multiple canonical tags or incorrect hreflang tags. What could be wrong?**
A5: This usually indicates a conflict with another SEO module or your theme that might also be trying to add canonical or hreflang tags.
1. **Check for other SEO modules:** Disable any other SEO modules one by one to identify the conflicting one.
2. **Check your theme:** Some themes might hardcode canonical tags.
3. **Clear Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) after making any module changes.
If the issue persists, contact MyPresta.eu support for assistance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Free hreflang & canonical urls” module (`myhreflang`) is a lightweight PrestaShop module primarily designed to inject `hreflang` and `canonical` meta tags into the `<head>` section of the front-office pages. It adheres to the standard PrestaShop module architecture, utilizing hooks to integrate its functionality without modifying core files. The module’s logic resides mainly within its main PHP file, `index.php`, which handles configuration, installation, uninstallation, and the core logic for tag generation. It leverages PrestaShop’s `Context` and `Link` classes to determine the current page, available languages, and generate correct URLs.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is handled within the main module file and its hooked methods.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or `ObjectModel`s in a `classes/` directory. All core logic is self-contained within the `myhreflang` class in `index.php`.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. Its functionality is purely server-side HTML tag generation.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. Its functionality is purely server-side HTML tag generation and has no visual impact.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template to render the `hreflang` and `canonical` tags.

- **Hook templates (`views/templates/hook/`)**:
  - `myhreflang/views/templates/hook/hreflang.tpl`: This template is responsible for outputting the actual `<link rel="alternate" hreflang="..." href="..." />` and `<link rel="canonical" href="..." />` tags.
    - **Rendered in hook**: `displayHeader`
    - **Purpose**: It receives an array of `hreflang_links` and a `canonical_link` from the module’s `hookDisplayHeader` method. It then iterates through these to generate the necessary HTML `<link>` tags.
    - **Variables available**:
      - `$hreflang_links`: An array of associative arrays, each containing `lang_code` (e.g., ‘en’, ‘en-US’, ‘x-default’) and `url`.
      - `$canonical_link`: A string containing the canonical URL for the current page.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module does **not** create any custom SQL tables. It stores its configuration settings directly in the `ps_configuration` table using standard PrestaShop `Configuration::get()` and `Configuration::updateValue()` methods.

  - Configuration keys stored in `ps_configuration`:
    - `MYHREFLANG_HREFLANG_ENABLED` (boolean)
    - `MYHREFLANG_CANONICAL_ENABLED` (boolean)
    - `MYHREFLANG_XDEFAULT_ENABLED` (boolean)
    - `MYHREFLANG_LANG_CODE_ONLY` (boolean)
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | Executed in the `<head>` section of every front-office page. | This is the primary hook used by the module. It calls the `hookDisplayHeader()` method to generate and inject the `hreflang` and `canonical` `<link>` tags into the page’s HTML `<head>`. |

## 5. Official Support & Updates

For official support, module updates, and any further assistance with the “Free hreflang & canonical urls” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to help with any questions or technical issues you may encounter.
