---
title: "Product date change - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product date change PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product date change - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product date change Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/product-date-change/)
>
> ---


# Product date change

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for the “Product date change” module. This is where you will select products and modify their dates.

#### **Product Selection**

- **What this setting does:** This section allows you to search for and select the specific products whose dates you wish to modify.
- **Effect of changing this setting:**
  - *Searching for a product:* Typing in the search box will filter your product list, making it easier to find the exact product you need.
  - *Selecting a product:* Once a product is selected, its current creation and update dates will be displayed, and you will be able to input new dates.
- **Recommended value:** Use the search bar to quickly locate products by name or ID.
- **Merchant scenario / example:** You want to change the date for “Summer Dress 2023”. You type “Summer Dress” into the search box, and the module displays matching products. You then click on “Summer Dress 2023” to select it.

#### **Change Product Creation Date**

- **What this setting does:** This field allows you to set a new `date_add` (creation date) for the selected product. This date is often used by PrestaShop to determine if a product is “new.”
- **Effect of changing this setting:**
  - *When a new date is entered and saved:* The product’s creation date in your database will be updated. This can cause the product to reappear in “New Products” blocks or change its position when sorting by “Date added.”
  - *When left unchanged:* The product’s original creation date will be preserved.
- **Recommended value:** Set a date that reflects when you want the product to be considered “new” or when it was genuinely added to your catalog. For re-highlighting, a recent date (today or yesterday) is ideal.
- **Merchant scenario / example:** Your “Winter Coat” product was added last year. You want to promote it as a “new arrival” for the upcoming winter season. You select the product, then set the “Change Product Creation Date” to today’s date. Now, it will show up in your “New Products” section.

#### **Change Product Update Date**

- **What this setting does:** This field allows you to set a new `date_upd` (last update date) for the selected product. This date is used for internal tracking and can also influence product sorting.
- **Effect of changing this setting:**
  - *When a new date is entered and saved:* The product’s last update date in your database will be modified. This can affect sorting options where customers sort by “Date updated.”
  - *When left unchanged:* The product’s original update date will be preserved.
- **Recommended value:** Set a date that reflects the last time you made significant changes to the product (e.g., updated description, price, images) or if you want to bring it to the top of “recently updated” lists.
- **Merchant scenario / example:** You’ve just updated the description and added new images for your “Organic Coffee Beans” product. You want this product to appear higher when customers sort by “recently updated.” You select the product and set the “Change Product Update Date” to today’s date.

#### **Save Button**

- **What this setting does:** This button applies all the date changes you’ve made for the selected product.
- **Effect of changing this setting:** Clicking “Save” will commit the new creation and/or update dates to your PrestaShop database. You will typically see a success message.
- **Recommended value:** Always click “Save” after making any date modifications.
- **Merchant scenario / example:** After setting both the creation and update dates for your “Limited Edition Sneakers,” you click “Save” to apply these changes to your store.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Product Search Field | N/A | Find products by name or ID to modify their dates. |
| Module Configuration Page | Change Product Creation Date | Current product’s `date_add` | Sets a new creation date. Affects “New Products” visibility and “Date added” sorting. Recommended: A recent date for re-highlighting. |
| Module Configuration Page | Change Product Update Date | Current product’s `date_upd` | Sets a new last update date. Affects “Date updated” sorting. Recommended: A recent date after significant product changes. |
| Module Configuration Page | Save Button | N/A | Applies all selected date changes to the product in the database. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I changed the date, but the product isn’t showing as “new” on my homepage. What’s wrong?**
A1:

- **Clear Cache:** PrestaShop heavily relies on caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). This is the most common fix.
- **Module Configuration:** Check the settings of your “New Products” module (e.g., “New products block” or “New products page”). Ensure it’s configured to display products based on their creation date and that the number of days for “new” products is set appropriately (e.g., 30 days). If you set a product’s creation date to be older than this threshold, it won’t appear as new.
- **Theme Specifics:** Some themes might have their own caching or custom logic for “new products.” If clearing cache doesn’t work, consult your theme’s documentation or support.

**Q2: Will changing the product date affect my SEO?**
A2: Directly, no. Search engines like Google primarily focus on the content of your product page (description, images, reviews) and external links, not internal PrestaShop product dates. However, indirectly, if changing the date makes the product appear as “new” and drives more internal traffic or sales, that increased engagement *can* positively influence SEO over time. It’s more about user experience and merchandising than direct SEO manipulation.

**Q3: Can I change dates for multiple products at once (bulk edit)?**
A3: This module is designed for individual product date changes. If you need to bulk edit dates for a large number of products, you would typically need a more advanced import/export tool or a custom script. For a few products, doing them one by one with this module is efficient.

**Q4: What happens if I set a future date?**
A4: PrestaShop will accept a future date. However, the practical effect might be limited. A product set with a future creation date might not appear in “new products” lists until that date arrives. It’s generally recommended to use current or past dates.

**Q5: I changed the date, but when I edit the product in the Back Office, the old date is still there.**
A5: This module directly modifies the `date_add` and `date_upd` fields in the database. When you view a product in the standard PrestaShop product edit page, it should reflect these changes. If it doesn’t, ensure you clicked “Save” in the module’s configuration, cleared your PrestaShop cache, and reloaded the product edit page. If the issue persists, there might be a conflict with another module or a deeper caching issue.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Product date change` module (`pdc`) is a straightforward PrestaShop module designed to interact directly with the `Product` ObjectModel. It leverages the standard `getContent()` method for its Back Office configuration, providing a simple form to select a product and modify its `date_add` and `date_upd` fields. It does not introduce new database tables, complex controllers, or extensive front-office logic, making it lightweight and focused on its core administrative task.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom front-office or back-office controllers. All logic is encapsulated within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or ObjectModels in the `classes/` directory. It directly interacts with PrestaShop’s core `Product` ObjectModel.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Styling is expected to be handled by PrestaShop’s default Back Office styles.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`pdc/views/pdc.tpl`**:
  - **Scope**: Back-office admin configuration.
  - **Purpose**: This template renders the main configuration form for the module. It includes:
    - A search input field to find products.
    - Display areas for the current `date_add` and `date_upd` of the selected product.
    - Input fields (likely date pickers) for setting new `date_add` and `date_upd` values.
    - A submit button to save the changes.
  - **Usage**: This template is rendered by the `getContent()` method of the `pdc` module.
  - **Key Selectors**: Developers can inspect the generated HTML for specific IDs or classes to override styling if needed, though typically not required for a simple admin form.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom database tables.
  - It directly modifies the `date_add` and `date_upd` columns within the existing `ps_product` table (and potentially `ps_product_shop` if context-specific dates are managed, though the module description implies direct product object modification).
  - Configuration values (if any, though none are explicitly listed beyond direct product manipulation) would be stored in `ps_configuration`.
- **Registered Hooks Table**:
  This module does not register any specific hooks for front-office display or back-office actions beyond the standard `displayBackOfficeHeader` (for assets, if any) and `moduleRoutes` (if custom URLs were needed, which they are not for this module). Its primary interaction is through the `getContent()` method.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renders in the `<head>` section of Back Office pages. | (Potentially) To include any necessary JS/CSS for the module’s configuration page, though none are present in this module. |
| `actionProductUpdate` | Executed after a product is updated. | The module’s internal logic for updating product dates might trigger this hook, but the module itself does not explicitly register to listen to it or perform actions based on it. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Product date change” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the module’s functionality and compatibility.
