---
title: "Facebook Shop - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Shop PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Shop - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Shop Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-shop/)
>
> ---


# Facebook Shop

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
- **Facebook Fan Page**: You must have an active Facebook Fan Page (not a personal profile) where you are an administrator.
- **SSL Certificate**: Your PrestaShop store must have an active SSL certificate (HTTPS) for the Facebook Shop to function correctly, as Facebook requires secure connections for embedded applications.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for your Facebook Shop module. You’ll find a series of tabs or sections to customize how your shop appears and functions on Facebook.

#### General Settings Tab (or similar initial view)

- **Display MyPresta.eu Updates:**

  - **What this setting does:** Controls whether you see notifications about updates from MyPresta.eu directly in your module configuration.
  - **Effect of changing this setting:**
    - *When enabled:* You’ll receive alerts for new versions or important news from MyPresta.eu, helping you keep your module up-to-date.
    - *When disabled:* You won’t see these notifications, which might mean you miss out on important updates or bug fixes.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Keep this enabled to ensure you’re always aware of the latest improvements and security patches for your Facebook Shop module.
- **Facebook Shop Language Display:** (`faceshop_lang_disp`)

  - **What this setting does:** Determines whether the language selector is visible in your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can switch the language of your Facebook Shop, useful for international stores.
    - *When disabled:* The shop will display in the default language, or the language detected by Facebook, without an explicit selector.
  - **Recommended value:** YES (if you have multiple languages enabled in PrestaShop)
  - **Merchant scenario / example:** If you sell to customers in different countries and have translated your PrestaShop store, enable this to allow them to browse in their preferred language.
- **Facebook Shop Currency Display:** (`faceshop_curr_disp`)

  - **What this setting does:** Determines whether the currency selector is visible in your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can switch the currency displayed in your Facebook Shop, useful for international stores.
    - *When disabled:* The shop will display prices in your default currency.
  - **Recommended value:** YES (if you have multiple currencies enabled in PrestaShop)
  - **Merchant scenario / example:** If you accept payments in USD, EUR, and GBP, enable this so customers can see prices in their local currency.
- **Enable Module Rewrite (SEO Friendly URLs):** (`faceshop_modrew`)

  - **What this setting does:** Controls whether the module uses SEO-friendly URLs within the Facebook Shop, similar to your main PrestaShop store.
  - **Effect of changing this setting:**
    - *When enabled:* URLs for products and categories within the Facebook Shop will be clean and descriptive (e.g., `yourstore.com/product/my-awesome-product`). This is generally better for SEO and user experience.
    - *When disabled:* URLs might be less readable (e.g., `yourstore.com/index.php?id_product=123`).
  - **Recommended value:** YES
  - **Merchant scenario / example:** Always enable this for better search engine visibility and a more professional look for your product links shared from Facebook.

#### Homepage Settings Tab

- **Display Homepage Items Count:** (`faceshop_homepage_itemcount`)

  - **What this setting does:** Sets the number of products to display on the homepage of your Facebook Shop.
  - **Effect of changing this setting:**
    - *When set to 10:* Your Facebook Shop homepage will show 10 products.
    - *When set to 20:* Your Facebook Shop homepage will show 20 products.
  - **Recommended value:** 12-24 (enough to show variety without overwhelming the page).
  - **Merchant scenario / example:** If you want to showcase a wide range of products immediately, set a higher number. If you prefer a cleaner look with fewer, more prominent items, set a lower number.
- **Display Homepage Discounted Products:** (`faceshop_homepage_disphot`)

  - **What this setting does:** Controls whether discounted (on-sale) products are featured on the homepage of your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Products currently on sale will be prominently displayed, encouraging impulse buys.
    - *When disabled:* Only regular-priced products will appear on the homepage (unless other display options are enabled).
  - **Recommended value:** YES
  - **Merchant scenario / example:** Use this to drive attention to your promotions and clear out inventory.
- **Display Homepage New Products:** (`faceshop_homepage_dispnew`)

  - **What this setting does:** Controls whether your newest products are featured on the homepage of your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Recently added products will be showcased, keeping your shop fresh and exciting for returning visitors.
    - *When disabled:* New products won’t have a dedicated section on the homepage.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you frequently add new items, this is a great way to highlight them and encourage repeat visits.
