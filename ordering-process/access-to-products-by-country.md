---
title: "Access to products by country - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Access to products by country PrestaShop module by MyPresta.eu."
sidebar:
  label: "Access to products by country - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Access to products by country Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/access-to-products-by-country/)
>
> ---


# Access to products by country

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Access to products by country” module. You’ll find all the settings here to define how product access is restricted.

#### General Settings

- **Enabled / Disabled (Module Status)**

  - **What this setting does:** This is the master switch for the module.
  - **Effect of changing this setting:**
    - *When Enabled:* The module will actively filter products based on country restrictions.
    - *When Disabled:* The module will be inactive, and all products will be visible to all customers, regardless of their country.
  - **Recommended value:** **Enabled** once you’ve configured your rules.
  - **Merchant scenario / example:** You’re setting up the module for the first time; keep it disabled until you’ve defined all your rules, then enable it to go live.
- **What you want to do? (Restriction Type)**

  - **What this setting does:** Defines the core logic of your country restrictions: do you want to *block* products in selected countries, or *allow* products *only* in selected countries?
  - **Effect of changing this setting:**
    - *When set to “Block access to products in selected countries”:* Products you configure will be hidden from customers in the countries you specify. They will be visible everywhere else.
    - *When set to “Allow access to products ONLY in selected countries”:* Products you configure will *only* be visible to customers in the countries you specify. They will be hidden everywhere else.
  - **Recommended value:** Choose based on your primary use case. If you have a few countries where a product is restricted, choose “Block”. If a product is exclusive to a few countries, choose “Allow ONLY”.
  - **Merchant scenario / example:**
    - *Block:* You sell a specific brand that cannot be shipped to Canada. You would select “Block access” and then choose Canada for that product.
    - *Allow ONLY:* You have a special edition product only available for sale in the USA and Mexico. You would select “Allow access ONLY” and then choose USA and Mexico for that product.
- **Select countries**

  - **What this setting does:** This is where you select the specific countries that will be affected by the “What you want to do?” rule.
  - **Effect of changing this setting:** The selected countries will be either blocked from seeing the product or will be the only ones allowed to see it, depending on the “What you want to do?” setting.
  - **Recommended value:** Select all relevant countries based on your product restrictions.
  - **Merchant scenario / example:** If you’re blocking sales to Canada and Australia, you would select both Canada and Australia from the list.
- **Select categories**

  - **What this setting does:** Allows you to apply the country restriction rules to entire product categories instead of individual products.
  - **Effect of changing this setting:** All products within the selected categories will inherit the country restriction rules defined above.
  - **Recommended value:** Use this for broad restrictions. Leave empty if you want to manage restrictions product-by-product.
  - **Merchant scenario / example:** All products in your “Electronics” category cannot be sold in Brazil. You would select the “Electronics” category here.
- **Select Manufacturer**

  - **What this setting does:** Allows you to apply the country restriction rules to all products from specific manufacturers.
  - **Effect of changing this setting:** All products from the selected manufacturers will inherit the country restriction rules.
  - **Recommended value:** Use this for brand-level restrictions. Leave empty if you want to manage restrictions product-by-product or category-by-category.
  - **Merchant scenario / example:** You have a distribution agreement that prevents you from selling “Brand X” products in Europe. You would select “Brand X” here.

#### Customer & Group Exclusions

- **Exclude groups of customers**

  - **What this setting does:** Allows you to exempt certain customer groups from the country restrictions. For example, you might have a special B2B group that is allowed to purchase restricted products.
  - **Effect of changing this setting:** Customers belonging to the selected groups will *not* be subject to the country restrictions defined by this module. They will see all products.
  - **Recommended value:** Select groups that need special access, such as “Wholesale Customers” or “Employees”. Leave empty if all customers should be subject to restrictions.
  - **Merchant scenario / example:** You have a “VIP Customers” group who are allowed to purchase products that are otherwise restricted in their country. You would select the “VIP Customers” group here.
- **Exclude customers**

  - **What this setting does:** Allows you to exempt specific individual customers from the country restrictions.
  - **Effect of changing this setting:** The selected individual customers will *not* be subject to the country restrictions. They will see all products.
  - **Recommended value:** Use this for specific exceptions. Leave empty if not needed.
  - **Merchant scenario / example:** A specific customer is a long-term partner and needs access to all products regardless of their location. You would select their customer account here.

#### Geolocation & Simulation Settings

