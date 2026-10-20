---
title: "Facebook cart share + voucher coupon - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook cart share + voucher coupon PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook cart share + voucher coupon"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook cart share + voucher coupon Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Facebook cart share + voucher coupon

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop and Facebook API interactions.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
This is the main configuration screen for the "Facebook cart share + voucher coupon" module. You'll find it by navigating to **Modules > Module Manager**, searching for "Facebook cart share + voucher coupon", and clicking "Configure".

#### **General Settings**

-   **Facebook App ID (cshare_appid / cshare_app_id)**
    -   **What this setting does:** This is a unique identifier for your Facebook Application, which is required for the module to interact with Facebook's API. You need to create a Facebook App on the Facebook Developers platform (developers.facebook.com) to get this ID.
    -   **Effect of changing this setting:**
        -   *When set correctly:* The module can successfully connect to Facebook, allowing customers to share their carts and for your store to track these shares.
        -   *When left empty or set incorrectly:* The Facebook share functionality will not work, and customers will not be able to share their carts.
    -   **Recommended value:** Your unique Facebook App ID.
    -   **Merchant scenario / example:** You've registered your PrestaShop store as an app on Facebook Developers and received an App ID like `123456789012345`. Enter this ID here.

-   **Display Share Button On (cshare_lasttab)**
    -   **What this setting does:** Determines where the "Share Cart on Facebook" button will appear in your store's front office.
    -   **Effect of changing this setting:**
        -   *When set to "Shopping Cart Page":* The button appears on the page where customers review their cart contents before proceeding to checkout.
        -   *When set to "Order Confirmation Page":* The button appears after the customer has successfully placed an order.
        -   *When set to "Both":* The button appears on both pages.
    -   **Recommended value:** "Both" to maximize visibility and sharing opportunities.
    -   **Merchant scenario / example:** You want to encourage sharing both before and after a purchase, so you select "Both".

-   **Facebook Share Button Style (cshare_button_style)**
    -   **What this setting does:** Allows you to choose the visual style of the Facebook share button.
    -   **Effect of changing this setting:** Changes the appearance of the share button to better match your store's design or your preference for a larger/smaller button.
    -   **Recommended value:** Experiment to find what looks best with your theme.
    -   **Merchant scenario / example:** Your theme has a minimalist design, so you might choose a simple, text-based share button rather than a large, graphical one.

#### **Voucher Settings**

-   **Enable Voucher Generation (cshare_voucher)**
    -   **What this setting does:** Toggles whether a discount voucher is generated and offered to the customer after they successfully share their cart on Facebook.
    -   **Effect of changing this setting:**
        -   *When enabled:* A unique voucher code is created and displayed to the customer after sharing.
        -   *When disabled:* No voucher is generated or offered, removing the direct incentive for sharing.
    -   **Recommended value:** "YES" to leverage the incentive for sharing and boost conversions.
    -   **Merchant scenario / example:** You want to reward customers for sharing and encourage repeat purchases, so you enable this.

-   **Voucher Gift (cshare_gift)**
    -   **What this setting does:** Defines the type and value of the discount voucher customers receive. This corresponds to the "Discount Type" and "Value" settings when creating a new cart rule in PrestaShop.
    -   **Effect of changing this setting:**
        -   *Fixed amount:* Customer receives a specific monetary discount (e.g., $5 off).
        -   *Percentage:* Customer receives a percentage discount (e.g., 10% off).
        -   *Free shipping:* Customer receives free shipping on their next order.
    -   **Recommended value:** A value that is attractive enough to incentivize sharing but also sustainable for your business.
    -   **Merchant scenario / example:** You decide to offer a "10% discount" to encourage new purchases, so you select "Percentage" and set the value in the next field.

-   **Voucher Value (cshare_image)**
    -   **What this setting does:** Sets the specific value for the voucher, depending on the "Voucher Gift" type chosen.
    -   **Effect of changing this setting:**
        -   *If "Fixed amount" is chosen:* This will be the exact monetary value of the discount.
        -   *If "Percentage" is chosen:* This will be the percentage of the discount.
    -   **Recommended value:** A compelling discount (e.g., 5, 10, 15 for percentage; 5, 10, 20 for fixed amount).
    -   **Merchant scenario / example:** You chose "Percentage" for "Voucher Gift", so here you enter "10" for a 10% discount.

#### **Shared Content Settings**

These settings control what information about the customer's cart is included in the Facebook post when they share it.

-   **Show Prices (cshare_show_prices)**
    -   **What this setting does:** Determines whether the individual prices of products in the cart are displayed in the Facebook share post.
    -   **Effect of changing this setting:**
        -   *When enabled:* Each product listed in the shared cart will show its price.
        -   *When disabled:* Product prices will be omitted from the shared post.
    -   **Recommended value:** "YES" to provide transparency and encourage clicks, unless your pricing strategy requires otherwise.
    -   **Merchant scenario / example:** You want potential customers to see the value of the items, so you enable "Show Prices".

-   **Show Total (cshare_show_total)**
    -   **What this setting does:** Determines whether the total value of the shopping cart is displayed in the Facebook share post.
    -   **Effect of changing this setting:**
        -   *When enabled:* The total price of all items in the cart will be shown.
        -   *When disabled:* The cart total will not be included in the post.
    -   **Recommended value:** "YES" to give a clear overview of the cart's value.
    -   **Merchant scenario / example:** A customer has a cart worth $250, and you want their friends to see this significant purchase, so you enable "Show Total".

-   **Show Products (cshare_show_products)**
    -   **What this setting does:** Determines whether the names and quantities of the individual products in the cart are listed in the Facebook share post.
    -   **Effect of changing this setting:**
        -   *When enabled:* A list of products (e.g., "T-Shirt x1, Jeans x1") will appear in the post.
        -   *When disabled:* Only a general message about sharing the cart will appear, without specific product details.
    -   **Recommended value:** "YES" to showcase the specific items and generate interest.
    -   **Merchant scenario / example:** You want to highlight the specific products a customer is buying, so you enable "Show Products".

-   **Show Product URL (cshare_show_product_url)**
    -   **What this setting does:** Determines whether direct links to the individual product pages are included in the Facebook share post.
    -   **Effect of changing this setting:**
        -   *When enabled:* Each product listed will have a clickable link to its page on your store.
        -   *When disabled:* Product names will be displayed but without direct links.
    -   **Recommended value:** "YES" to drive traffic directly to product pages.
    -   **Merchant scenario / example:** You want friends of the sharer to easily click through and view the products, so you enable "Show Product URL".

#### **Advanced Settings**

-   **Force HTTPS (cshare_http)**
    -   **What this setting does:** Ensures that all URLs generated for Facebook sharing use HTTPS, even if your PrestaShop configuration might sometimes default to HTTP. This is crucial for security and Facebook's requirements.
    -   **Effect of changing this setting:**
        -   *When enabled:* All shared links will be secure (HTTPS).
        -   *When disabled:* Links might sometimes be HTTP, which can cause issues with Facebook's API and security warnings.
    -   **Recommended value:** "YES" if your store uses HTTPS (which it should!).
    -   **Merchant scenario / example:** Your entire store runs on HTTPS, so you enable this to ensure consistency and avoid browser warnings.

-   **PrestaShop Shop Name (PS_SHOP_NAME)**
    -   **What this setting does:** This field typically pulls your store's name from PrestaShop's general settings. It's used in the shared Facebook post.
    -   **Effect of changing this setting:** Ensures the correct store name is displayed in the Facebook post.
    -   **Recommended value:** Leave as default (it should auto-populate from your PrestaShop configuration).
    -   **Merchant scenario / example:** Your store is named "My Awesome Shop", and this field correctly displays "My Awesome Shop".

-   **PrestaShop Shop Email (PS_SHOP_EMAIL)**
    -   **What this setting does:** This field typically pulls your store's contact email from PrestaShop's general settings. It might be used for internal module operations or in generated content.
    -   **Effect of changing this setting:** Ensures the correct email is used if the module needs to reference it.
    -   **Recommended value:** Leave as default (it should auto-populate from your PrestaShop configuration).
    -   **Merchant scenario / example:** Your store's contact email is `info@myawesomeshop.com`, and this field correctly displays it.

-   **PrestaShop Tax (PS_TAX)**
    -   **What this setting does:** This field typically pulls your store's default tax setting. It might be used to calculate prices correctly in the shared content.
    -   **Effect of changing this setting:** Ensures tax considerations are handled correctly if prices are displayed.
    -   **Recommended value:** Leave as default (it should auto-populate from your PrestaShop configuration).
    -   **Merchant scenario / example:** Your store operates with a 20% VAT, and this field reflects that.

#### **Internal Module Settings (Usually Leave as Default)**

-   **MyPresta.eu Updates (mypresta_updates, update_, updatev_)**
    -   **What this setting does:** These are internal settings used by MyPresta.eu modules to check for updates and ensure compatibility.
    -   **Effect of changing this setting:** Modifying these could interfere with the module's ability to receive updates or function correctly.
    -   **Recommended value:** Leave as default.
    -   **Merchant scenario / example:** You generally don't need to interact with these.

-   **Facebook Init (cshare_fbinit)**
    -   **What this setting does:** An internal flag that indicates whether the Facebook SDK has been initialized.
    -   **Effect of changing this setting:** Modifying this could prevent the Facebook sharing functionality from loading correctly.
    -   **Recommended value:** Leave as default.
    -   **Merchant scenario / example:** This is a technical setting not meant for merchant interaction.

### 2.2 Dedicated Admin Screens & Controller Views
This module does not introduce any dedicated custom admin screens or controllers beyond its main configuration page. All settings are managed directly within the standard module configuration interface.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Facebook App ID | Your unique App ID | Essential for Facebook API connection; sharing won't work without it. |
| Module Configuration | Display Share Button On | Both | Controls where the share button appears (Cart, Order Confirmation, or both). |
| Module Configuration | Facebook Share Button Style | (Varies) | Changes the visual appearance of the share button. |
| Module Configuration | Enable Voucher Generation | YES | Toggles the creation and display of a discount voucher after sharing. |
| Module Configuration | Voucher Gift | Percentage / Fixed amount | Defines the type of discount (e.g., 10% off, $5 off, Free shipping). |
| Module Configuration | Voucher Value | (Your desired value) | Sets the specific value for the chosen voucher gift type. |
| Module Configuration | Show Prices | YES | Includes individual product prices in the Facebook share post. |
| Module Configuration | Show Total | YES | Includes the total cart value in the Facebook share post. |
| Module Configuration | Show Products | YES | Lists individual product names and quantities in the Facebook share post. |
| Module Configuration | Show Product URL | YES | Adds direct links to product pages in the Facebook share post. |
| Module Configuration | Force HTTPS | YES | Ensures all shared links are secure (HTTPS). |
| Module Configuration | PrestaShop Shop Name | (Auto-populated) | Displays your store's name in the Facebook post. |
| Module Configuration | PrestaShop Shop Email | (Auto-populated) | Store's contact email. |
| Module Configuration | PrestaShop Tax | (Auto-populated) | Store's default tax setting. |
| Module Configuration | MyPresta.eu Updates | (Internal) | Internal settings for module updates. |
| Module Configuration | Facebook Init | (Internal) | Internal flag for Facebook SDK initialization. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The Facebook share button isn't appearing on my cart/order confirmation page.**
*   **A:** First, check the module configuration in your Back Office (**Modules > Module Manager > Configure Facebook cart share + voucher coupon**). Ensure "Display Share Button On" is set correctly (e.g., "Shopping Cart Page", "Order Confirmation Page", or "Both"). Also, verify that your Facebook App ID is correctly entered. If it's still not showing, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q2: When customers click the share button, nothing happens or they get an error.**
*   **A:** This almost always points to an issue with your Facebook App ID or the Facebook App configuration itself.
    1.  **Double-check your Facebook App ID:** Make sure it's entered correctly in the module configuration.
    2.  **Verify Facebook App Settings:** Log in to [developers.facebook.com](https://developers.facebook.com/). Ensure your app is "Live" (not in development mode). Check the "Settings > Basic" section for your app: the "App Domains" and "Website" fields must accurately list your store's domain (e.g., `yourstore.com` and `https://www.yourstore.com`).
    3.  **Force HTTPS:** Ensure the "Force HTTPS" option in the module configuration is set to "YES" if your store uses HTTPS.

**Q3: Vouchers are not being generated after a successful share.**
*   **A:**
    1.  **Check "Enable Voucher Generation":** In the module configuration, ensure this setting is set to "YES".
    2.  **Voucher Gift & Value:** Make sure you've selected a "Voucher Gift" type (e.g., Percentage, Fixed amount) and entered a valid "Voucher Value".
    3.  **PrestaShop Cart Rule Limits:** PrestaShop has limits on the number of cart rules. While unlikely for this module, if you have an extremely high volume of shares, ensure your server can handle the creation of new cart rules.
    4.  **Error Logs:** Check your PrestaShop error logs (usually in `var/logs/` or `app/logs/` for PS 1.7+) for any related errors during the voucher generation process.

**Q4: The shared content on Facebook doesn't look right (e.g., missing prices, wrong image).**
*   **A:**
    1.  **Module Settings:** Review the "Shared Content Settings" in the module configuration (Show Prices, Show Total, Show Products, Show Product URL). Ensure they are all set to "YES" if you want maximum detail.
    2.  **Facebook Open Graph:** Facebook uses Open Graph (OG) tags from your product pages to generate previews. Ensure your PrestaShop theme and other modules are correctly generating these OG tags (especially `og:image`, `og:title`, `og:description`). You can use Facebook's [Sharing Debugger](https://developers.facebook.com/tools/debug/) to see how Facebook scrapes your URLs.
    3.  **Cache:** Clear your PrestaShop cache and your browser cache. Facebook also caches shared content, so use the Sharing Debugger to "Scrape Again" if you've made changes.

**Q5: The module doesn't look good with my custom theme.**
*   **A:** The module uses its own CSS (`css.css`, `ps16.css`). Your custom theme might be overriding or conflicting with these styles.
    1.  **Inspect Element:** Use your browser's developer tools (F12) to inspect the share button and voucher display. Identify the CSS classes applied by the module and your theme.
    2.  **Custom CSS:** You can add custom CSS to your theme's `custom.css` (or equivalent) file to override the module's styles and make it match your theme better. Target the module's specific classes to avoid affecting other parts of your store.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Facebook cart share + voucher coupon" module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class and `ModuleFrontController` for front-office interactions. It integrates with Facebook's JavaScript SDK for sharing functionality and uses PrestaShop's `CartRule` object for voucher generation. Configuration is managed via the `getContent()` method in the main module file, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    *   `cartshare/controllers/front/cartshare.php`
        *   **Class name & parent class:** `CartshareCartshareModuleFrontController` extends `ModuleFrontController`.
        *   **Responsibility:** This controller is likely responsible for handling the AJAX callback from Facebook after a share, or for rendering the dedicated cart share page if the module has one. It would process the share event and trigger the voucher generation logic. It might also be responsible for rendering the `cartsharepage.tpl` template.
    *   `cartshare/controllers/front/index.php`
        *   **Class name & parent class:** This is typically an empty file or a simple redirect to prevent directory listing, common in PrestaShop modules. It does not contain a specific controller class.
        *   **Responsibility:** Security measure to prevent direct access to the `front` directory.

-   **Back-Office Admin Controllers**:
    *   None. All administration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)
This module does not appear to define any custom classes or `ObjectModel`s within the `classes/` directory. Its core logic for voucher generation likely directly interacts with PrestaShop's `CartRule` class.

### 4.4 JavaScript Assets (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Scope:** Front-office.
    *   **Details:** This script is crucial for the client-side interaction. It likely initializes the Facebook JavaScript SDK using the `cshare_appid` from the module configuration. It binds event listeners to the "Share on Facebook" button, handles the Facebook sharing dialog, and upon successful sharing, makes an AJAX call to the `cartshare.php` front controller to trigger voucher generation and display the voucher code to the user. It might also handle the display of the voucher code dynamically on the page.

### 4.5 CSS Stylesheets (`views/css/`)

-   `cartshare/css.css`
    *   **Scope:** Front-office.
    *   **Details:** Contains general styling for the module's elements, such as the share button, the voucher display area, and any other UI components introduced by the module.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Scope:** Front-office.
    *   **Details:** Likely contains specific styling adjustments or overrides tailored for PrestaShop 1.6 themes, ensuring compatibility and proper rendering on older versions.
-   `cartshare/views/css/css/css.css`
    *   **Scope:** Front-office.
    *   **Details:** This path seems redundant (`css/css/`). It's possible it's a duplicate or an older version of `cartshare/css.css`, or contains very specific styling for certain elements. Developers should check its contents to understand its purpose.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Hook:** `displayHeader`
        *   **Output:** This template is responsible for including the Facebook JavaScript SDK initialization code and potentially the module's main JavaScript (`script.js`) and CSS files. It ensures the Facebook API is ready before the share button is rendered.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Hook:** `displayShoppingcart`, `displayOrderConfirmation` (depending on module configuration)
        *   **Output:** Renders the "Share Cart on Facebook" button and the container for displaying the voucher code after a successful share. This is the primary visual component customers interact with.

-   **Front-office templates (`views/templates/front/`)**:
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Purpose:** This template is likely rendered by the `CartshareCartshareModuleFrontController` and could be a dedicated page or a partial view for displaying the cart contents to be shared, or the voucher code.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Purpose:** This template dynamically generates the content that will be passed to the Facebook sharing dialog. It constructs the title, description, image, and URLs based on the customer's cart and the module's configuration settings (e.g., `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Purpose:** This template might be an override or an additional block specifically designed to be included within the standard PrestaShop shopping cart page, potentially to render the share button or other module-specific content directly within the cart summary.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   This module does not create custom SQL tables.
    *   Configuration settings are stored in the `ps_configuration` table, using keys such as `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES`, etc.
    *   Vouchers are generated as standard PrestaShop `CartRule` entries, stored in `ps_cart_rule` and related tables.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | Initializes Facebook SDK, loads module's JS/CSS assets. |
| `displayShoppingcart` | On the shopping cart summary page. | Renders the "Share Cart on Facebook" button and voucher display area. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Renders the "Share Cart on Facebook" button and voucher display area. |
| `displayShoppingCart` | (Duplicate of `displayShoppingcart` in module info, likely refers to the same hook) | Renders the "Share Cart on Facebook" button and voucher display area. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and professional support for the "Facebook cart share + voucher coupon" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
