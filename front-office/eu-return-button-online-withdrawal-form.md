---
title: "EU Return Button – Online Withdrawal Form - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the EU Return Button – Online Withdrawal Form PrestaShop module by MyPresta.eu."
sidebar:
  label: "EU Return Button – Online Withdrawal Form - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy EU Return Button – Online Withdrawal Form Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# EU Return Button – Online Withdrawal Form

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you control the general behavior and appearance of the return button and form.

#### General Settings Tab

- **Enable Module:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The return button and online withdrawal form become active and visible to customers according to your other settings.
    - *When disabled:* The module is completely deactivated. The button will not appear, and the forms will not be accessible.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You would disable this only if you temporarily want to stop offering online returns, perhaps during maintenance or a policy change.
- **Display Return Button In:**

  - **What this setting does:** Determines where the main “Return” or “Withdrawal” button will appear on your store’s front office. You can select multiple locations.
  - **Effect of changing this setting:**
    - *When selected (e.g., Header):* A button will appear in the chosen location, providing a direct link to the return form.
    - *When unselected:* The button will not appear in that specific location.
  - **Recommended value:** Header and/or Footer for easy access, and Product Page to inform customers upfront.
  - **Merchant scenario / example:** If you want customers to easily find the return option from any page, enable “Header” and “Footer”. If you want to emphasize your return policy on product pages, enable “Product Page”.
- **Button Text:**

  - **What this setting does:** Allows you to customize the text displayed on the return button.
  - **Effect of changing this setting:** The text on the button will change to your specified value.
  - **Recommended value:** “Return Request”, “Online Withdrawal Form”, or “Start a Return”.
  - **Merchant scenario / example:** You might change it from “Return” to “Withdrawal Form” to align with specific legal terminology in your region.
- **Minimum Order Status for Withdrawal:**

  - **What this setting does:** Defines the earliest order status at which a customer can initiate a return request for an order. Orders with a status below this will not be eligible.
  - **Effect of changing this setting:**
    - *When set to “Payment accepted”:* Customers can only request a return once their payment has been successfully processed.
    - *When set to “Shipped”:* Customers can only request a return after their order has been marked as shipped.
  - **Recommended value:** “Payment accepted” or “Shipped”, depending on your policy.
  - **Merchant scenario / example:** If you only accept returns for items that have actually been paid for and processed, set this to “Payment accepted”. If you only accept returns for items that have already left your warehouse, set it to “Shipped”.
- **Maximum Days for Withdrawal:**

  - **What this setting does:** Sets the maximum number of days after an order is placed (or shipped, depending on your policy) during which a customer can submit a return request.
  - **Effect of changing this setting:**
    - *When set to 14:* Customers have 14 days from the order date to request a return. After 14 days, the option will no longer be available for that order.
    - *When set to 30:* Customers have 30 days.
  - **Recommended value:** 14 (for standard EU compliance) or 30 (if you offer an extended return period).
  - **Merchant scenario / example:** To comply with the standard 14-day EU right of withdrawal, set this to 14. If you offer a more generous policy, you can extend it to 30 or more.
- **Allow Guest Withdrawals:**

  - **What this setting does:** Determines whether customers who checked out as guests (without creating an account) can use the online withdrawal form.
  - **Effect of changing this setting:**
    - *When enabled:* Guest customers can access the form by providing their order reference and email address.
    - *When disabled:* Only registered customers who are logged in can initiate a return.
  - **Recommended value:** YES (for maximum customer convenience and EU compliance).
  - **Merchant scenario / example:** Enabling this ensures that all customers, regardless of their checkout method, can easily initiate a return, which is crucial for compliance and customer satisfaction.
- **Allow Attachments:**

  - **What this setting does:** Allows customers to upload files (e.g., photos of damaged products, proof of purchase) when submitting their return request.
  - **Effect of changing this setting:**
    - *When enabled:* An upload field will appear on the form.
    - *When disabled:* Customers cannot upload files.
  - **Recommended value:** YES (especially for products where visual proof might be needed for damage or defects).
  - **Merchant scenario / example:** If you sell fragile items, allowing attachments helps customers quickly provide evidence of damage, speeding up the resolution process.
