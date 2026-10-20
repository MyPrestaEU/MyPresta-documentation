---
title: "Gift Cards - sell voucher codes - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Gift Cards - sell voucher codes PrestaShop module by MyPresta.eu."
sidebar:
  label: "Gift Cards - sell voucher codes - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Gift Cards - sell voucher codes Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Gift Cards - sell voucher codes

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Gift Cards - sell voucher codes” module provides several configuration screens to manage your gift cards effectively.

### 2.1 Module Main Configuration Page (Back Office > Modules > Module Manager > Configure Gift Cards - sell voucher codes)

This is the primary configuration screen for the module, where you set up general behavior and access other management sections.

- **What this setting does:** This section typically contains global settings for the module, such as enabling/disabling features, linking to other management screens, and potentially setting default behaviors for gift cards.
- **Effect of changing this setting:** Changes here will affect how gift cards are displayed, purchased, and managed across your entire store.
- **Recommended value:** Review each option carefully. Generally, enable features you intend to use and follow the module’s default recommendations unless you have a specific reason to change them.
- **Merchant scenario / example:** You might find a setting here to enable a dedicated “Gift Cards” link in your store’s footer. Enabling this would make it easier for customers to find and purchase gift cards.

### 2.2 Gift Card Groups Management (Back Office > Gift Cards > Gift Card Groups)

This screen allows you to define different categories or groups for your gift cards. Think of these as templates or types of gift cards you want to offer.

- **Screen Name & Menu Location:** **Back Office > Gift Cards > Gift Card Groups**
- **Available Actions & Settings:**
  - **Listing Table:** Displays all existing gift card groups. You’ll see columns like Group Name, Value, Status (active/inactive), and actions (Edit, Delete).
  - **Add New Gift Card Group:** Click this button to create a new type of gift card.
    - **Group Name:** (e.g., “Birthday Gift Card”, “Christmas Voucher”, “Any Occasion Gift Card”)
      - *What this setting does:* This is the internal name for your gift card group. It helps you organize and identify different types of gift cards in the back office.
      - *Effect of changing this setting:* Only affects your back office organization.
      - *Recommended value:* Descriptive and clear.
    - **Value:** (e.g., “25.00”, “50.00”, “100.00”)
      - *What this setting does:* This defines the monetary value of the gift card in this group.
      - *Effect of changing this setting:* This is the amount customers will pay for and recipients will receive as credit.
      - *Recommended value:* Common, appealing denominations for your target market.
    - **Active:** (Yes/No switch)
      - *What this setting does:* Controls whether gift cards from this group are available for purchase in your store.
      - *Effect of changing this setting:*
        - *When enabled:* Customers can see and buy gift cards of this value.
        - *When disabled:* Gift cards of this value are hidden from the front office and cannot be purchased.
      - *Recommended value:* YES for active gift cards you want to sell.
    - **Other fields:** May include options for validity period, minimum purchase for redemption, or specific product restrictions.
      - *What this setting does:* These fields allow you to fine-tune the conditions under which the gift card can be used.
      - *Effect of changing this setting:* Directly impacts the usability and restrictions of the gift card for the recipient.
      - *Recommended value:* Set according to your business policy (e.g., 1 year validity, no minimum purchase).
- **Effect of changes:** Creating new groups allows you to offer various gift card denominations. Editing groups changes the value or availability of existing gift card types. Deleting a group removes the option to purchase that specific gift card type.
- **Recommended workflow for daily store management:**
  1. Start by creating a few common gift card values (e.g., $25, $50, $100).
  2. As your business grows or for seasonal promotions, add new groups with different values or specific validity periods.
  3. Deactivate groups you no longer wish to sell, rather than deleting them, to preserve historical data.

### 2.3 Gift Card History (Back Office > Gift Cards > Gift Card History)

This screen provides a comprehensive overview of all gift cards that have been purchased and their current status.