- **Set priority of origin identification methods**

  - **What this setting does:** Determines the order in which the module tries to identify the customer’s country. This is crucial for accuracy.
  - **Effect of changing this setting:** The module will first try the method at the top of the list. If that fails or isn’t available, it moves to the next.
  - **Recommended value:**
    1. **Delivery Address (if available):** This is the most accurate for actual purchase intent.
    2. **Geolocation:** Good for initial browsing.
    3. **Customer Account Country:** If logged in.
  - **Merchant scenario / example:** A customer is browsing from the USA (geolocation), but intends to ship to Canada. If “Delivery Address” is prioritized, the module will use Canada for restrictions once they enter it in the cart.
- **Use delivery address**

  - **What this setting does:** When enabled, the module will consider the customer’s selected delivery address country in the shopping cart as their “origin” for applying restrictions.
  - **Effect of changing this setting:**
    - *When Enabled:* If a customer adds a restricted product to their cart and then selects a delivery address in a blocked country, the module will prevent checkout or remove the product.
    - *When Disabled:* The module will rely solely on IP geolocation or the customer’s registered country, which might not match their intended shipping destination.
  - **Recommended value:** **YES**. This provides the most accurate and practical restriction enforcement during the checkout process.
  - **Merchant scenario / example:** A customer from Germany (where a product is allowed) adds it to their cart, but then selects a shipping address in Austria (where the product is blocked). With this setting enabled, the module will prevent the order.
- **Simulate visit**

  - **What this setting does:** Allows you to test your country restrictions by simulating a visit from a specific country without actually changing your IP address.
  - **Effect of changing this setting:**
    - *When Enabled:* The module will treat your current session as if you are browsing from the country specified in “Simulate IP”.
    - *When Disabled:* The module uses your actual IP address for geolocation.
  - **Recommended value:** **Disabled** for live stores. **Enabled** only for testing.
  - **Merchant scenario / example:** You want to check if a product is correctly hidden for customers in France. You enable “Simulate visit”, enter a French IP address (or select France if available), and then browse your store.
- **Simulate IP**

  - **What this setting does:** When “Simulate visit” is enabled, this field allows you to enter an IP address from the country you want to simulate, or select a country from a dropdown list.
  - **Effect of changing this setting:** The module will use this IP/country for all restriction checks during your simulated session.
  - **Recommended value:** Enter a valid IP address or select a country for testing purposes.
  - **Merchant scenario / example:** To simulate a visit from Germany, you might enter `88.130.179.0` (a German IP) or simply select “Germany” from the list.

#### Whitelist Settings

- **Activate whitelist**

  - **What this setting does:** This setting leverages PrestaShop’s built-in geolocation whitelist feature. If PrestaShop’s geolocation is active, this whitelist allows you to define specific IP addresses or IP ranges that should *always* be allowed to access your store, regardless of their detected country. This is useful for your own office IPs or trusted partners.
  - **Effect of changing this setting:**
    - *When Enabled:* The module will respect PrestaShop’s geolocation whitelist. IPs on this list will bypass any country restrictions.
    - *When Disabled:* The whitelist will not be considered.
  - **Recommended value:** **YES** if you use PrestaShop’s geolocation and have IPs you want to whitelist.
  - **Merchant scenario / example:** Your office is in a country where certain products are restricted, but you need to access them for administrative purposes. You would add your office’s IP address to PrestaShop’s geolocation whitelist and enable this setting.
- **Whitelist**

  - **What this setting does:** This is where you manage the specific IP addresses or IP ranges that are whitelisted. This directly corresponds to PrestaShop’s `PS_GEOLOCATION_WHITELIST` setting.
  - **Effect of changing this setting:** Any IP address or range entered here will bypass all geolocation-based restrictions.
  - **Recommended value:** Add your own office IP addresses, development server IPs, or any other trusted IPs that should always have full access.
  - **Merchant scenario / example:** You add `192.168.1.1/24` (your office network) to ensure all employees can access all products.

#### Update Settings (Internal)

- **mypresta\_updates, update\_, updatev\_**
  - **What these settings do:** These are internal settings used by MyPresta.eu modules to manage updates and version checks. They are not meant for direct merchant interaction.
  - **Effect of changing this setting:** Modifying these could interfere with module update notifications.
  - **Recommended value:** Leave these settings as they are.
  - **Merchant scenario / example:** No merchant scenario; these are for internal module management.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Enabled / Disabled** | Enabled | Master switch for module functionality. |
