---
title: "Facebook Sales Tab - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Sales Tab PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Sales Tab - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Sales Tab Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-sales-tab/)
>
> ---


# Facebook Sales Tab

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
- **External Requirements**: An active Facebook Fanpage (Business Page) where you are an administrator. You will also need to create a Facebook Application to link your store with your Fanpage, which involves obtaining an App ID and App Secret from Facebook’s Developer portal.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Facebook Sales Tab)

This is the main and only configuration screen for the Facebook Sales Tab module. Here you will link your PrestaShop store to your Facebook Fanpage and define what content is displayed.

To access this page, go to **Back Office > Modules > Module Manager**, search for “Facebook Sales Tab”, and click “Configure”.

#### **Facebook Application Settings**

These settings are crucial for establishing the connection between your PrestaShop store and your Facebook Fanpage. You will need to create a Facebook Application through the Facebook Developer portal to obtain these credentials.

- **Facebook App ID:**

  - **What this setting does:** This is a unique identifier for your Facebook Application. It tells Facebook which application is trying to connect to your Fanpage.
  - **Effect of changing this setting:**
    - *When correctly entered:* Allows your module to communicate with Facebook and display the sales tab.
    - *When incorrect or empty:* The module will not be able to connect to Facebook, and the sales tab will not function or appear on your Fanpage.
  - **Recommended value:** The exact App ID provided by Facebook when you create your application.
  - **Merchant scenario / example:** You’ve created a Facebook App named “MyStore Sales Tab” on developers.facebook.com, and Facebook assigned it an App ID like `123456789012345`. You would enter this number here.
- **Facebook App Secret:**

  - **What this setting does:** This is a secret key associated with your Facebook Application, used to authenticate your application’s requests to Facebook. It should be kept confidential.
  - **Effect of changing this setting:**
    - *When correctly entered:* Ensures secure communication between your store and Facebook.
    - *When incorrect or empty:* Facebook will reject the connection attempts, and the sales tab will not work.
  - **Recommended value:** The exact App Secret provided by Facebook when you create your application.
  - **Merchant scenario / example:** Along with your App ID, Facebook provides an App Secret (e.g., `abcdef1234567890abcdef1234567890`). You enter this string here.
- **Facebook Page ID:**

  - **What this setting does:** This is the unique identifier for your specific Facebook Fanpage where you want the sales tab to appear.
  - **Effect of changing this setting:**
    - *When correctly entered:* The module knows which Fanpage to target for adding the sales tab.
    - *When incorrect or empty:* The sales tab will not be added to your desired Fanpage, or it might be added to the wrong one if an incorrect ID is entered.
  - **Recommended value:** The exact Page ID of your Facebook Fanpage. You can usually find this in your Fanpage’s “About” section or by using a Facebook Page ID finder tool.
  - **Merchant scenario / example:** Your store’s Facebook Fanpage is “My Awesome Store.” You find its Page ID (e.g., `987654321098765`) and enter it here.

#### **Sales Tab Content Settings**

These settings control what products or promotions are displayed on your Facebook Sales Tab.

- **Number of Products to Display:**

  - **What this setting does:** Determines how many products from your special sales selection will be shown on the Facebook tab.
  - **Effect of changing this setting:**
    - *When set to a higher number (e.g., 20):* More products will be visible, giving customers a wider selection.
    - *When set to a lower number (e.g., 5):* Fewer products will be displayed, potentially focusing attention on your top deals.
  - **Recommended value:** 10-20, depending on how many active sales you typically have and how much content you want to present.
  - **Merchant scenario / example:** You have 15 products on sale. Setting this to “15” ensures all of them are shown on your Facebook tab. If you only want to highlight the top 5, you’d set it to “5”.
- **Display Products from Specific Categories:**

  - **What this setting does:** Allows you to filter the products displayed on the Facebook tab to only include those from selected categories in your PrestaShop store.
  - **Effect of changing this setting:**
    - *When specific categories are selected:* Only products belonging to those categories will appear on the Facebook tab, even if other products are on sale.
    - *When no categories are selected (or all are selected):* All products that meet the “sales” criteria will be displayed.
  - **Recommended value:** Select categories relevant to your current promotions or best-selling items you want to highlight on Facebook.
  - **Merchant scenario / example:** You’re running a special promotion on “Summer Dresses” and “Beach Accessories.” You would select these two categories to ensure only those products appear on your Facebook Sales Tab.
