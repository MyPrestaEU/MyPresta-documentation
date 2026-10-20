---
title: "Maximum purchase value by manufacturer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Maximum purchase value by manufacturer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Maximum purchase value by manufacturer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Maximum purchase value by manufacturer Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Maximum purchase value by manufacturer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you can enable or disable the module and access the dedicated management area for setting up manufacturer limits.

- **What this setting does:** This section typically contains a simple switch to enable or disable the module’s core functionality. It also provides a direct link to the dedicated screen where you define the actual maximum purchase values for manufacturers.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively check customer carts against the defined manufacturer limits and prevent orders if limits are exceeded.
  - *When disabled:* The module will cease to function, and no manufacturer purchase limits will be enforced.
- **Recommended value:** “YES” (Enabled) if you intend to use the module’s features.
- **Merchant scenario / example:** You’ve just installed the module and want to start setting up limits. You’d enable it here, then proceed to the “Manage Manufacturer Limits” section.

### 2.2 Dedicated Admin Screen: Manufacturer Limits (Back Office > Modules > Maximum purchase value by manufacturer > Configure > “Manage Manufacturer Limits” button or a dedicated menu entry)

This screen is where you define and manage the actual maximum purchase values for each manufacturer. It will typically present a list of your manufacturers and allow you to add, edit, or delete rules.

**Screen Name & Menu Location:**
You will access this screen by clicking the “Configure” button next to the module in the Module Manager, and then likely clicking a prominent button like “Manage Manufacturer Limits” or “Add New Rule”. Alternatively, the module might create a new menu item under “Catalog” or “Shop Parameters” for direct access to `AdminMaobm`.

**Available Actions & Settings:**

1. **Listing Table of Existing Rules:**

   - You will see a table listing all the manufacturer limits you have already set up.
   - Columns typically include: Manufacturer Name, Maximum Value, and actions like “Edit” or “Delete”.
   - **Effect of changes:** This table provides an overview of your active rules. Deleting a rule will remove the purchase limit for that specific manufacturer.
   - **Recommended workflow:** Regularly review this table to ensure your limits are up-to-date with your business needs.
2. **Add New / Edit Rule Form:**

   - When you click “Add New” or “Edit” an existing rule, you’ll typically see a form with the following fields:
     - **Manufacturer:** A dropdown list or search box to select the manufacturer you want to apply the limit to.
       - **What this setting does:** Specifies which manufacturer this rule applies to.
       - **Effect of changing this setting:** The rule will only apply to products associated with the selected manufacturer.
       - **Recommended value:** Select the specific manufacturer you wish to limit.
       - **Merchant scenario / example:** You want to set a limit for “Acme Corp.” products, so you select “Acme Corp.” from the list.
     - **Maximum Purchase Value:** An input field where you enter the maximum total value (in your store’s default currency) that a customer can purchase from the selected manufacturer in a single order.
       - **What this setting does:** Defines the monetary ceiling for products from the chosen manufacturer.
       - **Effect of changing this setting:** If the total value of products from this manufacturer in a customer’s cart exceeds this number, they will be blocked from ordering.
       - **Recommended value:** A numerical value representing the maximum allowed total, e.g., “500.00” for 500 units of your default currency.
       - **Merchant scenario / example:** You want to limit “Acme Corp.” products to a maximum of $500 per order. You would enter “500” here.
     - **Save Button:** To apply your changes.
       - **Effect of changes:** Saves the new rule or updates an existing one in the database, making it active immediately.

**Recommended workflow for daily store management:**

