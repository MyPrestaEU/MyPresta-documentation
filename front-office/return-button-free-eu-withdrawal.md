---
title: "Return Button Free - EU Withdrawal - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Return Button Free - EU Withdrawal PrestaShop module by MyPresta.eu."
sidebar:
  label: "Return Button Free - EU Withdrawal"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Return Button Free - EU Withdrawal Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Return Button Free - EU Withdrawal

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
This is the main configuration screen for the module, where you control its general behavior and appearance.

#### General Settings Tab

-   **Enable Module:**
    -   **What this setting does:** This is the master switch to activate or deactivate the module's functionality on your store.
    -   **Effect of changing this setting:**
        -   *When enabled:* The withdrawal button and functionality will be active and visible to customers according to your other settings.
        -   *When disabled:* The module's features will be completely hidden from the front office, and customers will not be able to submit withdrawal requests through it.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You would enable this when you're ready to offer the withdrawal option to your customers. You might disable it temporarily during maintenance or if you need to make significant changes to your return policy.

-   **Display Withdrawal Button In:**
    -   **What this setting does:** Determines where the main "Withdrawal Request" button appears on your store's front office.
    -   **Effect of changing this setting:**
        -   *Header:* The button appears in the top section of your website, often globally visible.
        -   *Left Column:* The button appears in the left sidebar (if your theme has one).
        -   *Right Column:* The button appears in the right sidebar (if your theme has one).
        -   *Product Page:* The button appears on individual product pages.
        -   *Footer:* The button appears in the bottom section of your website.
    -   **Recommended value:** Footer (often a good, unobtrusive location for legal links) or Header (for maximum visibility). Choose based on your theme's layout and your preference for prominence.
    -   **Merchant scenario / example:** If you want customers to easily find the option, placing it in the Header or Footer is common. If you prefer it to be less prominent but still accessible, a column might be suitable.

-   **Allow Guest Withdrawal Requests:**
    -   **What this setting does:** Controls whether customers who checked out without creating an account can still submit a withdrawal request.
    -   **Effect of changing this setting:**
        -   *When enabled:* Guests will be able to access the withdrawal form by providing their order reference and email address.
        -   *When disabled:* Only registered customers who are logged into their accounts will be able to submit withdrawal requests.
    -   **Recommended value:** YES (Highly recommended for EU compliance, as the right of withdrawal applies to all consumers, not just registered ones).
    -   **Merchant scenario / example:** Enabling this ensures you comply with consumer rights for all customers, regardless of their checkout method, and avoids frustrating guests who can't find a way to withdraw.

-   **Order States for Withdrawal Eligibility:**
    -   **What this setting does:** Defines which order statuses make an order eligible for a withdrawal request. For example, you might only allow withdrawals for orders that have been "Delivered" or "Shipped."
    -   **Effect of changing this setting:** Customers will only see the withdrawal option for orders that match one of the selected statuses in their order history or when entering a guest order reference.
    -   **Recommended value:** Select statuses like "Payment accepted," "Preparation in progress," "Shipped," "Delivered." Avoid statuses like "Canceled" or "Refunded" as withdrawals are not applicable there.
    -   **Merchant scenario / example:** You want to allow withdrawals for orders that are already processed or delivered, but not for orders that are still pending payment or have already been canceled.

-   **Order States for Withdrawal Confirmation:**
    -   **What this setting does:** Specifies which order status should be automatically applied to an order once a withdrawal request has been successfully submitted by the customer. This helps you quickly identify orders with pending withdrawal requests.
    -   **Effect of changing this setting:** When a customer submits a withdrawal, the order's status will change to the one you select here.
    -   **Recommended value:** Create a new, distinct order status like "Withdrawal Requested" or "EU Withdrawal Pending" in your PrestaShop order statuses settings (under Shop Parameters > Order Settings > Statuses) and select it here.
    -   **Merchant scenario / example:** Setting a specific status like "Withdrawal Requested" allows your customer service team to easily filter and manage orders that require attention for a withdrawal process.

