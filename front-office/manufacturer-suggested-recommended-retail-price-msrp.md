---
title: "Manufacturer suggested / recommended retail price (MSRP) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Manufacturer suggested / recommended retail price (MSRP) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Manufacturer suggested / recommended retail price (MSRP) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Manufacturer suggested / recommended retail price (MSRP) Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Manufacturer suggested / recommended retail price (MSRP)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the MSRP module, accessible after installation by clicking the “Configure” button. Here you will define how MSRPs are displayed and managed across your store.

#### **Enable MSRP Display**

- **What this setting does:** This is the master switch to turn the MSRP feature on or off for your entire store.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will start displaying MSRP information on your product pages and product listings, provided you have entered MSRPs for your products.
  - *When disabled (NO):* The MSRP feature will be completely inactive, and no MSRP information will be shown to customers, even if you have entered values.
- **Recommended value:** YES (to utilize the module’s features).
- **Merchant scenario / example:** If you’re setting up the module for the first time, enable it to see the changes. If you need to temporarily hide MSRPs for a promotion or maintenance, you can disable it here.

#### **Display MSRP on Product Page**

- **What this setting does:** Controls whether the MSRP is shown on individual product detail pages.
- **Effect of changing this setting:**
  - *When enabled (YES):* The MSRP, your price, and “You Save” information will appear on the product page.
  - *When disabled (NO):* The MSRP will not be shown on the product page, even if enabled globally.
- **Recommended value:** YES (This is a primary location for customers to see value).
- **Merchant scenario / example:** You might disable this if you prefer to only highlight savings on category pages, or if your product page design is already very crowded.

#### **Display MSRP on Product List**

- **What this setting does:** Controls whether the MSRP is shown on pages displaying multiple products, such as category pages, search results, or featured product blocks.
- **Effect of changing this setting:**
  - *When enabled (YES):* The MSRP, your price, and “You Save” information will appear for each product in product listings.
  - *When disabled (NO):* The MSRP will not be shown on product list pages.
- **Recommended value:** YES (Great for quick comparisons and highlighting value while browsing).
- **Merchant scenario / example:** Enabling this helps customers quickly identify good deals while browsing categories, potentially increasing click-through rates to product pages.

#### **Show Tax Included Price**

- **What this setting does:** Determines if the displayed MSRP should include taxes or be shown as tax-excluded.
- **Effect of changing this setting:**
  - *When enabled (YES):* The MSRP will be shown with applicable taxes already added, reflecting the final price a customer would pay.
  - *When disabled (NO):* The MSRP will be shown without taxes.
- **Recommended value:** YES (Generally, customers prefer to see final prices, especially in B2C contexts).
- **Merchant scenario / example:** If your store primarily serves B2C customers, showing tax-included prices is clearer. For B2B stores, tax-excluded might be preferred.

#### **Show Tax Excluded Price**

- **What this setting does:** Determines if the displayed MSRP should exclude taxes or be shown as tax-included.
- **Effect of changing this setting:**
  - *When enabled (YES):* The MSRP will be shown without taxes.
  - *When disabled (NO):* The MSRP will be shown with applicable taxes already added.
- **Recommended value:** NO (Unless you specifically target B2B customers or operate in a region where tax-excluded prices are standard for initial display).
- **Merchant scenario / example:** If you enable “Show Tax Included Price,” you would typically disable this one to avoid confusion. Only enable both if you want to show both values side-by-side (which might be confusing for customers).

#### **Display “You Save” Information**

- **What this setting does:** Controls whether the module calculates and displays the monetary difference between the MSRP and your store’s selling price.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will show a message like “You save $X.XX” or “You save X%” next to the MSRP and your price.
  - *When disabled (NO):* Only the MSRP and your price will be shown, without the explicit savings calculation.
- **Recommended value:** YES (This is a key benefit of using the module, strongly motivating purchases).
- **Merchant scenario / example:** This feature directly highlights the value proposition. If your prices are consistently lower than MSRP, enabling this will significantly boost perceived value.

#### **MSRP Field for Products**

- **What this setting does:** This setting defines where you will input the MSRP for each product in your PrestaShop Back Office.
- **Effect of changing this setting:**
  - *When selected:* The module will use the chosen product field to retrieve the MSRP value. You will need to manually enter the MSRP for each product in the specified field.
