---
title: "Customer Files Upload - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer Files Upload PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer Files Upload - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer Files Upload Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/customer-files-upload/)
>
> ---


# Customer Files Upload

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module. Ensure your server has enough disk space to store uploaded files.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, accessed after installation or by clicking “Configure” from the Module Manager.

- **Enable Module:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s functionality across your store.
  - **Effect of changing this setting:**
    - *When enabled:* All file upload features, customer file management, and back-office tools become active.
    - *When disabled:* The module’s features are completely turned off, and no upload forms or “My Files” sections will appear.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you’re setting up the module for the first time or performing maintenance, you might disable it temporarily. Otherwise, keep it enabled to offer the file upload service.
- **Allow uploads on Product Page:**

  - **What this setting does:** Controls whether customers can upload files directly from a product’s page.
  - **Effect of changing this setting:**
    - *When enabled:* An upload form will appear on product pages, allowing customers to attach files before adding the product to their cart.
    - *When disabled:* No upload form will be visible on product pages.
  - **Recommended value:** YES (if your products require pre-purchase customization files)
  - **Merchant scenario / example:** If you sell custom-printed mugs, enabling this allows customers to upload their photo directly on the mug’s product page.
- **Allow uploads on Shopping Cart Page:**

  - **What this setting does:** Determines if an upload area is shown on the shopping cart summary page.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can upload general files related to their entire cart or specific items before proceeding to checkout.
    - *When disabled:* No upload form will be visible on the shopping cart page.
  - **Recommended value:** YES (if customers might need to provide general order instructions or files for multiple items)
  - **Merchant scenario / example:** A customer ordering multiple custom items might upload a single document with general instructions or a branding guide for the whole order.
- **Allow uploads on Order Confirmation Page:**

  - **What this setting does:** Controls whether customers can upload files immediately after placing an order, on the order confirmation screen.
  - **Effect of changing this setting:**
    - *When enabled:* An upload form appears on the “Order Confirmation” page, allowing customers to attach files to their newly placed order.
    - *When disabled:* No upload form will be visible on the order confirmation page.
  - **Recommended value:** YES (highly recommended for most use cases)
  - **Merchant scenario / example:** A customer just bought a custom banner. They can immediately upload their high-resolution design file on the confirmation page without navigating elsewhere.
- **Allow uploads in Customer Account (My Files & Order History):**

  - **What this setting does:** Enables the “My Files” section in the customer’s account and allows uploads on individual order detail pages within their history.
  - **Effect of changing this setting:**
    - *When enabled:* Customers get a dedicated “My Files” area to manage all their uploads and can add files to specific past orders.
    - *When disabled:* Customers cannot manage files from their account, and no upload options will appear on order history pages.
  - **Recommended value:** YES (provides maximum flexibility and customer control)
  - **Merchant scenario / example:** A customer realizes they forgot to upload a specific font file for their custom t-shirt order a day later. They can log into their account, go to the order, and upload it.
- **Maximum File Size (MB):**

  - **What this setting does:** Sets the upper limit for the size of each individual file a customer can upload.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 10):* Customers will be prevented from uploading files larger than 10MB.
    - *When set to 0 or empty:* The module will typically defer to your server’s PHP upload limits, which might be very high or very low.
  - **Recommended value:** 5-20 MB (adjust based on typical file types; e.g., high-res images might need more).
  - **Merchant scenario / example:** If you expect customers to upload high-resolution photos, you might set this to 20MB. If only small documents are needed, 5MB might suffice to save server space.
