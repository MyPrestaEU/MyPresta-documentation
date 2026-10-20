---
title: "Homepage Best Sellers - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage Best Sellers PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage Best Sellers - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage Best Sellers Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-best-sellers/)
>
> ---


# Homepage Best Sellers

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Homepage Best Sellers” module in your Module Manager. You will be presented with a simple configuration screen.

#### Settings & Options:

1. **Number of products to display**

   - **What this setting does:** This controls how many best-selling products will be shown in the dedicated block on your homepage.
   - **Effect of changing this setting:**
     - *When set to a higher number (e.g., 10):* More best-selling products will appear on your homepage, giving customers a wider selection. This might make the block longer or require more scrolling.
     - *When set to a lower number (e.g., 4):* Fewer best-selling products will be displayed, making the block more compact and focused.
   - **Recommended value:** Start with a number that fits well within your homepage design, typically between 4 and 8. You can adjust it based on how many products you want to highlight and how much space you have.
   - **Merchant scenario / example:** If your homepage is already quite busy, you might set it to 4 to keep it clean. If you have a lot of popular products and a spacious design, you could set it to 8 or 10 to showcase more variety.
2. **Display product attributes on product page** (This setting is likely a remnant or mislabeled, as `PS_ATTRIBUTE_CATEGORY_DISPLAY` is a core PrestaShop setting, not typically controlled by a simple best-sellers module. However, if it appears here, treat it as such.)

   - **What this setting does:** This setting, if present and active, would control whether product attributes (like size, color, material) are shown on the product page itself. It’s generally a global PrestaShop setting.
   - **Effect of changing this setting:**
     - *When enabled:* Product attributes will be visible on the product page, allowing customers to see available variations.
     - *When disabled:* Product attributes might be hidden or displayed differently on the product page.
   - **Recommended value:** Generally, you want product attributes to be displayed on product pages so customers can make informed choices. So, “YES” or enabled.
   - **Merchant scenario / example:** If you sell t-shirts in different sizes and colors, enabling this ensures customers can see and select “Small, Red” or “Large, Blue” on the product page.

#### Additional Notes:

- The module also includes internal update mechanisms (`update_`, `updatev_`) which are not user-configurable but ensure the module can check for and apply updates.
- The module uses hooks like `displayHome` to render its content and `updateproduct`, `addproduct`, `deleteproduct` to keep track of product changes and potentially refresh its best-seller list. This happens automatically in the background.

### 2.2 Dedicated Admin Screens & Controller Views

This module does not introduce any dedicated new admin screens or custom controller views beyond its main configuration page. All settings are managed directly on the module’s configuration form.

### 2.3 Configuration Quick Reference Table

## 3. ## | Screen / View | Setting / Option | Default / Recommended | Purpose & Impact

## 4. ## title Homepage: Best Sellers - Merchant Manual & Configuration Guide description: “Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage Best Sellers PrestaShop module by MyPresta.eu.” sidebar: label: “Homepage Best Sellers”

# Homepage Best Sellers

## 5. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store and are sufficient for this module. No unusual or advanced server configurations are needed.

## 6. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 6.1 Module Configuration Page (Back Office > Modules > Configure)

After successfully installing the “Homepage Best Sellers” module, navigate to **Modules > Module Manager**, locate “Homepage Best Sellers,” and click the “Configure” button. You will be presented with a simple, intuitive configuration screen.

#### Settings & Options:

1. **Number of products to display**

   - **What this setting does:** This is the primary control for the module. It determines exactly how many of your top-selling products will be showcased within the “Best Sellers” block on your store’s homepage.
   - **Effect of changing this setting:**
     - *When enabled / set to a higher number (e.g., 10):* Your homepage will feature more best-selling products. This can be great for stores with a wide range of popular items, offering customers more choice. However, be mindful that a very high number might make the block quite long, requiring more scrolling, or could potentially clutter your homepage design depending on your theme.
     - *When disabled / set to a lower number (e.g., 4):* Fewer best-selling products will be displayed. This makes the block more compact and focused, which can be ideal for minimalist designs or when you want to highlight only the absolute top few items.
   - **Recommended value:** A good starting point is usually between **4 and 8 products**. This provides enough variety without overwhelming the page. You should experiment with different numbers to see what looks best with your specific PrestaShop theme and overall homepage layout.
   - **Merchant scenario / example:** If you run a fashion store and want to show a curated selection of your absolute hottest items, you might set this to `4`. If you have a large electronics store and want to demonstrate the breadth of your popular gadgets, setting it to `8` or `10` could be more effective.
2. **Display product attributes on product page** (Configuration Key: `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

   - **What this setting does:** This setting, if present in the module’s configuration, controls whether product attributes (like size, color, material, etc.) are displayed on the actual product page when a customer views a product. It’s important to note that `PS_ATTRIBUTE_CATEGORY_DISPLAY` is typically a core PrestaShop global setting, not usually managed by a specific module like “Best Sellers.” If it appears here, it’s likely a convenience link or a module attempting to manage a global setting.
   - **Effect of changing this setting:**
     - *When enabled (e.g., “Yes” or checked):* Product attributes will be clearly visible on the product page, allowing customers to select specific variations (e.g., “Red, Size M”). This is crucial for products with options.
     - *When disabled (e.g., “No” or unchecked):* Product attributes might be hidden or not displayed in the standard way on the product page, which could confuse customers trying to select product variations.
   - **Recommended value:** **YES** (or enabled). For almost all e-commerce stores, it is essential to display product attributes on the product page to allow customers to choose variations and make informed purchasing decisions.
   - **Merchant scenario / example:** If you sell shoes, enabling this ensures customers can select “Size 9, Black” from the options on the shoe’s product page. Disabling it would make it impossible for them to specify their desired size or color.

#### Internal/Non-Configurable Settings:

- `update_`, `updatev_`: These are internal module version tracking and update check parameters. They are not meant for merchant interaction but ensure the module can verify its version and potentially notify you of updates.

### 6.2 Dedicated Admin Screens & Controller Views

The “Homepage Best Sellers” module is designed for simplicity and efficiency. It does **not** introduce any additional dedicated admin screens, custom menu items, or complex controller views beyond its single, straightforward configuration page accessible via the Module Manager. All management is done directly on that one screen.

### 6.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact
