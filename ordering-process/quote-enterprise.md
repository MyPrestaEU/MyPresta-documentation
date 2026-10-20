---
title: "Quote Enterprise - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Quote Enterprise PrestaShop module by MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Quote Enterprise Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required. Ensure your server meets PrestaShop’s minimum requirements.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Quote Enterprise)

This is the main configuration screen where you define the core behavior and appearance of the Quote Enterprise module.

#### General Settings Tab

- **Enable Quote Enterprise:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* The quoting system becomes active on your store, and customers can start requesting quotes.
    - *When disabled:* All quoting functionality is hidden from the front office, and no new quotes can be requested. Existing quotes in the back office remain accessible for management.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this when you’re ready to offer quoting services. Disable it temporarily during maintenance or if you decide to stop offering quotes.
- **Allow Quote Requests from Cart:**

  - **What this setting does:** Determines if customers can convert their entire shopping cart into a quote request.
  - **Effect of changing this setting:**
    - *When enabled:* A “Request a Quote” button or link will appear in the shopping cart summary, allowing customers to submit all items in their cart for a quote.
    - *When disabled:* Customers can only request quotes from individual product pages or via the floating button (if enabled), not directly from their cart.
  - **Recommended value:** YES (for most B2B and bulk order scenarios)
  - **Merchant scenario / example:** If you primarily deal with large, multi-item orders where pricing is often negotiated, enable this. If your quotes are usually for single, custom products, you might disable it.
- **Allow Quote Requests from Product Page:**

  - **What this setting does:** Controls whether a “Request a Quote” button appears on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can add a specific product to a quote request directly from its page, instead of adding it to the cart.
    - *When disabled:* The quote request option is removed from product pages.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Essential for custom products, high-value items, or when you want to offer an alternative to direct purchase for any product.
- **Display Floating Quote Button:**

  - **What this setting does:** Adds a persistent, floating button to your store’s front office, allowing customers to initiate a quote request from almost any page.
  - **Effect of changing this setting:**
    - *When enabled:* A small, clickable button (often in a corner of the screen) will appear, opening the quote request form or a list of existing quotes.
    - *When disabled:* The floating button will not be visible.
  - **Recommended value:** YES (for high visibility and ease of access)
  - **Merchant scenario / example:** Use this to make the quoting option highly visible across your store, encouraging more requests.
- **Minimum Order Value for Quote Request:**

  - **What this setting does:** Sets a minimum total value (in your default currency) that a quote request must meet to be submitted.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 100):* Customers cannot submit a quote request if the total value of items in their request is below this amount. An error message will be displayed.
    - *When set to 0 or left empty:* No minimum value is enforced.
  - **Recommended value:** 0 (or a value that filters out trivial requests)
  - **Merchant scenario / example:** If you only want to process quotes for significant orders, set a minimum value (e.g., $500) to reduce administrative overhead for small requests.
- **Default Quote Validity (Days):**

  - **What this setting does:** Defines how many days a newly created quote will be valid for, by default.
  - **Effect of changing this setting:**
    - *When set to a number (e.g., 30):* All new quotes created by your team will automatically have an expiration date 30 days from their creation.
    - *When set to 0 or left empty:* Quotes will not have a default validity period, and your team will need to manually set one or manage them without expiration.
  - **Recommended value:** 30 (or a period typical for your industry)
  - **Merchant scenario / example:** Setting a 30-day validity encourages customers to act within a reasonable timeframe and protects you from fluctuating prices.

#### Email Templates Tab

This section allows you to customize the email notifications sent by the module.

- **Email Template Manager:**
  - **What this setting does:** Provides a visual interface to edit the content of various email templates related to quotes (e.g., new quote request, quote updated, quote accepted).
  - **Effect of changing this setting:**
    - *When you edit a template:* The corresponding email sent to customers or your team will reflect your changes, including text, branding, and layout.
  - **Recommended value:** Customize to match your brand voice and provide clear instructions.
  - **Merchant scenario / example:** Change the “New Quote Request” email to include specific instructions for your sales team or add a personalized greeting for customers.

#### Advanced Settings Tab