-   **Order States for Withdrawal Completion:**
    -   **What this setting does:** Specifies which order status should be automatically applied to an order once you, the merchant, have processed and completed the withdrawal (e.g., issued a refund).
    -   **Effect of changing this setting:** After you mark a withdrawal request as completed in the module's admin interface, the associated order's status will update to this chosen status.
    -   **Recommended value:** Select an existing status like "Refunded" or create a new one like "EU Withdrawal Completed."
    -   **Merchant scenario / example:** Once you've processed the refund and closed the withdrawal case, updating the order status to "Refunded" provides a clear record for both you and the customer.

-   **Enable Statistics:**
    -   **What this setting does:** Controls whether the module collects anonymous statistics about its usage. This data helps the module developer improve the module.
    -   **Effect of changing this setting:**
        -   *When enabled:* The module will send anonymous usage data.
        -   *When disabled:* No usage data will be sent.
    -   **Recommended value:** YES (Helps improve the module for everyone).
    -   **Merchant scenario / example:** You enable this to contribute to the module's development, or disable it if you have strict data privacy policies that prevent any external data transmission.

#### Legal Information Tab

-   **Withdrawal Period (Days):**
    -   **What this setting does:** Defines the number of calendar days a customer has to exercise their right of withdrawal, starting from the day they receive the goods.
    -   **Effect of changing this setting:** The module will display this period to customers and use it internally for any date calculations or eligibility checks.
    -   **Recommended value:** 14 (This is the minimum legal requirement in the EU, but you can offer a longer period if you wish).
    -   **Merchant scenario / example:** You set this to 14 days to comply with EU law. If you offer a more generous return policy, you might set it to 30 days.

-   **Withdrawal Form Text:**
    -   **What this setting does:** Allows you to customize the introductory text displayed at the top of the withdrawal request form. This is a multi-language field.
    -   **Effect of changing this setting:** The text you enter will appear to customers when they access the withdrawal form.
    -   **Recommended value:** Provide clear, concise instructions or a brief explanation of the withdrawal process.
    -   **Merchant scenario / example:** You might add a message like: "Please fill out this form to exercise your right of withdrawal. You have 14 days from the receipt of your order to submit this request."

-   **Confirmation Email Text:**
    -   **What this setting does:** Allows you to customize the text included in the confirmation email sent to customers after they submit a withdrawal request. This is a multi-language field.
    -   **Effect of changing this setting:** The text you enter will be part of the email customers receive, serving as a durable medium proof of their request.
    -   **Recommended value:** Include important information such as next steps, where to send the goods, and any specific return instructions.
    -   **Merchant scenario / example:** You might write: "Thank you for your withdrawal request. Your request has been received and will be processed shortly. Please return the goods to [Your Return Address] within 14 days. For more details, please refer to our return policy."

-   **Withdrawal Policy Link:**
    -   **What this setting does:** Allows you to provide a link to your store's detailed withdrawal or return policy page.
    -   **Effect of changing this setting:** A link will be displayed on the withdrawal form, directing customers to your full policy.
    -   **Recommended value:** Provide the URL to your dedicated CMS page for returns/withdrawals.
    -   **Merchant scenario / example:** You have a CMS page titled "Returns & Refunds Policy" at `yourstore.com/content/returns-refunds`. You would enter this URL here.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| **General Settings Tab** | Enable Module | YES | Activates/deactivates module functionality. |
| | Display Withdrawal Button In | Footer / Header | Sets location of the main withdrawal button. |
| | Allow Guest Withdrawal Requests | YES | Enables withdrawal for non-registered customers. |
| | Order States for Withdrawal Eligibility | Payment accepted, Shipped, Delivered | Defines which order statuses allow withdrawal requests. |
| | Order States for Withdrawal Confirmation | "Withdrawal Requested" (Custom) | Status applied to order upon customer submission. |
| | Order States for Withdrawal Completion | "Refunded" (Existing) / "EU Withdrawal Completed" (Custom) | Status applied to order upon merchant completion. |
| | Enable Statistics | YES | Allows anonymous usage data collection for module improvement. |
| **Legal Information Tab** | Withdrawal Period (Days) | 14 | Sets the legal period for withdrawal. |
| | Withdrawal Form Text | Customizable | Introductory text on the withdrawal form. |
| | Confirmation Email Text | Customizable | Text included in the withdrawal confirmation email. |
| | Withdrawal Policy Link | Your CMS page URL | Link to your detailed return/withdrawal policy. |

### 2.2 Dedicated Admin Screens & Controller Views

#### Withdrawal Requests (Back Office > Modules > Return Button Free > Withdrawal Requests)
This dedicated administration screen is where you manage all incoming withdrawal requests from your customers.

-   **Screen Name & Menu Location:** **Withdrawal Requests** (found under the main "Modules" menu, then "Return Button Free" submenu).
-   **Available Actions & Settings:**
    -   **Listing Table:** Displays a comprehensive list of all withdrawal requests.
        -   **ID:** Unique identifier for each request.
        -   **Submitted:** Date and time the request was submitted.
        -   **Order:** The associated PrestaShop order reference.
        -   **First name, Last name, Email:** Customer's contact details.
        -   **Scope:** Indicates if it's a full order withdrawal (this free version only supports full order withdrawal).
        -   **Type:** The type of withdrawal (e.g., "EU Withdrawal").
        -   **Status:** The current status of the withdrawal request (e.g., "Pending," "Processed," "Canceled").
    -   **View Details:** Click on any request in the list to open a detailed view.
        -   This view provides all information submitted by the customer, including order details, products, and any additional notes.
        -   You can add internal notes, change the status of the withdrawal (e.g., from "Pending" to "Processed" or "Canceled"), and track the history of changes.
        -   The "Order States for Withdrawal Completion" setting (from the main configuration) will be applied to the associated order when you mark a withdrawal as completed here.
    -   **Filtering and Searching:** You can filter the list by status, customer name, order ID, etc., to quickly find specific requests.
-   **Effect of changes:**
    -   **Changing Status:** Updating the status of a withdrawal request (e.g., to "Processed" or "Completed") will update the record in the module and, if configured, the associated PrestaShop order's status. This helps you track progress and communicate with customers.
    -   **Adding Notes:** Internal notes are for your team's reference and are not visible to the customer. They help in documenting the communication and actions taken for each withdrawal.
-   **Recommended workflow for daily store management:**
    1.  Regularly check the "Withdrawal Requests" screen for new "Pending" requests.
    2.  Click on a request to view its details.
    3.  Review the customer's information and the associated order.
    4.  Communicate with the customer as needed (e.g., provide return shipping instructions).
    5.  Once the goods are received and inspected, process the refund in PrestaShop's order management.
    6.  Update the withdrawal request status in the module to "Processed" or "Completed." This will also update the main order status if you configured "Order States for Withdrawal Completion."
    7.  Add any relevant internal notes about the refund, tracking numbers, or communication.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

-   **Q: The withdrawal button isn't showing up on my store.**
    -   **A:** First, check if the module is "Enabled" in its configuration. Then, verify that you have selected a "Display Withdrawal Button In" location (e.g., Footer, Header). If your theme is heavily customized, it might not be hooking correctly. Try selecting a different display location. Also, ensure your Smarty cache is cleared (Advanced Parameters > Performance > Clear cache).
-   **Q: Customers are submitting withdrawal requests, but the order status isn't changing.**
    -   **A:** Go to the module's configuration and check the "Order States for Withdrawal Confirmation" setting. Ensure you have selected an appropriate order status there. If you created a new status, make sure it's properly configured in PrestaShop (Shop Parameters > Order Settings > Statuses).
-   **Q: Can customers withdraw individual products from an order with this module?**
    -   **A:** No, the free "Return Button Free - EU Withdrawal" module is designed for **full-order withdrawal** only, as per the EU Directive. If you need to handle partial returns for individual products, you would need a more advanced returns management module.
-   **Q: The module is installed, but the text on the form or email is in the wrong language or looks generic.**
    -   **A:** The "Withdrawal Form Text" and "Confirmation Email Text" settings are multi-language fields. Ensure you have entered the desired text for each language enabled in your store. You can switch between languages using the flag icon next to the text area in the module configuration.
-   **Q: I've updated the module, and now something looks off. What should I do?**
    -   **A:** After any module update, it's a good practice to clear your PrestaShop cache. Go to **Advanced Parameters > Performance** and click "Clear cache." If the issue persists, check the module's configuration settings to ensure they are still as you expect.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the "Return Button Free - EU Withdrawal" module, intended for developers and webmasters.

