---
title: "Loyalty points – Customer overview & points management - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Loyalty points – Customer overview & points management PrestaShop module by MyPresta.eu."
sidebar:
  label: "Loyalty points – Customer overview & points management - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Loyalty points – Customer overview & points management Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Loyalty points – Customer overview & points management

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and are typically available on all compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration page for the “Loyalty points – Customer overview & points management” module. This screen provides general settings for the module’s behavior.

#### Enable Manual Email Notification

- **What this setting does:** This switch controls whether an email notification is sent to the customer when you manually adjust their loyalty points.
- **Effect of changing this setting:**
  - *When enabled:* If you manually add or remove points for a customer, they will receive an email informing them of the change and their new balance. This helps keep customers informed and builds transparency.
  - *When disabled:* Manual point adjustments will occur silently, without any email notification to the customer. This might be preferred for minor internal corrections or if you manage customer communication through other channels.
- **Recommended value:** YES
- **Merchant scenario / example:** You’ve just added 50 bonus points to a customer’s account as a birthday gift. If this setting is enabled, the customer immediately receives an email saying, “Happy Birthday! We’ve added 50 loyalty points to your account. Your new balance is X points.” This enhances the customer experience and makes the reward tangible.

### 2.2 Dedicated Admin Screens & Controller Views

#### Customer Loyalty Points Management (Back Office > Catalog > Loyalty Points)

This is the core management screen for the module, accessible via a new menu item in your PrestaShop back office.

- **Screen Name & Menu Location:** **Catalog > Loyalty Points** (or similar, depending on your PrestaShop version and menu customization).
- **Available Actions & Settings:**
  - **Customer List:** You’ll see a comprehensive list of all your customers, along with their current loyalty point balances.
  - **Search & Filter:** Easily find specific customers by name, email, or ID.
  - **View History:** For each customer, you can click to view a detailed log of all loyalty point transactions (earned, spent, expired, and manually adjusted).
  - **Add/Remove Points:**
    - Click on a customer’s row or an “Edit” icon to access their individual point management interface.
    - You’ll find fields to manually add or subtract a specific number of loyalty points.
    - A “Reason” field allows you to note why the adjustment was made (e.g., “Birthday bonus,” “Compensation for delayed order,” “Point correction”). This reason is crucial for your internal records and for customer service.
    - Upon saving, the customer’s balance is updated, and if the “Enable Manual Email Notification” setting is active, an email is sent.
  - **Pagination:** Standard PrestaShop pagination (`PS_LIST_LIMIT`) will apply, allowing you to control how many customers are displayed per page.
- **Effect of changes:**
  - **Adding Points:** Increases the customer’s loyalty point balance. This can be used to reward customers, offer compensation, or run special promotions.
  - **Removing Points:** Decreases the customer’s loyalty point balance. This might be necessary to correct errors, revoke points from returned orders, or manage fraudulent activity.
  - **Viewing History:** Provides a transparent audit trail of all point movements, invaluable for customer support and internal reporting.
- **Recommended workflow for daily store management:**
  1. **Regularly check customer point balances:** Especially after promotions or if customers report discrepancies.
  2. **Use the “Reason” field diligently:** Always provide a clear, concise reason for any manual adjustment. This will save you time and confusion later when reviewing history or explaining changes to customers.
  3. **Leverage email notifications:** For positive adjustments (bonuses, rewards), enabling email notifications can significantly boost customer satisfaction and awareness of their loyalty benefits. For corrections, consider if an email is necessary or if internal notes suffice.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Manual Email Notification | YES | Controls whether customers receive an email when their loyalty points are manually adjusted. |
| Catalog > Loyalty Points | Customer List & Search | N/A | Displays all customers and their current loyalty point balances. |
| Catalog > Loyalty Points | Add/Remove Points | N/A | Allows manual adjustment of a customer’s loyalty points. |
| Catalog > Loyalty Points | Reason for Adjustment | N/A (Required Input) | Provides an internal note for why points were added or removed. |
| Catalog > Loyalty Points | View History | N/A | Shows a detailed log of all loyalty point transactions for a specific customer. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve added points, but the customer says they haven’t received an email.**
A: First, check if “Enable Manual Email Notification” is set to YES in the module’s main configuration. If it is, check your store’s email logs (if available) or your server’s mail logs to see if the email was sent. Also, advise the customer to check their spam/junk folder. Ensure your PrestaShop email settings are correctly configured and your mail server is functioning.

**Q2: I can’t find the “Loyalty Points” menu item in my Back Office.**
A: After installation, the module should create a new menu item, typically under “Catalog” or “Customers.” If it’s missing, try clearing your PrestaShop cache (Advanced Parameters > Performance > Clear cache). If it still doesn’t appear, ensure the module is enabled and installed correctly. Also, check your user permissions in **Advanced Parameters > Team > Profiles** to ensure your admin profile has access to the module’s controller.

