---
title: "Product page as shop homepage - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product page as shop homepage PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product page as shop homepage - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product page as shop homepage Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-page-as-shop-homepage/)
>
> ---


# Product page as shop homepage

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Product page as shop homepage” module. You will see a single, straightforward configuration option.

- **Setting Name:** Product to display on homepage
  - **What this setting does:** This is the most crucial setting. It allows you to select exactly which product from your catalog will become your shop’s new homepage.
  - **Effect of changing this setting:**
    - *When a product is selected:* Your store’s main URL will display the full product page of the chosen product.
    - *When no product is selected (or module is disabled):* Your store will revert to its default homepage behavior (e.g., displaying featured products, categories, or a custom CMS page).
  - **Recommended value:** Select the product you want to feature most prominently. Use the search bar to find your desired product quickly.
  - **Merchant scenario / example:** You’ve just launched a revolutionary new gadget. You want every visitor to your store to see this product first. You would type the product name (e.g., “Super Gadget X”) into the search box, select it from the dropdown, and save. Now, anyone visiting `www.yourstore.com` will land directly on the “Super Gadget X” product page.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Product to display on homepage | (None selected initially) / Select your key product | Defines which product’s page will replace your shop’s default homepage. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My homepage is still showing the old content after configuring the module. What should I do?**
A: This is usually a caching issue.
1. Go to **Advanced Parameters > Performance** in your PrestaShop Back Office.
2. Click “Clear cache” in the top right corner.
3. Also, clear your browser’s cache and cookies, then try accessing your store again.

**Q: Can I change the featured product easily?**
A: Yes! Simply go back to **Modules > Module Manager**, find “Product page as shop homepage”, click “Configure”, and select a different product from the dropdown. Save your changes, and clear your cache.

**Q: What happens if the selected product is out of stock or disabled?**
A: If the selected product is out of stock, its product page will still be displayed, but the “Add to Cart” button might be disabled or show an “Out of Stock” message, depending on your PrestaShop inventory settings. If the product is completely disabled, PrestaShop might show a “Page Not Found” error, or revert to the default homepage. Always ensure the selected product is active and available.

**Q: Does this module affect my SEO?**
A: When you set a product page as your homepage, the main URL of your store (`www.yourstore.com`) will now serve the content of that product page. Search engines will index this content for your main domain. If you previously had a rich, keyword-optimized homepage, you might see a shift in how your main domain ranks. Ensure the chosen product page is well-optimized for SEO (title, description, images, content).

**Q: Can I use this with a custom theme?**
A: Yes, the module works by overriding how PrestaShop dispatches the `IndexController`. It should be compatible with most custom themes as it leverages PrestaShop’s standard product page rendering. If you encounter styling issues, it’s likely related to your theme’s CSS, not the module’s core functionality.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Product page as shop homepage” module operates by overriding core PrestaShop front controllers to redirect the default homepage (`IndexController`) behavior. Instead of loading the standard homepage template, it forces the `ProductController` to render the page for a specific product ID, effectively making a product page the default landing page for the shop’s root URL. This is achieved through a series of overrides in the `override/` directory.

### 4.2 Controllers (`controllers/`)

This module primarily uses overrides to modify controller behavior.

- **Front-Office Controllers**:
  - `homepageproduct/override/controllers/front/index.php`
    - This file is a placeholder or an older override. In modern PrestaShop, the `IndexController` is typically overridden directly. Its presence suggests a compatibility mechanism or an older approach.
  - `homepageproduct/override/controllers/front/IndexController.php`
    - **Class Name & Parent Class:** `IndexController` (overrides `IndexControllerCore`)
    - **Responsibility:** This is the core override. When the shop’s root URL is accessed, PrestaShop normally dispatches `IndexController`. This override intercepts that dispatch. It checks the module’s configuration for a `homepageproduct_product` ID. If a product ID is set, it then internally redirects or forwards the request to the `ProductController` for that specific product, effectively rendering the product page instead of the default homepage. It ensures that the current controller context is correctly set to `ProductController` and that the product data is loaded.

### 4.3 Core Classes & Models (`classes/`)

This module uses overrides to modify core class behavior, specifically related to controller handling.

- `homepageproduct/override/classes/controller/FrontController.php`
  - **Class Name & Parent Class:** `FrontController` (overrides `FrontControllerCore`)
  - **Responsibility:** This override likely contains logic to ensure that the `IndexController` override functions correctly within the `FrontController`’s dispatch process. It might adjust how the controller is initialized or how templates are assigned when the homepage is being served as a product page.
- `homepageproduct/override/classes/controller/index.php`
  - Similar to `override/controllers/front/index.php`, this appears to be a placeholder or an older override mechanism.
- `homepageproduct/override/classes/index.php`
  - Another placeholder or older override.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All front-office interactivity for the product page comes from PrestaShop’s core product page JS.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. The styling of the product page is entirely handled by the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not introduce new front-office templates for display. It reuses existing PrestaShop product page templates.

- **Admin templates (`views/templates/admin/`)**:
  - `homepageproduct/lib/searchTool/views/scripts.tpl`
    - This template is likely used within the module’s `getContent()` method in the back office. It probably contains JavaScript or Smarty logic to render the product search input field, allowing the administrator to easily find and select a product by name or ID for the homepage. It might include AJAX calls to `AdminProducts` or similar controllers for product suggestions.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It stores its configuration in the `ps_configuration` table:
    - `homepageproduct_product`: Stores the ID of the product selected to be the homepage.
    - `mypresta_updates`, `update_`, `updatev_`: Used for module update checks by MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: A standard PrestaShop configuration key, not directly managed by this module but potentially accessed.
- **Registered Hooks Table**:
  The module does not explicitly register any new display hooks. Its functionality is achieved through controller overrides. However, since it renders a standard product page, all hooks normally present on a product page (e.g., `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`) will be executed as if it were a regular product page.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Before page content | For including CSS, JS, meta tags. |
| `displayLeftColumn` | Left column of product page | Displaying blocks like categories, filters. |
| `displayRightColumn` | Right column of product page | Displaying blocks like cart, custom content. |
| `displayFooter` | At the bottom of the page | For including JS, footer content. |
| `displayProductButtons` | Near Add to Cart button | Adding custom buttons or actions on product page. |
| `displayProductExtraContent` | Below product description | Adding extra tabs or content to product page. |
| `actionValidateOrder` | After an order is validated | For post-order processing (e.g., tracking). |
| *(Any other hook normally on a product page)* | Varies | Standard PrestaShop product page hook execution. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Product page as shop homepage” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continued enhancement of our modules.
