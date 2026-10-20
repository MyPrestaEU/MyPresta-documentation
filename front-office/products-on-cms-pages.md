---
title: "Products on CMS pages - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Products on CMS pages PrestaShop module by MyPresta.eu."
sidebar:
  label: "Products on CMS pages - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Products on CMS pages Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/products-on-cms-pages/)
>
> ---


# Products on CMS pages

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Products on CMS pages” module in the Module Manager. You will see the main configuration screen.

#### **Hide products and shortcodes**

- **What this setting does:** This setting controls whether the module processes and displays products from the shortcodes you’ve placed in your CMS pages. It also affects whether the shortcodes themselves are visible to customers if the module is not processing them.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will *not* process the shortcodes. Instead of displaying product lists, the shortcodes (e.g., `[products ids="1,2,3"]`) will be hidden from the customer’s view on the front office. This is useful if you want to temporarily disable the product display without removing the shortcodes from your CMS content.
  - *When disabled (NO):* The module will actively look for and process the shortcodes in your CMS pages. It will replace them with the corresponding product lists, making your products visible to customers.
- **Recommended value:** **NO** (unless you specifically want to hide the product lists and shortcodes).
- **Merchant scenario / example:**
  - You’ve set up several CMS pages with product shortcodes for a seasonal promotion. When the promotion ends, instead of manually editing each CMS page to remove the shortcodes, you can simply enable “Hide products and shortcodes” to instantly hide all product listings from those pages. When the next promotion starts, you disable it again.

### 2.2 How to Use Shortcodes in Your CMS Pages

This module doesn’t have dedicated admin screens beyond the main configuration. Its primary functionality is controlled by “shortcodes” that you insert directly into your CMS page content.

**To add products to a CMS page:**

1. Navigate to **Shop Parameters > CMS** in your PrestaShop Back Office.
2. Edit an existing CMS page or create a new one.
3. In the main content editor (usually a rich text editor like TinyMCE), you can type or paste the shortcodes.

**Available Shortcodes:**

- **Display specific products by ID:**

  - `[products ids="1,2,3,4"]`
  - **Purpose:** This shortcode allows you to display a list of specific products by their unique ID numbers. You can find product IDs in your Back Office under **Catalog > Products**.
  - **Example:** If you want to show Product A (ID 1), Product B (ID 2), and Product C (ID 3), you would use `[products ids="1,2,3"]`.
- **Display products from a specific category:**

  - `[products category="5"]`
  - **Purpose:** This shortcode displays all products belonging to a specific category. You can find category IDs in your Back Office under **Catalog > Categories** by editing a category and looking at the URL or the “ID” column in the category list.
  - **Example:** To show all products from your “Electronics” category (assuming its ID is 5), you would use `[products category="5"]`.
- **Display products from a specific manufacturer/brand:**

  - `[products manufacturer="1"]`
  - **Purpose:** This shortcode displays all products associated with a particular manufacturer or brand. Manufacturer IDs can be found under **Catalog > Brands & Suppliers > Brands**.
  - **Example:** To display all products from “Apple” (assuming its ID is 1), you would use `[products manufacturer="1"]`.
- **Display new products:**

  - `[products new="5"]`
  - **Purpose:** This shortcode displays the most recently added products to your store. The number “5” indicates how many new products you want to show.
  - **Example:** To show the 5 newest products, use `[products new="5"]`.
- **Display best-selling products:**

  - `[products bestseller="5"]`
  - **Purpose:** This shortcode displays your top-selling products. The number “5” indicates how many best-selling products you want to show.
  - **Example:** To show your 5 best-selling products, use `[products bestseller="5"]`.
- **Display products on sale:**

  - `[products sale="5"]`
  - **Purpose:** This shortcode displays products that are currently on sale. The number “5” indicates how many sale products you want to show.
  - **Example:** To show 5 products that are currently discounted, use `[products sale="5"]`.
- **Display featured products (from homepage):**

  - `[products featured="5"]`
  - **Purpose:** This shortcode displays products that are marked as “featured” on your homepage (usually controlled by the “Featured products” module). The number “5” indicates how many featured products you want to show.
  - **Example:** To show 5 of your featured products, use `[products featured="5"]`.

**Important Notes:**

- You can combine shortcodes on the same page, but each shortcode will generate its own list of products.
- Ensure there are no extra spaces or typos within the shortcode brackets `[]`.
- After adding shortcodes, save your CMS page. The products will appear on the front office automatically (unless you have “Hide products and shortcodes” enabled in the module configuration).

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Hide products and shortcodes | NO | Controls whether product lists from shortcodes are displayed (NO) or hidden (YES) on CMS pages. |
| CMS Page Editor | `[products ids="1,2,3"]` | N/A | Displays specific products by their IDs. |
| CMS Page Editor | `[products category="5"]` | N/A | Displays all products from a specific category. |
| CMS Page Editor | `[products manufacturer="1"]` | N/A | Displays all products from a specific manufacturer. |
| CMS Page Editor | `[products new="5"]` | N/A | Displays the 5 newest products. |
| CMS Page Editor | `[products bestseller="5"]` | N/A | Displays the 5 best-selling products. |
| CMS Page Editor | `[products sale="5"]` | N/A | Displays the 5 products currently on sale. |
| CMS Page Editor | `[products featured="5"]` | N/A | Displays the 5 featured products from the homepage. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My products are not showing up on the CMS page, but the shortcodes are visible.**
A: Check the module’s configuration page (**Modules > Module Manager > Configure** for “Products on CMS pages”). Ensure that “Hide products and shortcodes” is set to **NO**. If it’s set to YES, the module will hide the products and the shortcodes themselves. Also, double-check your shortcode syntax for any typos or missing quotes.