- **Screen Name & Menu Location:** **Back Office > Gift Cards > Gift Card History**
- **Available Actions & Settings:**
  - **Listing Table:** Displays a list of all generated gift certificates. Columns typically include:
    - **Voucher Code:** The unique code associated with the gift card.
    - **Original Value:** The initial value of the gift card.
    - **Current Balance:** The remaining balance on the gift card (if partially used).
    - **Recipient Email:** The email address of the person who received the gift card.
    - **Sender Name:** The name of the person who purchased the gift card.
    - **Order ID:** The ID of the order through which the gift card was purchased.
    - **Status:** (e.g., “Pending”, “Active”, “Used”, “Expired”).
    - **Actions:** May include options to view order details, resend the gift card email, or manually adjust the balance (use with caution).
  - **Search and Filter:** Tools to find specific gift cards by code, email, order ID, or status.
- **Effect of changes:** This screen is primarily for monitoring and management. You can track the usage of gift cards, identify outstanding balances, and assist customers with their gift card inquiries.
- **Recommended workflow for daily store management:**
  1. Regularly check this section to monitor gift card sales and redemption.
  2. Use the search function to quickly find a gift card if a customer has a query about its balance or status.
  3. If a customer reports not receiving their gift card email, you can verify its status and potentially resend it from here.

### 2.4 Gift Card Vouchers Management (Back Office > Gift Cards > Gift Card Vouchers)

This screen is dedicated to managing the individual voucher codes generated for each gift card purchase.

- **Screen Name & Menu Location:** **Back Office > Gift Cards > Gift Card Vouchers**
- **Available Actions & Settings:**
  - **Listing Table:** Shows individual gift voucher codes. Columns might include:
    - **Voucher Code:** The unique code.
    - **Associated Gift Card Group:** Which type of gift card this voucher belongs to.
    - **Value:** The value of this specific voucher.
    - **Customer:** The customer associated with the voucher (either sender or recipient).
    - **Date Added/Generated:** When the voucher was created.
    - **Status:** (e.g., “Active”, “Used”, “Expired”).
    - **Actions:** Options to view details, edit (e.g., change status, extend validity), or delete (use with extreme caution as this removes the voucher).
- **Effect of changes:** This screen allows for granular control over individual gift card vouchers. You can manually activate/deactivate vouchers, extend their validity, or even modify their value if necessary (e.g., for customer service issues).
- **Recommended workflow for daily store management:**
  1. Use this screen for advanced management tasks, such as manually issuing a gift card as a goodwill gesture or resolving specific customer issues related to a voucher.
  2. Be cautious when editing or deleting vouchers, as this directly impacts customer credit.
  3. This screen provides a detailed view of each voucher’s lifecycle.

### 2.5 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | *General Settings* | Varies | Global module behavior, display options, and links to other management areas. |
| **Gift Card Groups** | **Group Name** | Descriptive | Internal name for the gift card type. |
|  | **Value** | Common denominations (e.g., $25, $50) | Monetary value of the gift card. |
|  | **Active** | YES | Controls visibility and purchasability of the gift card type. |
|  | *Validity Period* | As per policy | Defines how long the gift card is valid after purchase. |
|  | *Min. Purchase for Redemption* | As per policy | Sets a minimum order value for the gift card to be used. |
| **Gift Card History** | *Voucher Code* | N/A | Unique identifier for each purchased gift card. |
|  | *Current Balance* | N/A | Remaining credit on the gift card. |
|  | *Status* | N/A | Tracks the lifecycle of the gift card (Active, Used, Expired). |
| **Gift Card Vouchers** | *Voucher Code* | N/A | Unique identifier for each generated voucher. |
|  | *Status* | N/A | Tracks the individual voucher’s state. |
|  | *Edit/Delete Actions* | Use with caution | Allows manual modification or removal of individual vouchers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers can’t find the gift cards in my store.**

- **A:** First, ensure that the “Gift Card Groups” you’ve created are marked as “Active” in the Back Office under **Gift Cards > Gift Card Groups**. Second, check your module’s main configuration page (Modules > Module Manager > Configure Gift Cards - sell voucher codes) for options to display links in the header, footer, or columns. If your theme has custom menu management, you might need to manually add a link to the gift card page (usually accessible via a friendly URL like `yourstore.com/gifts`).

**Q2: A customer bought a gift card, but the recipient hasn’t received the email.**

- **A:** Go to **Gift Cards > Gift Card History** in your Back Office. Find the specific gift card by order ID or sender/recipient email. Check its status – it should be “Active” or “Pending” if not yet used. Look for an option to “Resend Email” for that specific voucher. Also, advise the customer to check their spam/junk folder. Ensure your store’s email settings (Advanced Parameters > E-mail) are correctly configured and that your server can send emails reliably.

**Q3: The gift card discount isn’t applying at checkout.**

- **A:** Verify the following:
  1. **Code Entry:** Ensure the customer is entering the correct, full gift card code without typos or extra spaces.
  2. **Validity:** Check the gift card’s status in **Gift Cards > Gift Card History** or **Gift Cards > Gift Card Vouchers**. Is it “Active”? Has it expired? Is there a remaining balance?
  3. **Minimum Purchase:** Does the gift card have a minimum purchase requirement that the current cart total doesn’t meet?
  4. **Product Restrictions:** Are there any product categories or specific products excluded from gift card use? (This would be configured in the Gift Card Group settings).
  5. **Cache:** Sometimes, clearing your PrestaShop cache (Advanced Parameters > Performance) can resolve display or functionality issues.

**Q4: Can I customize the email template for the gift cards?**

- **A:** Yes, the module includes an email template manager. You should find options within the module’s configuration or a dedicated section (e.g., under **Gift Cards > Email Templates**) to edit the content and appearance of the email sent to gift card recipients. This allows you to brand the email and include specific instructions or messages.

**Q5: What happens if a customer’s order total is less than the gift card value?**

- **A:** The module is designed to handle this. If the order total is less than the gift card value, the remaining balance should stay on the gift card, allowing the recipient to use it for future purchases until the balance is depleted or the card expires. You can verify the remaining balance in the **Gift Cards > Gift Card History** section.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Gift Cards - sell voucher codes” module follows a standard PrestaShop MVC (Model-View-Controller) pattern, although it does not explicitly define custom `ObjectModel` classes in the `classes/` directory. Instead, it leverages PrestaShop’s core `CartRule` (voucher) functionality and extends admin capabilities through dedicated `AdminController`s for managing gift card groups, history, and individual vouchers. Front-office interaction is handled by `ModuleFrontController`s, primarily for displaying gift cards and managing user accounts. The module heavily relies on PrestaShop’s configuration system (`Configuration::get()`) for its settings and integrates with various hooks to display content and manage order processes.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/gifts.php`
  - **Class Name & Parent Class**: `GiftcertificateGiftsModuleFrontController` extending `ModuleFrontController`
  - **Responsibility**: This controller is responsible for displaying the main gift cards page in the front office. It fetches available gift card groups and renders them using the `gifts.tpl` template, allowing customers to browse and select gift cards for purchase.
- `controllers/front/index.php`
  - **Class Name & Parent Class**: `GiftcertificateIndexModuleFrontController` extending `ModuleFrontController`
  - **Responsibility**: This is a placeholder or fallback controller, often used to redirect or handle base module routing. In many cases, it might simply redirect to the `gifts.php` controller or serve as a base for other front-office actions.

#### Back-Office Admin Controllers

- `controllers/admin/AdminGiftcertificateGroupController.php`
  - **Tab Name and Managed Entity**: “Gift Card Groups” (under the main “Gift Cards” menu). Manages `gift_group` entities.
  - **Responsibility**: This controller provides the interface for creating, editing, and deleting gift card groups. It handles the form submission for defining gift card values, names, and other group-specific settings. It uses PrestaShop’s `HelperList` and `HelperForm` for rendering the grid and forms.
- `controllers/admin/AdminGiftcertificateHistoryController.php`
  - **Tab Name and Managed Entity**: “Gift Card History” (under the main “Gift Cards” menu). Manages `giftcertlist` entities.
  - **Responsibility**: This controller displays a historical overview of all purchased gift cards. It lists voucher codes, values, recipients, and statuses. It allows administrators to track gift card usage and potentially resend emails. It uses PrestaShop’s `HelperList` for the grid view and interacts with configuration keys like `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` for email-related actions.
- `controllers/admin/AdminGiftcertificateVoucherController.php`
  - **Tab Name and Managed Entity**: “Gift Card Vouchers” (under the main “Gift Cards” menu). Manages `gift_voucher` entities.
  - **Responsibility**: This controller provides detailed management for individual gift card voucher codes. It allows administrators to view, edit (e.g., change status, extend validity), or delete specific vouchers. It uses PrestaShop’s `HelperList` and `HelperForm` for managing individual voucher records.
- `controllers/admin/index.php`
  - **Tab Name and Managed Entity**: N/A
  - **Responsibility**: This file typically serves as a security measure to prevent direct directory listing or access. It usually contains a simple `header('Location: ../../../index.php'); exit;` or similar to redirect to the main PrestaShop admin.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests the module either:

1. Directly manipulates database tables using `Db::getInstance()` without `ObjectModel`s.
2. Relies on PrestaShop’s core `CartRule` (voucher) class for the actual voucher logic, and its own admin controllers manage the “gift card” aspect as a wrapper around `CartRule` creation and management.
3. The main module file (`ajax_giftcertificate.php`) or its included libraries contain the core logic and data handling.

### 4.4 JavaScript Assets (`views/js/`)

- `giftcertificate/js/script.js`
  - **Scope**: Likely Front-office or general module functionality.
  - **Details**: Contains general JavaScript for the module, potentially handling AJAX requests for adding gift cards to the cart, dynamic updates on the gift card page, or front-end form validations.
- `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Scope**: Back-office (Admin).
  - **Details**: Manages the functionality for editing and creating email templates within the module’s configuration. This would include handling form submissions, AJAX calls for saving templates, and potentially rich text editor integrations.
- `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
  - **Scope**: Back-office (Admin).
  - **Details**: Similar to the email template manager, but for PDF templates, likely used for generating printable gift cards. Handles form interactions, saving PDF template designs, and preview functionality.
- `giftcertificate/lib/searchTool/views/js/autocomplete.js`
  - **Scope**: Back-office (Admin).
  - **Details**: Provides autocomplete functionality for search fields within the admin controllers, such as searching for customers or products when creating/editing gift cards or vouchers.
- `giftcertificate/lib/voucherengine/script.js`
  - **Scope**: Likely Front-office or general module functionality.
  - **Details**: Contains JavaScript specific to the voucher generation and redemption logic, potentially interacting with the cart or checkout process to apply gift card discounts.

### 4.5 CSS Stylesheets (`views/css/`)

- `giftcertificate/css.css`
  - **Scope**: General, could be front-office or back-office.
  - **Details**: Contains core styling for the module’s elements, potentially including general layout, button styles, or common components.
- `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Scope**: Back-office (Admin).
  - **Details**: Styles for the email template management interface, ensuring a consistent look within the PrestaShop back office.
- `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
  - **Scope**: Back-office (Admin).
  - **Details**: Styles for the PDF template management interface, similar to the email template manager.
- `giftcertificate/lib/searchTool/views/css/autocomplete.css`
  - **Scope**: Back-office (Admin).
  - **Details**: Styling for the autocomplete search results and input fields.
- `giftcertificate/lib/voucherengine/ps16.css`
  - **Scope**: Front-office (specifically for PrestaShop 1.6 themes).
  - **Details**: Contains compatibility styles for PrestaShop 1.6 themes, addressing potential layout or element differences to ensure proper display of gift card components.
- `giftcertificate/views/css/giftcertificate.css`
  - **Scope**: Front-office (customer-facing).
  - **Details**: Primary stylesheet for the front-office display of gift cards, including the dedicated gift card page, product page elements, and potentially “My Account” section styling. Developers can override these classes in their theme’s `custom.css` or child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
  - **Hook**: `displayAdminOrder`
  - **Output**: Renders information related to gift cards within the PrestaShop order detail page in the Back Office. This might show which gift cards were purchased in the order or which gift cards were used to pay for the order.
- `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
  - **Hook**: `displayMyAccountBlock` (PrestaShop 1.6)
  - **Output**: Adds a link or block to the customer’s “My Account” page, directing them to their purchased gift cards or gift card history.
- `giftcertificate/views/templates/hook/my-account-16.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.6)
  - **Output**: Specific template for adding a link to the “My Account” page for PrestaShop 1.6 themes.
- `giftcertificate/views/templates/hook/my-account-17.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.7+)
  - **Output**: Specific template for adding a link to the “My Account” page for PrestaShop 1.7 and newer themes.