- **Enable REST API:**

  - **What this setting does:** Activates a programmatic interface (API) for the module, allowing external systems or custom applications to interact with your quotes.
  - **Effect of changing this setting:**
    - *When enabled:* The module exposes endpoints that can be used by developers to create, read, update, and delete quotes programmatically.
    - *When disabled:* The API is inactive and cannot be accessed.
  - **Recommended value:** NO (unless you have specific integration needs)
  - **Merchant scenario / example:** If you integrate with a CRM, ERP, or a custom mobile app, enabling the API allows these systems to automatically create or update quotes in PrestaShop. Requires developer expertise.
- **API Key Management:**

  - **What this setting does:** Allows you to generate and manage API keys, which are necessary for authenticating requests to the module’s REST API.
  - **Effect of changing this setting:**
    - *When you create a key:* You get a unique identifier that external applications must use to access the API.
    - *When you revoke a key:* Any application using that key will lose access to the API.
  - **Recommended value:** Generate keys only when needed for specific integrations.
  - **Merchant scenario / example:** Create a new API key for your CRM system to push new leads as quote requests into PrestaShop.
- **Cron Job URL for Expiry & Digest:**

  - **What this setting does:** Provides a URL that, when accessed, triggers background tasks like checking quote expirations and sending daily digests to your team.
  - **Effect of changing this setting:**
    - *When configured on your server:* The module will automatically perform these tasks at regular intervals (e.g., daily), ensuring quotes are marked expired and your team receives timely summaries.
    - *When not configured:* Expiry checks and digest emails will not be automated.
  - **Recommended value:** Configure this URL as a daily cron job on your hosting server.
  - **Merchant scenario / example:** Set up a cron job to run this URL once a day to ensure customers are notified of expiring quotes and your sales team gets a daily summary of new requests.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Quotes Management (Back Office > Quote Enterprise > Quotes)

This is the central hub for your sales team to manage all quote requests.

- **Screen Name & Menu Location:** **Quote Enterprise > Quotes**
- **Available Actions & Settings:**
  - **Quote List Table:** Displays all submitted quotes with key information like customer name, status, total value, and creation date.
  - **Filtering & Searching:** Tools to find specific quotes by customer, status, date range, etc.
  - **View/Edit Quote:** Click on any quote to open a detailed view where you can:
    - **Adjust Products & Quantities:** Modify the items, quantities, and prices within the quote.
    - **Add/Remove Products:** Search and add new products to the quote or remove existing ones.
    - **Apply Discounts:** Offer specific discounts on the quote total or individual items.
    - **Set Validity:** Define the expiration date for the quote.
    - **Add Notes/Messages:** Communicate with the customer directly through the quote interface.
    - **Change Status:** Update the quote’s status (e.g., Pending, Sent, Accepted, Rejected, Expired).
    - **Generate PDF:** Create a professional PDF proforma invoice for the customer.
    - **Convert to Order:** With a single click, convert an accepted quote into a standard PrestaShop order, ready for checkout.
    - **Send Email:** Send updated quote details or messages to the customer.
  - **Bulk Actions:** Select multiple quotes to perform actions like changing status, deleting, or exporting.
- **Effect of changes:**
  - Modifying a quote updates its details in the database and can trigger email notifications to the customer.
  - Converting to order creates a new order in PrestaShop’s standard order management system, pre-filled with the quoted items and prices.
  - Changing status updates the customer’s view in their account and can trigger specific email templates.
- **Recommended workflow for daily store management:**
  1. Regularly check the “Quotes” list for new “Pending” requests.
  2. Open each new request, review the items, adjust prices/quantities if necessary, and add any internal notes.
  3. Set a validity period and generate a PDF proforma.
  4. Change the status to “Sent” and email the quote to the customer.
  5. Follow up on “Sent” quotes. If accepted, convert to order. If rejected or expired, update the status accordingly.

#### 2.2.2 Audit Log (Back Office > Quote Enterprise > Audit Log)

This screen provides a detailed history of all actions performed on quotes.

- **Screen Name & Menu Location:** **Quote Enterprise > Audit Log**
- **Available Actions & Settings:**
  - **Log List Table:** Displays a chronological list of events related to quotes, including who performed the action, what action was taken (e.g., “Quote Created,” “Price Changed,” “Status Updated”), and when it occurred.
  - **Filtering:** Filter the log by date, user, or action type to find specific events.
