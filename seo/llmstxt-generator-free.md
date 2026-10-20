---
title: "LLMS.txt Generator Free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the LLMS.txt Generator Free PrestaShop module by MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy LLMS.txt Generator Free Module on MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/seo/llmstxt-generator-free/)
>
> ---


# LLMS.txt Generator Free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Your server must allow writing files to the root directory of your PrestaShop installation for the `llms.txt` file to be created and updated.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” to access the module’s main settings page. This is where you’ll define what content goes into your `llms.txt` file.

#### General Settings

- **Store Profile (for each active language)**
  - **What this setting does:** This allows you to write a short, concise description of your store in each language your shop supports. This profile will be included in the `llms.txt` file, giving AI models a quick overview of what your business is about.
  - **Effect of changing this setting:**
    - *When filled out:* The text you provide will be added to the `llms.txt` file, helping AI models understand your store’s purpose and offerings in specific languages.
    - *When left empty:* No store profile will be included for that language, potentially making it harder for AI to grasp your store’s essence.
  - **Recommended value:** Fill this out for every active language. Keep it brief (1-2 sentences) and descriptive.
  - **Merchant scenario / example:** If your store sells organic pet food, you might write: “MyStore offers a wide selection of premium organic pet food and natural pet supplies for dogs and cats. We prioritize health, sustainability, and happy pets.”

#### Content Selection

- **Promoted Categories**

  - **What this setting does:** This allows you to select specific product categories from your store that you want to highlight to AI crawlers. These categories will be explicitly listed in the `llms.txt` file.
  - **Effect of changing this setting:**
    - *When categories are selected:* AI models will be directed to these categories, signaling their importance and potentially increasing their visibility in AI-powered searches.
    - *When no categories are selected:* AI models will not receive specific guidance on which categories to prioritize from your `llms.txt` file.
  - **Recommended value:** Select 3-5 of your most important or best-selling categories.
  - **Merchant scenario / example:** If you specialize in “Women’s Dresses,” “Men’s Shoes,” and “Kids’ Toys,” select these categories to tell AI that these are core offerings.
- **Include Top 5 Bestsellers with Prices**

  - **What this setting does:** When enabled, the module will automatically identify your top 5 best-selling products and include their names, links, and current prices in the `llms.txt` file.
  - **Effect of changing this setting:**
    - *When enabled:* AI models will get direct access to information about your most popular products, including their prices, which can be crucial for AI-driven shopping recommendations.
    - *When disabled:* Your bestsellers will not be explicitly highlighted with their prices in the `llms.txt` file.
  - **Recommended value:** YES. This is a powerful feature to showcase your most popular items.
  - **Merchant scenario / example:** A customer asks an AI, “What are the best-selling items at [Your Store Name]?” With this enabled, the AI can provide a direct answer with current prices.
- **Include CMS Pages**

  - **What this setting does:** This allows you to select important static content pages (like “About Us,” “Contact Us,” “Privacy Policy,” “Delivery Information”) that you want AI models to be aware of.
  - **Effect of changing this setting:**
    - *When CMS pages are selected:* AI models will be directed to these informational pages, helping them understand your store’s policies, background, and how to contact you.
    - *When no CMS pages are selected:* AI models might have to discover these pages through general crawling, which could be less efficient.
  - **Recommended value:** Select all essential informational pages that build trust and provide customer service details.
  - **Merchant scenario / example:** Ensure your “Returns Policy” and “FAQ” pages are included so AI can accurately answer customer questions about these topics.

#### Action

- **Save and Regenerate llms.txt file**
  - **What this button does:** This button saves all the settings you’ve configured on this page and immediately regenerates the `llms.txt` file in your store’s root directory with the updated information.
  - **Effect of clicking this button:** Your `llms.txt` file will be updated with your latest selections. This action is also triggered automatically when you update products or categories in your store.
  - **Recommended value:** Always click this button after making any changes to ensure your `llms.txt` file is up-to-date.
  - **Merchant scenario / example:** After adding a new “Store Profile” description, click this button to make sure the AI crawlers get the new information.

#### Upgrade to Pro Version (Upsell Block)

This section is an informational block promoting the Pro version of the module. It highlights additional features available in the paid version, such as full catalogue export, crawler analytics, filters, and cron job support. This is not a configurable setting but a suggestion for advanced needs.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Store Profile (per language) | Fill for all languages | Provides AI models with a brief, structured description of your store. |
| Module Configuration | Promoted Categories | Select 3-5 key categories | Directs AI crawlers to your most important product categories. |
| Module Configuration | Include Top 5 Bestsellers with Prices | YES | Highlights your most popular products with current prices to AI. |
| Module Configuration | Include CMS Pages | Select all essential pages | Guides AI to important informational pages (e.g., About Us, Contact). |
| Module Configuration | Save and Regenerate llms.txt file | Click after any changes | Saves settings and updates the `llms.txt` file in your store’s root. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but I don’t see any changes on my website. Is it working?**
A1: Yes, it’s likely working correctly! The `llms.txt` file is a technical file for AI crawlers, not for human visitors. You won’t see any visual changes on your store’s front-office. To verify it’s working, you can try to access `yourstore.com/llms.txt` in your browser. You should see the generated content there.