**Q3: The customer’s loyalty point balance isn’t updating on the front office after I make a manual change.**
A: This is usually a caching issue. Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache). If you use a third-party caching module or CDN, clear its cache as well. The module updates the database directly, so the front office should reflect changes once caching is refreshed.

**Q4: Can I import/export loyalty point data with this module?**
A: This module focuses on manual management and viewing within the PrestaShop back office. It does not include built-in import/export functionalities for bulk data operations. For such tasks, you might need to consider custom database queries or other specialized modules.

**Q5: What happens if I uninstall this module?**
A: Upon uninstallation, the module will remove its dedicated admin menu items and potentially its configuration settings. However, it is designed to manage existing loyalty points, which are typically part of PrestaShop’s core loyalty system or another loyalty module. The points themselves should remain in the database, but you would lose the convenient management interface provided by this module. Always back up your database before uninstalling any module.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Loyalty points – Customer overview & points management” module (`myprestaloyalty_customerpoints`) is built following PrestaShop’s MVC pattern, primarily extending `Module` for its core functionality and `AdminController` for its dedicated back-office interface. It interacts with PrestaShop’s core loyalty system (or a compatible loyalty module) by providing an enhanced management layer. The module introduces a custom `ObjectModel` to log manual point adjustments, ensuring an audit trail.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not include any dedicated front-office controllers. All customer-facing interactions regarding loyalty points are handled by PrestaShop’s core loyalty module or the theme itself.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
    - **Class name & parent class**: `AdminMyprestaloyaltyCustomerPointsController` extends `ModuleAdminController`.
    - **Responsibility**: This is the primary back-office controller for managing customer loyalty points. It provides the list view of customers with their loyalty balances, allows searching and filtering, and handles the form for manually adding/removing points for individual customers. It manages the `customer_points` entity (though it primarily interacts with existing loyalty point data, it also logs manual changes via `MyprestaloyaltyCustomerPointsManualLog`).
    - **Tab name**: “Loyalty Points” (or similar, dynamically set during installation).
    - **Managed entity**: It displays and allows modification of customer loyalty points, logging these changes.
  - `controllers/admin/index.php`
    - **Class name & parent class**: This file typically serves as a placeholder or a simple redirect in PrestaShop modules. It might contain a basic `die()` statement or a redirect to prevent direct access, ensuring that the controller logic is executed through PrestaShop’s dispatching mechanism. It does not manage a specific entity or provide a distinct view.

### 4.3 Core Classes & Models (`classes/`)

- `classes/MyprestaloyaltyCustomerPointsManualLog.php`
  - **Class name**: `MyprestaloyaltyCustomerPointsManualLog` extends `ObjectModel`.
  - **Database table**: `_myprestaloyalty_customer_points_manual_log` (or similar, prefixed by `_DB_PREFIX_`).
  - **`$definition` fields**:
    - `id_myprestaloyalty_customer_points_manual_log`: Primary key.
    - `id_customer`: The ID of the customer whose points were adjusted.
    - `id_employee`: The ID of the employee who made the adjustment.
    - `points_change`: The number of points added or removed (can be positive or negative).
    - `reason`: A text field explaining the reason for the adjustment.
    - `date_add`: Timestamp of when the adjustment was made.
  - **Key public methods and business logic**: This class is responsible for persisting the details of every manual loyalty point adjustment made through the back-office interface. It provides a historical record, crucial for auditing and customer support.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All interactions on the back-office management screen are handled by PrestaShop’s default jQuery and form submission mechanisms.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. It relies on PrestaShop’s default back-office styling for its configuration forms and list views, ensuring a consistent look and feel.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not include any custom Smarty template files. The configuration form and the admin list/edit views are rendered using PrestaShop’s default `getContent()` and `ModuleAdminController` templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_myprestaloyalty_customer_points_manual_log`:
    - `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `points_change` INT(11) NOT NULL
    - `reason` TEXT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
    - KEY `id_customer` (`id_customer`)
    - KEY `id_employee` (`id_employee`)
  - **Configuration Records (in `ps_configuration`)**:
    - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Stores the boolean value for enabling/disabling email notifications for manual point adjustments.
- **Registered Hooks Table**:
  This module primarily provides back-office functionality and does not register any front-office display hooks (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent`, etc.) or action hooks (`actionValidateOrder`, `actionProductUpdate`, etc.) in its core `install()` method. Its integration is through the `AdminController` and direct database interaction for logging.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Loyalty points – Customer overview & points management” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