- **Allowed File Types (comma-separated):**

  - **What this setting does:** Specifies which file extensions are permitted for upload.
  - **Effect of changing this setting:**
    - *When set to “jpg,png,pdf”:* Only files with these extensions can be uploaded. Any other file type will be rejected.
    - *When left empty:* All file types might be allowed (not recommended for security).
  - **Recommended value:** Only include types you expect (e.g., `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Avoid executable files.
  - **Merchant scenario / example:** If you only need design files, you might list `ai,eps,svg,psd,pdf,jpg,png`. If you need documents, `doc,docx,pdf` would be appropriate.
- **Force File Upload for specific products (Product IDs):**

  - **What this setting does:** Allows you to make file uploads mandatory for certain products. Enter product IDs separated by commas.
  - **Effect of changing this setting:**
    - *When product IDs are entered:* If a customer tries to add one of these products to the cart or proceed to checkout without uploading a file, they will be prompted to do so.
    - *When left empty:* No products will have mandatory file uploads.
  - **Recommended value:** Use only for products where a file is absolutely essential for processing the order.
  - **Merchant scenario / example:** For a “Custom Business Card Design” product (ID 123), you might enter `123`. The customer cannot complete the purchase without uploading their logo or design brief.
- **Email Notification to Customer on File Upload:**

  - **What this setting does:** Controls whether an email is sent to the customer when they successfully upload a file.
  - **Effect of changing this setting:**
    - *When enabled:* The customer receives a confirmation email that their file has been received.
    - *When disabled:* No email notification is sent to the customer.
  - **Recommended value:** YES (improves customer trust and provides confirmation)
  - **Merchant scenario / example:** A customer uploads a photo for a personalized gift. An email confirms the upload, reassuring them that their file was received correctly.
- **Email Notification to Admin on File Upload:**

  - **What this setting does:** Controls whether an email is sent to the store administrator(s) when a customer uploads a file.
  - **Effect of changing this setting:**
    - *When enabled:* The store admin receives an email alert, making them aware of new files that need attention.
    - *When disabled:* No email notification is sent to the admin.
  - **Recommended value:** YES (essential for timely order processing)
  - **Merchant scenario / example:** A customer uploads a design file. The admin receives an email, prompting them to check the order and begin processing the custom item.
- **Display Upload Button in Header/Footer/Columns:**

  - **What this setting does:** Allows you to choose where a general “Upload Files” button or link appears on your store (e.g., in the header, footer, or side columns).
  - **Effect of changing this setting:**
    - *When a hook is selected:* A link or button will appear in that location, directing customers to their “My Files” section or a general upload page.
    - *When “None” is selected:* No general upload button will be displayed outside of product/cart/order pages.
  - **Recommended value:** Consider `displayHeader` or `displayFooter` for easy access to “My Files” if you expect frequent uploads.
  - **Merchant scenario / example:** Placing a “My Files” link in the footer allows returning customers to quickly access and manage their uploaded documents.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Customer Files Manager (Back Office > Modules > Customer Files Upload > Customer Files)

This screen provides a centralized place for you, the store owner, to view and manage all files uploaded by your customers.

- **Screen Name & Menu Location:** You can find this by navigating to **Modules > Module Manager**, finding “Customer Files Upload,” and clicking “Configure.” Within the module’s configuration, there should be a tab or link labeled “Customer Files” or “Manage Files.” Alternatively, it might appear directly under the “Modules” menu as “Customer Files.”
- **Available Actions & Settings:**
  - **File Listing Table:** Displays a list of all uploaded files, including details like:
    - **File Name:** The name of the uploaded file.
    - **Customer:** The name of the customer who uploaded the file.
    - **Order ID:** If the file is linked to a specific order.
    - **Product:** If the file is linked to a specific product.
    - **Upload Date:** When the file was uploaded.
    - **Size:** The size of the file.
    - **Actions:** Typically includes options to **Download** the file, **View Details**, or **Delete** the file.
  - **Filtering and Searching:** You can usually filter files by customer, order ID, product, or date range to quickly find specific uploads.
  - **Bulk Actions:** Options to select multiple files and perform actions like bulk deletion.
- **Effect of changes:**
  - **Downloading a file:** Retrieves the customer’s uploaded file to your computer for processing.
  - **Deleting a file:** Permanently removes the file from your server and from the customer’s “My Files” section. Use with caution!
- **Recommended workflow for daily store management:** Regularly check this section for new uploads, especially after receiving admin email notifications. Download necessary files for order fulfillment, and periodically review and delete old or unnecessary files to free up server space.

#### 2.2.2 Order Detail Page Integration (Back Office > Orders > Orders > View Order)

The module integrates directly into your existing PrestaShop order detail pages.

- **Screen Name & Menu Location:** When you view a specific order in your Back Office (e.g., **Orders > Orders**, then click “View” next to an order).
- **Available Actions & Settings:**
  - Within the order detail page, a new section or tab will appear, specifically for “Customer Files” or “Uploaded Files.”
  - This section will list all files that the customer has uploaded for *that specific order*.
  - You will see file names, upload dates, and options to **Download** each file.
  - There might also be an option for the admin to **Upload a file** on behalf of the customer or for internal use related to the order.
- **Effect of changes:**
  - **Downloading files from here:** Allows you to quickly access files relevant to the order you are currently viewing, streamlining order processing.
  - **Admin Upload:** If available, allows you to add internal notes or files related to the order directly to the order’s file list.
- **Recommended workflow for daily store management:** When processing an order that requires customer files, navigate to the order detail page, locate the “Customer Files” section, and download all necessary documents before starting production or fulfillment.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Module | YES | Master switch for module functionality. |
|  | Allow uploads on Product Page | YES (if needed) | Shows upload form on product pages. |
|  | Allow uploads on Shopping Cart Page | YES (if needed) | Shows upload form on cart page. |
|  | Allow uploads on Order Confirmation Page | YES | Shows upload form after order placement. |
|  | Allow uploads in Customer Account | YES | Enables “My Files” and order history uploads. |
|  | Maximum File Size (MB) | 5-20 MB | Limits individual file upload size. |
|  | Allowed File Types | `jpg,png,pdf,...` | Restricts file extensions for security/relevance. |
|  | Force File Upload for specific products (IDs) | Empty (use as needed) | Makes upload mandatory for specified products. |
|  | Email Notification to Customer | YES | Sends email confirmation to customer on upload. |
|  | Email Notification to Admin | YES | Sends email alert to admin on new upload. |
|  | Display Upload Button in Header/Footer/Columns | `displayFooter` (or as needed) | Places a general “Upload Files” link in selected hook. |
| **Customer Files Manager** | File Listing | N/A | View, filter, download, and delete all customer files. |
|  | Bulk Actions | N/A | Perform actions on multiple selected files. |
| **Order Detail Page** | Customer Files Section | N/A | View and download files specific to the current order. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers can’t see the upload forms or “My Files” section.**
A:

- **Check Module Status:** Ensure the module is enabled in **Modules > Module Manager**.
- **Check Configuration:** Go to the module’s configuration page and verify that “Enable Module” is set to YES and that specific upload locations (Product Page, Cart, Customer Account) are also enabled.
- **Clear Cache:** Sometimes PrestaShop’s cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance** and click “Clear cache.”
- **Theme Compatibility:** If you’re using a highly customized theme, it might not be correctly hooking into the module’s display points. Contact MyPresta.eu support or your web developer.

**Q2: Customers are getting an error when trying to upload files.**
A:

- **Check File Size Limit:** Verify the “Maximum File Size (MB)” in the module’s configuration. The customer’s file might be too large.
- **Check Allowed File Types:** Ensure the file type the customer is trying to upload is listed in the “Allowed File Types” setting (e.g., if they’re uploading a `.zip` file, `zip` must be in the list).
- **Server Limits:** Your web host might have server-side PHP upload limits (`upload_max_filesize`, `post_max_size`) that are lower than your module’s setting. You might need to contact your host or adjust your `php.ini` file.

**Q3: I’m not receiving email notifications when customers upload files.**
A:

- **Check Email Notification Settings:** In the module’s configuration, ensure “Email Notification to Admin on File Upload” is set to YES.
- **PrestaShop Email Settings:** Verify that your PrestaShop store’s email settings are correctly configured and sending emails successfully (**Advanced Parameters > E-mail**). Send a test email from there.
- **Spam Folder:** Check your spam or junk folder for the notifications.
- **Server Mailer:** Ensure your server’s mail function is working correctly.

**Q4: How do I translate the module’s text into other languages?**
A:

- Navigate to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and then select “Customer Files Upload” from the module dropdown.
- You can then translate all visible strings used by the module.

**Q5: Where are the uploaded files stored on my server?**
A: The module typically stores files in a dedicated folder within your PrestaShop installation, often named `upload` or `orderfiles_uploads` inside the module’s directory or a general `upload` directory. You can access these via FTP/SFTP, but it’s always best to manage them through the Back Office interface to maintain database integrity.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Customer Files Upload” module follows a standard PrestaShop module architecture, leveraging MVC principles. It extends `Module` for its core functionality and configuration, uses `ModuleFrontController` for front-office interactions (uploading, managing files), and `AdminController` for back-office management. Data is stored in the file system and potentially linked via `ps_configuration` for settings. The module heavily relies on PrestaShop’s hook system to inject its functionality into various parts of the store.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/customerfiles.php`
  - **Class name & parent class:** `CustomerfilesCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Likely handles the main customer-facing “My Files” page, displaying a list of uploaded files and providing options for management. It would fetch files associated with the logged-in customer.
- `controllers/front/download.php`
  - **Class name & parent class:** `DownloadCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Manages secure file downloads. It takes a file ID or path, verifies customer permissions (if applicable), and serves the file to the browser, often forcing a download.
- `controllers/front/filesmanager.php`
  - **Class name & parent class:** `FilesmanagerCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Could be a generic file management interface, potentially used for AJAX calls related to file operations (e.g., deleting a file from the customer’s view).
- `controllers/front/index.php`
  - **Class name & parent class:** `IndexCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Often a placeholder or a redirect controller. In some modules, it might serve as a default entry point or handle basic routing.
- `controllers/front/myfiles.php`
  - **Class name & parent class:** `MyfilesCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Similar to `customerfiles.php`, this likely handles the specific “My Files” section within the customer’s account, displaying their uploaded files and potentially an upload form.
- `controllers/front/thumb.php`
  - **Class name & parent class:** `ThumbCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** Generates and serves thumbnails for uploaded image files, improving performance and display on file listing pages.
- `controllers/front/upload.php`
  - **Class name & parent class:** `UploadCustomerfilesModuleFrontController` extends `ModuleFrontController`
  - **Responsibility:** The core upload handler. It receives file uploads (via AJAX or standard form submission), validates file type and size, moves the file to the designated directory, and records file information in the database.

#### Back-Office Admin Controllers

- `controllers/admin/customerFiles.php`
  - **Class name & parent class:** `AdminCustomerFilesController` extends `ModuleAdminController`
  - **Tab name and managed entity:** “Customer Files” (or similar). This controller manages the main grid view of all customer-uploaded files in the Back Office. It provides functionality for listing, filtering, viewing details, downloading, and deleting files.
  - **Associated Config Keys:** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (for email notifications), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (likely related to email template settings for customer notifications).
- `controllers/admin/index.php`
  - **Class name & parent class:** `IndexCustomerfilesModuleAdminController` extends `ModuleAdminController`
  - **Tab name and managed entity:** Similar to front-office `index.php`, this might be a placeholder or a redirect controller for the admin section of the module.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes in the `classes/` directory. This suggests the module might be using `ObjectModel` directly within the main module file or admin controllers, or it’s a legacy module structure where data handling is embedded. If data is stored in a custom table, the `install()` method of the main module would define its schema.

### 4.4 JavaScript Assets (`views/js/`)

- `js/jquery.form.js`
  - **Scope:** Likely Front-office and Back-office.
  - **Explanation:** A jQuery plugin for easily submitting forms via AJAX, including file uploads. It handles the complexities of `multipart/form-data` and provides progress callbacks.
- `js/orders.js`
  - **Scope:** Back-office (specifically order detail pages).
  - **Explanation:** This script likely adds functionality to the PrestaShop order detail page, such as displaying the uploaded files section, handling admin-side file downloads, or potentially allowing admins to upload files to an order.
- `js/script-customers.js`
  - **Scope:** Front-office (customer account pages).
  - **Explanation:** Handles client-side logic for the “My Files” section in the customer account, including displaying file lists, managing delete actions, and initiating new uploads.
- `js/script.js`
  - **Scope:** Front-office (general, product, cart pages) and potentially Back-office configuration.
  - **Explanation:** A general-purpose script for the module. It likely initializes upload forms, handles file validation (size, type) before submission, displays upload progress, and manages UI interactions related to file uploads across various front-office locations.

### 4.5 CSS Stylesheets (`views/css/`)

- `css/ajaxuploader.css`
  - **Scope:** Front-office.
  - **Explanation:** Styles for the AJAX-based file upload interface, including progress bars, drag-and-drop zones, and file input elements.
- `css/backoffice.css`
  - **Scope:** Back-office.
  - **Explanation:** Specific styles for the module’s administration pages, such as the “Customer Files Manager” grid, configuration forms, and integration into the order detail page.
- `css/orderfiles.css`
  - **Scope:** Front-office.
  - **Explanation:** General styling for the module’s front-office components, including file lists, buttons, and messages displayed to customers.
- `css.css`
  - **Scope:** Front-office.
  - **Explanation:** Could be a legacy or general stylesheet, potentially containing core styles for the module’s visual elements.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `displayProductPageUploadFormSmall.tpl`: Renders a compact upload form on the product page.
- `filesmanager-orderhistory.tpl`: Displays the file manager/upload section within the customer’s order history detail page.
- `force-redirect.tpl`: A utility template, possibly for handling redirects after certain actions or for displaying messages before redirection.
- `header.tpl`: Injected into `displayHeader`, typically for loading CSS/JS assets or meta tags required by the module.
- `my-account-17.tpl`: Renders the “My Files” link or block in the customer’s account dashboard for PrestaShop 1.7.x and newer.
- `my-account.tpl`: Renders the “My Files” link or block in the customer’s account dashboard for older PrestaShop versions (1.5.x, 1.6.x).
- `orderConfirmation.tpl`: Displays the upload form or file list on the order confirmation page.
- `product-files-button.tpl`: Renders a button or link on the product page that might open an upload modal or redirect to an upload section.
- `product-files.tpl`: Displays a list of files associated with a product or an upload form on the product page.
- `shopping-cart-force-files-alert.tpl`: Displays an alert in the shopping cart if mandatory files are missing for certain products.
- `shopping-cart-qty-infos-alert.tpl`: Potentially related to alerts for quantity-based file requirements in the cart.
- `shopping-cart.tpl`: Displays the upload form or file list on the shopping cart summary page.
- `tab.tpl`: A generic tab template, possibly used for displaying a “Files” tab on product pages or in the customer account.

#### Admin templates (`views/templates/admin/`)

- `admin.tpl`: General admin template, possibly for the module’s main configuration page or a dashboard.
- `adminOrderDetailUpload.tpl`: Integrates the file upload/management section into the PrestaShop order detail page in the Back Office.
- `boscript.tpl`: Contains JavaScript specific to the Back Office, potentially for initializing forms or handling AJAX on admin pages.
- `bulk-delete-files.tpl`: Template for a bulk delete confirmation or interface within the admin file manager.
- `comments_cartfiles.tpl`: Displays comments or notes related to files uploaded for a specific cart.
- `comments_orderfiles.tpl`: Displays comments or notes related to files uploaded for a specific order.
- `comments_productfiles.tpl`: Displays comments or notes related to files uploaded for a specific product.
- `customerfilesmanager.tpl`: The main template for the “Customer Files Manager” grid view in the Back Office.
- `_configure/helpers/list/list_action_details.tpl`: Template for a “details” action button in a list helper.
- `_configure/helpers/list/list_content.tpl`: Template for the main content of a list helper (e.g., the rows of the file list).
- `_configure/prestashopbug/helpers/list/*.tpl`: These templates (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) suggest a custom or overridden list helper implementation, possibly to address specific display needs or bugs in older PrestaShop versions.

#### Front-office templates (`views/templates/front/`)

- `access-denied.tpl`: Displays a message when a customer tries to access a file or page without proper permissions.
- `customerfilesmanager.tpl`: The main template for the customer’s “My Files” page, displaying their uploaded files and management options.
- `filesmanager.tpl`: A generic file manager template, potentially used for various front-office file listing and upload scenarios.
- `my-files.tpl`: Another template for the customer’s “My Files” section, likely similar to `customerfilesmanager.tpl` or used in conjunction.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module likely creates at least one custom table to store metadata about the uploaded files. A typical table structure would be `ps_orderfiles` (or similar), containing fields like:
    - `id_order_file` (Primary Key)
    - `id_customer` (Foreign key to `ps_customer`)
    - `id_order` (Foreign key to `ps_order`, nullable)
    - `id_product` (Foreign key to `ps_product`, nullable)
    - `filename` (Original name of the file)
    - `filepath` (Path to the stored file on the server)
    - `filesize` (Size in bytes)
    - `file_extension`
    - `date_add` (Timestamp of upload)
    - `comment` (Optional comment from customer or admin)
  - Configuration settings are stored in `ps_configuration` with keys like `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH`, and other module-specific settings.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS, JavaScript, and potentially meta tags for the module. |
| `displayProductAdditionalInfo` (or similar product page hook) | On the product page, typically below the product description or add-to-cart button. | Display the product-specific upload form or button. |
| `displayShoppingCartFooter` (or similar cart page hook) | On the shopping cart summary page. | Display the cart-wide upload form or file list. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Display the post-purchase upload form. |
| `displayCustomerAccount` | In the customer’s “My Account” dashboard. | Add a link or block to the “My Files” section. |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | In the customer’s “My Account” dashboard. | Add a link or block to the “My Files” section. |
| `displayRightColumn` / `displayLeftColumn` | In the side columns of the store. | Display a general “Upload Files” button/link if configured. |
| `displayFooter` | In the footer of every page. | Display a general “Upload Files” button/link if configured. |
| `actionValidateOrder` | After an order has been successfully validated. | Potentially used to link uploaded files to the newly created order ID or trigger admin notifications. |
| `actionProductUpdate` / `actionProductAdd` | When a product is updated or added. | Could be used to manage product-specific file requirements or clean up associated files. |
| `actionCustomerAccountAdd` | When a new customer account is created. | (Less likely for this module, but possible for initial setup). |
| `actionAdminOrdersView` | When an administrator views an order in the Back Office. | Inject the module’s file management section into the order detail page. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Customer Files Upload” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions perfectly and helps you maximize your store’s potential.
