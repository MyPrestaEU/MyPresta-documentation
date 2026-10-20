---
title: "Password protected product pages - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Password protected product pages PrestaShop module by MyPresta.eu."
sidebar:
  label: "Password protected product pages"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Password protected product pages Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/password-protected-product-pages/)
>
> ---


# Password protected product pages

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
This is the main configuration screen for the module, accessed by clicking "Configure" after installation or from the Module Manager.

- **What this setting does:** This screen typically contains general settings for the module, though for "Password protected product pages," the primary management of passwords for specific products is handled in a dedicated admin screen (see 4.2). This screen might offer options for the appearance of the password input page or general module behavior.
- **Effect of changing this setting:** Any changes here would affect how the password protection mechanism behaves globally, or the default appearance of the password entry form.
- **Recommended value:** Default values are usually a good starting point.
- **Merchant scenario / example:** If there's an option to customize the message shown on the password page, you might change it from "Enter password" to "Please enter your VIP access code."

### 2.2 Dedicated Admin Screen: Product Passwords (Back Office > Catalog > Product Passwords)
This is the most important screen for managing which products are password protected and what those passwords are. You will find this new menu item under **Catalog** in your PrestaShop Back Office.

- **Screen Name & Menu Location:** **Catalog > Product Passwords**
- **Available Actions & Settings:**
    -   **Listing Table:** This screen displays a list of all products that currently have a password assigned to them. You'll typically see columns like:
        -   **Product Name:** The name of the product being protected.
        -   **Product ID:** The unique identifier for the product.
        -   **Password:** The password required to access the product page.
        -   **Actions:** Buttons to "Edit" or "Delete" the password for a specific product.
    -   **Add New Password:** There will be a button (e.g., "Add new product password" or a plus icon) to add a new password protection entry. When you click this, you will typically be presented with a form:
        -   **Product Selector:** A field to search for and select the product you want to protect. This might be an autocomplete field where you type the product name.
        -   **Password Field:** An input field where you define the password for that specific product.
    -   **Edit Password:** Clicking "Edit" next to an existing entry allows you to change the password for that product or potentially change the associated product.
    -   **Delete Password:** Clicking "Delete" removes the password protection from that product, making it publicly accessible again.
- **Effect of changes:**
    -   **Adding a password:** The selected product page will immediately become password protected in the front office.
    -   **Changing a password:** Customers will need to use the new password to access the product page.
    -   **Deleting a password:** The product page will revert to being publicly accessible without any password requirement.
- **Recommended workflow for daily store management:**
    1.  To protect a new product: Navigate to **Catalog > Product Passwords**, click "Add new product password," select your product, and set a strong, unique password.
    2.  To update a password: Find the product in the list, click "Edit," and enter the new password.
    3.  To remove protection: Find the product in the list and click "Delete."
    4.  Regularly review your protected products to ensure the passwords are still relevant and secure.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | (General settings, if any) | (Module default) | Global behavior or appearance of the password entry page. |
| Catalog > Product Passwords | Add New Product Password | N/A | Select a product and assign a password to restrict access to its page. |
| Catalog > Product Passwords | Edit Product Password | N/A | Modify the password for an already protected product. |
| Catalog > Product Passwords | Delete Product Password | N/A | Remove password protection, making the product page public again. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I've set a password, but the product page is still public. What's wrong?**
A1:
*   **Check the password entry:** Double-check in **Catalog > Product Passwords** that the product is listed and the password is correctly set.
*   **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" if available). This ensures your store is loading the latest configuration.
*   **Module Status:** Ensure the "Password protected product pages" module is enabled in **Modules > Module Manager**.
*   **Product Status:** Make sure the product itself is enabled and visible in your catalog.

**Q2: Can I have different passwords for different products?**
A2: Yes, absolutely! The module is designed for this. You can assign a unique password to each individual product you wish to protect via the **Catalog > Product Passwords** screen.

**Q3: What happens if a customer tries to access a protected product page directly via its URL without the password?**
A3: They will be redirected to the password entry page. They will not be able to see the product content until they enter the correct password.

**Q4: How do I translate the text on the password entry page (e.g., "Enter password")?**
A4: You can usually translate module texts through PrestaShop's translation interface. Go to **International > Translations**, select "Installed modules translations," choose your theme, and then select the "Password protected product pages" module. You should find the editable text strings there.