- **Initial Setup:** Go through your list of manufacturers and identify any for which you need to set purchase limits. Add a new rule for each.
- **Monitoring:** Keep an eye on your sales and inventory. If you notice a manufacturer’s products being bought in excessive quantities, or if supplier agreements change, come back to this screen to adjust or add new limits.
- **Updates:** When new manufacturers are added to your store, consider if they require a purchase limit rule.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Module Status (Enable/Disable) | Enabled | Activates or deactivates the module’s functionality. |
| AdminMaobmController (Manufacturer Limits) | Manufacturer | Select from list | Specifies the manufacturer to which the limit applies. |
| AdminMaobmController (Manufacturer Limits) | Maximum Purchase Value | Your desired monetary limit (e.g., 500.00) | Sets the maximum total value for products from the selected manufacturer in a single order. Exceeding this blocks checkout. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: A customer is trying to check out, but they see a message about exceeding a manufacturer limit. What should I do?**
A: This means the module is working as intended. The customer has too many items from a specific manufacturer in their cart, and the total value of those items exceeds the limit you set. You can either:
1. Advise the customer to reduce the quantity of items from that manufacturer.
2. Temporarily disable or adjust the limit for that manufacturer in the module’s configuration if you deem the order acceptable (but be cautious with this).

**Q: I’ve set a limit, but it doesn’t seem to be working. Customers can still order more than the maximum.**
A:
1. **Check Module Status:** Ensure the module is enabled in **Modules > Module Manager** and on its main configuration page.
2. **Verify Rule:** Double-check the rule you created under the “Manage Manufacturer Limits” screen. Is the correct manufacturer selected? Is the “Maximum Purchase Value” set correctly?
3. **Clear Cache:** Sometimes PrestaShop’s cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache”.
4. **Product Manufacturer:** Ensure the products in question are correctly assigned to the manufacturer for which you set the limit. Check the product’s settings in your catalog.

**Q: Can I set different limits for different customer groups?**
A: This module, in its standard form, applies a single limit per manufacturer across all customers. If you require customer group-specific limits, this would require custom development.

**Q: The warning message is not clear or doesn’t match my store’s language/theme.**
A:
1. **Translations:** Go to **International > Translations**, select “Installed modules translations”, your theme, and the module “Maximum purchase value by manufacturer”. You can customize the warning message text there.
2. **Theme Styling:** The module uses standard PrestaShop styling for its messages. If it looks out of place, your theme might have custom CSS that needs adjustment. A webmaster can inspect the `maobm.css` file and your theme’s CSS to make it visually consistent.

**Q: What happens if a product has no manufacturer assigned?**
A: Products without an assigned manufacturer will not be subject to any limits set by this module, as the rules are manufacturer-specific.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Maximum purchase value by manufacturer” module (`maobm`) follows a standard PrestaShop module architecture. It primarily uses a `Module` class for installation and basic configuration, an `AdminController` for managing the manufacturer limits, and `FrontController`s to handle AJAX requests and integrate with the front-office cart process. The module leverages PrestaShop’s hook system to inject its logic into the cart and checkout flow, preventing orders if limits are exceeded. It stores its configuration in `ps_configuration` and manages specific manufacturer limits through a dedicated database table (though no `ObjectModel` is explicitly listed, it implies direct DB interaction or a simple `AdminController` managing configuration).

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/ajax.php`
    - **Class Name**: `MaobmAjaxModuleFrontController` (implied, extends `ModuleFrontController`)
    - **Responsibility**: This controller likely handles AJAX requests from the front-office, such as when a customer updates their cart. It would re-evaluate the manufacturer limits and return a response (e.g., a warning message or a status indicating if the order can proceed). It might be hooked into `actionCartSave` or similar events to provide real-time feedback.
  - `controllers/front/index.php`
    - **Class Name**: `MaobmIndexModuleFrontController` (implied, extends `ModuleFrontController`)
    - **Responsibility**: This controller might serve as a fallback or a simple entry point, though its primary function could be minimal if `ajax.php` handles most front-end interactions. It could potentially display a generic message or redirect if accessed directly.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMaobm.php`
    - **Class Name**: `AdminMaobmController` (extends `ModuleAdminController`)
    - **Tab Name**: Likely a custom tab created by the module, or accessible via the module’s configuration page.
    - **Managed Entity**: Manages the specific manufacturer limit rules. It provides the interface for listing, adding, editing, and deleting these rules. This controller would interact directly with the database to store and retrieve the manufacturer IDs and their associated maximum values. It would typically use `HelperList` for the overview table and `HelperForm` for the add/edit form.
  - `controllers/admin/index.php`
    - **Class Name**: `AdminMaobmIndexController` (implied, extends `ModuleAdminController`)
    - **Responsibility**: Similar to the front-office `index.php`, this might be a placeholder or a simple redirect. In PrestaShop, `index.php` files in controller directories often serve as security measures to prevent direct directory listing.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes in the `classes/` directory. This suggests that the module either:

1. Directly manipulates database tables (e.g., `ps_maobm_limits`) using `Db::getInstance()` in its controllers or the main module file.
2. Stores all configuration in `ps_configuration` using `Configuration::updateValue()`, with the `AdminMaobmController` managing these configuration entries.
   Given the “unlimited number of rules” feature, direct DB interaction for a custom table is more likely than `ps_configuration` for storing multiple manufacturer limits.

### 4.4 JavaScript Assets (`views/js/`)

- `views/js/maobm.js`
  - **Scope**: Likely Front-office.
  - **Details**: This script would be responsible for client-side interactions related to the module’s functionality. It might:
    - Bind event listeners to cart update actions (e.g., quantity changes, product removal).
    - Make AJAX calls to `controllers/front/ajax.php` to re-evaluate manufacturer limits in real-time without a full page reload.
    - Display warning messages or disable the checkout button if limits are exceeded, based on the AJAX response.
    - Potentially integrate with PrestaShop’s `prestashop.on` events for better compatibility.

### 4.5 CSS Stylesheets (`views/css/`)

- `views/css/maobm.css`
  - **Scope**: Primarily Front-office, possibly some Back-office styling for custom elements.
  - **Details**: This stylesheet would contain the necessary CSS rules to style the warning messages displayed to the customer in the cart or checkout process. It might define classes for:
    - `#maobm-warning-message` or similar containers for the error text.
    - Styling for disabled checkout buttons.
    - Ensuring responsiveness across different screen sizes.
  - **Key CSS class selectors developers can override**: Look for classes like `.maobm-alert`, `.maobm-error-message`, or specific IDs used for the warning container.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Hook**: This template is likely rendered in a hook that appears on the shopping cart page, such as `displayShoppingCartFooter` or `displayShoppingCart`.
    - **Output**: It would be responsible for displaying the warning message to the customer if they exceed a manufacturer’s purchase limit. It would receive variables from the module indicating whether a limit is exceeded and the relevant message to show.
- **Admin templates (`views/templates/admin/`)**: (Not explicitly listed, but implied by `AdminMaobmController`)

  - The `AdminMaobmController` would typically use PrestaShop’s `HelperList` and `HelperForm` templates for its interface, but it might have custom `.tpl` files for specific parts of its configuration or for displaying a list of rules. These would usually be found in `views/templates/admin/maobm/` or similar.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_maobm_limits` (Implied): A custom table to store the manufacturer limits.
    - `id_maobm_limit` (Primary Key, AUTO\_INCREMENT)
    - `id_manufacturer` (Foreign Key to `ps_manufacturer.id_manufacturer`)
    - `max_value` (Decimal or Float, storing the maximum allowed purchase value)
    - `date_add`, `date_upd` (Standard PrestaShop timestamps)
  - `ps_configuration`: Module might store general settings (like module enabled/disabled status) here.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | To include `maobm.css` and `maobm.js` assets. |
| `displayShoppingCart` or `displayShoppingCartFooter` | Renders content on the shopping cart page. | To display the warning message (`displayShoppingCart.tpl`) if limits are exceeded. |
| `actionCartSave` | Executed after a cart is saved or updated. | To re-evaluate manufacturer limits and potentially update cart status or display messages. |
| `actionValidateOrder` | Executed before an order is officially validated. | **CRITICAL**: To perform a final check on manufacturer limits and prevent order validation if limits are exceeded. This is where the order blocking logic would reside. |
| `displayAdminProductsExtra` (or similar) | Could be used to display manufacturer limit information directly on the product edit page in the BO. | (Optional) To provide quick access to limit info for the product’s manufacturer. |
| `displayBackOfficeHeader` | Renders in the `<head>` section of all back-office pages. | To include back-office specific CSS/JS for `AdminMaobmController`. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Maximum purchase value by manufacturer” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and configuration.