- **Display Homepage Root Category:** (`faceshop_homepage_root`)

  - **What this setting does:** Allows you to select a specific root category to display products from on your Facebook Shop homepage. If left empty, it will display products from your default PrestaShop root category.
  - **Effect of changing this setting:**
    - *When a specific category is selected:* Only products from that category and its subcategories will appear on the homepage.
    - *When left empty:* Products from your entire store’s default root category will be considered for the homepage display.
  - **Recommended value:** Leave empty unless you have a specific marketing strategy.
  - **Merchant scenario / example:** If you’re running a special campaign for “Summer Collection” and want only those products on your Facebook Shop homepage, you would select the “Summer Collection” category here.

#### Header Settings Tab

- **Display Header in Facebook Shop:** (`faceshop_header_disp`)
  - **What this setting does:** Controls whether the header section of your PrestaShop store (logo, search bar, cart summary) is visible within the embedded Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Your Facebook Shop will have a familiar header, making it feel more like your main store.
    - *When disabled:* The header will be hidden, providing a more minimalist look.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Keeping the header visible helps maintain brand consistency and provides essential navigation elements like the search bar.

#### Category Page Settings Tab

- **Root Category for Facebook Shop:** (`faceshop_cat_root`)

  - **What this setting does:** Defines the main category from which your Facebook Shop will start displaying products and categories. This acts as the “root” for your Facebook Shop’s navigation.
  - **Effect of changing this setting:**
    - *When “Home” (default PrestaShop root) is selected:* All categories and products from your entire store will be accessible.
    - *When a specific category (e.g., “Clothing”) is selected:* Only “Clothing” and its subcategories/products will be visible in the Facebook Shop.
  - **Recommended value:** “Home” (or your main store’s root category) unless you want to limit the scope of your Facebook Shop.
  - **Merchant scenario / example:** If you only want to sell a specific line of products (e.g., “Electronics”) on Facebook, you would set this to your “Electronics” category.
- **Display New Products on Category Pages:** (`faceshop_cat_dispnew`)

  - **What this setting does:** Controls whether new products are highlighted or have a dedicated section on category listing pages within your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers browsing categories will easily spot recently added items.
    - *When disabled:* New products will simply appear in the regular listing without special emphasis.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Helps customers discover your latest arrivals even when they’re browsing specific product types.
- **Display Discounted Products on Category Pages:** (`faceshop_cat_disphot`)

  - **What this setting does:** Controls whether discounted products are highlighted or have a dedicated section on category listing pages within your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers browsing categories will easily spot items on sale.
    - *When disabled:* Discounted products will simply appear in the regular listing without special emphasis.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Encourages purchases by making sale items more visible within relevant categories.
- **Items Count per Category Page:** (`faceshop_cat_itemcount`)

  - **What this setting does:** Sets the number of products to display per page when customers are browsing categories in your Facebook Shop.
  - **Effect of changing this setting:**
    - *When set to 12:* Each category page will show 12 products before pagination.
    - *When set to 30:* Each category page will show 30 products.
  - **Recommended value:** 12-24 (standard for most e-commerce sites).
  - **Merchant scenario / example:** A higher number reduces clicks but can make pages load slower. A lower number requires more clicks but can feel less overwhelming.
- **Category Display Style:** (`faceshop_cat_dispstyle`)

  - **What this setting does:** Determines how categories are presented in the Facebook Shop.
  - **Effect of changing this setting:**
    - *Option A (e.g., “Grid View”):* Categories are shown as a grid of images/names.
    - *Option B (e.g., “List View”):* Categories are shown as a vertical list.
  - **Recommended value:** Grid View (often more visually appealing).
  - **Merchant scenario / example:** Choose the style that best fits your brand’s aesthetic and how you want customers to navigate your product range.

#### Slider Settings Tab

- **Display Slider in Facebook Shop:** (`faceshop_slider_disp`)

  - **What this setting does:** Controls whether an image slider (carousel) is displayed in your Facebook Shop. This slider typically showcases featured products, promotions, or banners.
  - **Effect of changing this setting:**
    - *When enabled:* A rotating banner or product slider will appear, grabbing attention.
    - *When disabled:* No slider will be shown, resulting in a static layout.
  - **Recommended value:** YES (if you have compelling images for a slider).
  - **Merchant scenario / example:** Use the slider to highlight your latest collection, seasonal sales, or best-selling items right at the top of your Facebook Shop.
