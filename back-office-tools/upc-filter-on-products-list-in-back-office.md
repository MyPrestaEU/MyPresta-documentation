---
title: "UPC filter on products list in back office - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the UPC filter on products list in back office PrestaShop module by MyPresta.eu."
sidebar:
  label: "UPC filter on products list in back office - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy UPC filter on products list in back office Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# UPC filter on products list in back office

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are required beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This module is designed to be plug-and-play. It does not have a dedicated configuration screen with settings to adjust. Once installed, the module automatically integrates the UPC column and filter into your product list in the back office.

You will find the new functionality by navigating to:
**Back Office > Catalog > Products**

On this page, you will now see:

- A new column labeled “UPC” displaying the UPC code for each product.
- A new filter field at the top of the “UPC” column, allowing you to type in a UPC code (or part of one) to filter the product list.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve installed the module, but I don’t see the UPC column or filter on my product list.**
A:
\* **Clear Cache:** The most common solution is to clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right corner.
\* **Check Module Status:** Ensure the module is enabled. Go to **Modules > Module Manager**, search for “UPC filter on products list in back office,” and verify it’s active.
\* **Theme Compatibility:** While rare for back-office modules, a highly customized admin theme *could* potentially interfere. If clearing cache doesn’t work, temporarily switch to the default PrestaShop admin theme to see if the column appears.
\* **Module Position:** This module modifies existing templates. Ensure the module is correctly installed and not showing any errors during installation.

**Q: The UPC column is there, but some products don’t show a UPC.**
A: This module simply displays the UPC code that is already stored in your product’s information. If a product doesn’t show a UPC, it means that the UPC field for that specific product in your PrestaShop catalog is empty. You’ll need to edit the product (Catalog > Products > Edit Product > Quantities tab) and enter the UPC code there.

**Q: Can I change the position of the UPC column?**
A: The module integrates the UPC column into a specific position within the product list table. There is no configuration option within the module to change its position. This would require custom template modifications (see Developer Guide).

**Q: Does this module add UPC fields to products if they don’t exist?**
A: No, this module assumes your PrestaShop installation already has the standard UPC field available for products (which it does by default). It only displays and filters based on the data you’ve already entered into that field.

**Q: Will this module slow down my back office?**
A: The module is highly optimized. It leverages PrestaShop’s existing filtering mechanisms and only adds a simple column display. It should not noticeably impact the performance of your back office product list.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters looking to understand, debug, or extend the “UPC filter on products list in back office” module.

### 4.1 Architecture Overview

The module primarily functions by overriding specific Twig templates used for the product catalog list in the PrestaShop back office. It injects the necessary HTML for the UPC column header and filter input, and then modifies the product row template to display the UPC value. The filtering logic is handled by PrestaShop’s native `AdminProducts` controller, which automatically recognizes the `upc` field for filtering once it’s present in the template.

### 4.2 Controllers (`controllers/`)

This module does **not** introduce any custom front-office or back-office controllers. Its functionality is achieved through template overrides and leveraging existing PrestaShop controller logic.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** introduce any custom PHP classes or `ObjectModel` definitions. It directly interacts with existing PrestaShop product data.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. The filtering functionality is handled server-side by PrestaShop’s `AdminProducts` controller.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. It relies on PrestaShop’s default back-office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

This module utilizes the new Twig templating engine introduced in PrestaShop 1.7+ for back-office pages. It overrides two core product list templates:

- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

  - **Purpose:** This template is responsible for rendering the main product catalog page, including the table header and the search/filter form.
  - **Modification:** The module injects a new `<th>` element for the “UPC” column into the table header and a corresponding input field for filtering into the search form. This allows the `upc` field to be recognized by the `AdminProducts` controller for filtering.
- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

  - **Purpose:** This template is responsible for rendering the individual rows of the product list table.
  - **Modification:** The module adds a new `<td>` element within the product loop to display the `product.upc` value for each product.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does **not** create any custom database tables. It reads the `upc` field from the standard `ps_product` table.
- **Registered Hooks Table**: This module does **not** register any specific hooks in the traditional PrestaShop sense (e.g., `displayHeader`, `actionValidateOrder`). Its integration is achieved purely through Twig template overrides, which are a form of implicit “hooking” into the rendering process.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “UPC filter on products list in back office” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality.