**Q: My products are not showing up, and neither are the shortcodes (just blank space).**
A: This usually means the module is active and trying to process the shortcodes, but it’s encountering an issue.
1. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” in the top right.
2. **Check Product IDs/Category IDs:** Ensure the IDs you’re using in `[products ids="..."]`, `[products category="..."]`, or `[products manufacturer="..."]` are correct and correspond to existing, active products/categories/manufacturers in your store.
3. **Product Visibility:** Make sure the products you’re trying to display are active and visible in your store (not disabled, out of stock if stock management is strict, or set to “hidden”).

**Q: The products appear, but they don’t look good with my theme’s styling.**
A: The module uses basic styling, but your theme’s CSS might override or conflict with it.
1. **Theme Customization:** Most themes have options for custom CSS. You or your webmaster can add custom CSS rules to target the product listings generated by this module.
2. **Contact Theme Developer:** If you’re unsure, contact your theme developer for advice on how to best style product grids.
3. **Contact MyPresta.eu Support:** If you suspect a module-specific styling issue, reach out to MyPresta.eu support.

**Q: Can I use multiple shortcodes on the same CMS page?**
A: Yes, you can use as many different shortcodes as you like on a single CMS page. Each shortcode will generate its own separate list of products.

**Q: Does this module support multi-language stores?**
A: Yes, the module works with PrestaShop’s multi-language capabilities. The product names and descriptions displayed will be in the language selected by the customer, just like on regular product or category pages. The shortcodes themselves (`[products ids="..."]`) remain the same across all languages.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Products on CMS pages” module primarily functions by overriding the core `CmsController` to intercept and process content before it’s rendered to the user. It uses regular expressions to find specific shortcodes within the CMS page content and replaces them with dynamically generated product lists. The product data is fetched using PrestaShop’s `Product::getProducts` and `Product::getProductsProperties` methods, and then rendered via Smarty templates.

### 4.2 Controllers (`controllers/`)

This module utilizes an override to extend core PrestaShop functionality.

- **Front-Office Controllers**:

  - `cmsproducts/override/controllers/front/CmsController.php`
    - **Class name & parent class**: `CmsController` (overrides `CmsControllerCore`)
    - **Responsibility**: This is the core of the module’s functionality. It overrides the `initContent()` method of the standard `CmsController`. Within `initContent()`, it retrieves the CMS page content, scans it for the defined shortcodes (e.g., `[products ids="..."]`), processes these shortcodes by fetching relevant product data, and then replaces the shortcodes with rendered product HTML before the page content is displayed. It also ensures that the module’s CSS is loaded.
  - `cmsproducts/override/controllers/front/index.php`
    - **Class name & parent class**: N/A (empty file)
    - **Responsibility**: This is a standard empty `index.php` file placed in subdirectories to prevent directory listing, a common security practice. It has no functional impact on the module’s logic.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the main module class’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or `ObjectModel` definitions are present in this module. It leverages existing PrestaShop core classes like `Product`, `Category`, `Manufacturer`, `Context`, `Tools`, and `Configuration`.

### 4.4 JavaScript Assets (`views/js/`)

No custom JavaScript files are included in this module. All functionality is handled server-side via PHP.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes two CSS files for styling the product listings. These are loaded via the `actionAdminControllerSetMedia` hook (for back-office context, though the override handles front-office loading).

- `cmsproducts/cmsproducts.css`
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: Contains general styling for the product grid/list generated by the shortcodes. This would include styles for product containers, images, names, prices, and potentially “Add to Cart” buttons to ensure a consistent look.
  - **Key CSS class selectors developers can override**: Likely targets classes like `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
- `cmsproducts/css.css`
  - **Scope**: Front-office customer styling.
  - **Main UI components and containers it styles**: Similar to `cmsproducts.css`, this file likely provides additional or specific styling rules for the product display, potentially for responsiveness or specific layout adjustments.
  - **Key CSS class selectors developers can override**: Similar to `cmsproducts.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render the product lists.

- **Hook templates (`views/templates/hook/`)**: None explicitly defined as hook templates. The templates are rendered directly by the `CmsController` override.
- **Admin templates (`views/templates/admin/`)**: None.
- **Front-office templates (`views/templates/front/`)**:
  - `cmsproducts/html.tpl`
    - **Purpose**: This template likely serves as a wrapper or a general container for the product lists. It might include basic HTML structure surrounding the product items.
  - `cmsproducts/products-carousel.tpl`
    - **Purpose**: This template is designed to render products in a carousel or slider format. It would contain the necessary HTML structure and potentially JavaScript initialization for a product carousel. This template is likely used when a specific shortcode parameter or module setting (not exposed in the current config) implies a carousel display.
  - `cmsproducts/products.tpl`
    - **Purpose**: This is the primary template for rendering a standard grid or list of products. It iterates through the product data passed from the PHP controller and displays individual product details (image, name, price, add to cart button, etc.). This is the most commonly used template for the `[products ...]` shortcodes.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: This module does not create any custom database tables. It stores its configuration settings in the standard `ps_configuration` table.
  - `ps_configuration` entries:
    - `mypresta_updates`: Stores information related to module updates from MyPresta.eu.
    - `cmsproducts_hide`: Stores the value of the “Hide products and shortcodes” setting (1 for enabled/YES, 0 for disabled/NO).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller sets its media assets. | While listed, the primary CSS loading for the front office is handled by the `CmsController` override. This hook might be used for potential future admin-side styling or if the module had an admin controller. |

The core functionality of processing shortcodes and rendering products is achieved through the `CmsController` override, which directly manipulates the content before display, rather than relying on a specific front-office hook for content injection.

## 5. Official Support & Updates

For official updates, technical support, and to access the latest versions of the “Products on CMS pages” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist merchants and developers with any questions or issues related to the module.
