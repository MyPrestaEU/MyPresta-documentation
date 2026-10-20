---
title: "Loyalty points - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Loyalty points PrestaShop module by MyPresta.eu."
sidebar:
  label: "Loyalty points - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Loyalty points Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/loyalty-points/)
>
> ---


# Loyalty points

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s configuration, go to **Modules > Module Manager** in your PrestaShop back office, search for “Loyalty points”, and click the “Configure” button.

This screen allows you to define the core rules of your loyalty program.

#### **Loyalty points exchange rate**

- **What this setting does:** This crucial setting defines how many loyalty points a customer earns for a specific amount of money spent in your store. It’s the foundation of your loyalty program.
- **Effect of changing this setting:**
  - *If set to “1 point for every €10 spent”:* A customer spending €50 will earn 5 points.
  - *If set to “1 point for every €5 spent”:* A customer spending €50 will earn 10 points.
  - A higher value (e.g., €10) means customers earn points slower, while a lower value (e.g., €1) means they earn points faster.
- **Recommended value:** This depends on your profit margins and desired customer incentive. A common starting point is “1 point for every €10 spent” or “1 point for every €5 spent”.
- **Merchant scenario / example:** If your average order value is €50 and you want customers to feel rewarded quickly, “1 point for every €5 spent” might be better. If your margins are tighter, “1 point for every €10 spent” might be more sustainable.

#### **Loyalty points value**

- **What this setting does:** This setting determines the monetary value of each loyalty point when a customer decides to convert them into a discount voucher.
- **Effect of changing this setting:**
  - *If set to “1 point = €0.10”:* A customer with 100 points can get a €10 voucher.
  - *If set to “1 point = €0.05”:* A customer with 100 points can get a €5 voucher.
  - A higher value makes points more attractive and valuable to the customer, but costs your store more in discounts.
- **Recommended value:** This should be balanced with the “Loyalty points exchange rate” to ensure your program is both appealing to customers and financially viable for your business. A common ratio is that 10 points (earned from spending €100 if the rate is 1 point per €10) are worth €1.
- **Merchant scenario / example:** If you give 1 point for every €10 spent, and 1 point is worth €0.10, then a customer spending €100 gets 10 points, which can be exchanged for a €1 voucher. This means they get a 1% discount back on their purchases. You might increase this to 2% or 3% to be more competitive.

#### **Minimum points to convert**

- **What this setting does:** This sets the minimum number of loyalty points a customer must accumulate before they are allowed to convert them into a discount voucher.
- **Effect of changing this setting:**
  - *If set to “50 points”:* Customers cannot redeem points until they have at least 50.
  - *If set to “10 points”:* Customers can redeem points much sooner.
  - A higher minimum encourages customers to make more purchases to reach the threshold, potentially increasing their lifetime value. A lower minimum offers quicker gratification.
- **Recommended value:** Set a value that encourages repeat purchases without being so high that customers feel it’s unattainable. 50-100 points is a good starting range, depending on your point earning rate.
- **Merchant scenario / example:** If 1 point is earned per €10, and 50 points are needed, a customer needs to spend €500 to get their first voucher. This ensures they are a committed customer before receiving a significant discount.

#### **Voucher validity (days)**

- **What this setting does:** This defines how many days a discount voucher generated from loyalty points will be valid for.
- **Effect of changing this setting:**
  - *If set to “30 days”:* The voucher expires 30 days after it’s generated.
  - *If set to “365 days”:* The voucher is valid for a full year.
  - A shorter validity period encourages customers to use their voucher sooner, driving quicker repeat purchases. A longer period offers more flexibility but might delay purchases.
- **Recommended value:** 30 to 90 days is a common range. This creates a sense of urgency without being overly restrictive.
- **Merchant scenario / example:** A 60-day validity period gives customers enough time to find something they want to buy without letting the voucher sit unused indefinitely.

#### **Enable loyalty program**

- **What this setting does:** This is a master switch to turn the entire loyalty points program on or off.
- **Effect of changing this setting:**
  - *When enabled (YES):* The loyalty program is active. Customers will earn points, see point information on product pages and in their cart, and can manage points in their account.
  - *When disabled (NO):* The loyalty program is inactive. No points will be earned, no point information will be displayed, and customers cannot redeem points. Existing points will be retained but inaccessible until re-enabled.
- **Recommended value:** YES, once you have configured all other settings.
- **Merchant scenario / example:** You might disable it temporarily for maintenance or if you’re running a different promotional campaign that conflicts with the loyalty program.

#### **Display loyalty points on product page**

- **What this setting does:** This controls whether the information about loyalty points earned for a product is shown on the individual product pages in your store.
- **Effect of changing this setting:**
  - *When enabled (YES):* Customers will see text like “Earn X points with this purchase” on each product page.
  - *When disabled (NO):* This information will not appear on product pages.
- **Recommended value:** YES. Displaying this information prominently helps customers understand the value proposition of your loyalty program and encourages purchases.
- **Merchant scenario / example:** Keeping this enabled ensures customers are always aware of the rewards they can earn, which can be a deciding factor in their purchase.

