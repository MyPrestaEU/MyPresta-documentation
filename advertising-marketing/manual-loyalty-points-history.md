---
title: "Manual Loyalty Points & History - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Manual Loyalty Points & History PrestaShop module by MyPresta.eu."
sidebar:
  label: "Manual Loyalty Points & History - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Manual Loyalty Points & History Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Manual Loyalty Points & History

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). This module also requires the main PrestaShop loyalty system (e.g., `myprestaloyalty` or the default PrestaShop loyalty module) to be installed and active, as it extends its functionality.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the module, where you can set up global preferences.

- **Enable Email Notifications for Manual Point Changes:**
  - **What this setting does:** Controls whether customers receive an email notification when their loyalty points are manually adjusted by an administrator.
  - **Effect of changing this setting:**
    - *When enabled (YES):* After you manually add or subtract points for a customer, an email will be sent to their registered email address, informing them of the change and their new balance.
    - *When disabled (NO):* No email notifications will be sent to customers for manual point adjustments.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this to keep customers fully informed and engaged with their loyalty program. If a customer receives points as compensation, an email notification confirms the action and reinforces your customer service. If disabled, customers might not immediately realize their balance has changed.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 Manual Loyalty Points Management (Back Office > Modules > Manual Loyalty Points)

This is the core screen where you will manage and log all manual loyalty point adjustments. You can find this screen by navigating to **Modules > Manual Loyalty Points** in your PrestaShop Back Office menu.

This screen presents a list of all historical manual loyalty point adjustments. You can also add new adjustments from here.

**Available Actions & Settings:**

- **“Add new loyalty points adjustment” Button:**

  - **What this button does:** Clicking this button takes you to a form where you can manually add or subtract loyalty points for a specific customer.
  - **Effect of clicking this button:** Opens a new form to create a new loyalty point entry.
- **Loyalty Points Adjustment Form (Accessed via “Add new loyalty points adjustment”):**

  - **Customer Search Field:**

    - **What this field does:** Allows you to search for and select the customer whose loyalty points you wish to adjust. Start typing the customer’s name or email, and a list of matching customers will appear.
    - **Effect of changing this setting:** Once a customer is selected, the adjustment will be applied to their account.
    - **Recommended value:** Select the correct customer.
    - **Merchant scenario / example:** You need to add points for “John Doe”. Type “John” and select him from the dropdown.
  - **Points to Add/Subtract Field:**

    - **What this field does:** This is where you enter the number of loyalty points to adjust.
    - **Effect of changing this setting:**
      - *Positive number (e.g., 50):* Adds 50 points to the customer’s loyalty balance.
      - *Negative number (e.g., -25):* Subtracts 25 points from the customer’s loyalty balance.
    - **Recommended value:** The exact number of points you intend to add or subtract.
    - **Merchant scenario / example:** A customer received a damaged item, so you add “100” points as compensation. Another customer returned an item for which they earned points, so you subtract “-50” points.
  - **Validity Period (Days) Field:**

    - **What this field does:** Defines how many days the manually added points will be valid from the date of adjustment. After this period, the points will expire.
    - **Effect of changing this setting:**
      - *Set to a number (e.g., 365):* Points will expire after 365 days.
      - *Set to 0 or empty:* Points will have no expiration date (or follow the default expiration of your main loyalty module, if any).
    - **Recommended value:** Consider your loyalty program’s overall strategy. If you want to encourage quick redemption, set a shorter period. For general goodwill, a longer period or no expiration might be better.
    - **Merchant scenario / example:** You give 50 points as a birthday gift, valid for “30” days to encourage a quick purchase. For a major compensation, you might leave it empty for no expiration.
  - **Reason / Comment Field:**

    - **What this field does:** A text field to record the reason for the loyalty point adjustment. This is for internal tracking and auditing.
    - **Effect of changing this setting:** This text will be saved in the loyalty log, providing a clear history of why the points were adjusted. It is not visible to the customer.
    - **Recommended value:** Always provide a clear and concise reason.
    - **Merchant scenario / example:** “Compensation for damaged product #12345”, “Birthday gift for VIP customer”, “Points for offline event participation”.
  - **“Save” Button:**

    - **What this button does:** Applies the loyalty point adjustment to the customer’s account and saves the entry in the history log.
    - **Effect of clicking this button:** The customer’s loyalty points are updated, and a new entry appears in the “Manual Loyalty Points Management” table. If email notifications are enabled, the customer receives an email.
- **Loyalty Points History Table:**

  - **What this table does:** Displays a chronological list of all manual loyalty point adjustments made through this module.
  - **Columns:**
    - **ID:** Unique identifier for the log entry.
    - **Customer:** The name of the customer whose points were adjusted.
    - **Points:** The number of points added or subtracted.
    - **Validity (Days):** The expiration period set for the points.
    - **Reason:** The internal comment provided for the adjustment.
    - **Date Add:** The date and time the adjustment was made.
    - **Admin:** The name of the administrator who made the adjustment.
  - **Effect of changes:** This table provides a complete audit trail. You can sort and filter entries to review past adjustments.

**Recommended workflow for daily store management:**

