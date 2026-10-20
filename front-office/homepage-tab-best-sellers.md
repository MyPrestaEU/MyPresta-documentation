---
title: "Homepage tab best sellers - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage tab best sellers PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage tab best sellers - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage tab best sellers Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-tab-best-sellers/)
>
> ---


# Homepage tab best sellers

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Homepage tab best sellers” module in the Module Manager. You will be taken to its configuration page.

#### Number of products to be displayed

- **What this setting does:** This setting controls how many best-selling products will be shown within the “Best Sellers” tab on your homepage.
- **Effect of changing this setting:**
  - *When set to a higher number (e.g., 12):* More products will be displayed in the tab, giving customers a wider selection of your best sellers to browse. This can be good for stores with many popular items.
  - *When set to a lower number (e.g., 4):* Fewer products will be displayed, creating a more concise and focused presentation. This can be beneficial for stores with fewer best sellers or when you want to emphasize a select few.
- **Recommended value:** A good starting point is typically between **8 and 12** products. This provides enough variety without overwhelming the customer or making the page too long.
- **Merchant scenario / example:** If you have a large catalog and many products that consistently sell well, you might set this to 10 or 12 to showcase more of your popular items. If you prefer a cleaner, more minimalist homepage, you might set it to 6.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact ## 5. Practical Use Cases & Best Practices (Pro Tips)

1. **Leverage Social Proof for New Visitors:**
   - **Scenario:** A new customer lands on your homepage. They don’t know your brand or your products.
   - **Pro Tip:** The “Best Sellers” tab immediately provides social proof, showing them what other customers are buying and loving. Ensure your best sellers have good product images and clear descriptions. Consider running a temporary promotion (e.g., “Our Top 5 Best Sellers - 10% Off This Week!”) to draw even more attention to this section.
2. **Optimize for Seasonal & Trending Products:**
   - **Scenario:** Your store experiences seasonal sales spikes (e.g., holiday gifts, summer apparel) or has products that suddenly become trendy.
   - **Pro Tip:** While the module automatically identifies best sellers, you can indirectly influence this by strategically promoting certain products. For instance, during summer, if you want your swimwear to appear in “Best Sellers,” ensure they are well-stocked, competitively priced, and perhaps featured in other marketing efforts. As they sell more, they will naturally rise in the best-seller rankings and appear in the tab.
3. **Cross-Promote with Other Homepage Sections:**
   - **Scenario:** You have other product sections on your homepage (e.g., “New Products,” “Featured Products”).
   - **Pro Tip:** Use the “Best Sellers” tab as a complementary section. If a product is new and selling exceptionally well, it might appear in both “New Products” and “Best Sellers,” reinforcing its popularity. Avoid having too many overlapping products if possible, to give customers more variety, but don’t hide a genuinely best-selling new product just for the sake of variety. The module’s automatic nature will handle this naturally.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My “Best Sellers” tab isn’t showing up on the homepage.**

- **A:** First, ensure the module is installed and enabled in **Modules > Module Manager**. Then, check its configuration. If the tab still doesn’t appear, it might be a caching issue. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). If your theme is heavily customized, it might not be correctly hooking into `displayHomeTab` and `displayHomeTabContent`. In this case, you may need to consult with your theme developer or a PrestaShop expert.

**Q2: The products in the “Best Sellers” tab don’t seem to be my actual best sellers.**

- **A:** The module relies on PrestaShop’s internal sales data to determine best sellers.
  - Ensure you have actual sales data for products. New stores or stores with very few sales might not have enough data for a meaningful “best sellers” list.
  - The “best sellers” calculation is usually based on the number of units sold over a period. It might take some time for recent sales to reflect in the list.
  - Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) to ensure the latest data is being pulled.

**Q3: How often does the “Best Sellers” list update?**

- **A:** The list of best sellers is dynamically generated by PrestaShop based on sales data. It updates automatically as orders are placed and processed. However, for the changes to be visible on the front office, you might need to clear your PrestaShop cache, especially if you have aggressive caching enabled.

**Q4: Can I change the title of the tab (e.g., from “Best Sellers” to “Our Top Picks”)?**

- **A:** Yes, you can. The tab title is typically a translatable string within the module.
  1. Go to **International > Translations**.
  2. Select “Installed modules translations”.
  3. Choose your theme.
  4. Select your language.
  5. Find the “Homepage tab best sellers” module in the list.
  6. Locate the text string for the tab title (e.g., “Best Sellers”) and change it to your desired text. Remember to save your changes.

**Q5: The products look strange or misaligned in the tab.**

- **A:** This is usually a CSS styling conflict with your PrestaShop theme. The module provides the product data, but your theme is responsible for how that data is displayed (layout, fonts, colors, image sizes).
  - Ensure your theme is up-to-date.
  - Try clearing your PrestaShop cache (**Advanced Parameters > Performance**).
  - If the issue persists, you may need to add custom CSS to your theme to override the module’s or theme’s default styling. This usually requires a web developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Homepage tab best sellers” module for developers and webmasters.

### 4.1 Architecture Overview

The `Homepage tab best sellers` module is a straightforward PrestaShop module designed to integrate seamlessly with the homepage tab system. It follows a classic PrestaShop module structure, primarily utilizing the `Module` class and front-office hooks. It does not introduce custom controllers, models, or complex JavaScript/CSS, relying instead on PrestaShop’s core functionalities for product data retrieval and existing theme styling for presentation. Its main logic resides within the `homebestsellerstab.php` file, handling configuration and hook registration.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office content is rendered directly via Smarty templates hooked into `displayHomeTab` and `displayHomeTabContent`.
- **Back-Office Admin Controllers**: None. Module configuration is handled by the `getContent()` method within the main module class.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or extend `ObjectModel`. It leverages PrestaShop’s core `Product` and `ProductSale` classes (or similar internal mechanisms) to retrieve best-selling product data.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module does not include any custom JavaScript files. Any interactive behavior (like tab switching) is expected to be handled by the PrestaShop theme’s existing JavaScript.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The module does not include any custom CSS files. The styling of the tab and the product listings within it is entirely dependent on the active PrestaShop theme. Developers should inspect the generated HTML and target relevant classes/IDs in their theme’s CSS to customize the appearance.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses two Smarty template files, both located in the `views/templates/hook/` directory, to render its content in the front office.

- **`views/templates/hook/tab.tpl`**

  - **Hook**: `displayHomeTab`
  - **Purpose**: This template is responsible for rendering the actual clickable tab element on the homepage. It typically contains the `<li>` or `<a>` tag that represents the “Best Sellers” tab, including its translatable title.
  - **Output**: A tab element that, when clicked, reveals the content rendered by `homebestsellerstab.tpl`.
- **`views/templates/hook/homebestsellerstab.tpl`**

  - **Hook**: `displayHomeTabContent`
  - **Purpose**: This template renders the actual list or grid of best-selling products when the “Best Sellers” tab is active. It receives an array of product data from the module’s PHP logic.
  - **Output**: HTML markup for displaying products (e.g., `div` containers, product images, names, prices, add-to-cart buttons). It typically iterates over the `$products` variable passed to it.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration (e.g., `HOME_BEST_NBR`) in PrestaShop’s `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose The `HOME_BEST_NBR` configuration key is used to store the number of products to be displayed.
The `PS_LANG_DEFAULT` and `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` are PrestaShop core configuration keys used to manage the default language and employee form language settings. These are not directly configured by the module but are accessed for context.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Homepage tab best sellers” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). You can download the most recent version of the module from your order history. For technical assistance or inquiries, please use the support channels provided on the MyPresta.eu website.