- **Effect of changes:** This is a read-only log; you cannot make changes here. It serves as a historical record.
- **Recommended workflow for daily store management:**
  - Use the audit log to track changes, troubleshoot issues, or review team activity on quotes. It’s invaluable for accountability and understanding the lifecycle of each quote.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Quote Enterprise | YES | Master switch for module functionality. |
|  | Allow Quote Requests from Cart | YES | Adds quote button to cart page. |
|  | Allow Quote Requests from Product Page | YES | Adds quote button to product pages. |
|  | Display Floating Quote Button | YES | Shows a persistent quote button on front office. |
|  | Minimum Order Value for Quote Request | 0 | Sets a minimum value for quote submissions. |
|  | Default Quote Validity (Days) | 30 | Sets default expiration for new quotes. |
|  | Email Template Manager | Customize | Edit email content for various quote events. |
|  | Enable REST API | NO | Activates API for external integrations (developer only). |
|  | API Key Management | N/A | Manage API keys for secure API access (developer only). |
|  | Cron Job URL for Expiry & Digest | Configure | Automates quote expiry checks and team digests. |
| **Quotes Management** | Quote List | N/A | View, filter, and manage all quotes. |
|  | View/Edit Quote | N/A | Adjust items, prices, status, generate PDF, convert to order. |
|  | Bulk Actions | N/A | Apply actions to multiple selected quotes. |
| **Audit Log** | Log List | N/A | Review historical actions on all quotes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My “Request a Quote” buttons aren’t showing up on the front office.**
A:

1. **Check Module Status:** Ensure “Enable Quote Enterprise” is set to YES in the module’s configuration.
2. **Check Specific Settings:** Verify that “Allow Quote Requests from Cart” and “Allow Quote Requests from Product Page” are enabled as needed.
3. **Clear Cache:** Go to **Advanced Parameters > Performance** and clear your PrestaShop cache (Smarty cache, filesystem cache). Sometimes, changes don’t appear until the cache is refreshed.
4. **Theme Compatibility:** If you’re using a custom theme, there might be a compatibility issue. Contact MyPresta.eu support with details of your theme.

**Q: Customers are not receiving quote notification emails.**
A:

1. **Check Email Templates:** In the module configuration, go to the “Email Templates” tab and ensure the templates are correctly configured and saved.
2. **PrestaShop Email Settings:** Verify your general PrestaShop email settings (SMTP, PHP mail) under **Advanced Parameters > E-mail**. Send a test email from there to confirm your store’s mail system is working.
3. **Spam Folders:** Advise customers to check their spam or junk folders.
4. **Cron Job (for digests/reminders):** If it’s about expiry reminders or daily digests, ensure the cron job URL is correctly configured on your server to run regularly.

**Q: Can I customize the appearance of the quote request form or buttons?**
A: Yes, the module uses standard PrestaShop templating. For basic styling changes (colors, fonts), you can often override the module’s CSS in your theme’s custom CSS file. For more complex layout changes, you would need to override the module’s TPL files in your theme. This usually requires a web developer.

**Q: How do I convert an accepted quote into a regular order?**
A: In the PrestaShop Back Office, navigate to **Quote Enterprise > Quotes**. Open the specific quote you want to convert. Within the quote detail view, there will be a button (e.g., “Convert to Order” or “Create Order”). Clicking this will generate a new order in your standard PrestaShop order list, pre-populated with the quoted items and prices.

**Q: What happens if a quote expires?**
A: If the cron job is configured, the module will automatically mark expired quotes as “Expired.” Customers will no longer be able to accept or convert an expired quote to an order. Your sales team can still view expired quotes and potentially reactivate or create a new quote if needed.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Quote Enterprise module follows a robust PrestaShop MVC (Model-View-Controller) architecture, heavily leveraging `ObjectModel` for data persistence. It integrates seamlessly with PrestaShop’s hook system for front-office display and back-office actions. The module includes dedicated admin controllers for managing quotes and audit logs, front controllers for customer interaction (request, list, view, API), and a comprehensive set of helper classes for business logic, PDF generation, email handling, and more. A REST API is also provided for external system integration.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/api.php`
  - Class name: `QuoteenterpriseApiModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Handles API requests from the front-office, likely for specific customer-facing integrations or dynamic content loading.