1. When a situation arises requiring manual point adjustment (e.g., customer complaint, special promotion), navigate to **Modules > Manual Loyalty Points**.
2. Click “Add new loyalty points adjustment”.
3. Search for and select the customer.
4. Enter the number of points (positive for adding, negative for subtracting).
5. Set a validity period if desired.
6. Crucially, add a clear “Reason / Comment” for future reference.
7. Click “Save”.
8. Review the history table to confirm the entry.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Email Notifications | YES | Send email to customer on manual point changes. |
| Manual Loyalty Points | Customer Search | N/A | Select customer for point adjustment. |
| Manual Loyalty Points | Points to Add/Subtract | N/A | Enter positive or negative value for points. |
| Manual Loyalty Points | Validity Period (Days) | Empty (No Expiration) | Set expiration for manually added points. |
| Manual Loyalty Points | Reason / Comment | N/A | Internal note for audit trail. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I added points, but the customer says they didn’t receive an email.**
A: First, check if “Enable Email Notifications for Manual Point Changes” is set to YES in the module’s configuration. If it is, check your store’s email logs (if available) or your server’s mail logs to see if the email was sent. Also, advise the customer to check their spam or junk folder. Ensure your PrestaShop email settings are correctly configured and sending emails successfully.

**Q: The customer’s loyalty points balance didn’t update after I added points.**
A: This module updates the core PrestaShop loyalty system. If the balance isn’t showing, first clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache). If the issue persists, ensure your main loyalty module (e.g., the default PrestaShop loyalty module or `myprestaloyalty`) is correctly installed and active, as this module relies on it.

**Q: Can I edit a loyalty point adjustment after I’ve saved it?**
A: No, for auditing and data integrity, individual loyalty point adjustments cannot be edited once saved. If you made a mistake, you should add a *new* adjustment to correct it (e.g., if you accidentally added 100 points instead of 50, add a new entry subtracting 50 points) and clearly note the correction in the “Reason / Comment” field.

**Q: What happens if I subtract more points than a customer has?**
A: The system will typically allow the subtraction, resulting in a negative loyalty point balance for the customer. This might be useful in specific scenarios, but generally, you should ensure customers have sufficient points before subtracting.

**Q: How do I know who made a specific point adjustment?**
A: The “Admin” column in the “Manual Loyalty Points Management” history table clearly shows which administrator account made each adjustment, providing a full audit trail.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `Manual Loyalty Points & History` module (myprestaloyalty\_manual) is designed as a standard PrestaShop module, extending the core loyalty functionality. It primarily operates within the Back Office, providing an administrative interface for manual point adjustments and logging. It leverages PrestaShop’s MVC pattern for its admin controller and uses an `ObjectModel` for persistent storage of manual log entries. The module integrates with the existing loyalty system by directly manipulating customer loyalty points.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: This module does not include any dedicated front-office controllers. All customer-facing loyalty point display is handled by the main loyalty module.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Class name & parent class**: `AdminMyprestaloyaltyManualController` extends `ModuleAdminController`.
    - **Responsibility**: This is the primary administrative controller for managing manual loyalty point adjustments. It handles the display of the loyalty log list (using `HelperList`) and the form for adding new adjustments (using `HelperForm`). It processes form submissions, validates data, creates `MyprestaloyaltyManualLog` objects, and updates the customer’s loyalty points. It also triggers email notifications if enabled.
    - **Tab name**: “Manual Loyalty Points” (under Modules menu).
    - **Managed entity**: `MyprestaloyaltyManualLog` (the log of manual adjustments).
  - `controllers/admin/index.php`

    - **Responsibility**: This is an empty placeholder file, often included in PrestaShop module `controllers/admin` directories to prevent directory listing. It does not contain any functional controller logic.

### 4.3 Core Classes & Models (`classes/`)

- `classes/index.php`

  - **Responsibility**: Empty placeholder file to prevent directory listing.
- `classes/MyprestaloyaltyManualLog.php`

  - **What database table it interacts with**: `ps_myprestaloyalty_manual_log`
  - **Extends `ObjectModel`**: Yes.
  - **`$definition` fields**:
    - `id_myprestaloyalty_manual_log`: Primary key.
    - `id_customer`: ID of the customer affected.
    - `points`: Number of points adjusted (can be positive or negative).
    - `validity`: Validity period in days for the points.
    - `reason`: Textual reason for the adjustment.
    - `id_employee`: ID of the administrator who made the adjustment.
    - `date_add`: Timestamp of when the entry was added.
  - **Key public methods and business logic encapsulated**:
    - Standard `ObjectModel` methods (`add`, `update`, `delete`).
    - Handles data validation for its fields.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files. Standard PrestaShop JS for form handling and AJAX (e.g., customer search) is utilized.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. It relies on PrestaShop’s default Back Office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. It relies on PrestaShop’s default `HelperList` and `HelperForm` templates for its Back Office interface.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_myprestaloyalty_manual_log`:
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Configuration Records (in `ps_configuration`)**:

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Stores the boolean value (0 or 1) for enabling/disabling email notifications.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office. | Used to include module-specific CSS/JS (though this module has none) or to register admin menu items. |
  | `actionCustomerAccountAdd` | After a new customer account is created. | Not explicitly used by this module, but a common loyalty hook. |
  | `actionValidateOrder` | After an order has been successfully validated. | Not explicitly used by this module, but a common loyalty hook. |
  | `actionObjectCustomerUpdateAfter` | After a customer object is updated. | Not explicitly used by this module. |
  | `actionObjectCustomerDeleteAfter` | After a customer object is deleted. | Not explicitly used by this module. |

  *Note: The module’s primary functionality (adding/subtracting points) is triggered directly from its Admin Controller, not via front-office hooks. The module interacts with the core loyalty system’s methods to adjust points.*

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Manual Loyalty Points & History” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the module’s functionality.
