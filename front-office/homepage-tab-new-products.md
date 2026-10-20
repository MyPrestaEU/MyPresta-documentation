---
title: "Homepage tab new products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage tab new products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage tab new products"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage tab new products Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-tab-new-products/)
>
> ---


# Homepage tab new products

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, click "Configure" next to the "Homepage tab new products" module in the Module Manager. You will be taken to the main configuration screen.

#### **Number of products to be displayed**
-   **What this setting does:** This controls how many of your newest products will be shown in the "New Products" tab on your homepage.
-   **Effect of changing this setting:**
    -   *When set to a higher number (e.g., 12):* More new products will be visible to customers without them needing to navigate to a full "New Products" page. This can be great for stores with a high volume of new arrivals.
    -   *When set to a lower number (e.g., 4):* Fewer products will be displayed, resulting in a cleaner, less cluttered look. This might be preferred if you want to highlight only the absolute freshest items or have limited space.
-   **Recommended value:** Start with `8` or `12`. Adjust based on your theme's layout and how many products you typically add.
-   **Merchant scenario / example:** If you run a fashion store and add 20 new items weekly, setting this to `12` ensures a good selection is always visible. If you sell high-value, niche products and only add 2-3 new items monthly, `4` might be sufficient to avoid empty spaces.

#### **Product list classes**
-   **What this setting does:** This advanced setting allows you to add custom CSS classes to the container that holds the list of new products. This is primarily used for styling purposes, often to integrate seamlessly with your specific PrestaShop theme's design.
-   **Effect of changing this setting:**
    -   *When classes are added (e.g., `product-grid-container my-custom-style`):* Your theme's CSS or your custom CSS can then target these classes to apply specific styling (e.g., change column layout, spacing, font sizes, colors) to the new product list.
    -   *When left empty:* The module will use its default styling or inherit styles from your theme's general product list.
-   **Recommended value:** Leave empty unless you or your web developer need to apply specific custom styling to the product list. If you're unsure, do not change this setting.
-   **Merchant scenario / example:** Your theme displays product grids with 3 columns, but you want the "New Products" tab to show 4 columns. Your web developer might tell you to add a class like `col-lg-3` (if your theme uses Bootstrap grid classes) here, then add custom CSS to make it work.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option           | Default / Recommended | Purpose & Impact
| Screen / View