#### **Display loyalty points in shopping cart**

- **What this setting does:** This controls whether the total loyalty points to be earned for the current order are displayed in the shopping cart summary.
- **Effect of changing this setting:**
  - *When enabled (YES):* Customers will see a summary of points they will earn for their current cart contents.
  - *When disabled (NO):* This information will not appear in the shopping cart.
- **Recommended value:** YES. This serves as a final incentive before checkout, reminding customers of the future benefits of their purchase.
- **Merchant scenario / example:** Displaying points in the cart can reduce abandonment by adding another layer of value to the purchase, especially if the customer is on the fence.

#### **Loyalty points program description**

- **What this setting does:** This allows you to provide a custom description or explanation of your loyalty program. This text will typically be displayed in the customer’s “My Account” section where they manage their points.
- **Effect of changing this setting:**
  - *When filled with text:* Customers will see your custom message explaining how the program works, its benefits, or any specific rules.
  - *When left empty:* No custom description will be shown, potentially leaving customers with less information.
- **Recommended value:** Provide a clear, concise, and engaging description. Explain how points are earned, their value, and how to redeem them.
- **Merchant scenario / example:** “Earn 1 point for every €10 you spend! Collect 50 points and get a €5 voucher for your next purchase. It’s our way of saying thank you for being a loyal customer!”

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Loyalty points exchange rate | 1 point for every €10 spent | Defines how many points are earned per currency unit spent. |
| Module Configuration | Loyalty points value | 1 point = €0.10 | Defines the monetary value of each point when converted to a voucher. |
| Module Configuration | Minimum points to convert | 50 points | Sets the minimum points required before a customer can redeem them for a voucher. |
| Module Configuration | Voucher validity (days) | 60 days | How long a generated voucher is valid for. |
| Module Configuration | Enable loyalty program | YES | Master switch to turn the entire loyalty program on/off. |
| Module Configuration | Display loyalty points on product page | YES | Shows point earning info on individual product pages. |
| Module Configuration | Display loyalty points in shopping cart | YES | Shows total points to be earned in the shopping cart summary. |
| Module Configuration | Loyalty points program description | Custom text | Provides a detailed explanation of the program to customers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers aren’t seeing the loyalty points information on product pages or in the cart. What’s wrong?**
A:

1. **Check “Enable loyalty program”:** Ensure this setting is set to YES in the module configuration.
2. **Check display settings:** Verify that “Display loyalty points on product page” and “Display loyalty points in shopping cart” are both set to YES.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, changes don’t appear until the cache is refreshed.
4. **Theme Compatibility:** While the module is designed for compatibility, custom themes might sometimes override default display hooks. If clearing cache doesn’t work, contact MyPresta.eu support.

**Q: Customers are earning points, but they can’t convert them to vouchers.**
A:

1. **Check “Minimum points to convert”:** Ensure the customer has accumulated at least the number of points specified in this setting. If the minimum is 50, and they only have 45, they won’t see the conversion option.
2. **Voucher Generation Process:** Guide your customers to their “My Account” section, then to the “My Loyalty Points” (or similar) section, where they should find an option to convert their points into a voucher.

**Q: A customer generated a voucher, but it’s not working or has disappeared.**
A:

1. **Check “Voucher validity (days)”:** The voucher might have expired if the customer waited too long to use it.
2. **Voucher Code:** Ensure the customer is entering the voucher code correctly during checkout.
3. **Voucher Status:** In the PrestaShop back office, go to **Catalog > Discounts > Cart Rules**. Search for the generated voucher code. Check its validity dates, minimum amount, and if it has already been used.

**Q: Can I manually add or remove loyalty points for a customer?**
A: The current version of the module does not provide a direct interface in the back office to manually adjust customer loyalty points. Points are automatically calculated based on orders. If you need to make manual adjustments, you might need to consider a custom development or contact MyPresta.eu support for advanced options.