**Q2: I’m getting an error that the module cannot write the `llms.txt` file.**
A2: This usually indicates a file permission issue on your server. The module needs permission to create and update the `llms.txt` file in your PrestaShop’s root directory.
- **Solution:** Contact your hosting provider and ask them to ensure that the PrestaShop application has write permissions (e.g., chmod 755 or 775 for directories, 644 or 664 for files) in your store’s root folder.

**Q3: How often is the `llms.txt` file updated?**
A3: The `llms.txt` file is regenerated automatically whenever you:
- Click the “Save and Regenerate llms.txt file” button in the module’s configuration.
- Update a product (e.g., change price, name, description).
- Update a category (e.g., change name, description).
This ensures the file is always fresh with your latest store data.

**Q4: My custom theme doesn’t seem to be affected by this module. Is there a conflict?**
A4: No, there shouldn’t be any conflict. This module operates entirely in the background, generating a text file. It does not modify your theme’s design, CSS, or JavaScript. Its purpose is to provide structured data to AI crawlers, not to change the visual appearance of your store.

**Q5: Can I manually edit the `llms.txt` file?**
A5: It’s strongly recommended **not** to manually edit the `llms.txt` file directly. Any changes you make will be overwritten the next time the module regenerates the file (e.g., when you save settings or update products/categories). Always use the module’s configuration interface to control its content.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `LLMS.txt Generator Free` module is a lightweight PrestaShop module primarily focused on generating a static text file (`llms.txt`) in the store’s root directory. It follows a standard PrestaShop module structure, leveraging the `Module` class for installation, uninstallation, and configuration. The core logic resides within the main module file, handling configuration persistence and file generation. It uses PrestaShop’s `Configuration` class for settings and hooks for automatic regeneration.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is handled within the main module file’s `getContent()` method for configuration and via hooks for background operations.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** contain any custom classes or `ObjectModel` definitions in the `classes/` directory. It directly utilizes PrestaShop’s core classes like `Configuration`, `Product`, `Category`, `CMS`, `Language`, and `Shop`.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** contain any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- **`llmstxtfree/views/css/admin-config.css`**
  - **Scope:** Back-office admin form styling.
  - **Main UI components and containers it styles:** Provides basic styling for the module’s configuration page, likely for layout, spacing, and potentially some visual cues for the upsell block.
  - **Key CSS class selectors developers can override in their theme:** Typically targets elements within the module’s `getContent()` output, such as `.panel`, `.form-group`, or custom classes defined in `configure.tpl`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:
  - **`llmstxtfree/views/templates/admin/configure.tpl`**
    - **Purpose:** This is the main Smarty template rendered by the `getContent()` method of the module. It defines the structure and fields for the module’s configuration page in the PrestaShop Back Office.
    - **Content:** Contains the HTML form for all settings described in Section 4.1, including input fields for store profile, category selection, bestseller toggle, CMS page selection, and the save button. It also includes the `pro-upsell.tpl` template.
  - **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
    - **Purpose:** This template is included within `configure.tpl` and displays promotional content for the Pro version of the module.
    - **Content:** Typically contains text, images, and links encouraging the merchant to upgrade to the paid version, highlighting additional features.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does **not** create any custom SQL tables.
  - It stores its configuration settings (e.g., selected categories, CMS pages, store profiles, bestseller toggle) in the standard PrestaShop `ps_configuration` table. Configuration keys typically follow the pattern `LLMSTXTFREE_SETTING_NAME`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content in the `<head>` section of front-office pages. | Not directly used for content output, but often registered by modules for asset loading or initial setup. In this module, it’s likely for general module initialization or potentially for future features. |
| `displayRightColumn` | Renders content in the right column of front-office pages. | Not used for content output in this module. |
| `displayLeftColumn` | Renders content in the left column of front-office pages. | Not used for content output in this module. |
| `displayFooter` | Renders content in the footer of front-office pages. | Not used for content output in this module. |
| `displayProductExtraContent` | Renders extra content on the product page. | Not used for content output in this module. |
| `actionProductUpdate` | Executed after a product is updated in the Back Office. | **Crucial for this module:** Triggers the automatic regeneration of the `llms.txt` file to ensure bestseller data and product links are up-to-date. |
| `actionCategoryUpdate` | Executed after a category is updated in the Back Office. | **Crucial for this module:** Triggers the automatic regeneration of the `llms.txt` file to ensure promoted category links and names are up-to-date. |
| `actionObjectCmsUpdateAfter` | Executed after a CMS page is updated. | Triggers the automatic regeneration of the `llms.txt` file to ensure selected CMS page links and titles are up-to-date. |
| `actionObjectCmsAddAfter` | Executed after a new CMS page is added. | Triggers the automatic regeneration of the `llms.txt` file. |
| `actionObjectCmsDeleteAfter` | Executed after a CMS page is deleted. | Triggers the automatic regeneration of the `llms.txt` file. |

## 5. Official Support & Updates

For official updates, technical support, and to explore additional modules and services, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the LLMS.txt Generator Free module.