- **Recommended value:** The module usually creates a custom field or suggests using an existing one. Follow the module’s instructions to identify the correct field.
- **Merchant scenario / example:** After installing the module, you’ll go to **Catalog > Products**, edit a product, and find a new input field (or an existing one repurposed) where you can type in the MSRP for that specific product.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable MSRP Display | YES | Master switch to activate/deactivate MSRP feature store-wide. |
| Module Configuration | Display MSRP on Product Page | YES | Show MSRP on individual product detail pages. |
| Module Configuration | Display MSRP on Product List | YES | Show MSRP on category/search result pages. |
| Module Configuration | Show Tax Included Price | YES | Display MSRP with taxes included (B2C friendly). |
| Module Configuration | Show Tax Excluded Price | NO | Display MSRP without taxes (B2B friendly, avoid conflict with ‘Tax Included’). |
| Module Configuration | Display “You Save” Information | YES | Show the calculated savings (MSRP - Your Price). |
| Module Configuration | MSRP Field for Products | (Module-specific) | Defines which product field in BO stores the MSRP value. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve enabled the module and entered MSRPs, but nothing is showing on my store. What’s wrong?**
A1:

- **Check Global Enablement:** Ensure “Enable MSRP Display” is set to YES in the module configuration.
- **Check Specific Display Settings:** Verify “Display MSRP on Product Page” and “Display MSRP on Product List” are also set to YES for the areas you expect to see it.
- **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Product-Specific MSRP:** Double-check that you have actually entered an MSRP value for the specific products you are testing.
- **Theme Compatibility:** Sometimes, highly customized themes might require minor adjustments to display new elements. If after clearing cache it still doesn’t appear, contact MyPresta.eu support.

**Q2: The “You Save” amount seems incorrect or doesn’t appear.**
A2:

- **Enable “You Save”:** Make sure “Display ‘You Save’ Information” is enabled in the module settings.
- **MSRP vs. Your Price:** The “You Save” calculation depends on both the MSRP and your product’s selling price. Ensure both values are correctly set for the product. If your selling price is higher than or equal to the MSRP, no savings will be displayed.
- **Tax Settings:** The calculation might be affected by whether you’re showing tax-included or tax-excluded prices. Ensure your tax settings are consistent.

**Q3: How do I enter the MSRP for each product?**
A3: After installing the module, navigate to **Catalog > Products** in your PrestaShop Back Office. Edit an existing product or create a new one. Within the product editing interface, you should find a new field specifically for “MSRP” (or a repurposed existing field, as defined in the module’s configuration). Enter the manufacturer’s suggested retail price there and save the product.

**Q4: The MSRP text doesn’t match my store’s design/font. How can I change it?**
A4: The module uses its own CSS for styling. For minor adjustments (like font size, color), you can often override these styles in your theme’s custom CSS file (e.g., `themes/yourtheme/assets/css/custom.css` or `themes/yourtheme/css/custom.css`). For more extensive changes, you might need a web developer to inspect the module’s CSS and apply more specific overrides.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Manufacturer suggested / recommended retail price (MSRP)” module is a standard PrestaShop module designed to extend front-office product display functionalities. It primarily operates by hooking into existing PrestaShop display points (like product pages and product listings) to inject MSRP information. It leverages PrestaShop’s configuration system for its settings and Smarty templates for rendering the front-office output. The module’s core logic resides in its main PHP file, handling installation, uninstallation, configuration, and hook registration.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method in the main module file, and front-office display is managed through hooks and template rendering.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances in the `classes/` directory. It directly interacts with existing PrestaShop product data and configuration.

### 4.4 JavaScript Assets (`views/js/`)

- **`msrp/views/admin/js/msrp.js`**

  - **Scope:** Back-office.
  - **Purpose:** This script likely handles any dynamic behavior or validation within the module’s configuration form in the PrestaShop Back Office. This could include showing/hiding fields based on other selections, AJAX calls for saving settings, or client-side validation.
  - **Details:** Binds event listeners to configuration form elements, performs form submission handling, and potentially updates the UI based on user input.