| Module Configuration | **What you want to do?** | Block access | Defines if rules block access or allow access ONLY. |
| Module Configuration | **Select countries** | (None) | Countries affected by the restriction rule. |
| Module Configuration | **Select categories** | (None) | Categories whose products are affected by the rule. |
| Module Configuration | **Select Manufacturer** | (None) | Manufacturers whose products are affected by the rule. |
| Module Configuration | **Exclude groups of customers** | (None) | Customer groups exempt from restrictions. |
| Module Configuration | **Exclude customers** | (None) | Individual customers exempt from restrictions. |
| Module Configuration | **Set priority of origin identification methods** | Delivery Address, Geolocation, Customer Account Country | Order of methods to determine customer’s country. |
| Module Configuration | **Use delivery address** | YES | Considers delivery address for restriction enforcement. |
| Module Configuration | **Simulate visit** | Disabled | Enables/disables IP simulation for testing. |
| Module Configuration | **Simulate IP** | (Empty) | IP address/country to simulate for testing. |
| Module Configuration | **Activate whitelist** | YES | Enables/disables PrestaShop’s geolocation whitelist. |
| Module Configuration | **Whitelist** | (Empty) | List of IP addresses/ranges to bypass restrictions. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: Products are still visible in a blocked country, what should I do?**
A1: First, check your module configuration:
\* Is the module “Enabled”?
\* Is “What you want to do?” set correctly (e.g., “Block access” if you want to hide them)?
\* Are the correct “Select countries” chosen?
\* Are the “Select categories” or “Select Manufacturer” correctly applied to the products in question?
\* If you’re testing, ensure “Simulate visit” is enabled and “Simulate IP” is set to the correct country.
\* Finally, clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**) and your browser cache.

**Q2: My own IP address seems to be blocked, even though I’m in an allowed country.**
A2: This can happen if your IP is somehow misidentified or if you’ve made a mistake in your configuration.
\* Check the “Whitelist” setting and ensure your office or personal IP address is added there if you want to bypass all restrictions.
\* Verify your actual public IP address (you can use websites like “what is my IP”).
\* Ensure “Activate whitelist” is enabled if you’re using PrestaShop’s built-in geolocation whitelist.

**Q3: How does the module determine a customer’s country?**
A3: The module uses a priority system:
1. **Delivery Address:** If “Use delivery address” is enabled and the customer has entered a shipping address in the cart, this is prioritized.
2. **Geolocation:** It uses the customer’s IP address to determine their geographical location.
3. **Customer Account Country:** If the customer is logged in, it uses the country registered in their account.
You can adjust the priority of these methods in the module’s configuration.

**Q4: I have a custom theme, will this module work?**
A4: Yes, the module is designed to work with standard PrestaShop themes. It primarily filters products at the data level before they are rendered by the theme. However, if your custom theme has highly unusual product listing logic or overrides core PrestaShop product display hooks, minor adjustments might be needed. If you encounter issues, contact MyPresta.eu support.

**Q5: Can I restrict access to specific products, not just categories or manufacturers?**
A5: Yes, the module works by filtering products. While the main configuration screen allows you to select categories and manufacturers, the module’s core logic applies to individual products. You can leave “Select categories” and “Select Manufacturer” empty and manage restrictions directly on individual product pages (if the module adds a tab there, which is common for such modules). *Based on the provided info, the module works by configuring rules that apply to products based on categories/manufacturers selected in the main config. It doesn’t explicitly state a product-level configuration tab, but the description implies “each product individually”. If there’s no product tab, the category/manufacturer selection is the primary way to target products.*

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Access to products by country” module (`atpbc`) is built as a standard PrestaShop module, leveraging the MVC pattern where appropriate. Its primary function is to intercept product queries and filter results based on configured country restrictions and the identified customer’s location. It integrates with PrestaShop’s core by hooking into various display and action points, particularly those related to product fetching and display. Geolocation is a key component, determining the customer’s origin, which is then cross-referenced with the module’s rules.

### 4.2 Controllers (`controllers/`)

The module does not appear to have custom front-office or back-office controllers in its `controllers/` directory based on the provided inventory. All configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to have custom classes or `ObjectModel` definitions in a `classes/` directory. The core logic and data handling are likely encapsulated within the main `atpbc.php` file, using `Configuration` for settings and direct database queries or PrestaShop’s `Product` and `Category` classes for data manipulation.

### 4.4 JavaScript Assets (`views/js/`)

