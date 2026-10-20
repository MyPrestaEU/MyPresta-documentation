---
title: "Hide products by country - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Hide products by country PrestaShop module by MyPresta.eu."
sidebar:
  label: "Hide products by country - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Hide products by country Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/hide-products-by-country/)
>
> ---


# Hide products by country

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

You can access the module’s configuration by navigating to **Modules > Module Manager** and searching for “Hide products by country,” then clicking “Configure.”

#### General Settings

- **Enabled / Disabled (Switch)**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The module actively filters products based on your settings.
    - *When disabled:* The module stops filtering products, and all products will be visible to all customers regardless of country.
  - **Recommended value:** **Enabled** once you’ve configured your rules.
  - **Merchant scenario / example:** You’re setting up the module for the first time and want to test it before making it live, so you keep it disabled. Once ready, you enable it.
- **What you want to do? (Dropdown)**

  - **What this setting does:** Defines the core logic of your product hiding rules.
  - **Effect of changing this setting:**
    - *Hide products for selected countries:* Products chosen in the “Select categories” and “Select Manufacturer” sections will be hidden from customers in the “Select countries” list. This is the most common use case.
    - *Show products only for selected countries:* Products chosen will ONLY be visible to customers in the “Select countries” list. For all other countries, these products will be hidden.
  - **Recommended value:** Usually **Hide products for selected countries**.
  - **Merchant scenario / example:**
    - *Hide products:* You sell a specific brand that cannot be sold in Germany. You select “Hide products for selected countries,” choose the brand, and select Germany.
    - *Show products only:* You have a special collection of products exclusively for the US market. You select “Show products only for selected countries,” choose the collection, and select the United States.
- **Select countries (Multi-select list)**

  - **What this setting does:** Allows you to choose the specific countries that your “What you want to do?” rule will apply to.
  - **Effect of changing this setting:** Only customers identified as being from these selected countries will be affected by the product visibility rules you set.
  - **Recommended value:** Select all relevant countries for your rules.
  - **Merchant scenario / example:** If you’re hiding products for customers in France and Spain, you would select “France” and “Spain” from this list.
- **Select categories (Category tree)**

  - **What this setting does:** Lets you pick specific product categories whose products will be subject to the hiding/showing rule.
  - **Effect of changing this setting:** All products within the selected categories (and their subcategories, if you choose to include them) will be affected by the “What you want to do?” rule.
  - **Recommended value:** Select the categories containing the products you wish to control.
  - **Merchant scenario / example:** You want to hide all products in your “Electronics” category for customers in Canada. You would select “Electronics” here.
- **Select Manufacturer (Multi-select list)**

  - **What this setting does:** Allows you to choose specific manufacturers whose products will be subject to the hiding/showing rule.
  - **Effect of changing this setting:** All products from the selected manufacturers will be affected by the “What you want to do?” rule.
  - **Recommended value:** Select the manufacturers whose products you wish to control.
  - **Merchant scenario / example:** You have a distribution agreement that prevents you from selling “Brand X” products in Australia. You would select “Brand X” here.
- **Exclude groups of customers (Multi-select list)**

  - **What this setting does:** Allows you to exempt certain customer groups from the module’s product hiding rules.
  - **Effect of changing this setting:** Customers belonging to the selected groups will always see all products, regardless of their country or the module’s settings. This is useful for B2B partners or VIPs.
  - **Recommended value:** Leave empty unless you have specific customer groups that need to bypass the rules.
  - **Merchant scenario / example:** You have a “Wholesalers” customer group who should always see your full catalog, even if some products are restricted for regular customers in their country. You would select “Wholesalers” here.
- **Exclude customers (Searchable input)**

  - **What this setting does:** Allows you to exempt individual customers from the module’s product hiding rules.
  - **Effect of changing this setting:** Specific customers you select will always see all products, regardless of their country or the module’s settings.
  - **Recommended value:** Leave empty unless you have specific individual customers that need to bypass the rules.
  - **Merchant scenario / example:** A specific key account manager needs to see all products for a client, even if they are browsing from a restricted country. You would search for and select that customer here.

#### Geolocation & Simulation Settings