- **Attachment Max Size (MB):**

  - **What this setting does:** Sets the maximum file size for each attachment a customer can upload.
  - **Effect of changing this setting:** Files larger than this limit will be rejected by the form.
  - **Recommended value:** 2-5 MB.
  - **Merchant scenario / example:** Setting a reasonable limit prevents customers from uploading excessively large files that could slow down your server or email system.
- **Attachment Allowed Extensions (comma separated):**

  - **What this setting does:** Specifies which file types (e.g., jpg, png, pdf) customers are allowed to upload.
  - **Effect of changing this setting:** Only files with these extensions will be accepted.
  - **Recommended value:** jpg, jpeg, png, gif, pdf.
  - **Merchant scenario / example:** Limiting to common image and document formats ensures you receive usable files and prevents malicious uploads.
- **Require Status Message:**

  - **What this setting does:** When you change the status of a return request in the back office, this setting determines if you are required to add a message to the customer.
  - **Effect of changing this setting:**
    - *When enabled:* An input field for a message will be mandatory when updating a return status.
    - *When disabled:* You can change statuses without adding a message.
  - **Recommended value:** YES (for clear communication and audit trails).
  - **Merchant scenario / example:** Enabling this ensures your team always provides a reason or update to the customer when changing the status, improving transparency.

#### Order States Tab

This tab allows you to define the various statuses for return requests and how they interact with your existing PrestaShop order statuses.

- **New Withdrawal Status:**

  - **What this setting does:** Selects the PrestaShop order status that will be assigned to a new return request when it is first submitted by a customer.
  - **Effect of changing this setting:** All new return requests will automatically be marked with this status in your back office.
  - **Recommended value:** Create a new custom order status like “Return Requested” or “Withdrawal Pending” for clear identification.
  - **Merchant scenario / example:** By creating a specific “Return Requested” status, your customer service team can easily filter and identify new return requests that need their attention.
- **Accepted Withdrawal Status:**

  - **What this setting does:** Selects the PrestaShop order status that will be assigned when you, as the merchant, accept a customer’s return request.
  - **Effect of changing this setting:** When you mark a return as “Accepted” in the module, its status will change to this selected order status.
  - **Recommended value:** Create a new custom order status like “Return Accepted” or “Withdrawal Approved”.
  - **Merchant scenario / example:** Once you’ve reviewed a request and approved it, changing its status to “Return Accepted” can trigger an email to the customer with further instructions.
- **Declined Withdrawal Status:**

  - **What this setting does:** Selects the PrestaShop order status that will be assigned when you decline a customer’s return request.
  - **Effect of changing this setting:** When you mark a return as “Declined” in the module, its status will change to this selected order status.
  - **Recommended value:** Create a new custom order status like “Return Declined” or “Withdrawal Rejected”.
  - **Merchant scenario / example:** If a return request falls outside your policy (e.g., past the return window), you would change its status to “Return Declined” and ideally send a message explaining why.
- **Closed Withdrawal Status:**

  - **What this setting does:** Selects the PrestaShop order status that will be assigned when a return request is completed or resolved (e.g., refund issued, replacement sent).
  - **Effect of changing this setting:** When you mark a return as “Closed” in the module, its status will change to this selected order status.
  - **Recommended value:** Create a new custom order status like “Return Completed” or “Withdrawal Closed”.
  - **Merchant scenario / example:** After a refund has been processed, marking the return as “Return Completed” provides a clear audit trail and removes it from your active return queue.
- **Order States to Exclude from Withdrawal:**

  - **What this setting does:** Allows you to select specific PrestaShop order statuses for which customers *cannot* initiate a return request, even if they meet other criteria.
  - **Effect of changing this setting:** Orders with any of the selected statuses will not show the return option to the customer.
  - **Recommended value:** “Canceled”, “Refunded”, “Error”, or any other status that signifies an order is no longer eligible for a new return request.
  - **Merchant scenario / example:** If an order has already been “Refunded,” you wouldn’t want a customer to be able to submit another return request for it.

### 2.2 Dedicated Admin Screens & Controller Views

#### Withdrawal Requests (Back Office > Orders > Withdrawal Requests)

This is the central hub for managing all return and withdrawal requests submitted by your customers.