- `controllers/front/cron.php`
  - Class name: `QuoteenterpriseCronModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Serves as the endpoint for the cron job, triggering background tasks such as checking quote expirations and sending digest emails.
- `controllers/front/index.php`
  - Class name: `QuoteenterpriseIndexModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Likely a fallback or base controller, or handles a default route for the module’s front-office section.
- `controllers/front/list.php`
  - Class name: `QuoteenterpriseListModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Displays a list of quotes for the logged-in customer in their account area.
- `controllers/front/pdf.php`
  - Class name: `QuoteenterprisePdfModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Generates and serves PDF versions of quotes for customers to download.
- `controllers/front/quoteList.php`
  - Class name: `QuoteenterpriseQuoteListModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Similar to `list.php`, potentially an alternative or specific view for quote listings, possibly for AJAX loading.
- `controllers/front/request.php`
  - Class name: `QuoteenterpriseRequestModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Handles the display and submission of the quote request form from product pages, cart, or floating button. Processes form data and creates new quote entries.
- `controllers/front/view.php`
  - Class name: `QuoteenterpriseViewModuleFrontController` (extends `ModuleFrontController`)
  - Responsibility: Displays the detailed view of a single quote for the customer, showing items, prices, status, and messages.

#### Back-Office Admin Controllers

- `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
  - Class name: `AdminQuoteEnterpriseAuditLogController` (extends `ModuleAdminController`)
  - Tab name: Quote Enterprise > Audit Log
  - Managed entity: `quote_audit_log` (likely a custom `ObjectModel` for audit entries)
  - Responsibility: Provides a grid view for administrators to review all historical actions and changes related to quotes.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`
  - Class name: `AdminQuoteEnterpriseQuotesController` (extends `ModuleAdminController`)
  - Tab name: Quote Enterprise > Quotes
  - Managed entity: `quote` (likely a custom `ObjectModel` for quotes)
  - Responsibility: The primary interface for managing quotes, including listing, viewing, editing, converting to order, and sending communications.
- `controllers/admin/index.php`
  - Class name: `QuoteenterpriseAdminIndexModuleFrontController` (extends `ModuleAdminController`)
  - Responsibility: Likely a placeholder or base admin controller, potentially redirecting to the main quotes list or dashboard.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`: Empty file, common practice to prevent directory listing.
- `classes/QuoteAdmin.php`: Contains logic for admin-specific tasks, potentially related to module configuration or general admin utilities.
- `classes/QuoteAdminAjax.php`: Handles AJAX requests originating from the back-office, such as dynamic product search for adding to a quote.
- `classes/QuoteAdminQuoteForm.php`: Manages the complex form logic for editing and creating quotes in the back-office.
- `classes/QuoteApi.php`: Core class for the module’s REST API, handling authentication, routing, and data serialization.
- `classes/QuoteApiDocumentation.php`: Provides methods to generate or display documentation for the module’s API endpoints.
- `classes/QuoteBulkActions.php`: Implements logic for performing actions on multiple selected quotes in the admin list (e.g., bulk status change).
- `classes/QuoteConverter.php`: Handles the crucial logic of converting an accepted quote into a standard PrestaShop order.
- `classes/QuoteDashboard.php`: Provides data and logic for the module’s dashboard view in the back-office (if present), summarizing quote activity.
- `classes/QuoteDuplicator.php`: Logic for duplicating existing quotes.
- `classes/QuoteenterpriseModuleFrontController.php`: Base class for front-office controllers, providing common methods and properties.
- `classes/QuoteExpiry.php`: Manages the logic for checking quote validity, marking quotes as expired, and sending related notifications.
- `classes/QuoteExporter.php`: Handles the export of quote data (e.g., CSV, Excel).
- `classes/QuoteFeeProduct.php`: Likely an `ObjectModel` or helper for managing special “fee” products that can be added to quotes (e.g., for services, custom charges).
- `classes/QuoteListHelper.php`: Provides utility methods for displaying and filtering quote lists in both front and back office.
- `classes/QuoteMailer.php`: Centralized class for sending various email notifications related to quotes.
- `classes/QuoteNotifyDigest.php`: Logic for compiling and sending daily or periodic digests of quote activity to administrators.
- `classes/QuotePdf.php`: Handles the generation of PDF proforma invoices for quotes.
- `classes/QuoteProductHelper.php`: Utility methods for interacting with PrestaShop products within the context of a quote.
- `classes/QuoteQtyHelper.php`: Assists with quantity management and validation within quotes.
- `classes/QuoteQuotesManager.php`: Core business logic for managing quotes, including creation, updates, and status changes.
- `classes/QuoteReference.php`: Manages the generation and uniqueness of quote reference numbers.
- `classes/QuoteRequestHelper.php`: Assists with processing and validating quote requests submitted by customers.
- `classes/QuoteSchema.php`: Defines the database schema for custom tables used by the module (e.g., `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
- `classes/QuoteSettingDescTrait.php`: A PHP trait likely used to provide common descriptions or metadata for module settings.
- `classes/QuoteTaxHelper.php`: Handles tax calculations specific to quotes.
- `classes/QuoteThemeCompat.php`: Contains logic to ensure compatibility with various PrestaShop themes, potentially by detecting theme features or providing overrides.
- `classes/QuoteTimeline.php`: Manages and displays the timeline of events for a specific quote (similar to order history).
- `classes/QuoteValidityHelper.php`: Utility methods for calculating and validating quote expiration dates.
- `classes/QuoteVisibility.php`: Controls the visibility of quote-related elements on the front office (e.g., who can request a quote, where buttons appear).