### 4.1 Architecture Overview
The module follows a standard PrestaShop MVC (Model-View-Controller) pattern. It leverages `ModuleFrontController` for front-office interactions and `AdminController` for back-office management. `ObjectModel` is used for persistent data storage related to withdrawal requests. Key services and helper classes encapsulate business logic and ensure compatibility across PrestaShop versions. The module integrates with various PrestaShop hooks to display its functionality.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers
These controllers handle customer-facing interactions related to withdrawal requests.

-   `rbfree/controllers/front/confirm.php`
    *   Class name: `RbfConfirmModuleFrontController` (extends `RbfModuleFrontController`)
    *   Responsibility: Displays the final confirmation step of the withdrawal form, allowing the customer to review and submit their request. Handles the POST submission to create a new `RbfWithdrawal` entry.
-   `rbfree/controllers/front/form.php`
    *   Class name: `RbfFormModuleFrontController` (extends `RbfModuleFrontController`)
    *   Responsibility: Renders the initial withdrawal request form. Handles input validation for order reference, email, and customer details.
-   `rbfree/controllers/front/print.php`
    *   Class name: `RbfPrintModuleFrontController` (extends `RbfModuleFrontController`)
    *   Responsibility: Provides a printable version of the withdrawal request form, typically after submission, for customer records.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Class name: `RbfModuleFrontController` (extends `ModuleFrontController`)
    *   Responsibility: Base class for all front-office controllers of the module, providing common utilities, security checks, and Smarty variable assignments.
-   `rbfree/controllers/front/status.php`
    *   Class name: `RbfStatusModuleFrontController` (extends `RbfModuleFrontController`)
    *   Responsibility: Displays the current status of a specific withdrawal request to the customer.
-   `rbfree/controllers/front/track.php`
    *   Class name: `RbfTrackModuleFrontController` (extends `RbfModuleFrontController`)
    *   Responsibility: Allows customers (including guests) to track their withdrawal request by entering an order reference and email.

#### Back-Office Admin Controllers
These controllers manage the administration interface for withdrawal requests.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Class name: `AdminRbfWithdrawalController` (extends `ModuleAdminController`)
    *   Tab name: "Withdrawal Requests" (under "Modules > Return Button Free")
    *   Managed entity: `RbfWithdrawal`
    *   Responsibility: Provides the CRUD (Create, Read, Update, Delete) interface for managing withdrawal requests. Displays a list of requests, allows viewing detailed information, updating status, and adding notes. Handles form submissions for status changes and notes.

### 4.3 Core Classes & Models (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Class name: `RbfCompatibility`
    *   Responsibility: Provides helper methods for ensuring compatibility across different PrestaShop versions (e.g., handling differences in `Context` or `Tools` methods).
-   `rbfree/classes/RbfSecurity.php`
    *   Class name: `RbfSecurity`
    *   Responsibility: Contains security-related helper methods, such as token generation and validation, to protect forms against CSRF attacks.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Class name: `RbfSelfHeal`
    *   Responsibility: Implements logic for self-healing or diagnostic checks, ensuring module integrity and data consistency.
-   `rbfree/classes/RbfStatsService.php`
    *   Class name: `RbfStatsService`
    *   Responsibility: Handles the collection and submission of anonymous usage statistics if enabled by the merchant.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Class name: `RbfWithdrawal` (extends `ObjectModel`)
    *   Database table: `ps_rbf_withdrawal`
    *   `$definition` fields: Defines the structure of a withdrawal request, including `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd`, etc.
    *   Key public methods: `add()`, `update()`, `delete()`, methods for retrieving withdrawal details, managing status transitions.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Class name: `RbfWithdrawalAttachment` (extends `ObjectModel`)
    *   Database table: `ps_rbf_withdrawal_attachment`
    *   `$definition` fields: Stores information about files attached to a withdrawal request (if the Pro version supports it).
    *   Key public methods: Methods for managing attachments.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Class name: `RbfWithdrawalHistory` (extends `ObjectModel`)
    *   Database table: `ps_rbf_withdrawal_history`
    *   `$definition` fields: Records changes to a withdrawal request's status or other key attributes.
    *   Key public methods: `add()`, methods for retrieving history.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Class name: `RbfWithdrawalNote` (extends `ObjectModel`)
    *   Database table: `ps_rbf_withdrawal_note`
    *   `$definition` fields: Stores internal notes added by administrators to a withdrawal request.
    *   Key public methods: `add()`, methods for retrieving notes.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Class name: `RbfWithdrawalProduct` (extends `ObjectModel`)
    *   Database table: `ps_rbf_withdrawal_product`
    *   `$definition` fields: Stores details of products included in a withdrawal request.
    *   Key public methods: Methods for managing associated products.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Class name: `RbfWithdrawalService`
    *   Responsibility: Encapsulates core business logic for handling withdrawal requests, such as creating new requests, updating order statuses, sending emails, and validating eligibility.