- **Screen Name & Menu Location:** You can find this screen by navigating to **Orders > Withdrawal Requests** in your PrestaShop back office menu.
- **Available Actions & Settings:**
  - **Listing Table:** Displays a comprehensive list of all return requests, including:
    - **ID:** Unique identifier for the request.
    - **Customer Name:** The customer who submitted the request.
    - **Order Reference:** The associated PrestaShop order.
    - **Date:** When the request was submitted.
    - **Status:** The current status of the request (e.g., “Return Requested”, “Return Accepted”).
    - **Actions:** Buttons to “View” the request details, change its status, or perform other management tasks.
  - **Filtering & Searching:** You can filter the list by status, customer, order reference, and date range to quickly find specific requests.
  - **Bulk Actions:** Allows you to select multiple requests and perform actions like changing their status simultaneously.
  - **View Details:** Clicking “View” for a specific request opens a detailed page where you can:
    - See all customer-provided information (reason, comments, attached files).
    - Review the products included in the return request.
    - View a history of status changes and internal notes.
    - Add private notes for internal team communication.
    - Change the status of the request (e.g., from “Return Requested” to “Return Accepted”).
    - Send messages to the customer (if “Require Status Message” is enabled).
    - Download attachments.
    - Print the withdrawal form.
- **Effect of changes:**
  - **Changing Status:** Updates the status of the return request, which can trigger email notifications to the customer and update the display in their customer account.
  - **Adding Notes:** Records internal communication or decisions related to the request, visible only to back-office users.
  - **Sending Messages:** Communicates directly with the customer regarding their return request.
- **Recommended workflow for daily store management:**
  1. Regularly check the “Withdrawal Requests” list for new requests (status “Return Requested”).
  2. Review each new request, checking the order details, customer comments, and any attachments.
  3. Decide whether to accept or decline the request based on your store’s return policy.
  4. Change the status accordingly (e.g., to “Return Accepted” or “Return Declined”). If “Require Status Message” is enabled, provide a clear message to the customer.
  5. Follow through with the next steps (e.g., issue a refund, arrange for return shipping) and update the status to “Return Completed” once resolved.
  6. Use internal notes for team communication or to record specific actions taken.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Enable Module | YES | Activates/deactivates the entire module. |
|  | Display Return Button In | Header, Footer, Product Page | Controls where the return button appears on the front office. |
|  | Button Text | “Return Request” | Customizes the text on the return button. |
|  | Minimum Order Status for Withdrawal | “Payment accepted” | Sets the earliest order status for return eligibility. |
|  | Maximum Days for Withdrawal | 14 | Defines the return window in days from order date. |
|  | Allow Guest Withdrawals | YES | Allows non-registered customers to use the form. |
|  | Allow Attachments | YES | Enables/disables file uploads on the form. |
|  | Attachment Max Size (MB) | 2-5 MB | Sets the maximum size for uploaded files. |
|  | Attachment Allowed Extensions | jpg, jpeg, png, gif, pdf | Specifies allowed file types for uploads. |
|  | Require Status Message | YES | Makes a message mandatory when changing return status. |
| **Order States Tab** | New Withdrawal Status | “Return Requested” (custom) | Status for newly submitted requests. |
|  | Accepted Withdrawal Status | “Return Accepted” (custom) | Status when merchant approves a request. |
|  | Declined Withdrawal Status | “Return Declined” (custom) | Status when merchant rejects a request. |
|  | Closed Withdrawal Status | “Return Completed” (custom) | Status when a request is fully resolved. |
|  | Order States to Exclude from Withdrawal | “Canceled”, “Refunded” | Prevents returns for orders with these statuses. |
| **Withdrawal Requests (Admin)** | View/Edit Request | N/A | Manage individual return requests, change status, add notes. |
|  | Filter/Search | N/A | Locate specific requests by various criteria. |
|  | Bulk Actions | N/A | Perform actions on multiple selected requests. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The return button isn’t showing up on my store. What should I do?**
A1:

- **Check Module Status:** Go to **Modules > Module Manager**, find “EU Return Button – Online Withdrawal Form”, and ensure it is “Enabled”.
- **Check Display Locations:** In the module’s configuration, under the “General Settings” tab, verify that you have selected at least one “Display Return Button In” location (e.g., Header, Footer).
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, old cached content prevents new module elements from appearing.
- **Theme Compatibility:** While the module is designed for broad compatibility, custom themes might require minor adjustments. If the button still doesn’t appear, contact MyPresta.eu support with details about your theme.

**Q2: Customers are reporting they can’t submit a return for a specific order, even though it’s within the return period.**
A2:

- **Check Minimum Order Status:** In the module’s configuration, under “General Settings”, review “Minimum Order Status for Withdrawal”. Ensure the customer’s order has reached this status. For example, if it’s set to “Shipped” and the order is still “Payment accepted”, they won’t see the option.
- **Check Excluded Order States:** In the module’s configuration, under the “Order States” tab, check “Order States to Exclude from Withdrawal”. If the customer’s order has one of these statuses (e.g., “Canceled”, “Refunded”), they won’t be able to initiate a new return.
- **Maximum Days for Withdrawal:** Double-check the “Maximum Days for Withdrawal” setting. The return window might have expired for that specific order.

**Q3: I changed a setting, but it’s not reflected on the front office.**
A3:

- **Clear Cache:** This is the most common reason. Always clear your PrestaShop cache after making configuration changes in any module. Navigate to **Advanced Parameters > Performance** and click “Clear cache”. If you use a third-party caching module or CDN, clear their caches as well.
- **Browser Cache:** Ask your customers (or yourself) to clear their browser cache or try viewing the page in an incognito/private window to rule out browser-side caching issues.

**Q4: How do I translate the module’s text into other languages?**
A4:

- Go to **International > Translations** in your PrestaShop back office.
- Select “Installed modules translations”.
- Choose your theme, the language you want to translate, and then select “EU Return Button – Online Withdrawal Form” from the module list.
- You will then see a list of all translatable strings within the module, including button text, form labels, and messages. Enter your translations and save.

**Q5: I want to customize the look and feel of the return form to match my theme.**
A5:

- The module includes CSS files (`front-classic.css`, `front-hummingbird.css`, `front.css`) designed for common PrestaShop themes.
- For advanced styling, you’ll need a web developer. They can inspect the module’s HTML structure and override its CSS rules in your theme’s `custom.css` file or by creating a new stylesheet that loads after the module’s CSS. Avoid directly editing the module’s CSS files, as your changes will be lost during updates.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “EU Return Button – Online Withdrawal Form” module (`rbpro`) follows PrestaShop’s standard MVC (Model-View-Controller) architecture. It leverages `ModuleFrontController` for customer-facing interactions and `AdminController` for back-office management. Core business logic is encapsulated in dedicated service and ObjectModel classes, ensuring data integrity and separation of concerns. The module integrates with PrestaShop’s hook system for dynamic content injection and utilizes Smarty for templating. It also includes compatibility layers for different PrestaShop versions and a security class for input validation.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle customer interactions related to the return form and status tracking.

- `rbpro/controllers/front/confirm.php`

  - **Class Name:** `RbpConfirmModuleFrontController` (extends `RbpModuleFrontController`)
  - **Responsibility:** Displays the final confirmation step of the withdrawal form. Processes the submitted form data, creates the `RbpWithdrawal` entry, and redirects to the success or error page. Handles data validation before saving.
- `rbpro/controllers/front/form.php`

  - **Class Name:** `RbpFormModuleFrontController` (extends `RbpModuleFrontController`)
  - **Responsibility:** Renders the main online withdrawal form. Handles initial display of eligible orders/products, processes user selections, and prepares data for the confirmation step. Manages guest access via order reference and email.
- `rbpro/controllers/front/print.php`

  - **Class Name:** `RbpPrintModuleFrontController` (extends `RbpModuleFrontController`)
  - **Responsibility:** Provides a printable version of the withdrawal form or request details. Typically used by customers to include with their returned package.
- `rbpro/controllers/front/RbpModuleFrontController.php`

  - **Class Name:** `RbpModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This is a base class for all front-office controllers within the `rbpro` module. It provides common functionalities like setting up breadcrumbs, handling module-specific assets, and potentially shared security checks or data initialization.
- `rbpro/controllers/front/status.php`

  - **Class Name:** `RbpStatusModuleFrontController` (extends `RbpModuleFrontController`)
  - **Responsibility:** Displays the current status and history of a specific return request to the customer. Accessible via a unique tracking link or from the customer’s account.
- `rbpro/controllers/front/track.php`

  - **Class Name:** `RbpTrackModuleFrontController` (extends `RbpModuleFrontController`)
  - **Responsibility:** Provides a simple interface for customers (especially guests) to enter an order reference and email to track the status of their withdrawal request.

#### Back-Office Admin Controllers

- `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
  - **Class Name:** `AdminRbpWithdrawalController` (extends `ModuleAdminController`)
  - **Tab Name:** “Withdrawal Requests” (under “Orders”)
  - **Managed Entity:** `RbpWithdrawal`
  - **Responsibility:** Manages the listing, viewing, editing, and status updates of all customer withdrawal requests in the PrestaShop back office. Implements `renderList()` for the overview table and `renderForm()` for the detailed view of a single request. Handles actions like changing status, adding notes, and managing attachments.