- **`msrp/views/js/msrp.js`**

  - **Scope:** Front-office.
  - **Purpose:** This script is responsible for any client-side interactions or dynamic updates related to the MSRP display on the front office. This could involve updating the “You Save” amount dynamically if product attributes change (e.g., selecting a different size/color that affects price), or handling display logic.
  - **Details:** Binds to `prestashop.on` events (e.g., `updatedProduct` for product page price changes), manipulates DOM elements to update MSRP or savings display, and ensures responsiveness.

### 4.5 CSS Stylesheets (`views/css/`)

- **`msrp/views/admin/css/msrp.css`**

  - **Scope:** Back-office admin form styling.
  - **Purpose:** Provides specific styling for the module’s configuration page within the PrestaShop Back Office, ensuring a consistent and user-friendly interface.
  - **Key Selectors:** Targets elements within the module’s `getContent()` output, such as form fields, labels, and sections.
- **`msrp/views/css/msrp.css`**

  - **Scope:** Front-office customer styling.
  - **Purpose:** Styles the displayed MSRP, your price, and “You Save” information on product pages and product listings. This ensures the information is clearly visible and integrates well with the store’s overall design.
  - **Key Selectors:** Targets specific `div` or `span` elements generated by the module’s Smarty templates (e.g., `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Developers can override these classes in their theme’s `custom.css` to match their branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`msrp/views/admin/msrp.tpl`**

  - **Scope:** Admin templates.
  - **Purpose:** This template renders the module’s configuration form in the PrestaShop Back Office. It contains the HTML structure for all the settings described in Section 4.1.
  - **Details:** Uses PrestaShop’s helper form components (e.g., `helperForm`) to create input fields, switches, and buttons for module settings.
- **`msrp/views/templates/msrp-product-list.tpl`**

  - **Scope:** Hook templates (e.g., `displayProductPriceBlock` or similar for product listings).
  - **Purpose:** This template is responsible for displaying the MSRP information on product listing pages (categories, search results, etc.). It typically receives product data and module configuration settings to render the MSRP, current price, and “You Save” message.
  - **Details:** Contains logic to check if MSRP is available, if “You Save” should be displayed, and formats the prices according to tax settings.
- **`msrp/views/templates/msrp-product-page.tpl`**

  - **Scope:** Hook templates (e.g., `displayProductPriceBlock` or `displayProductButtons` on product pages).
  - **Purpose:** This template renders the MSRP information on individual product detail pages. It’s designed to integrate seamlessly near the main product price block.
  - **Details:** Similar to `msrp-product-list.tpl`, it handles conditional display of MSRP, current price, and savings, applying tax rules and formatting.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create custom SQL tables.
  - Configuration settings are stored in the `ps_configuration` table, typically with keys prefixed by `MSRP_` (e.g., `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
  - MSRP values for products are stored in an existing product field, as configured in the module (e.g., `ps_product_lang.description_short` or a custom product field if created by the module).
- **Registered Hooks Table**:
  The module registers hooks to inject its content into the front office and manage its lifecycle.

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `install()` | During module installation | Creates configuration entries, registers hooks, potentially adds product fields. |
  | `uninstall()` | During module uninstallation | Cleans up configuration entries, unregisters hooks, removes product fields. |
  | `displayHeader` | In the `<head>` section of every page | Injects module’s CSS and JS files for front-office display. |
  | `displayProductPriceBlock` | Within the product price block on product pages and listings | Main hook for rendering MSRP, current price, and “You Save” information. This hook is called multiple times with different parameters (e.g., `type='after_price'`). |
  | `actionProductUpdate` | After a product is updated in the Back Office | Potentially used to ensure MSRP data is correctly saved or processed. |
  | `actionProductSave` | After a product is saved in the Back Office | Similar to `actionProductUpdate`, ensures MSRP data integrity. |
  | `actionProductDelete` | After a product is deleted | Cleans up any associated MSRP data if stored separately. |
  | `displayAdminProductsExtra` | In the product editing page in the Back Office | Adds the MSRP input field to the product form. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “Manufacturer suggested / recommended retail price (MSRP)” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team and developers are ready to help you maximize the potential of this module for your PrestaShop store.