### 4.4 JavaScript Assets (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Scope: Back-office
    *   Details: Manages the interactive selection of order states in the module's configuration, likely for the "Order States for Withdrawal Eligibility/Confirmation/Completion" settings.
-   `rbfree/views/js/front.js`
    *   Scope: Front-office
    *   Details: Contains general front-office JavaScript for the module. This might include form validation, AJAX submissions for withdrawal forms, dynamic content loading, or interactions with the withdrawal button.
-   `rbfree/views/js/order-history.js`
    *   Scope: Front-office (Customer Account > Order History)
    *   Details: Specifically handles the integration of the withdrawal link/button within the customer's order history page, potentially adding event listeners to dynamically show/hide options based on order status.

### 4.5 CSS Stylesheets (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Scope: Back-office (Module Configuration)
    *   Details: Styles for the main module configuration page (`configure.tpl`), ensuring a consistent look within the PrestaShop admin.
-   `rbfree/views/css/admin-dashboard.css`
    *   Scope: Back-office (AdminRbfWithdrawalController dashboard)
    *   Details: Styling for the dashboard view of withdrawal requests, including table layouts, status indicators, and general layout.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Scope: Back-office
    *   Details: Styles for the order state selection interface used in the module's configuration.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Scope: Back-office
    *   Details: Styling for "Pro" version teaser elements within the free module's admin interface.
-   `rbfree/views/css/admin-searchtool.css`
    *   Scope: Back-office
    *   Details: Styles for search and filtering tools within the admin withdrawal list.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Scope: Back-office (AdminRbfWithdrawalController view)
    *   Details: Styling for the detailed view of a single withdrawal request in the admin, including notes, history, and product lists.
-   `rbfree/views/css/front-classic.css`
    *   Scope: Front-office (Classic theme)
    *   Details: Specific styling adjustments for the Classic PrestaShop theme, ensuring visual consistency with the theme's design.
-   `rbfree/views/css/front-hummingbird.css`
    *   Scope: Front-office (Hummingbird theme)
    *   Details: Specific styling adjustments for the Hummingbird PrestaShop theme, ensuring visual consistency with the theme's design.
-   `rbfree/views/css/front.css`
    *   Scope: Front-office
    *   Details: General front-office styling for the withdrawal forms, buttons, and status pages, applied across themes.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook: `displayCustomerAccount` (or similar)
    *   Outputs: A link in the customer's account dashboard for the Classic theme.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook: `displayCustomerAccount` (or similar)
    *   Outputs: A link in the customer's account dashboard for the Hummingbird theme.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (or similar)
    *   Outputs: The main withdrawal button for the Classic theme.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (or similar)
    *   Outputs: The main withdrawal button for the Hummingbird theme.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (or similar)
    *   Outputs: Generic main withdrawal button, used as a fallback or for common elements.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook: `displayOrderDetail` (or similar)
    *   Outputs: A withdrawal link/button within the order detail page for the Classic theme.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook: `displayOrderDetail` (or similar)
    *   Outputs: A withdrawal link/button within the order detail page for the Hummingbird theme.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook: `displayOrderDetail` (or similar)
    *   Outputs: Generic withdrawal link/button within the order detail page.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook: `displayAdminOrder` (or similar)
    *   Outputs: A notice or summary of withdrawal status on the order view page in the Back Office.