### 4.3 Core Classes & Models (`classes/`)

- `rbpro/classes/index.php`

  - **Responsibility:** Standard empty `index.php` file to prevent directory listing.
- `rbpro/classes/RbpCompatibility.php`

  - **Responsibility:** Provides static methods to handle compatibility issues across different PrestaShop versions (e.g., `_PS_VERSION_` specific logic, deprecated function replacements). Ensures the module functions correctly from PS 1.6 to 9.x.
- `rbpro/classes/RbpSecurity.php`

  - **Responsibility:** Contains static methods for security-related tasks, such as input validation, sanitization, and potentially CSRF token generation/verification for module-specific forms.
- `rbpro/classes/RbpStatsService.php`

  - **Responsibility:** A service class responsible for collecting and potentially processing statistics related to withdrawal requests (e.g., number of requests, average processing time).
- `rbpro/classes/RbpWithdrawal.php`

  - **Extends:** `ObjectModel`
  - **Database Table:** `rbp_withdrawal`
  - **`$definition` fields:** Defines the structure of a withdrawal request, including fields like `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message`, etc.
  - **Key Public Methods:** Methods for CRUD operations on withdrawal requests, retrieving associated products, history, and notes.
- `rbpro/classes/RbpWithdrawalAttachment.php`

  - **Extends:** `ObjectModel`
  - **Database Table:** `rbp_withdrawal_attachment`
  - **`$definition` fields:** Defines the structure for attachments linked to a withdrawal request, including `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
  - **Key Public Methods:** Methods for managing attachment files (upload, retrieve, delete).
- `rbpro/classes/RbpWithdrawalHistory.php`

  - **Extends:** `ObjectModel`
  - **Database Table:** `rbp_withdrawal_history`
  - **`$definition` fields:** Defines the history of status changes for a withdrawal request, including `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
  - **Key Public Methods:** Methods for logging and retrieving status changes and associated messages.
- `rbpro/classes/RbpWithdrawalNote.php`

  - **Extends:** `ObjectModel`
  - **Database Table:** `rbp_withdrawal_note`
  - **`$definition` fields:** Defines internal notes added by employees to a withdrawal request, including `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
  - **Key Public Methods:** Methods for adding and retrieving internal notes.
- `rbpro/classes/RbpWithdrawalProduct.php`

  - **Extends:** `ObjectModel`
  - **Database Table:** `rbp_withdrawal_product`
  - **`$definition` fields:** Defines the specific products included in a withdrawal request, linking to `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
  - **Key Public Methods:** Methods for managing the list of products within a return request.
- `rbpro/classes/RbpWithdrawalService.php`

  - **Responsibility:** A service layer class that orchestrates complex business logic involving multiple `RbpWithdrawal` related ObjectModels. Examples include creating a new withdrawal request (which involves `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory`), updating its status, sending email notifications, and handling attachments.

### 4.4 JavaScript Assets (`views/js/`)

- `rbpro/lib/searchTool/views/js/autocomplete.js`

  - **Scope:** Back-office (likely for searching orders/customers in admin forms).
  - **Details:** Implements autocomplete functionality for input fields, typically for searching customers or orders when creating/editing withdrawal requests manually in the back office. Binds to `keyup` events and makes AJAX calls to fetch suggestions.
- `rbpro/views/js/admin-order-state-picker.js`

  - **Scope:** Back-office (module configuration and AdminRbpWithdrawalController).
  - **Details:** Enhances the order state selection dropdowns in the module’s configuration and potentially in the withdrawal detail view. May add visual cues or filtering capabilities.
- `rbpro/views/js/front.js`

  - **Scope:** Front-office (withdrawal forms and status pages).
  - **Details:** Handles client-side interactions on the withdrawal form, such as:
    - Dynamic product selection based on order.
    - Validation of form fields before submission.
    - AJAX calls for form submission or data loading.
    - Displaying messages or handling file uploads.