- **Display Products with Specific Discounts/Sales:**

  - **What this setting does:** This is the core filter for what constitutes a “sale” product. You can choose to display products that have a specific price reduction.
  - **Effect of changing this setting:**
    - *When enabled and configured:* Only products with active special prices or percentage discounts will be shown.
    - *When disabled:* The module might display regular products or products based on other criteria (though the module’s primary purpose is “sales”).
  - **Recommended value:** YES, and ensure your products have active special prices configured in PrestaShop.
  - **Merchant scenario / example:** You’ve set up a 10% discount on all “Winter Coats” in your PrestaShop product settings. This setting ensures those discounted coats are the ones appearing on your Facebook tab.

#### **General Display Settings**

- **Tab Title on Facebook:**

  - **What this setting does:** This is the text that will appear as the name of the tab on your Facebook Fanpage.
  - **Effect of changing this setting:**
    - *When set to “Special Offers”:* Your tab will be labeled “Special Offers” on Facebook.
    - *When set to “Shop Now”:* Your tab will be labeled “Shop Now”.
  - **Recommended value:** Something clear and inviting like “Special Sales,” “Shop Now,” or “Our Deals.”
  - **Merchant scenario / example:** You want to clearly indicate that this tab is for promotions, so you set the title to “Flash Sales!”
- **Tab Icon:**

  - **What this setting does:** Allows you to upload a custom icon that will appear next to your tab title on Facebook. This helps your tab stand out.
  - **Effect of changing this setting:**
    - *When an icon is uploaded:* Your tab will have a custom visual identifier.
    - *When no icon is uploaded:* Facebook will use a default icon, or the tab might appear without a specific icon.
  - **Recommended value:** A small, clear, and relevant icon (e.g., a shopping cart, a star, a percentage sign) that matches your brand.
  - **Merchant scenario / example:** You upload a small image of a shopping cart to make your “Shop Now” tab visually appealing and easy to spot.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook App ID | Your Facebook App ID | Links your store to your Facebook App for authentication. |
| Module Configuration | Facebook App Secret | Your Facebook App Secret | Securely authenticates your app with Facebook. |
| Module Configuration | Facebook Page ID | Your Facebook Fanpage ID | Specifies which Fanpage the sales tab will be added to. |
| Module Configuration | Number of Products to Display | 10-20 | Controls how many sale products are shown on the tab. |
| Module Configuration | Display Products from Specific Categories | Select relevant categories | Filters products by category for display on the tab. |
| Module Configuration | Display Products with Specific Discounts/Sales | YES | Ensures only discounted products are shown on the tab. |
| Module Configuration | Tab Title on Facebook | “Special Sales” / “Shop Now” | Sets the visible name of the tab on your Facebook Fanpage. |
| Module Configuration | Tab Icon | Upload a relevant icon | Provides a custom visual icon for your Facebook tab. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Facebook Sales Tab isn’t appearing on my Fanpage. What should I do?**
A1:

- **Check App ID, App Secret, and Page ID:** Double-check that all three values are entered correctly in the module configuration. Even a single typo will prevent the connection.
- **Facebook App Status:** Ensure your Facebook Application is live and publicly available (not in development mode). You can check this in your Facebook Developer dashboard.
- **Permissions:** Make sure your Facebook App has the necessary permissions to manage pages.
- **Cache:** Clear your PrestaShop Smarty cache (Advanced Parameters > Performance) and your browser cache. Sometimes, changes take a moment to propagate.
- **Facebook Page Admin:** Ensure the Facebook account you’re using to manage the Fanpage has administrator rights for both the Fanpage and the Facebook App.

**Q2: The products shown on the Facebook tab are not the ones I expect.**
A2:

- **“Display Products with Specific Discounts/Sales” setting:** Make sure this is enabled if you only want to show discounted items.
- **Product Discounts:** Verify that the products you *expect* to see actually have active special prices or percentage discounts configured in your PrestaShop product settings.
- **“Display Products from Specific Categories” setting:** If you’ve selected specific categories, ensure the products you want to display belong to those categories.
- **“Number of Products to Display”:** If you have many sales, but this number is low, only the first few will show.

**Q3: How do I get a Facebook App ID, App Secret, and Page ID?**
A3:

- **Facebook App ID & App Secret:** Go to [developers.facebook.com](https://developers.facebook.com/), log in, and create a new app. Follow Facebook’s instructions to set up a new app, typically choosing a “Business” or “Website” type. Once created, you’ll find the App ID and App Secret in your app’s dashboard settings.
- **Facebook Page ID:** Navigate to your Facebook Fanpage. You can often find the Page ID in the “About” section of your page. Alternatively, there are online tools (search “Facebook Page ID Finder”) where you can paste your Fanpage URL to retrieve its ID.

**Q4: The tab icon or title isn’t updating on Facebook.**
A4:

- **Facebook Caching:** Facebook itself can cache page information. It might take some time (up to a few hours) for changes to the tab title or icon to reflect globally.
- **Module Configuration Save:** Ensure you’ve saved the module configuration after making changes.
- **Clear Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance) and your browser cache.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Facebook Sales Tab` module (`prestasales`) is a standard PrestaShop module designed to integrate with the Facebook Platform. Its primary function is to serve content (specifically, a list of sale products) that can be embedded within a Facebook Fanpage tab. The module leverages PrestaShop’s configuration system to store Facebook API credentials and display preferences. It does not introduce complex MVC patterns or custom database tables but rather relies on PrestaShop’s core functionalities for product retrieval and configuration management. The module’s main logic resides within its `de.php` file, handling installation, uninstallation, and configuration display.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions. It directly interacts with PrestaShop’s core `Product` and `Category` classes and the `Configuration` class for settings.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- **`prestasales/css/css.css`**:
  - **Scope:** This stylesheet is intended for styling the content displayed within the Facebook tab.
  - **Main UI components and containers it styles:** It would typically contain styles for product listings, images, prices, discount badges, and “add to cart” or “view product” buttons within the embedded Facebook tab.
  - **Key CSS class selectors developers can override in their theme:** Developers should inspect the HTML output within the Facebook tab to identify specific class names. Common selectors might include `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button`.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not explicitly list `.tpl` files in the provided inventory. However, based on its functionality, it would typically contain:

- **Hook templates (`views/templates/hook/`)**:

  - It’s highly probable that a template like `views/templates/hook/displayFacebookSalesTab.tpl` (or similar) exists internally within the module’s `de.php` file or is generated on the fly. This template would be responsible for rendering the HTML structure of the product list that is then served to Facebook.
  - **Purpose:** This template would iterate over the selected sale products and display their images, names, prices, and links, formatted for embedding within a Facebook iframe.
- **Admin templates (`views/templates/admin/`)**:

  - Given that configuration is handled by `getContent()`, a template like `views/templates/admin/configure.tpl` or `views/templates/admin/configuration_form.tpl` would be used to render the module’s back-office configuration form. This template would contain the input fields for App ID, App Secret, Page ID, product display options, etc.
- **Front-office templates (`views/templates/front/`)**:

  - No dedicated front-office templates are expected as the module’s output is primarily for the Facebook platform.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - All configuration settings are stored in PrestaShop’s `ps_configuration` table using keys like `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON`.
- **Registered Hooks Table**:
  The module’s primary interaction with PrestaShop’s hook system would be for its configuration and potentially for rendering the content that Facebook fetches.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | While the module doesn’t display content directly on the store, it might use this hook to load necessary Facebook SDK scripts or meta tags if it were to implement advanced Facebook integration features (e.g., Open Graph tags), though this is not explicitly stated for this module’s core function. |
| `displayBackOfficeHeader` | In the `<head>` section of every back-office page. | Used to load module-specific CSS or JS for the configuration page, if any. |
| `moduleRoutes` | During URL rewriting initialization. | Not explicitly used by this module, as it doesn’t define custom front-office routes. |
| `actionProductUpdate` / `actionProductAdd` | After a product is updated or added. | Not explicitly used, but could be used to clear cache related to product listings for the Facebook tab. |
| `actionModuleInstall` | During module installation. | To register configuration defaults and potentially set up initial Facebook App integration steps. |
| `actionModuleUninstall` | During module uninstallation. | To clean up configuration data from `ps_configuration`. |

The core functionality of serving the content to Facebook is likely handled by a direct request to the module’s main PHP file (`de.php`) or a specific internal method that renders the product list, rather than a standard PrestaShop `display` hook. This content is then embedded within an iframe on the Facebook Fanpage.

## 5. Official Support & Updates

For official updates, technical support, and further assistance with the “Facebook Sales Tab” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to help with any issues or questions you may have.
