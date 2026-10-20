---
title: "Facebook Wishlist - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Facebook Wishlist PrestaShop module by MyPresta.eu."
sidebar:
  label: "Facebook Wishlist - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Facebook Wishlist Module on MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/social-networks/facebook-wishlist/)
>
> ---


# Facebook Wishlist

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available by default. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the Facebook Wishlist module in the Module Manager. This will take you to the main configuration screen.

#### **Facebook App ID**

- **What this setting does:** This is a unique identifier provided by Facebook for your specific application (in this case, your PrestaShop store’s integration with Facebook). It tells Facebook which app is requesting the wishlist action.
- **Effect of changing this setting:**
  - *When correctly entered:* The “Add to Facebook Wishlist” button will function correctly, allowing products to be added to Facebook timelines.
  - *When incorrect or empty:* The button will likely not work, or Facebook will display an error, preventing customers from adding products to their wishlists.
- **Recommended value:** This field *must* contain your valid Facebook App ID. You will need to create a Facebook App on the [Facebook for Developers](https://developers.facebook.com/) website to obtain this ID.
- **Merchant scenario / example:** You’ve created a Facebook App for your store, and Facebook has given you an App ID like `123456789012345`. You would enter this exact number here. Without it, Facebook won’t know which store is trying to share content.

#### **Facebook App Secret**

- **What this setting does:** This is a secret key associated with your Facebook App ID. It’s used for secure communication between your PrestaShop store and Facebook’s servers. It helps verify that requests are coming from your legitimate application.
- **Effect of changing this setting:**
  - *When correctly entered:* Secure communication is established, and the module functions as intended.
  - *When incorrect or empty:* Communication with Facebook may fail, leading to errors or non-functional wishlist features.
- **Recommended value:** This field *must* contain your valid Facebook App Secret. Like the App ID, you obtain this from your Facebook App settings on the [Facebook for Developers](https://developers.facebook.com/) website. Keep this secret secure and never share it publicly.
- **Merchant scenario / example:** After creating your Facebook App, you’ll find both the App ID and App Secret in your app’s dashboard. The secret might look like a long string of letters and numbers (e.g., `abcdef1234567890abcdef1234567890`). Enter it precisely as provided by Facebook.

#### **Facebook Page URL**

- **What this setting does:** This allows you to link your store’s official Facebook Page to the wishlist functionality. When customers interact with the wishlist, it can sometimes reference or link back to your main Facebook Page.
- **Effect of changing this setting:**
  - *When correctly entered:* Enhances brand visibility on Facebook and provides a direct link to your official page.
  - *When incorrect or empty:* The module will still function, but you might miss an opportunity to direct users to your main Facebook presence.
- **Recommended value:** Enter the full URL of your store’s official Facebook Page (e.g., `https://www.facebook.com/YourStoreName`). If you don’t have an official page, you can leave this empty.
- **Merchant scenario / example:** Your store has a Facebook Page at `https://www.facebook.com/MyPrestaEu`. Entering this URL here ensures that any social sharing related to the wishlist can potentially direct users to your main brand page on Facebook.

#### **Position of the button**

- **What this setting does:** This controls where the “Add to Facebook Wishlist” button appears on your product pages.
- **Effect of changing this setting:**
  - *When set to ‘Product page’:* The button will be displayed prominently on the product details page, typically near the “Add to Cart” button. This is the most common and recommended placement.
  - *When set to other options (e.g., ‘Header’, ‘Columns’, ‘Footer’):* The module might attempt to display the button in these areas, but its functionality is primarily tied to specific product information, making ‘Product page’ the most logical choice. Other positions might not display the button or might not function correctly without specific product context.
- **Recommended value:** **Product page**. This ensures the button is visible when customers are actively viewing a product they might want to wishlist.
- **Merchant scenario / example:** You want customers to easily find the wishlist button right when they are considering buying a product. Setting this to ‘Product page’ places it logically next to other purchase-related actions.

#### **Show button on product page**

- **What this setting does:** This is a simple ON/OFF switch to enable or disable the display of the “Add to Facebook Wishlist” button on your product pages.
- **Effect of changing this setting:**
  - *When enabled (YES):* The button will be visible and functional on all product pages.
  - *When disabled (NO):* The button will be hidden, and customers will not be able to add products to their Facebook wishlists via your store.
- **Recommended value:** **YES**. To utilize the module’s core functionality, this should always be enabled.
- **Merchant scenario / example:** You’ve completed all the setup and want your customers to start using the feature. You would set this to YES. If you temporarily want to hide the feature for maintenance or a campaign, you could set it to NO.

#### **Show button on category page**

- **What this setting does:** This controls whether the “Add to Facebook Wishlist” button appears on product listings within category pages.
- **Effect of changing this setting:**
  - *When enabled (YES):* A wishlist button will appear next to each product on category and listing pages. This can be useful for quick wishlisting but might clutter the layout depending on your theme.
  - *When disabled (NO):* The button will only appear on the individual product pages, keeping category pages cleaner.
- **Recommended value:** **NO**. While potentially useful, displaying the button on category pages can sometimes lead to a less optimal user experience or visual clutter. It’s generally more effective on the dedicated product page.
- **Merchant scenario / example:** You have a very clean category page design and want to minimize distractions. You would set this to NO, ensuring the wishlist action is only available when a customer is focused on a single product.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Facebook App ID | Your Facebook App ID | Unique identifier for your store’s Facebook integration. **Critical for functionality.** |
| Module Configuration | Facebook App Secret | Your Facebook App Secret | Secure key for communication with Facebook. **Critical for functionality.** |
| Module Configuration | Facebook Page URL | `https://www.facebook.com/YourStoreName` (if applicable) | Links to your official Facebook Page, enhancing brand visibility. |
| Module Configuration | Position of the button | Product page | Determines where the wishlist button appears. **Product page is recommended.** |
| Module Configuration | Show button on product page | YES | Enables/disables the button on individual product pages. **Recommended: YES.** |
| Module Configuration | Show button on category page | NO | Enables/disables the button on product listings in category pages. **Recommended: NO.** |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Add to Facebook Wishlist” button isn’t appearing on my product pages.**
A:

- **Check Module Status:** Ensure the module is installed and enabled in **Modules > Module Manager**.
- **Configuration Settings:** Go to the module’s configuration page and verify that “Show button on product page” is set to **YES**.
- **Facebook App ID/Secret:** Double-check that your Facebook App ID and App Secret are correctly entered. Incorrect credentials will prevent the button from loading or functioning.
- **Theme Compatibility:** Some highly customized themes might require minor adjustments. If the button still doesn’t appear, try temporarily switching to the default PrestaShop theme (Classic) to rule out a theme conflict. If it appears on Classic, your theme developer might need to integrate it.
- **Clear Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance**) and your browser cache after making configuration changes.

**Q2: The button appears, but nothing happens when I click it, or I get a Facebook error.**
A:

- **Facebook App ID/Secret:** This is almost always due to an incorrect or missing Facebook App ID or App Secret. Revisit your Facebook for Developers app settings and ensure the values are copied precisely.
- **Facebook App Settings:** On the Facebook for Developers platform, ensure your app is “Live” (not in development mode) and that the “Website” platform is added with your store’s URL correctly configured.
- **Domain Whitelisting:** In your Facebook App settings, under “Settings > Basic,” ensure your website’s domain is listed in the “App Domains” field.
- **Open Graph Tags:** The module relies on PrestaShop’s default Open Graph meta tags for product information. Ensure your PrestaShop store is generating these correctly (you can check your product page source code for `<meta property="og:..."` tags).

**Q3: How do I get a Facebook App ID and App Secret?**
A:

1. Go to [Facebook for Developers](https://developers.facebook.com/) and log in with your Facebook account.
2. Click “My Apps” > “Create App”.
3. Choose the app type (e.g., “Consumer” or “Business”) and follow the prompts to name your app.
4. Once created, navigate to “Settings > Basic” in your new app’s dashboard.
5. You will find your **App ID** and **App Secret** there.
6. Make sure to add your website’s domain (e.g., `yourstore.com`) to the “App Domains” field and save changes.
7. Add a “Website” platform to your app and enter your site URL.
8. Finally, ensure your app is set to “Live” mode (there’s usually a toggle switch at the top of the dashboard).

**Q4: Will this module slow down my website?**
A: The module itself is very lightweight. The primary interaction is a small button and a Facebook-hosted pop-up, which loads content directly from Facebook’s servers. Any perceived slowdown is more likely related to Facebook’s own loading times or general website performance issues rather than the module itself.

**Q5: Can I customize the appearance of the button?**
A: The module typically uses standard Facebook button styling or integrates with your theme’s existing button styles. While there isn’t a direct setting in the module to change its appearance, a web developer can customize it using CSS by targeting the specific CSS classes or IDs of the button element.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Facebook Wishlist module (`facebook-wishlist`) is a straightforward PrestaShop module primarily designed to inject Open Graph-based “Add to Wishlist” functionality into the front-office. It leverages PrestaShop’s hook system to render its button on product pages and relies on Facebook’s JavaScript SDK and Open Graph protocol for its core functionality. The module’s configuration is managed through the standard `getContent()` method in the main module file, storing settings in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not use custom front-office or back-office controllers. All logic is encapsulated within the main module file and its configuration.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel`s. All configuration is handled via `Configuration::get()` and `Configuration::updateValue()`.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include custom JavaScript files. It relies on the Facebook JavaScript SDK, which is typically loaded asynchronously and managed by Facebook itself once the correct Open Graph meta tags and App ID are present.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include custom CSS files. The button’s appearance is either handled by Facebook’s default styling for its social plugins or inherits styles from the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not contain a `views/templates` directory. The button HTML is likely generated directly within the main module file’s hook methods.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  This module does not create any custom database tables. All configuration settings are stored in the `ps_configuration` table using keys like `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE`, and `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE`.
- **Registered Hooks Table**:
  The module registers and utilizes the following PrestaShop hooks:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayHeader` | In the `<head>` section of every page. | Used to inject the Facebook JavaScript SDK initialization code and Open Graph meta tags (if not already present by PrestaShop’s core). This is crucial for Facebook to recognize your site and app. |
  | `displayProductButtons` | On the product page, typically near the “Add to Cart” button. | Renders the “Add to Facebook Wishlist” button. This is the primary hook for the module’s front-office display. |
  | `displayProductListFunctionalButtons` | On category/listing pages, next to each product. | Renders the “Add to Facebook Wishlist” button for products in lists, if enabled in configuration. |
  | `displayFooter` | In the footer of every page. | Potentially used for additional script loading or fallback button placement, though `displayProductButtons` is the main one. |
  | `displayLeftColumn` | In the left column of pages. | Alternative position for the button, if configured. |
  | `displayRightColumn` | In the right column of pages. | Alternative position for the button, if configured. |

  The module’s core functionality relies on the `displayHeader` hook to ensure the Facebook SDK is loaded and the `displayProductButtons` (or `displayProductListFunctionalButtons`) hook to render the interactive button. The button itself, when clicked, triggers the Facebook Open Graph `og:product:wishlist` action, which requires specific Open Graph meta tags (like `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`) to be present in the product page’s HTML. PrestaShop typically generates these tags by default.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Facebook Wishlist module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