- **Slider Transition Time (in milliseconds):** (`faceshop_slider_time`)

  - **What this setting does:** Sets how long each slide remains visible before transitioning to the next.
  - **Effect of changing this setting:**
    - *When set to 3000 (3 seconds):* Slides will change every 3 seconds.
    - *When set to 5000 (5 seconds):* Slides will change every 5 seconds.
  - **Recommended value:** 4000-6000 (4-6 seconds) to allow users enough time to read.
  - **Merchant scenario / example:** Adjust this based on the amount of information on your slides. Shorter times for image-only slides, longer for slides with text.
- **Slider Placement:** (`faceshop_slider_place`)

  - **What this setting does:** Determines where the slider appears within your Facebook Shop (e.g., top of the page, below categories).
  - **Effect of changing this setting:**
    - *When set to “Top”:* The slider will be the first thing customers see.
    - *When set to “Below Products”:* The slider will appear further down the page.
  - **Recommended value:** Top (for maximum visibility).
  - **Merchant scenario / example:** Place the slider at the top to immediately capture attention with your most important promotions.

#### Menu Settings Tab

- **Display New Products Link in Menu:** (`faceshop_menu_newproducts`)

  - **What this setting does:** Adds a link to “New Products” in the navigation menu of your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can easily click to see all your latest additions.
    - *When disabled:* This specific link will not appear in the menu.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Essential for stores that frequently update their inventory to help customers discover fresh items.
- **Display Sale Products Link in Menu:** (`faceshop_menu_saleproducts`)

  - **What this setting does:** Adds a link to “Sale Products” or “Discounts” in the navigation menu of your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can quickly find all your discounted items.
    - *When disabled:* This specific link will not appear in the menu.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Great for driving traffic to your promotions and increasing sales.
- **Display Information Pages Link in Menu:** (`faceshop_menu_informations`)

  - **What this setting does:** Adds a link to your PrestaShop CMS (Information) pages (e.g., About Us, Delivery, Terms & Conditions) in the navigation menu.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can access important non-product information directly.
    - *When disabled:* These links will not appear in the menu.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Crucial for building trust and providing necessary customer service information.
- **Display Contact Page Link in Menu:** (`faceshop_menu_contact`)

  - **What this setting does:** Adds a link to your PrestaShop Contact Us page in the navigation menu.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can easily find how to get in touch with you.
    - *When disabled:* This specific link will not appear in the menu.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Provides a direct channel for customer inquiries, improving support.
- **Menu Category Display Style:** (`faceshop_menu_catstyle`)

  - **What this setting does:** Determines how categories are displayed in the main navigation menu of your Facebook Shop.
  - **Effect of changing this setting:**
    - *Option A (e.g., “Dropdown”):* Categories appear in a dropdown menu.
    - *Option B (e.g., “Horizontal List”):* Categories appear as a horizontal list.
  - **Recommended value:** Dropdown (for many categories) or Horizontal List (for few categories).
  - **Merchant scenario / example:** If you have many product categories, a dropdown menu keeps the navigation clean. If you only have a few main categories, a horizontal list might be more direct.
- **Display Manufacturers Link in Menu:** (`faceshop_menu_manuf`)

  - **What this setting does:** Adds a link to your PrestaShop Manufacturers page in the navigation menu.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can browse products by brand or manufacturer.
    - *When disabled:* This specific link will not appear in the menu.
  - **Recommended value:** YES (if you sell products from multiple distinct brands).
  - **Merchant scenario / example:** If you’re a reseller of various brands, this helps customers find products from their favorite manufacturers.

#### Product Page Settings Tab

- **Display Breadcrumb Navigation:** (`faceshop_display_breadcrumb`)

  - **What this setting does:** Controls whether the “breadcrumb” navigation (e.g., Home > Category > Subcategory > Product) is shown on product pages.
  - **Effect of changing this setting:**
    - *When enabled:* Helps customers understand their location within the store hierarchy and easily navigate back to parent categories.
    - *When disabled:* The breadcrumb trail will be hidden.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Improves user experience by providing clear navigation paths, especially for stores with deep category structures.