- **Set priority of origin identification methods (Drag & Drop List)**

  - **What this setting does:** Determines the order in which the module tries to identify a customer’s country. This is crucial because different methods can sometimes give different results.
  - **Effect of changing this setting:** The module will try the methods from top to bottom. The first successful identification will be used.
    - *Delivery Address:* Uses the country from the customer’s selected delivery address (requires customer to be logged in and have an address).
    - *IP Address (Geolocation):* Uses the customer’s IP address to determine their country (most common for guests).
    - *Browser Language:* Infers country from the customer’s browser language settings (less reliable for precise country identification).
  - **Recommended value:**
    1. Delivery Address (if logged-in customer’s address is most important)
    2. IP Address (for general accuracy for all visitors)
    3. Browser Language (as a fallback, less precise)
  - **Merchant scenario / example:** You want to prioritize the customer’s actual delivery address if they are logged in, as this is the most accurate for shipping. For guests, you want to rely on IP geolocation. You would drag “Delivery Address” to the top, then “IP Address.”
- **Use delivery address (Switch)**

  - **What this setting does:** Controls whether the module considers the customer’s chosen delivery address country for product filtering.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer is logged in and has a delivery address selected, the module will use the country of that address to determine product visibility.
    - *When disabled:* The module will ignore the delivery address and rely on other methods (like IP address) even for logged-in customers.
  - **Recommended value:** **Enabled** for logged-in customers, as the delivery address is often the most accurate indicator of where the product needs to go.
  - **Merchant scenario / example:** A customer from the US is browsing from Canada. If “Use delivery address” is enabled and they have a US delivery address selected, they will see products available in the US. If disabled, they might see products available in Canada (based on their IP).
- **Activate whitelist (Switch)**

  - **What this setting does:** This setting works in conjunction with PrestaShop’s built-in geolocation feature (found under **Shop Parameters > General > Geolocation**). If PrestaShop’s geolocation is enabled, this module can use its whitelist.
  - **Effect of changing this setting:**
    - *When enabled:* If PrestaShop’s native geolocation is active and configured with a whitelist (countries allowed to browse), this module will respect that whitelist. Visitors from countries *not* on PrestaShop’s whitelist might be blocked or redirected before this module even applies its rules.
    - *When disabled:* This module will ignore PrestaShop’s geolocation whitelist and apply its rules based on its own country identification.
  - **Recommended value:** **Disabled** unless you are actively using and managing PrestaShop’s native geolocation whitelist.
  - **Merchant scenario / example:** You’ve set up PrestaShop’s geolocation to only allow visitors from EU countries. If you enable “Activate whitelist” here, visitors from outside the EU will be handled by PrestaShop’s core system, and this module will then apply its product-specific rules to the allowed EU visitors.
- **Simulate visit (Switch)**

  - **What this setting does:** This is a powerful testing tool that allows you to pretend you are browsing from a different country without actually changing your location or using a VPN.
  - **Effect of changing this setting:**
    - *When enabled:* The “Simulate IP” field becomes active, allowing you to enter an IP address. The module will then treat your current browsing session as if you are visiting from the country associated with that IP.
    - *When disabled:* The module identifies your country normally.
  - **Recommended value:** **Disabled** for live stores. Only enable temporarily for testing.
  - **Merchant scenario / example:** You want to verify that products are correctly hidden for customers in Germany. You enable “Simulate visit,” enter a German IP address (e.g., 85.214.132.112), and then browse your store to see if the correct products are hidden.
- **Simulate IP (Text input)**

  - **What this setting does:** When “Simulate visit” is enabled, you enter an IP address here to simulate a visitor from that IP’s country.
  - **Effect of changing this setting:** Your current browsing session will behave as if you are located in the country associated with the entered IP address, allowing you to test product visibility rules.
  - **Recommended value:** Leave empty unless “Simulate visit” is enabled for testing.
  - **Merchant scenario / example:** After enabling “Simulate visit,” you enter “192.168.1.1” (a common local IP, but you’d use a real public IP for a country) to test. For a German IP, you might use “85.214.132.112”.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Enabled** | Enabled | Master switch for module functionality. |
| Module Configuration | **What you want to do?** | Hide products for selected countries | Defines if products are hidden for selected countries or only shown to them. |
| Module Configuration | **Select countries** | (Empty) / Select relevant | Countries affected by the product visibility rule. |
| Module Configuration | **Select categories** | (Empty) / Select relevant | Categories whose products are affected. |
| Module Configuration | **Select Manufacturer** | (Empty) / Select relevant | Manufacturers whose products are affected. |
| Module Configuration | **Exclude groups of customers** | (Empty) | Customer groups exempt from hiding rules. |
| Module Configuration | **Exclude customers** | (Empty) | Individual customers exempt from hiding rules. |
| Module Configuration | **Set priority of origin identification methods** | Delivery Address, IP Address, Browser Language | Order of methods to identify customer’s country. |
| Module Configuration | **Use delivery address** | Enabled | Use customer’s delivery address country for filtering. |
| Module Configuration | **Activate whitelist** | Disabled | Respect PrestaShop’s native geolocation whitelist. |
| Module Configuration | **Simulate visit** | Disabled | Enable to test product visibility from a specific IP. |
| Module Configuration | **Simulate IP** | (Empty) | IP address to simulate when “Simulate visit” is enabled. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but the products are still visible/hidden incorrectly. What should I check first?**
A:

1. **Module Enabled:** Double-check that the main “Enabled” switch on the module configuration page is turned ON.
2. **Cache:** Clear your PrestaShop cache (Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right). Browser cache can also sometimes interfere, so try a hard refresh (Ctrl+F5 or Cmd+Shift+R) or an incognito/private browsing window.
3. **Simulation:** If you’re testing, ensure “Simulate visit” is enabled and “Simulate IP” is set correctly. If you’re not simulating, ensure “Simulate visit” is disabled.
4. **Rule Logic:** Review your “What you want to do?” setting (“Hide products for selected countries” vs. “Show products only for selected countries”) and ensure it matches your intent.
5. **Country/Category/Manufacturer Selection:** Make sure you’ve correctly selected the countries, categories, and manufacturers that should be affected.

**Q: How does the module identify a customer’s country?**
A: The module uses a priority system you configure:

1. **Delivery Address:** If the customer is logged in and has a delivery address, this is the most accurate.
2. **IP Address (Geolocation):** For guests or if no delivery address is used, it uses the visitor’s IP address to determine their country.
3. **Browser Language:** As a fallback, it can infer the country from the browser’s language settings, though this is less precise. You can adjust the priority in the module settings.

**Q: Will this module affect my SEO? Will Google still index my hidden products?**
A: The module hides products from the front-office display for specific countries. Generally, search engine crawlers (like Googlebot) often crawl from specific IP addresses (e.g., US-based IPs). If your products are hidden for the US, Google might not see them. If they are hidden for other countries but visible for the US, Google might still index them. For critical SEO concerns, consider using PrestaShop’s native “Disable product” feature or specific robots.txt rules if you absolutely do not want a product indexed anywhere. This module is primarily for front-end user experience and compliance, not SEO control.

**Q: Can I hide products for specific customers or customer groups, regardless of their country?**
A: Yes! The module includes “Exclude groups of customers” and “Exclude customers” settings. These allow you to specify groups or individual customers who will *always* see all products, effectively bypassing the country-based hiding rules. This is useful for VIPs, B2B partners, or internal staff.

**Q: What happens if a customer from a restricted country tries to access a hidden product via a direct link?**
A: The module is designed to prevent access. Typically, they will be redirected to the homepage or a “page not found” error, ensuring they cannot view or add the restricted product to their cart.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Hide products by country” module (`hbc`) primarily operates by overriding core PrestaShop classes and utilizing hooks to intercept and modify product queries before they are displayed to the customer. It leverages PrestaShop’s `ObjectModel` for configuration storage and relies on IP geolocation or customer address data to determine the visitor’s country. The module’s logic is injected into the product filtering process, ensuring that restricted products are removed from listings, search results, and direct access attempts.

### 4.2 Controllers (`controllers/`)

This module does not contain any dedicated Front-Office or Back-Office Admin Controllers. Its configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module implements overrides to modify core PrestaShop behavior.

- **`hbc/override/classes/index.php`**: Standard empty `index.php` file to prevent directory listing.
- **`hbc/override/classes/shop/index.php`**: Standard empty `index.php` file to prevent directory listing.
- **`hbc/override/classes/shop/Shop.php`**:
  - **Class Name**: `Shop` (overrides PrestaShop’s core `Shop` class)
  - **Parent Class**: `ShopCore`
  - **Responsibility**: This override is critical. It likely modifies how product context or shop context is determined, potentially injecting country-specific filtering logic at a very fundamental level of PrestaShop’s multi-shop and product retrieval system. This ensures that product visibility rules are applied consistently across various parts of the store. Developers should be aware that overriding `Shop.php` can have wide-ranging effects and may conflict with other modules that also override this core class.

### 4.4 JavaScript Assets (`views/js/`)