**Q5: Will this module work with my custom theme?**
A5: The module is designed to integrate seamlessly with standard PrestaShop themes. However, highly customized themes might require minor CSS adjustments to ensure the password entry form looks perfect. If you encounter styling issues, consult your webmaster or theme developer.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview
The "Password protected product pages" module primarily operates by overriding the default `ProductController` to intercept requests for protected products. It uses a dedicated admin controller to manage product-password associations, which are stored in the database. The front-office logic checks for a valid session cookie containing the password for a given product before rendering the actual product page.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Class name & parent class:** `ProductPasswdModuleFrontController` extending `ModuleFrontController`.
        *   **Responsibility:** This controller is likely responsible for rendering the password input form when a protected product is accessed. It handles the POST request when a user submits a password, validates it against the stored password for the product, and sets a session or cookie upon successful authentication to grant access. It might also handle redirection to the actual product page.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Class name & parent class:** `ProductController` (overridden).
        *   **Responsibility:** This is a crucial override. It intercepts the `init()` or `postProcess()` method of the core `ProductController`. Before the standard product page content is loaded, this override checks if the current product is password protected and if the user has already provided the correct password (e.g., via a session cookie). If the product is protected and no valid password is found, it redirects the user to the `ProductPasswdModuleFrontController` (or directly renders its template) to prompt for the password.

-   **Back-Office Admin Controllers**:
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Tab name and managed entity:** Accessible via **Catalog > Product Passwords**. Manages `prodpassword` entities (product ID and associated password).
        *   **Responsibility:** This is a standard `AdminController` responsible for the CRUD (Create, Read, Update, Delete) operations for product-password associations. It displays the list of protected products, allows administrators to add new product-password entries, edit existing passwords, and delete them. It likely uses `HelperList` for the grid view and `HelperForm` for add/edit forms.
    *   `prodpswd/controllers/admin/index.php`
        *   **Responsibility:** This file is typically an empty `index.php` file placed in subdirectories of PrestaShop modules to prevent directory listing, enhancing security. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)
The module dossier indicates no custom classes in the `classes/` directory. The `prodpassword` entity is likely managed directly by the `AdminProdPasswordController` using a simple `ObjectModel` definition within the module's main file or the controller itself, or it might be directly interacting with `Configuration` or a custom table without a dedicated `ObjectModel`. Given the `AdminProdPasswordController` manages a `prodpassword` table, it's highly probable there's an `ObjectModel` defined for it, even if not in a separate `classes/` folder.

### 4.4 JavaScript Assets (`views/js/`)
The module dossier indicates no custom JavaScript files. The front-office password form and back-office grid/form are expected to rely on standard PrestaShop JS or simple HTML form submissions.

### 4.5 CSS Stylesheets (`views/css/`)
The module dossier indicates no custom CSS files. The styling for the password entry page in the front office and the admin forms will likely inherit from the active PrestaShop theme and back-office styles.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   No specific hook templates are listed, suggesting the module primarily operates via controller overrides and dedicated front-office templates rather than injecting content into standard hooks.
-   **Admin templates (`views/templates/admin/`)**:
    *   No specific admin templates are listed. The `AdminProdPasswordController` likely uses standard PrestaShop `HelperList` and `HelperForm` templates for its interface.
-   **Front-office templates (`views/templates/front/`)**:
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Purpose:** This template is likely the custom password entry form displayed to customers when they try to access a protected product page. It contains the HTML structure for the password input field, submission button, and any accompanying messages (e.g., "Enter password to view this product").
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Purpose:** This template likely contains JavaScript or Smarty logic related to a search tool, possibly used within the admin configuration for selecting products to protect. It might include AJAX calls or dynamic filtering capabilities for product selection.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   `ps_prodpassword` (or similar): This custom table is expected to store the product ID (`id_product`) and the associated password (`password`) for each protected product. It's created during the module's `install()` method.
    *   Configuration records in `ps_configuration`: General module settings (if any) would be stored here.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `actionFrontControllerSetMedia` | Before a front controller's media (JS/CSS) are loaded. | Potentially to load custom JS/CSS for the password form, though none are listed in the dossier. |
| `displayHeader` | In the `<head>` section of the front office. | Could be used for meta tags or conditional JS/CSS, but not explicitly used for content. |
| `displayRightColumn` | In the right column of the front office. | Not directly used for module's core functionality. |
| `displayLeftColumn` | In the left column of the front office. | Not directly used for module's core functionality. |
| `displayFooter` | In the footer of the front office. | Not directly used for module's core functionality. |
| `actionProductControllerSetMedia` | After the `ProductController` has set its media. | Could be used to inject specific JS/CSS for the product page, but unlikely given the override. |
| `actionDispatcherBefore` | Before a front controller is dispatched. | The `override/controllers/front/ProductController.php` effectively acts at this stage for product pages. |
| `actionDispatcherAfter` | After a front controller has been dispatched. | Less likely for this module's core functionality. |

The primary mechanism for this module is the `ProductController` override, which acts as an implicit hook, intercepting requests before standard hooks are even processed for the product page content.

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Password protected product pages" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have.