- `giftcertificate/views/templates/hook/my-account.tpl`
  - **Hook**: `displayCustomerAccount` (General/Fallback)
  - **Output**: A general “My Account” link template, potentially used as a fallback or for older versions.

#### Admin templates (`views/templates/admin/`)

- `giftcertificate/views/templates/admin/admin.tpl`
  - **Scope**: General admin configuration.
  - **Output**: Likely the main configuration form for the module, rendered via `getContent()` in the main module file. It might include tabs or sections for various settings.
- `giftcertificate/views/templates/admin/adminOrder.tpl`
  - **Scope**: Admin order view.
  - **Output**: Similar to `displayAdminOrder.tpl` but potentially for a more integrated view within a custom admin order page, if the module overrides or extends it.
- `giftcertificate/views/templates/admin/list/list_action_email.tpl`
  - **Scope**: Admin list views (e.g., Gift Card History).
  - **Output**: A specific action button or link for sending emails, typically found in the action column of a `HelperList` table, allowing admins to resend gift card emails.

#### Front-office templates (`views/templates/front/`)

- `giftcertificate/views/templates/front/gifts.tpl`
  - **Scope**: Dedicated front-office page.
  - **Output**: The main template for displaying the list of available gift cards to customers, rendered by `GiftcertificateGiftsModuleFrontController`.

#### Library Templates (`lib/`)

- `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
  - **Scope**: Back-office (Admin).
  - **Output**: Templates for the email template management interface (e.g., `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/helpers/views/orderStates.tpl`
  - **Scope**: Back-office (Admin).
  - **Output**: A helper template, likely for displaying or selecting order states within module configurations or forms.
- `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
  - **Scope**: Back-office (Admin).
  - **Output**: Templates for the PDF template management interface (e.g., `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/searchTool/views/scripts.tpl`
  - **Scope**: Back-office (Admin).
  - **Output**: Contains JavaScript or Smarty logic related to the search tool, potentially including initialization scripts for autocomplete.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module likely creates custom tables to manage its data, although no explicit `classes/` with `ObjectModel` definitions were found. Based on the Admin Controllers, the following tables are implied:

- `ps_gift_group`: Stores definitions for gift card groups (e.g., value, name, validity, restrictions).
- `ps_giftcertlist`: Stores the history of purchased gift cards, including their unique codes, initial value, current balance, recipient, sender, and associated order.
- `ps_gift_voucher`: Stores details of individual voucher codes, potentially linking to `ps_cart_rule` if it leverages PrestaShop’s native voucher system.

Configuration records stored in `ps_configuration` would include:

- Module-specific settings configured via `getContent()`, such as email template IDs, PDF template IDs, display options, etc.
- `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` are core PrestaShop configurations used by the module for email sending.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS assets, meta tags, or module-specific data. |
| `displayLeftColumn` / `displayRightColumn` | In the left/right column of the front office. | Display a block for gift card promotion or a link to the gift card page. |
| `displayProductAdditionalInfo` / `displayProductButtons` | On the product page. | Potentially display a “Buy a Gift Card” button or related information. |
| `displayFooter` | In the footer section of every page. | Add a link to the gift card page. |
| `displayCustomerAccount` | On the customer’s “My Account” page. | Add a link to the customer’s gift card history/details. |
| `displayMyAccountBlock` | On the customer’s “My Account” page (PrestaShop 1.6 specific). | Add a link to the customer’s gift card history/details. |
| `actionValidateOrder` | After an order has been successfully validated. | Trigger the generation and sending of gift card vouchers when a gift card product is purchased. Update gift card history. |
| `displayAdminOrder` | On the Back Office order detail page. | Display gift card information related to the order (purchased or used). |
| `actionOrderStatusUpdate` | When an order’s status changes. | Potentially activate/deactivate gift cards based on order status (e.g., activate on “Payment Accepted”). |
| `actionFrontControllerSetMedia` | Before a front controller renders its template. | Load front-office specific CSS and JavaScript assets. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its template. | Load back-office specific CSS and JavaScript assets. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you are running the latest, most secure version of the “Gift Cards - sell voucher codes” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely assistance and continuous improvements to our modules.