- **`hbc/lib/searchTool/views/js/autocomplete.js`**:
  - **Scope**: Back-office (likely used in the module’s configuration form).
  - **Purpose**: This script provides autocomplete functionality, specifically for the “Exclude customers” input field in the module’s configuration. It likely makes AJAX calls to a PrestaShop admin endpoint to search for customers as the administrator types, improving usability for selecting individual customers.
  - **Key Functionality**:
    - Initializes an autocomplete widget on a specific input field (e.g., `#hbc_exclude_customer`).
    - Sends AJAX requests (e.g., to `admin-ajax.php` or a dedicated admin controller) with the typed query.
    - Parses JSON responses containing customer data (ID, name, email).
    - Displays suggestions in a dropdown list.
    - Handles selection of a customer, populating a hidden input with the customer ID and displaying the name.
    - Manages the removal of selected customers from the list.

### 4.5 CSS Stylesheets (`views/css/`)

- **`hbc/lib/searchTool/views/css/autocomplete.css`**:
  - **Scope**: Back-office (styles the autocomplete widget).
  - **Purpose**: Provides styling for the customer autocomplete search tool used in the module’s configuration. This includes styling for the input field, the dropdown list of suggestions, and potentially the display of selected customers.
  - **Key Selectors**: Likely targets classes and IDs associated with the autocomplete widget, such as `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`, and elements for displaying selected tags/tokens.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`hbc/lib/searchTool/views/scripts.tpl`**:

  - **Scope**: Back-office.
  - **Purpose**: This template likely includes the necessary JavaScript and CSS files for the autocomplete search tool (`autocomplete.js` and `autocomplete.css`) and potentially initializes the JavaScript logic. It’s probably included in the main configuration template.
- **`hbc/views/templates/admin/AdminTab.tpl`**:

  - **Scope**: Back-office.
  - **Purpose**: This template is likely a generic wrapper or a component used within the module’s configuration page. It might define the structure for a tabbed interface or a specific section within the module’s settings.
- **`hbc/views/templates/admin/button-subcategories.tpl`**:

  - **Scope**: Back-office.
  - **Purpose**: This template probably renders a button or a UI element related to category selection, specifically for including/excluding subcategories when selecting parent categories in the configuration form.
- **`hbc/views/templates/admin/configuration.tpl`**:

  - **Scope**: Back-office.
  - **Purpose**: This is the main Smarty template for the module’s configuration page. It renders all the settings, input fields, switches, and lists described in Section 4.1. It uses PrestaShop’s helper form components and likely includes `scripts.tpl` for the autocomplete functionality.
- **`hbc/views/templates/hook/displayHeader.tpl`**:

  - **Scope**: Front-office.
  - **Hook**: `displayHeader`
  - **Purpose**: This template is rendered in the `<head>` section of every front-office page. It might be used to:
    - Inject inline JavaScript for client-side country detection (less likely given server-side filtering).
    - Set JavaScript variables based on module configuration (e.g., simulation mode).
    - Include additional CSS or JS files that are needed globally for the module’s front-office functionality (though the core filtering is server-side).
    - Potentially handle redirects or initial checks based on geolocation before the page fully loads.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module primarily uses PrestaShop’s `ps_configuration` table to store its settings.
  - Configuration keys include: `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
  - No custom SQL tables are created by this module.
- **Registered Hooks Table**:

| Hook Name | Scope | Execution Timing | Technical Purpose |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | In the `<head>` section of every page. | Potentially for injecting client-side scripts, meta tags, or initial checks. |
| `actionAdminControllerSetMedia` | Back-office | When an admin controller sets its media assets. | Used to load CSS/JS for the module’s configuration page (e.g., `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-office | After the dispatcher has processed the request. | Could be used to perform redirects or final checks after a page has been identified but before rendering. |
| `displayFilterProductSearch` | Front-office | During product search filtering. | **CRITICAL**: This hook is used to inject the module’s logic into the product search query, ensuring hidden products are excluded from search results. |
| `actionProductUpdate` | Back-office | After a product is updated in the Back Office. | Could be used to clear cache related to product visibility or re-evaluate rules for the updated product. |
| `displayAdminProductsExtra` | Back-office | On the product edit page in the Back Office. | Could be used to display additional information or settings related to product hiding for the specific product being edited (though not explicitly identified in the settings). |
| `actionCartSave` | Front-office | When the cart is saved (e.g., product added/removed). | Could be used to prevent adding hidden products to the cart or to remove them if the customer’s country changes. |
| `FilterProductSearch` | Front-office | During product search filtering (similar to `displayFilterProductSearch`). | **CRITICAL**: Another hook for modifying product search queries, ensuring comprehensive filtering across different search contexts. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Hide products by country” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