- **Trim Product Description:** (`faceshop_pdisp_trim`)

  - **What this setting does:** If enabled, it will shorten long product descriptions on the product page, often showing a “Read More” link.
  - **Effect of changing this setting:**
    - *When enabled:* Product pages appear cleaner, and users can choose to expand the description if interested.
    - *When disabled:* Full product descriptions are always shown, which can make pages very long.
  - **Recommended value:** YES (for products with very long descriptions).
  - **Merchant scenario / example:** Prevents product pages from being overly long, especially on mobile, by showing a concise summary first.
- **Display Product Price:** (`faceshop_pdisp_price`)

  - **What this setting does:** Controls whether the product price is visible on product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The price will be clearly displayed.
    - *When disabled:* The price will be hidden.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Hiding prices is generally not recommended for an e-commerce store unless you have a specific B2B strategy requiring quotes. For most retail, prices are essential.
- **Display Product Name:** (`faceshop_pdisp_name`)

  - **What this setting does:** Controls whether the product name is visible on product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The product’s name will be displayed.
    - *When disabled:* The product name will be hidden.
  - **Recommended value:** YES
  - **Merchant scenario / example:** The product name is fundamental for identification; always keep this enabled.
- **Display Product Image:** (`faceshop_pdisp_image`)

  - **What this setting does:** Controls whether the product image is visible on product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The product’s main image and additional images will be displayed.
    - *When disabled:* Product images will be hidden.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Product images are crucial for online sales; always keep this enabled.

#### Social Sharing Settings Tab

- **Display Facebook Share Button:** (`faceshop_social_facebook`)

  - **What this setting does:** Adds a Facebook “Share” button to product pages within your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can easily share products with their Facebook friends, increasing viral marketing.
    - *When disabled:* The Facebook share button will not appear.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Encourage customers to spread the word about your products on their own timelines.
- **Display Pinterest Share Button:** (`faceshop_social_pinterest`)

  - **What this setting does:** Adds a Pinterest “Pin It” button to product pages within your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can easily pin product images to their Pinterest boards, driving traffic from Pinterest.
    - *When disabled:* The Pinterest share button will not appear.
  - **Recommended value:** YES (especially if your products are visually appealing).
  - **Merchant scenario / example:** Great for fashion, home decor, crafts, and other visually driven products to leverage Pinterest’s audience.
- **Display Google+ Share Button:** (`faceshop_social_google`)

  - **What this setting does:** Adds a Google+ share button to product pages within your Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can share products on Google+.
    - *When disabled:* The Google+ share button will not appear.
  - **Recommended value:** NO (Google+ has been discontinued).
  - **Merchant scenario / example:** This platform is no longer active, so keeping it enabled is unnecessary.

#### Footer Settings Tab

- **Display Footer in Facebook Shop:** (`faceshop_footer_disp`)
  - **What this setting does:** Controls whether the footer section of your PrestaShop store (copyright, links, payment icons) is visible within the embedded Facebook Shop.
  - **Effect of changing this setting:**
    - *When enabled:* Your Facebook Shop will have a familiar footer, maintaining brand consistency and providing additional links.
    - *When disabled:* The footer will be hidden.
  - **Recommended value:** YES
  - **Merchant scenario / example:** The footer often contains important legal links (privacy policy, terms of service) and contact information, which are good to keep visible for trust and compliance.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **General Settings** | Display MyPresta.eu Updates | YES | Receive module update notifications. |
|  | Facebook Shop Language Display (`faceshop_lang_disp`) | YES | Allow customers to change shop language. |
|  | Facebook Shop Currency Display (`faceshop_curr_disp`) | YES | Allow customers to change shop currency. |
|  | Enable Module Rewrite (SEO Friendly URLs) (`faceshop_modrew`) | YES | Use clean, descriptive URLs for better SEO and UX. |
| **Homepage Settings** | Display Homepage Items Count (`faceshop_homepage_itemcount`) | 12-24 | Number of products shown on the homepage. |
|  | Display Homepage Discounted Products (`faceshop_homepage_disphot`) | YES | Feature products on sale on the homepage. |
|  | Display Homepage New Products (`faceshop_homepage_dispnew`) | YES | Feature new arrivals on the homepage. |
|  | Display Homepage Root Category (`faceshop_homepage_root`) | Empty (default root) | Select a specific category for homepage products. |
| **Header Settings** | Display Header in Facebook Shop (`faceshop_header_disp`) | YES | Show your store’s header (logo, search, cart). |
| **Category Page Settings** | Root Category for Facebook Shop (`faceshop_cat_root`) | Home (default root) | Defines the starting category for the Facebook Shop. |
|  | Display New Products on Category Pages (`faceshop_cat_dispnew`) | YES | Highlight new products within categories. |
|  | Display Discounted Products on Category Pages (`faceshop_cat_disphot`) | YES | Highlight sale products within categories. |
|  | Items Count per Category Page (`faceshop_cat_itemcount`) | 12-24 | Number of products shown per category page. |
|  | Category Display Style (`faceshop_cat_dispstyle`) | Grid View | How categories are presented (grid/list). |
| **Slider Settings** | Display Slider in Facebook Shop (`faceshop_slider_disp`) | YES | Show an image/product slider. |
|  | Slider Transition Time (in milliseconds) (`faceshop_slider_time`) | 4000-6000 | Speed of slide transitions. |
|  | Slider Placement (`faceshop_slider_place`) | Top | Position of the slider (e.g., top of page). |
| **Menu Settings** | Display New Products Link in Menu (`faceshop_menu_newproducts`) | YES | Add “New Products” to the navigation menu. |
|  | Display Sale Products Link in Menu (`faceshop_menu_saleproducts`) | YES | Add “Sale Products” to the navigation menu. |
|  | Display Information Pages Link in Menu (`faceshop_menu_informations`) | YES | Add links to CMS pages (About Us, etc.). |
|  | Display Contact Page Link in Menu (`faceshop_menu_contact`) | YES | Add a “Contact Us” link. |
|  | Menu Category Display Style (`faceshop_menu_catstyle`) | Dropdown | How categories appear in the menu (dropdown/list). |
|  | Display Manufacturers Link in Menu (`faceshop_menu_manuf`) | YES | Add a link to manufacturers/brands. |
| **Product Page Settings** | Display Breadcrumb Navigation (`faceshop_display_breadcrumb`) | YES | Show navigation path (Home > Category > Product). |
|  | Trim Product Description (`faceshop_pdisp_trim`) | YES | Shorten long product descriptions. |
|  | Display Product Price (`faceshop_pdisp_price`) | YES | Show product price. |
|  | Display Product Name (`faceshop_pdisp_name`) | YES | Show product name. |
|  | Display Product Image (`faceshop_pdisp_image`) | YES | Show product images. |
| **Social Sharing Settings** | Display Facebook Share Button (`faceshop_social_facebook`) | YES | Allow sharing on Facebook. |
|  | Display Pinterest Share Button (`faceshop_social_pinterest`) | YES | Allow sharing on Pinterest. |
|  | Display Google+ Share Button (`faceshop_social_google`) | NO | Google+ is discontinued. |
| **Footer Settings** | Display Footer in Facebook Shop (`faceshop_footer_disp`) | YES | Show your store’s footer. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My Facebook Shop isn’t showing up, or I see an error message.**
A1:

- **Check SSL:** Ensure your PrestaShop store has a valid SSL certificate (HTTPS). Facebook requires secure connections for embedded applications. If your store is not HTTPS, the Facebook Shop will not load.
- **Facebook Page Settings:** Double-check that you are an administrator of the Facebook Fan Page and that the “Shop” tab is correctly added and configured on Facebook itself.
- **Module Configuration:** Go back to the module configuration in PrestaShop and ensure all settings are saved correctly.
- **Clear Cache:** In PrestaShop, go to **Advanced Parameters > Performance** and clear the Smarty cache, browser cache, and any other caches.

**Q2: Products are not displaying correctly, or images are missing.**
A2:

- **Product Settings:** Verify that the products you expect to see are active and visible in your main PrestaShop store.
- **Image Paths:** Ensure your product images have correct paths and are accessible publicly.
- **Module Settings:** Check the `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price` settings to ensure they are enabled.
- **Root Category:** Confirm that your `faceshop_cat_root` and `faceshop_homepage_root` settings are correctly pointing to categories that contain products.

**Q3: The module looks different on mobile devices within Facebook.**
A3:

- **Facebook App vs. Browser:** The experience can vary slightly between the Facebook mobile app and accessing Facebook via a mobile browser. The module is designed to be responsive, but Facebook’s own wrapper can influence the final look.
- **Check Responsiveness:** Test your main PrestaShop store on mobile to ensure it’s fully responsive. The Facebook Shop inherits much of its styling from your main store.
- **Custom CSS:** If you have custom CSS in your PrestaShop theme, it might be interfering. Consult a web developer to inspect the CSS within the Facebook iframe.

**Q4: How do I translate the Facebook Shop into other languages?**
A4:

- **PrestaShop Translations:** The Facebook Shop module pulls content (product names, descriptions, category names) directly from your PrestaShop store. Ensure all your product and category content is translated within PrestaShop itself.
- **Module Text:** For the module’s own interface text (e.g., “New Products” link), go to **International > Translations** in your PrestaShop Back Office. Select “Installed modules translations,” choose your theme, your language, and then find the “Facebook Shop” module to translate its specific strings.
- **Language Selector:** Make sure `faceshop_lang_disp` is enabled in the module configuration to allow customers to switch languages.

**Q5: My Facebook Shop is slow to load.**
A5:

- **Image Optimization:** Ensure your product images are optimized for web use (compressed, appropriate dimensions). Large images are a common cause of slow loading.
- **Hosting Performance:** Check your web hosting performance. A slow server will affect both your main store and your Facebook Shop.
- **Number of Products:** If you’re displaying a very high number of products on the homepage or category pages (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), consider reducing these numbers.
- **Caching:** Ensure PrestaShop’s caching mechanisms are properly configured (**Advanced Parameters > Performance**).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Facebook Shop module (`faceshop`) is designed as a standard PrestaShop module, primarily extending the `Module` class. It leverages PrestaShop’s configuration system (`Configuration::get()`, `Configuration::updateValue()`) to store its settings. The module’s core functionality involves rendering a simplified version of the PrestaShop front-office within an iframe on a Facebook Fan Page. It achieves this by dynamically adjusting the display based on a specific URL parameter (`?fc=module&module=faceshop&controller=shop`). The module doesn’t introduce custom database tables or complex ObjectModels but rather manipulates the existing PrestaShop front-office display through hooks and template overrides.

### 4.2 Controllers (`controllers/`)

This module does **not** contain dedicated front-office or back-office controllers in the `controllers/` directory.
Its front-office functionality is primarily handled by the main `faceshop.php` file, which intercepts requests via a custom `shop` controller parameter (e.g., `index.php?fc=module&module=faceshop&controller=shop`). This approach allows the module to render a modified version of the standard PrestaShop front-office within the Facebook iframe, rather than creating entirely new page structures.

### 4.3 Core Classes & Models (`classes/`)

The module does **not** introduce any custom classes or ObjectModels in a `classes/` directory. All core logic is encapsulated within the main `faceshop/faceshop.php` file.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for enhancing the front-office display within the Facebook iframe.

- `faceshop/jscolor/jscolor.js`
  - **Scope:** Back-office (likely used in the module configuration form).
  - **Description:** A JavaScript library for a color picker. It allows administrators to select colors easily for module settings, though no explicit color settings were identified in the configuration keys, it’s a common utility for UI customization.
- `faceshop/js/advajax.js`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** Likely a custom AJAX utility script. It would handle asynchronous requests for loading product data, pagination, or other dynamic content within the Facebook Shop without full page reloads. This improves user experience by making the shop feel more responsive.
- `faceshop/js/jquery.nivo.slider.pack.js`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** A packed version of the Nivo Slider jQuery plugin. This script is responsible for the functionality of the image slider (`faceshop_slider_disp`) on the Facebook Shop homepage, handling transitions, navigation, and auto-play.
- `faceshop/js/shop2.js`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** This is likely the main custom JavaScript file for the Facebook Shop’s front-end logic. It would contain code for:
    - Initializing the Nivo Slider.
    - Handling dynamic content loading (e.g., “Load More” buttons for products).
    - Adjusting the layout or behavior specifically for the Facebook iframe environment.
    - Potentially handling interactions with the Facebook SDK (though not explicitly mentioned, common for Facebook apps).
    - Any custom UI enhancements or event listeners specific to the embedded shop.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes several CSS files to style the embedded Facebook Shop, ensuring it looks consistent and functions correctly within the iframe.