- `rbpro/views/js/order-history.js`

  - **Scope:** Front-office (customer account > order history).
  - **Details:** Integrates the “Request Return” button or link into the customer’s order history page. May use AJAX to check order eligibility or dynamically show/hide the button.

### 4.5 CSS Stylesheets (`views/css/`)

- `rbpro/lib/searchTool/views/css/autocomplete.css`

  - **Scope:** Back-office.
  - **Details:** Styles for the autocomplete dropdowns and search input fields used in the admin panel.
- `rbpro/views/css/admin-config.css`

  - **Scope:** Back-office (module configuration page).
  - **Details:** Styles for the main module configuration form, including tabs, input fields, and general layout.
- `rbpro/views/css/admin-dashboard.css`

  - **Scope:** Back-office (potentially for a module dashboard or statistics view).
  - **Details:** Styles for any custom dashboard elements or statistical displays within the module’s admin interface.
- `rbpro/views/css/admin-order-state-picker.css`

  - **Scope:** Back-office.
  - **Details:** Specific styles for the enhanced order state selection elements in the admin.
- `rbpro/views/css/admin-searchtool.css`

  - **Scope:** Back-office.
  - **Details:** General styles for search tools and filtering components within the admin interface.
- `rbpro/views/css/admin-withdrawal-view.css`

  - **Scope:** Back-office (AdminRbpWithdrawalController detail view).
  - **Details:** Styles for the detailed view of a single withdrawal request, including sections for customer info, products, history, and notes.
- `rbpro/views/css/front-classic.css`

  - **Scope:** Front-office (for Classic theme compatibility).
  - **Details:** Specific styling adjustments for the withdrawal form and buttons to integrate seamlessly with the PrestaShop Classic theme.
- `rbpro/views/css/front-hummingbird.css`

  - **Scope:** Front-office (for Hummingbird theme compatibility).
  - **Details:** Specific styling adjustments for the withdrawal form and buttons to integrate seamlessly with the PrestaShop Hummingbird theme.
- `rbpro/views/css/front.css`

  - **Scope:** Front-office (general styling).
  - **Details:** Core CSS for the front-office withdrawal form, buttons, and status pages, providing a base style that can be overridden by theme-specific stylesheets.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

These templates are rendered when the module is hooked into specific display points.

- `rbpro/views/templates/hook/account-link-classic.tpl`

  - **Hook:** `displayCustomerAccount` (or similar)
  - **Outputs:** A link in the customer’s “My Account” section for the Classic theme, leading to the withdrawal form or tracking page.
- `rbpro/views/templates/hook/account-link-hummingbird.tpl`

  - **Hook:** `displayCustomerAccount` (or similar)
  - **Outputs:** A link in the customer’s “My Account” section for the Hummingbird theme.
- `rbpro/views/templates/hook/button-classic.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (or similar)
  - **Outputs:** The main “Return” or “Withdrawal” button, styled for the Classic theme.
- `rbpro/views/templates/hook/button-hummingbird.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (or similar)
  - **Outputs:** The main “Return” or “Withdrawal” button, styled for the Hummingbird theme.
- `rbpro/views/templates/hook/button.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (or similar)
  - **Outputs:** A generic “Return” or “Withdrawal” button, used as a fallback or base for theme-specific buttons.
- `rbpro/views/templates/hook/order-detail-classic.tpl`

  - **Hook:** `displayOrderDetail` (or similar)
  - **Outputs:** An option or button on the customer’s individual order detail page for the Classic theme, allowing them to initiate a return for that specific order.
- `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

  - **Hook:** `displayOrderDetail` (or similar)
  - **Outputs:** An option or button on the customer’s individual order detail page for the Hummingbird theme.
- `rbpro/views/templates/hook/order-detail.tpl`

  - **Hook:** `displayOrderDetail` (or similar)
  - **Outputs:** A generic option or button on the customer’s individual order detail page.
