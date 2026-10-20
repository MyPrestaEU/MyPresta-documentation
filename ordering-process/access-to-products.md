---
title: "Access to Products - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Access to Products PrestaShop module by MyPresta.eu."
sidebar:
  label: "Access to Products - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Access to Products Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/access-to-products/)
>
> ---


# Access to Products

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Access to Products)

This is the main configuration screen where you define the rules for product access.

#### General Settings

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Enable module** | YES | **Purpose:** Turns the module’s functionality on or off.   **Effect:**   *When enabled:* All your configured restrictions will be active on the front office.   *When disabled:* The module will have no effect, and all products will be visible and purchasable by all customers, regardless of group.   **Recommended:** YES, once you’ve configured your rules. |
| **Block possibility to view product page** | NO | **Purpose:** Controls whether customers not in allowed groups can even see the product’s dedicated page.   **Effect:**   *When enabled:* If a customer not in an allowed group tries to access the product page directly (e.g., via a link or search engine), they will be redirected or shown an access denied message.   *When disabled:* Unauthorized customers can still view the product page, but they will be prevented from adding it to their cart.   **Recommended:** YES for truly exclusive products, NO if you want them to see the product but not buy it (e.g., “contact us for wholesale”). |
| **Hide product on lists of products** | NO | **Purpose:** Determines if restricted products are hidden from category pages, search results, and other product listings for unauthorized customers.   **Effect:**   *When enabled:* Products will simply not appear in any product lists for customers not in the allowed groups.   *When disabled:* Products will appear in lists, but when the customer clicks on them, they will either be blocked from viewing the page (if “Block possibility to view product page” is YES) or blocked from adding to cart.   **Recommended:** YES for a cleaner, more targeted browsing experience for each customer group. |
| **Message for not allowed customers** | “You are not allowed to order this product.” | **Purpose:** The text displayed to customers who try to add a restricted product to their cart or view a restricted product page (if “Block possibility to view product page” is NO).   **Effect:** This message appears in the shopping cart next to the restricted product or on the product page.   **Recommended:** A clear, polite message. You can customize it to explain why (e.g., “This product is for wholesale customers only. Please log in to your wholesale account.”). |

#### Product Restrictions Table

This section displays a list of all products for which you have defined access restrictions. You can add new restrictions or edit existing ones here.

- **Product Name:** The name of the product being restricted.
- **Allowed Customer Groups:** A list of customer groups that *are* allowed to view and/or purchase this product.
- **Actions:** Edit (pencil icon) or Delete (trash can icon) the restriction.

#### Adding/Editing Product Restrictions

When you click “Add new restriction” or the “Edit” icon for an existing restriction, you’ll see a form:

- **Select Product:**

  - **What this setting does:** Allows you to search for and select the specific product you want to restrict.
  - **Effect of changing this setting:** This links the restriction rule to a particular product in your catalog.
  - **Recommended value:** Select the exact product.
  - **Merchant scenario:** You want to restrict “Wholesale Coffee Blend” to your wholesale customers. You’d search for and select “Wholesale Coffee Blend.”
- **Select Customer Groups:**

  - **What this setting does:** A list of all customer groups defined in your PrestaShop store (e.g., Visitor, Guest, Customer, Wholesaler, VIP). You select which of these groups *are allowed* to access the product.
  - **Effect of changing this setting:** Only customers belonging to the selected groups will be able to interact with the product according to your general settings (view, add to cart). All other groups will be restricted.
  - **Recommended value:** Select only the groups that should have access.
  - **Merchant scenario:** For “Wholesale Coffee Blend,” you would select “Wholesaler.” If you also wanted VIPs to have access, you’d select “Wholesaler” and “VIP.”

After making your selections, click **“Save”** to apply the restriction.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|
| Module Configuration | Enable module | YES | Activates/deactivates all module functionality. |
| Module Configuration | Block possibility to view product page | NO (consider YES for exclusivity) | Prevents unauthorized customers from seeing the product page. |
| Module Configuration | Hide product on lists of products | NO (consider YES for targeted display) | Hides restricted products from category/search results for unauthorized customers. |
| Module Configuration | Message for not allowed customers | “You are not allowed to order this product.” | Customizable message shown to unauthorized customers. |
| Product Restrictions Table | Select Product | N/A | Choose the product to apply restrictions to. |
| Product Restrictions Table | Select Customer Groups | N/A | Define which customer groups are *allowed* to access the selected product. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured restrictions, but they don’t seem to be working. What should I do?**
A:

1. **Check Module Status:** Ensure “Enable module” is set to YES in the module’s configuration.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office. Click “Clear cache” (or “Clear Smarty cache” in older versions). This is crucial for changes to take effect.
3. **Customer Group Assignment:** Double-check that the customer you are testing with is correctly assigned to the intended customer group (Customers > Customers, then edit the customer).
4. **Product Selection:** Verify that you have selected the correct product in the module’s restriction settings.
5. **Browser Cache:** Try clearing your browser’s cache or testing in an incognito/private browsing window to rule out client-side caching issues.

**Q: How do I translate the “Message for not allowed customers” into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop Back Office.
2. Select “Installed modules translations” as the Type of translation.
3. Choose your theme.
4. Select the language you want to translate.
5. Find the “Access to Products” module. You should see the field for the message there, ready for translation.

**Q: Will this module slow down my store?**
A: The module is designed to be lightweight and efficient. It integrates directly with PrestaShop’s core product and cart logic. Any performance impact should be negligible, especially after caching. If you notice significant slowdowns, ensure your server meets PrestaShop’s minimum requirements and that you’re using a recent PHP version.

**Q: What happens if a customer is in multiple groups, and one group is allowed while another is not?**
A: If a customer belongs to *any* group that is explicitly allowed access to a product, they will have access. The module grants access if *any* of the customer’s groups match an allowed group for that product. It’s an “OR” logic: if Group A is allowed OR Group B is allowed, and the customer is in Group A, they get access.

**Q: Can I restrict access to entire categories instead of individual products?**
A: This module focuses on individual product restrictions. To restrict entire categories, you would need to apply the restriction to each product within that category. For category-level restrictions, you might need a different module or custom development.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The “Access to Products” module (`pga`) primarily operates by overriding core PrestaShop classes to inject its access control logic. It leverages PrestaShop’s `ObjectModel` for configuration storage and modifies product visibility and cart behavior at key points in the front-office request lifecycle. The module’s main logic resides in `index.php` (the main module file) and its overrides.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All configuration is handled via the `getContent()` method in the main module file (`pga/index.php`).

### 4.3 Core Classes & Models (`classes/`)

The module utilizes PrestaShop’s override mechanism to modify core behavior.

- `pga/override/classes/Pack.php`

  - **Class Name:** `Pack` (overrides PrestaShop’s `Pack` class)
  - **Responsibility:** This override likely modifies how product packs are handled, specifically in relation to product visibility and access. It ensures that if a product within a pack is restricted, the pack itself respects those restrictions. This is crucial for maintaining consistent access control for bundled products.
  - **Key Methods (likely modified/added):** Methods related to `getPackProducts()` or `isPack()` might be extended to filter products based on `pga` restrictions.
- `pga/override/classes/shop/Shop.php`

  - **Class Name:** `Shop` (overrides PrestaShop’s `Shop` class)
  - **Responsibility:** This override is less common for product access modules and suggests a deeper integration. It might be used to ensure that product restrictions are correctly applied across different shops in a multi-shop environment, or to modify how product data is retrieved at a very fundamental level, potentially affecting product queries.
  - **Key Methods (likely modified/added):** Methods like `getProducts()` or `getProductById()` could be extended to filter results based on `pga` rules before they are even returned by the `Shop` context.

### 4.4 JavaScript Assets (`views/js/`)

- `pga/views/js/pga.js`
  - **Scope:** Back-office.
  - **Purpose:** This script is likely responsible for enhancing the user experience on the module’s configuration page. It might handle AJAX calls for product search, dynamic updates to the product restriction table, or client-side validation for the configuration form.
  - **Key Functionality:**
    - Event listeners for product search input fields (e.g., `keyup` events to trigger AJAX suggestions).
    - AJAX requests to a module endpoint (via `AdminController` or `index.php?fc=module&module=pga&controller=ajax`) to fetch product data or save restrictions.
    - DOM manipulation to display search results, add selected products to the restriction list, or update messages.

### 4.5 CSS Stylesheets (`views/css/`)

- `pga/views/css/pga.css`
  - **Scope:** Back-office.
  - **Purpose:** Provides styling for the module’s configuration interface in the PrestaShop Back Office.
  - **Main UI Components:** Styles for the product search input, the product restriction table, buttons, and any custom elements introduced by the module’s `getContent()` method.
  - **Key CSS Class Selectors:** Developers can inspect the module’s HTML output in the Back Office to identify specific classes (e.g., `.pga-product-search`, `.pga-restriction-table`) for potential overrides if custom admin theme styling is required.

### 4.6 Smarty Template Structure (`views/templates/`)

All templates are for the Back Office configuration.

- `pga/views/templates/admin/AdminTab.tpl`

  - **Purpose:** This template is likely a generic wrapper or a partial template used within the main configuration view. It might define the structure for a tabbed interface or a common header/footer for admin pages.
- `pga/views/templates/admin/csv.tpl`

  - **Purpose:** Suggests functionality related to CSV import/export of product restrictions. This template would render the interface for uploading a CSV file or generating one.
- `pga/views/templates/admin/csv_file.tpl`

  - **Purpose:** A sub-template or partial used by `csv.tpl`, possibly for displaying a file upload form or a list of CSV files.
- `pga/views/templates/admin/customerGroups.tpl`

  - **Purpose:** This template is crucial for the “Select Customer Groups” functionality. It renders the list of customer groups with checkboxes or a multi-select dropdown, allowing the admin to choose which groups are allowed for a specific product.
- `pga/views/templates/admin/main.tpl`

  - **Purpose:** This is the primary template for the module’s configuration page (rendered by `getContent()`). It orchestrates all other partials and displays the general settings, the product restriction table, and the add/edit restriction forms.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module stores its configuration in PrestaShop’s `ps_configuration` table for general settings (e.g., `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
  - For product-specific restrictions, the module likely creates a custom database table (e.g., `ps_pga_product_group`) to store the mapping between `id_product` and `id_group`. The `install()` method in `pga/index.php` would define this table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used to load module-specific CSS/JS for front-office display (e.g., if a custom message needs styling) or to perform early checks for product page redirection. |
| `displayRightColumn` / `displayLeftColumn` | In the right/left sidebar of front-office pages. | Less likely for this module, but could be used to display a custom block (e.g., “Login for exclusive access”) if configured. |
| `displayProductButtons` / `displayProductActions` (or similar product page hooks) | On the product page, near the Add to Cart button. | Used to hide or disable the “Add to Cart” button for unauthorized users, or to display the custom restriction message. |
| `displayFooter` | In the footer of every front-office page. | Less common for core functionality, but could be used for late-loading scripts or analytics related to product access. |
| `actionCartSave` / `actionObjectCartAddAfter` (or similar cart hooks) | When a product is added to or saved in the cart. | **CRITICAL:** This is where the module intercepts the cart process to check if the added product is restricted for the current customer’s group. If restricted, it prevents the addition or marks the item as invalid, displaying the custom message. |
| `actionProductListOverride` (or similar product listing hooks) | When PrestaShop generates a list of products (e.g., category page, search results). | **CRITICAL:** Used to filter out restricted products from product lists if “Hide product on lists of products” is enabled. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Before a front controller is dispatched or before media assets are set. | Could be used to implement the redirection logic for “Block possibility to view product page” by checking the requested product ID against restrictions. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Access to Products” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