- `faceshop/css.css`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** A general stylesheet for the Facebook Shop. It likely contains core layout rules, typography, and basic styling for common elements (buttons, links, forms) to ensure a consistent look.
- `faceshop/css/style.css`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** This could be a more specific stylesheet, potentially overriding or extending `css.css`. It might contain styles for specific module features or layout adjustments to better fit the Facebook environment.
- `faceshop/default/default.css`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** This stylesheet is likely part of the Nivo Slider plugin, providing default styling for the slider’s navigation, captions, and overall appearance. Developers can override these styles to match the store’s theme.
- `faceshop/style.css`
  - **Scope:** Front-office (within the Facebook iframe).
  - **Description:** Similar to `faceshop/css/style.css`, this could be another primary stylesheet or a fallback/legacy file. It would define the visual presentation of the shop’s elements, ensuring they are rendered correctly within the Facebook iframe.

### 4.6 Smarty Template Structure (`views/templates/`)

The module dossier indicates no specific `.tpl` files were found in `views/templates/`. This suggests that the module primarily works by:

1. **Intercepting standard PrestaShop front-office requests:** When accessed via the Facebook Shop URL, the module likely modifies the global Smarty variables or template paths to render existing PrestaShop theme templates.
2. **Using `display` methods within `faceshop.php`:** The module’s `display()` methods might directly render HTML or include snippets from the main PrestaShop theme, dynamically adding or removing elements based on its configuration.
3. **JavaScript-driven rendering:** Some elements might be dynamically injected or modified by the JavaScript files after the initial page load.

If custom templates were present, they would typically be found in:

- `views/templates/hook/`: For content rendered in specific PrestaShop hooks.
- `views/templates/admin/`: For custom back-office forms or displays.
- `views/templates/front/`: For standalone front-office pages or specific module content.

The absence of explicit `.tpl` files implies a more direct manipulation of the existing PrestaShop front-office rendering process.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table (or `_configuration` depending on table prefix) using the configuration keys listed in section 4.1.
- **Registered Hooks Table**:
  The module primarily interacts with the PrestaShop front-office display. While the dossier lists “Header, Columns, Product, or Footer” as front-office hooks, the module’s core functionality is to embed the *entire* front-office. It likely uses a combination of:

  - **`hookDisplayHeader`**: To inject its CSS and JavaScript assets, and potentially to modify the `<head>` section for Facebook iframe compatibility.
  - **`hookDisplayFooter`**: To inject additional scripts or content at the bottom of the page.
  - **`actionFrontControllerSetMedia`**: (PrestaShop 1.7+) To register its CSS and JS files.
  - **Internal logic for rendering the shop**: The module likely has internal logic that, when detected as being loaded within the Facebook iframe, modifies the standard PrestaShop front-office output to hide/show elements based on its configuration settings (e.g., `faceshop_header_disp`, `faceshop_footer_disp`). This is often achieved by overriding or manipulating Smarty variables and template assignments within the module’s `display()` or `hook` methods.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Before the main content of the page, within the `<head>` section. | Inject module’s CSS and JavaScript files, potentially modify meta tags for Facebook iframe. |
| `displayFooter` | At the end of the page content, before the closing `</body>` tag. | Inject additional scripts or tracking codes, or modify footer content if `faceshop_footer_disp` is enabled. |
| `actionFrontControllerSetMedia` (PS 1.7+) | During the media setting phase of a front controller. | Register CSS and JS files for optimal loading. |
| (Implicit) Product Page Hooks | On product detail pages. | Modify product page display based on `faceshop_pdisp_trim`, `faceshop_pdisp_price`, etc., and inject social sharing buttons. |
| (Implicit) Category Page Hooks | On category listing pages. | Modify category page display based on `faceshop_cat_dispnew`, `faceshop_cat_disphot`, etc. |
| (Implicit) Homepage Hooks | On the shop’s homepage. | Render slider, featured products, new products, and discounted products based on module settings. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for your Facebook Shop module, please refer to your customer account at MyPresta.eu. Our team is dedicated to ensuring your module functions optimally and helps you maximize your online sales.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support Contact:** <https://mypresta.eu/contact>
