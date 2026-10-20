---
title: "Notification about new customer account - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Notification about new customer account PrestaShop module by MyPresta.eu."
sidebar:
  label: "Notification about new customer account - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Notification about new customer account Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Notification about new customer account

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and are usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Notification about new customer account” module. You will be presented with the main configuration screen.

#### **1. Send notification to shop owner about new customer account**

- **What this setting does:** This switch controls whether you, the shop owner, receive an email notification when a new customer registers on your store.
- **Effect of changing this setting:**
  - *When enabled (YES):* Every time a customer successfully creates an account on your store’s front office, an email will be sent to the email address(es) specified in the “Email address(es) for notifications” field below.
  - *When disabled (NO):* You will not receive any email notifications about new customer registrations.
- **Recommended value:** YES.
- **Merchant scenario / example:** You want to be immediately aware of new customer sign-ups to track growth or identify potential leads for a welcome campaign. Enabling this ensures you get that crucial information.

#### **2. Email address(es) for notifications**

- **What this setting does:** This field specifies the email address(es) where the new customer registration notifications will be sent.
- **Effect of changing this setting:**
  - *When set to one or more email addresses:* Notifications will be delivered to these addresses. If you enter multiple addresses, separate them with a comma (e.g., `admin@yourstore.com, support@yourstore.com`).
  - *When left empty:* Even if “Send notification to shop owner” is enabled, no emails will be sent because there’s no recipient.
- **Recommended value:** Your primary store administration email address, or a dedicated team email (e.g., `info@yourstore.com`).
- **Merchant scenario / example:** You want both yourself and your customer support team to receive new registration alerts. You would enter `yourname@yourstore.com, support@yourstore.com` here.

#### **3. Send notification to customer if admin creates new account**

- **What this setting does:** This switch determines whether a welcome email is automatically sent to a customer if their account is manually created by an administrator in the PrestaShop Back Office (e.g., via Customers > Add new customer).
- **Effect of changing this setting:**
  - *When enabled (YES):* When you or another admin creates a new customer account in the Back Office, the newly created customer will automatically receive a welcome email. This email typically includes their login details or a confirmation of their account creation.
  - *When disabled (NO):* Customers whose accounts are manually created in the Back Office will not receive any automatic welcome email from the module. You would need to inform them manually if desired.
- **Recommended value:** YES.
- **Merchant scenario / example:** You frequently create accounts for B2B clients or for customers who call in orders. Enabling this ensures they receive an immediate, professional welcome email without you having to manually compose and send one every time.

#### **4. Save Button**

- **What this does:** After making any changes to the settings above, you must click this button to apply and save your new configuration.
- **Effect of clicking:** Your changes are saved to the database, and the module will begin to operate according to the new settings immediately.
- **Recommended action:** Always click “Save” after modifying any setting.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Send notification to shop owner about new customer account | YES | Controls if shop owner receives email on new customer registration. |
| Module Configuration | Email address(es) for notifications | Your store’s main email | Specifies recipient(s) for owner notifications (comma-separated). |
| Module Configuration | Send notification to customer if admin creates new account | YES | Controls if customer receives welcome email when admin creates their account. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’m not receiving new customer notifications, but the module is enabled. What should I check?**
A1:

- **Check Email Addresses:** Double-check the “Email address(es) for notifications” field in the module configuration. Ensure it’s correctly entered and there are no typos. If multiple, ensure they are comma-separated.
- **Spam Folder:** Check your email’s spam or junk folder. The notifications might be filtered there.
- **PrestaShop Email Settings:** Verify your PrestaShop’s main email settings (Advanced Parameters > E-mail) are correctly configured and sending emails successfully. You can send a test email from there.
- **Hosting Email Issues:** Contact your hosting provider to ensure there are no server-side email sending restrictions or issues with your mail server.

**Q2: My customers aren’t receiving welcome emails when I create their accounts in the Back Office.**
A2:

- **Module Setting:** Ensure “Send notification to customer if admin creates new account” is set to YES in the module’s configuration.
- **Customer Email:** Verify the email address entered for the customer in the Back Office is correct and valid.
- **Customer Spam Folder:** Advise the customer to check their spam or junk folder.
- **PrestaShop Email Settings:** As above, ensure your store’s general email settings are functional.

**Q3: Can I customize the content of the notification emails?**
A3: This module, in its current version, sends standard PrestaShop system emails. Customizing the content would typically require direct modification of PrestaShop’s email templates (found in `mails/` directory for your language) or the module’s core code, which is not recommended for merchants. For advanced customization, consult a developer.

**Q4: Will this module slow down my store?**
A4: No. This module performs a very lightweight operation (sending an email) only when a new customer account is created. It does not add any overhead to page loads or general store performance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Notification about new customer account” module.

### 4.1 Architecture Overview

The module `registernotification` is a standard PrestaShop module following the MVC-like pattern. It primarily leverages PrestaShop’s hook system to intercept events related to customer registration and then uses PrestaShop’s `Mail` class to send notifications. It stores its configuration directly in the `ps_configuration` table.

### 4.2 Controllers (`controllers/`)

This module does not utilize any custom front-office or back-office controllers. All logic is encapsulated within the main module class and its `getContent()` method for configuration.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. All core logic resides within the main `registernotification` class.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. It relies on PrestaShop’s default email templates for customer notifications.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom database tables. All its configuration settings are stored in the `ps_configuration` table using keys prefixed with `REGISTERNOTIFICATION_`.

  - `PS_CONFIGURATION` entries:
    - `REGISTERNOTIFICATION_SEND_OWNER`: Stores the boolean value (0 or 1) for sending notifications to the shop owner.
    - `REGISTERNOTIFICATION_EMAIL_ADDRESSES`: Stores the comma-separated string of email addresses for owner notifications.
    - `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN`: Stores the boolean value (0 or 1) for sending notifications to customers when created by an admin.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Executed immediately after a new customer account is successfully added to the database. | This hook is used to trigger the email notification to the shop owner when a customer registers via the front office. It also triggers the welcome email to the customer if their account was created by an admin in the back office. |
| `displayBackOfficeHeader` | Executed when the Back Office header is rendered. | Typically used for adding CSS/JS or displaying alerts in the Back Office. While listed as a potential hook, its primary use in this module would be for displaying a success/error message after configuration save, or potentially for adding module-specific assets (though none are present). |

### 4.8 Module File Structure (`registernotification/`)

- `index.php`: The main module file. This file contains the `registernotification` class, which extends `Module`. It handles:
  - `__construct()`: Module initialization, setting up name, tab, version, author, etc.
  - `install()`: Registers necessary hooks (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) and sets default configuration values in `ps_configuration`.
  - `uninstall()`: Unregisters hooks and deletes configuration values.
  - `getContent()`: Renders the module’s configuration form in the Back Office, handles form submission, and updates `ps_configuration`.
  - `hookActionCustomerAccountAdd($params)`: The core logic for sending emails. It checks module configuration and uses `Mail::Send()` to dispatch emails to the owner and/or the new customer based on the context of account creation.
  - `hookDisplayBackOfficeHeader()`: Potentially used for displaying confirmation messages after saving configuration.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Notification about new customer account” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