### 4.4 JavaScript Assets (`views/js/`)

- `lib/emailTemplatesManager/js/emailTemplatesManager.js`: Front-end logic for the email template editor in the back-office.
- `lib/searchTool/views/js/autocomplete.js`: Provides autocomplete functionality for searching products or customers in the back-office quote editor.
- `views/js/admin-audience-picker.js`: Handles logic for selecting customer groups or specific customers for quote visibility or targeting in the admin.
- `views/js/adminQuoteApi.js`: JavaScript for the admin API configuration screen, potentially handling key generation or API documentation display.
- `views/js/adminQuoteDashboard.js`: Scripts for interactive elements or data visualization on the admin dashboard.
- `views/js/adminQuoteDetail.js`: Handles dynamic interactions within the detailed quote view in the back-office (e.g., adding products, applying discounts, status changes).
- `views/js/adminQuoteEditor.js`: Core JavaScript for the back-office quote creation/editing form, including product selection, quantity updates, and price adjustments.
- `views/js/adminQuoteSelector.js`: Used for selecting quotes, possibly in a modal or linked context.
- `views/js/adminQuotesList.js`: Scripts for the admin quotes list, including filtering, sorting, and bulk actions.
- `views/js/front.js`: General front-office JavaScript for the module, handling button clicks, modal pop-ups for quote requests, form submissions, and dynamic updates.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/emailTemplatesManager/css/emailTemplatesManager.css`: Styling for the email template editor in the back-office.
- `lib/searchTool/views/css/autocomplete.css`: Styles for the autocomplete search results (e.g., product search).
- `views/css/admin-audience-picker.css`: Styling for the customer/audience picker interface in the admin.
- `views/css/admin_quoteenterprise.css`: Primary stylesheet for the module’s back-office interfaces (quotes list, detail, audit log).
- `views/css/front-hummingbird.css`: Specific front-office styling adjustments for the PrestaShop “Hummingbird” default theme.
- `views/css/front.css`: General front-office styling for quote buttons, forms, and customer account views. Developers can override classes like `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` in their theme.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `hook/adminOrderQuote.tpl`: Renders a quote-related block within the standard PrestaShop order detail page in the admin.
- `hook/cartQuoteButton.tpl`: Displays the “Request a Quote” button or link on the shopping cart page.
- `hook/customerAccount-hummingbird.tpl`: Renders the quote list link in the customer’s account area for the Hummingbird theme.
- `hook/customerAccount.tpl`: Renders the quote list link in the customer’s account area for classic themes.
- `hook/productListQuote.tpl`: Displays a quote button or option on product list pages (category, search results).
- `hook/quoteFloatButton.tpl`: Renders the persistent floating quote button on the front office.
- `hook/quoteListModal.tpl`: Template for a modal window displaying a list of quotes.
- `hook/quoteRequestButton.tpl`: Displays the “Request a Quote” button on individual product pages.
- `hook/quoteRequestModal.tpl`: Template for the modal window that opens the quote request form.

#### Admin templates (`views/templates/admin/`)

- `admin/api.tpl`: Renders the API configuration and key management interface.
- `admin/audience-picker.tpl`: Template for the customer/group selection tool in the admin.
- `admin/audit.tpl`: Displays the audit log table in the back-office.
- `admin/dashboard.tpl`: Renders the module’s dashboard overview in the back-office.
- `admin/notifications.tpl`: Displays admin notifications related to quotes.
- `admin/quoteDetail.tpl`: The comprehensive template for viewing and editing a single quote in the back-office.
- `admin/quotes.tpl`: Renders the main quotes list table in the back-office.
- `admin/quotesOverview.tpl`: A summary or overview section for quotes, possibly on the dashboard.
- `admin/scopeSelector.tpl`: Template for selecting the scope (e.g., shop, language) in the admin.
- `admin/visibilityConfigurator.tpl`: Template for configuring quote visibility rules.
- `admin/_api_documentation_modal.tpl`: Renders a modal window with API documentation for developers.
- `admin/_bulk_options.tpl`: Template for bulk action dropdowns in admin lists.

#### Front-office templates (`views/templates/front/`)

- `front/list.tpl`: Displays the customer’s list of quotes in their account.
- `front/request.tpl`: The main template for the customer’s quote request form.
- `front/view.tpl`: Displays the detailed view of a single quote for the customer.
- `front/_requestComplianceFields.tpl`: Partial template for additional compliance-related fields in the quote request form.
- `front/_requestLinesTable.tpl`: Partial template for displaying the product lines within a quote request form.

#### PDF templates (`views/templates/pdf/`)

- `pdf/quote.tpl`: Template used to generate the content of the PDF proforma invoice.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module creates custom tables, typically prefixed with `ps_` (or your custom prefix). Key tables include:

- `ps_quote`: Stores the main quote details (customer ID, status, total, validity, reference, etc.).
- `ps_quote_product`: Stores the individual products and their quantities/prices associated with each quote.
- `ps_quote_audit_log`: Records all changes and actions performed on quotes for auditing purposes.
- `ps_quote_api_key`: Stores API keys for external integrations.
- `ps_configuration`: Module settings are stored here with keys like `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injecting CSS/JS assets, meta tags, or global module initialization. |
| `displayRightColumn` | In the right column of your store (if enabled by theme). | Displaying the floating quote button or a static quote request block. |
| `displayLeftColumn` | In the left column of your store (if enabled by theme). | Displaying the floating quote button or a static quote request block. |
| `displayFooter` | In the footer section of every page. | Displaying the floating quote button or a static quote request block. |
| `displayProductButtons` | On the product page, near the “Add to Cart” button. | Displaying the “Request a Quote” button on product pages. |
| `displayShoppingCartFooter` | In the shopping cart summary, below the product list. | Displaying the “Request a Quote” button to convert cart to quote. |
| `displayCustomerAccount` | In the customer’s “My Account” page. | Adding a link to the customer’s list of quotes. |
| `actionValidateOrder` | After an order has been successfully validated. | Potentially used to link a quote to the resulting order or update quote status. |
| `actionAdminControllerSetMedia` | When an admin controller loads its assets. | Injecting module-specific CSS/JS for back-office pages. |
| `displayAdminOrder` | On the PrestaShop admin order detail page. | Displaying a block with quote information if the order originated from a quote. |
| `actionObjectProductUpdateAfter` | After a product is updated. | Potentially to update quote prices if product prices change (advanced feature). |
| `actionObjectProductDeleteAfter` | After a product is deleted. | To handle products removed from quotes. |
| `actionObjectCustomerDeleteAfter` | After a customer is deleted. | To handle quotes associated with a deleted customer. |
| `displayBackOfficeHeader` | In the `<head>` of every back-office page. | General back-office asset injection or global admin module setup. |
| `displayBackOfficeTop` | At the top of the back-office content area. | Displaying module-specific alerts or dashboard widgets. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the Quote Enterprise module.