- `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

  - **Hook:** `displayAdminOrder` (or similar)
  - **Outputs:** A notice or summary of withdrawal requests related to a specific order, displayed within the PrestaShop admin order view.

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office interface.

- `rbpro/lib/searchTool/views/scripts.tpl`

  - **Outputs:** JavaScript and CSS includes for the search tool library, typically included in admin forms that use autocomplete.
- `rbpro/views/templates/admin/configure.tpl`

  - **Outputs:** The main configuration form for the module, rendered by `getContent()` in `index.php`. Contains all the settings described in section 4.1.
- `rbpro/views/templates/admin/dashboard.tpl`

  - **Outputs:** A dashboard or summary view for the module, potentially showing statistics or recent withdrawal requests.
- `rbpro/views/templates/admin/order-state-picker.tpl`

  - **Outputs:** A custom template for selecting order states, used in the module configuration or admin withdrawal view.
- `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

  - **Outputs:** A small widget or notice displayed within the PrestaShop order detail page in the back office, indicating if there’s an active withdrawal request for that order.
- `rbpro/views/templates/admin/updates.tpl`

  - **Outputs:** A template for displaying module update notifications or changelogs within the admin interface.
- `rbpro/views/templates/admin/view.tpl`

  - **Outputs:** The detailed view template for a single withdrawal request, rendered by `AdminRbpWithdrawalController::renderForm()`. Shows all request details, products, history, notes, and status change options.

#### Front-office templates (`views/templates/front/`)

These are standalone page templates for the customer-facing withdrawal process.

- `rbpro/views/templates/front/confirm_step.tpl`

  - **Outputs:** The confirmation step of the withdrawal form, summarizing the customer’s selections before final submission.
- `rbpro/views/templates/front/error.tpl`

  - **Outputs:** A generic error page displayed if something goes wrong during the withdrawal process (e.g., invalid order, technical issue).
- `rbpro/views/templates/front/form.tpl`

  - **Outputs:** The main online withdrawal request form, allowing customers to select orders, products, and provide details.
- `rbpro/views/templates/front/print.tpl`

  - **Outputs:** A printable version of the withdrawal request, typically a simplified layout without navigation.
- `rbpro/views/templates/front/status.tpl`

  - **Outputs:** The page displaying the current status and history of a specific withdrawal request.
- `rbpro/views/templates/front/success.tpl`

  - **Outputs:** A success message page displayed after a withdrawal request has been successfully submitted.
- `rbpro/views/templates/front/track.tpl`

  - **Outputs:** The form where customers can enter their order reference and email to track a withdrawal request.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module creates and manages several custom tables:

- `ps_rbp_withdrawal`: Stores the main withdrawal request details (customer, order, status, reason, etc.).
- `ps_rbp_withdrawal_attachment`: Stores details about files uploaded by customers for a withdrawal request.
- `ps_rbp_withdrawal_history`: Logs all status changes and associated messages for each withdrawal request.
- `ps_rbp_withdrawal_note`: Stores internal notes added by employees to a withdrawal request.
- `ps_rbp_withdrawal_product`: Links specific products from an order to a withdrawal request, including quantity and reason.

Configuration records are stored in `ps_configuration` with keys typically prefixed with `RBP_` (e.g., `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS, display return button (if configured). |
| `displayFooter` | In the footer of every page. | Display return button (if configured). |
| `displayLeftColumn` | In the left column of pages. | Display return button (if configured). |
| `displayRightColumn` | In the right column of pages. | Display return button (if configured). |
| `displayProductButtons` | On the product page, near the add-to-cart button. | Display return button (if configured). |
| `displayCustomerAccount` | On the customer’s “My Account” page. | Add a link to the withdrawal form/tracking. |
| `displayOrderDetail` | On the customer’s individual order detail page. | Add an option to request a return for that order. |
| `displayAdminOrder` | In the PrestaShop back office, on the order detail page. | Display a notice or summary of related withdrawal requests. |
| `actionValidateOrder` | After an order has been successfully validated. | Potentially log order details for future withdrawal eligibility checks. |
| `actionOrderStatusUpdate` | After an order’s status has been changed. | Check if the order status affects withdrawal eligibility or trigger notifications. |
| `actionFrontControllerSetMedia` | Before a front controller renders its content. | Load front-office specific CSS and JavaScript assets. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its content. | Load back-office specific CSS and JavaScript assets. |
| `actionModuleInstall` | During module installation. | Create database tables, set default configuration values. |
| `actionModuleUninstall` | During module uninstallation. | Remove database tables, clean up configuration values. |

## 5. Official Support & Updates

For official updates, technical support, and any questions regarding the “EU Return Button – Online Withdrawal Form” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team and developers are available to assist you with any issues or inquiries.