- **`atpbc/lib/searchTool/views/js/autocomplete.js`**
  - **Scope:** Back-office.
  - **Purpose:** This script likely provides autocomplete functionality for input fields within the module’s configuration, such as selecting customers, categories, or manufacturers. It enhances the user experience by suggesting options as the admin types, reducing errors and speeding up configuration.
  - **Functionality:** Binds event listeners to specific input fields (e.g., `keyup`, `focus`), sends AJAX requests to a back-office endpoint (likely handled by the main module file or a core PrestaShop admin controller) to fetch suggestions, and displays these suggestions in a dropdown list. It handles selection and populating the input field.

### 4.5 CSS Stylesheets (`views/css/`)

- **`atpbc/lib/searchTool/views/css/autocomplete.css`**
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Provides styling for the autocomplete suggestions dropdown and potentially the input fields themselves, ensuring a consistent and user-friendly appearance within the PrestaShop back office.
  - **Key Selectors:** Likely targets classes like `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input` to control layout, colors, fonts, and hover states. Developers can override these in their custom admin theme or by adding higher-specificity CSS.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`atpbc/lib/searchTool/views/scripts.tpl`**

  - **Scope:** Back-office.
  - **Purpose:** This template is likely used to include the `autocomplete.js` script and potentially other JavaScript-related configurations or inline scripts for the `searchTool` functionality. It might also define variables passed to the JavaScript.
  - **Rendered in:** Probably hooked into `actionAdminControllerSetMedia` or directly included in the main configuration template.
- **`atpbc/views/templates/admin/AdminTab.tpl`**

  - **Scope:** Back-office.
  - **Purpose:** This template is likely a generic template for a custom admin tab or a section within the module’s configuration. It might contain the structure for displaying lists, forms, or other administrative content.
  - **Rendered in:** Could be included by `configuration.tpl` or used if the module had a dedicated admin controller.
- **`atpbc/views/templates/admin/button-subcategories.tpl`**

  - **Scope:** Back-office.
  - **Purpose:** This template likely renders a button or UI element specifically for managing subcategories within the module’s configuration, possibly for the “Select categories” setting to expand/collapse category trees.
  - **Rendered in:** Within the `configuration.tpl` when displaying category selection options.
- **`atpbc/views/templates/admin/configuration.tpl`**

  - **Scope:** Back-office.
  - **Purpose:** This is the main Smarty template for the module’s configuration page, rendered by the `getContent()` method in `atpbc.php`. It contains all the HTML forms, input fields, switches, and selection lists for the module’s settings.
  - **Rendered in:** When accessing the module’s configuration page in the PrestaShop Back Office.
- **`atpbc/views/templates/hook/displayHeader.tpl`**

  - **Scope:** Front-office.
  - **Purpose:** This template is hooked into `displayHeader`. It’s typically used to include front-office CSS, JavaScript, or meta tags that need to be loaded early in the page. For this module, it might include logic to detect the customer’s country or set up client-side variables for later use.
  - **Rendered in:** The `<head>` section of every front-office page.
- **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**

  - **Scope:** Front-office.
  - **Purpose:** This template is likely a fallback or specific display for when a customer is detected to have “no access” to a particular product or page. It might contain a redirect script, a message, or specific styling to hide content.
  - **Rendered in:** Potentially within `displayHeader` or another hook, conditional on access restrictions.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily uses PrestaShop’s `ps_configuration` table to store its settings (e.g., `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
  - It does not appear to create custom SQL tables based on the provided inventory.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Before an admin controller’s content is rendered, after media is set. | To include back-office JS/CSS (e.g., `autocomplete.js`, `autocomplete.css`) for the module’s configuration page. |
| `actionDispatcherAfter` | After the dispatcher has processed a request. | Potentially used to perform redirects or modify the response based on access rules after a page has been identified. |
| `displayFilterProductSearch` | During product search filtering. | To modify the product search results, removing restricted products based on country. |
| `actionProductUpdate` | After a product is updated in the Back Office. | To potentially clear cache related to product availability or re-evaluate rules for the updated product. |
| `displayAdminProductsExtra` | On the product edit page in the Back Office. | To add extra fields or a tab for product-specific access rules (though not explicitly stated, this is a common use for this hook). |
| `actionCartSave` | After a cart is saved or updated. | To check if products in the cart are allowed for the customer’s identified country (especially if “Use delivery address” is enabled). |
| `FilterProductSearch` | During product search filtering (similar to `displayFilterProductSearch`, often for manipulating query directly). | To modify the database query for product searches, ensuring restricted products are not retrieved. |
| `displayHeader` | In the `<head>` section of every front-office page. | To include front-office JavaScript/CSS (e.g., `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) or perform early country detection. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions optimally and provides the best possible experience for your store.