**Q: The loyalty program description isn’t showing up correctly in multiple languages.**
A: When you set the “Loyalty points program description,” ensure you are using the language selector at the top right of the text field to provide translations for all languages enabled in your store. If you only enter text in one language, it will only appear in that language.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Loyalty points` module (`myprestaloyalty`) follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and configuration. It integrates into the front office through various hooks to display loyalty information and provides a dedicated customer account page for point management. The module does not introduce custom database tables or `ObjectModel` classes, relying on PrestaShop’s `Configuration` for settings and potentially extending existing customer or order data through hooks.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `myprestaloyalty/controllers/front/default.php`
    - **Class name & parent class**: `MyPrestaLoyaltyDefaultModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller likely serves as a fallback or a generic entry point for front-office actions related to the module. It might handle initial requests or redirects if a more specific controller isn’t found. Given the `index.php` controller, `default.php` might be less critical or serve a specific, less common purpose.
  - `myprestaloyalty/controllers/front/index.php`
    - **Class name & parent class**: `MyPrestaLoyaltyIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This is the primary front-office controller for the module. It’s responsible for displaying the customer’s loyalty points information and handling the logic for converting points into vouchers. It likely fetches the customer’s current points, calculates potential voucher values, and processes the voucher generation request. It renders the `loyalty.tpl` template.
- **Back-Office Admin Controllers**: None identified. All configuration is handled via the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom classes or models (`ObjectModel` extensions) were identified in the provided module inventory. The module likely manages loyalty points logic directly within the main `myprestaloyalty.php` file and through PrestaShop’s `Configuration` for settings.

### 4.4 JavaScript Assets (`views/js/`)

- `myprestaloyalty/views/js/admin_manual_customer_search.js`
  - **Scope**: Back-office.
  - **Description**: This script suggests functionality for searching customers manually within the admin panel. While no admin controllers were explicitly listed, this JS file implies there might be an admin interface (perhaps integrated into an existing PrestaShop page or a custom form within `getContent()`) where an admin can search for customers, possibly to view or manage their loyalty points (though direct point modification is not confirmed by the module description). It likely uses AJAX to fetch customer data.
- `myprestaloyalty/views/js/myprestaloyalty.js`
  - **Scope**: Front-office.
  - **Description**: This is the main front-office JavaScript for the module. It likely handles dynamic interactions on the customer’s loyalty page (`loyalty.tpl`), such as:
    - Displaying current points and potential voucher values.
    - Handling the click event for the “Convert points to voucher” button.
    - Making AJAX requests to the `index.php` front controller to process the voucher generation.
    - Updating the UI to show the newly generated voucher code or success/error messages.

### 4.5 CSS Stylesheets (`views/css/`)

- `myprestaloyalty/views/css/myprestaloyalty.css`
  - **Scope**: Front-office (and potentially some back-office elements if common styles are used).
  - **Description**: This stylesheet provides the visual styling for the module’s front-office components. This includes:
    - The display of loyalty points on product pages.
    - The summary of points in the shopping cart.
    - The layout and styling of the “My Loyalty Points” section in the customer’s account, including the point balance, history, and voucher generation form.
    - Key CSS class selectors developers can override in their theme: Look for classes prefixed with `myprestaloyalty-` or similar, such as `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form`, etc.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Admin templates (`views/templates/admin/`)**:

  - `myprestaloyalty/views/templates/admin/advert.tpl`
    - **Description**: This template is likely used to display promotional content or advertisements from MyPresta.eu within the module’s configuration page in the back office. It’s a common practice for module developers to include such elements.
  - `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
    - **Description**: This template is a standard PrestaShop helper template used for rendering the module’s configuration form. It’s not unique to this module but is included to ensure the configuration page (`getContent()`) renders correctly, potentially with custom fields or specific styling.
- **Front-office templates (`views/templates/front/`)**:

  - `myprestaloyalty/views/templates/front/loyalty.tpl`
    - **Description**: This is the main template for the customer’s dedicated “My Loyalty Points” page, rendered by the `MyPrestaLoyaltyIndexModuleFrontController`. It displays the customer’s current point balance, the history of points earned and spent, and the interface for converting points into discount vouchers.
- **Hook templates (`views/templates/hook/`)**:

  - `myprestaloyalty/views/templates/hook/my-account.tpl`
    - **Hook**: `displayCustomerAccount` (or similar, e.g., `displayMyAccountBlock`).
    - **Description**: This template adds a link or a block to the customer’s “My Account” page, directing them to the module’s dedicated loyalty points page (`loyalty.tpl`).
  - `myprestaloyalty/views/templates/hook/product.tpl`
    - **Hook**: `displayProductExtraContent`, `displayProductButtons`, or `displayProductActions` (depending on PrestaShop version and theme).
    - **Description**: This template displays the information about how many loyalty points a customer will earn by purchasing the specific product on its product page.
  - `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
    - **Hook**: `displayShoppingCartFooter`, `displayCartExtraProductActions`, or `displayReassurance` (depending on PrestaShop version and theme).
    - **Description**: This template displays a summary of the total loyalty points the customer will earn for the items currently in their shopping cart.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: No custom SQL tables are created by this module. All module settings are stored in PrestaShop’s `ps_configuration` table, typically with keys prefixed by `MYPRESTALOYALTY_`.

  - Example configuration keys: `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | To include CSS and JS assets for the front-office. |
| `displayCustomerAccount` | On the customer’s “My Account” page. | To add a link to the “My Loyalty Points” section. |
| `displayProductExtraContent` (or similar) | On the product page, near product details/buttons. | To show points earned for the specific product. |
| `displayShoppingCartFooter` (or similar) | In the shopping cart summary. | To show total points earned for the current order. |
| `actionValidateOrder` | After an order has been successfully validated. | To calculate and award loyalty points to the customer based on the order total. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (optional) | In the respective column/footer areas. | Potentially used to display a quick link or summary of the loyalty program, if configured. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and dedicated technical support for the “Loyalty points” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions regarding the module’s functionality and integration.