#### Admin templates (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Used by: `getContent()` in `rbfree/index.php`
    *   Outputs: The main module configuration form in the Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Used by: `AdminRbfWithdrawalController`
    *   Outputs: The dashboard view listing all withdrawal requests.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Used by: Module configuration
    *   Outputs: The interactive order state selection widget.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Used by: `displayAdminOrder` hook
    *   Outputs: A notice about the withdrawal status on the order view page in the Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Used by: `AdminRbfWithdrawalController`
    *   Outputs: Introductory teaser for the Pro version on the dashboard.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Used by: `AdminRbfWithdrawalController`
    *   Outputs: General Pro version teaser on the dashboard.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Used by: Module configuration
    *   Outputs: Teaser for Pro version features related to exclusions.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Used by: Module configuration
    *   Outputs: Teaser for Pro version features related to order states.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Used by: Module configuration
    *   Outputs: Teaser for Pro version features related to withdrawal scope.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Used by: Various admin sections
    *   Outputs: Generic Pro version teaser.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Used by: Module configuration
    *   Outputs: Displays information about module updates.
-   `rbfree/views/templates/admin/view.tpl`
    *   Used by: `AdminRbfWithdrawalController`
    *   Outputs: The detailed view page for a single withdrawal request in the Back Office.

#### Front-office templates (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Used by: `RbfConfirmModuleFrontController`
    *   Outputs: The second step of the withdrawal form, for confirmation.
-   `rbfree/views/templates/front/error.tpl`
    *   Used by: Various front controllers
    *   Outputs: A generic error message page.
-   `rbfree/views/templates/front/form.tpl`
    *   Used by: `RbfFormModuleFrontController`
    *   Outputs: The initial withdrawal request form.
-   `rbfree/views/templates/front/print.tpl`
    *   Used by: `RbfPrintModuleFrontController`
    *   Outputs: The printable version of the withdrawal form.
-   `rbfree/views/templates/front/status.tpl`
    *   Used by: `RbfStatusModuleFrontController`
    *   Outputs: The page displaying the status of a specific withdrawal request.
-   `rbfree/views/templates/front/success.tpl`
    *   Used by: `RbfConfirmModuleFrontController`
    *   Outputs: A success message after a withdrawal request is submitted.
-   `rbfree/views/templates/front/track.tpl`
    *   Used by: `RbfTrackModuleFrontController`
    *   Outputs: The form for customers to track their withdrawal request.

### 4.7 Database Schema & Hooks Map

#### Database Tables
-   `ps_rbf_withdrawal`: Stores the main withdrawal request details (id, id_order, id_customer, status, dates, customer info).
-   `ps_rbf_withdrawal_attachment`: Stores details of any attachments to a withdrawal request.
-   `ps_rbf_withdrawal_history`: Stores a log of status changes and other updates for each withdrawal request.
-   `ps_rbf_withdrawal_note`: Stores internal notes added by administrators to a withdrawal request.
-   `ps_rbf_withdrawal_product`: Stores details of products included in a withdrawal request.
-   `ps_configuration`: Module settings are stored here with keys like `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS, or render the withdrawal button if configured. |
| `displayLeftColumn` | In the left sidebar of applicable pages. | Render the withdrawal button if configured. |
| `displayRightColumn` | In the right sidebar of applicable pages. | Render the withdrawal button if configured. |
| `displayFooter` | In the footer section of every page. | Render the withdrawal button if configured. |
| `displayProductButtons` | On the product page, near the add-to-cart button. | Render the withdrawal button if configured. |
| `displayCustomerAccount` | In the customer's "My Account" dashboard. | Add a link to the withdrawal form. |
| `displayOrderDetail` | On the customer's order detail page. | Add a link/button to initiate withdrawal for that specific order. |
| `displayAdminOrder` | On the Back Office order view page. | Display a notice or summary of any associated withdrawal request. |
| `actionOrderStatusUpdate` | When an order's status is changed. | Potentially trigger actions like updating withdrawal status or sending notifications. |
| `actionFrontControllerSetMedia` | Before a front controller renders its template. | Enqueue front-office CSS and JavaScript files. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its template. | Enqueue back-office CSS and JavaScript files. |
| `actionModuleInstall` | During module installation. | Create database tables, set default configuration. |
| `actionModuleUninstall` | During module uninstallation. | Remove database tables, delete configuration. |

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Return Button Free - EU Withdrawal" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have regarding the module's functionality.
