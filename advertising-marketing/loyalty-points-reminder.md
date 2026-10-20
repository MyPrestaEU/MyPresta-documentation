---
title: "Loyalty points reminder - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Loyalty points reminder PrestaShop module by MyPresta.eu."
sidebar:
  label: "Loyalty points reminder - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Loyalty points reminder Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Loyalty points reminder

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. The module relies on PrestaShop’s native mail functions and cron job capabilities.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Loyalty points reminder)

This is the main and only configuration screen for the “Loyalty points reminder” module. Here you will define how and when the reminder emails are sent.

#### **Enable / Disable Module**

- **What this setting does:** This is the master switch for the module.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively check for expiring loyalty points and send reminder emails according to your other settings.
  - *When disabled:* The module will not send any reminder emails, regardless of other settings.
- **Recommended value:** YES (once you’ve configured the other settings).
- **Merchant scenario / example:** You’ve just installed the module and want to start reminding customers. You’d enable this after setting up the days before expiry.

#### **Days before expiry to send reminder**

- **What this setting does:** This determines how many days *before* a customer’s loyalty points are set to expire that the reminder email will be sent.
- **Effect of changing this setting:**
  - *If set to 7:* Customers will receive an email 7 days before their points expire.
  - *If set to 30:* Customers will receive an email 30 days before their points expire.
- **Recommended value:** 7-14 days. This gives customers enough time to react without being too far in advance that they forget.
- **Merchant scenario / example:** You want to give customers a week to use their points. You would set this to “7”. If you want to give them more leeway, perhaps “14”.

#### **Cron Job URL**

- **What this setting does:** This displays a unique URL that you need to set up as a cron job on your server. A cron job is a scheduled task that tells your server to run a specific script at regular intervals (e.g., once a day). This is how the module automatically checks for expiring points and sends emails without you having to manually do anything.
- **Effect of changing this setting:** You cannot change this setting directly. It’s a generated URL.
  - *If the cron job is set up correctly:* The module will run automatically, sending emails as configured.
  - *If the cron job is NOT set up:* The module will never send any reminder emails, even if enabled.
- **Recommended value:** Copy this URL and set it up as a daily cron job on your hosting server.
- **Merchant scenario / example:** After configuring the “Days before expiry” setting, you would copy this URL and paste it into your hosting control panel’s cron job scheduler (e.g., cPanel, Plesk, or direct server access). You’d typically set it to run once every 24 hours.

#### **Test Email Address**

- **What this setting does:** Allows you to send a test reminder email to a specific address to ensure the module is working correctly and the email content looks good.
- **Effect of changing this setting:**
  - *Entering an email and clicking “Send Test Email”:* An email will be sent to the specified address, simulating a loyalty points reminder. This email will contain placeholder data as it’s a test.
- **Recommended value:** Use your own email address or a colleague’s for testing.
- **Merchant scenario / example:** Before going live, you want to see what the reminder email looks like. You’d enter your email address here and click the test button.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Enable / Disable Module** | YES | Master switch to activate or deactivate the reminder emails. |
| Module Configuration | **Days before expiry to send reminder** | 7-14 days | Defines how many days before points expire the email is sent. |
| Module Configuration | **Cron Job URL** | Copy & Set Daily | Essential for automated email sending; must be configured on your server. |
| Module Configuration | **Test Email Address** | Your email for testing | Sends a sample reminder email to verify content and delivery. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are not receiving reminder emails. What should I check?**
A:

1. **Is the module enabled?** Go to the module configuration and ensure “Enable / Disable Module” is set to YES.
2. **Is the cron job set up correctly?** This is the most common issue. The module relies on a cron job to run automatically. Copy the “Cron Job URL” from the module configuration and ensure it’s correctly configured on your hosting server to run daily.
3. **Check your PrestaShop email settings:** Go to **Advanced Parameters > E-mail** in your Back Office. Send a test email from there to ensure your store’s email system is functioning.
4. **Check spam folders:** Ask customers to check their spam or junk folders.
5. **Clear Smarty cache:** Sometimes, template changes or module updates require clearing the cache. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache”.

**Q: The test email works, but customers still aren’t getting reminders.**
A: This strongly suggests the cron job is the issue. The test email uses PrestaShop’s immediate mail sending, while actual reminders depend on the cron job running the module’s background process. Double-check your cron job setup with your hosting provider.

**Q: Can I customize the content of the reminder email?**
A: The module uses PrestaShop’s standard email templates. You would typically find the email template files in your theme’s `mails/` directory (e.g., `themes/yourtheme/mails/en/loyalty_points_reminder.html` and `loyalty_points_reminder.txt`). If these don’t exist, the module will use the default PrestaShop mail templates. You can override these in your theme to customize the text and appearance.

**Q: What happens if a customer doesn’t have any loyalty points?**
A: The module is designed to only send emails to customers who actually have loyalty points that are nearing their expiry date. If a customer has no points, or their points are not expiring soon, they will not receive an email.

**Q: Does this module work with custom loyalty point modules?**
A: This module is designed to work with PrestaShop’s native loyalty points system. If you use a third-party loyalty module, it might not integrate directly unless that module specifically extends or uses PrestaShop’s core loyalty functionalities in a compatible way.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Loyalty points reminder” module.

### 4.1 Architecture Overview

The “Loyalty points reminder” module (`lpreminder`) is a standard PrestaShop module following an MVC-like pattern. Its core functionality revolves around a scheduled task (cron job) that triggers a front controller to process expiring loyalty points and send emails. It leverages PrestaShop’s native `LoyaltyModule` and `Mail` classes.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are designed to be accessed via a specific URL, primarily for cron job execution.

- **`controllers/front/cronjob.php`**
  - **Class name & parent class:** `LpreminderCronjobModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the critical endpoint for the cron job. When accessed, it executes the module’s logic to identify customers with expiring loyalty points and dispatches reminder emails. It should ideally be protected (e.g., by a token or IP restriction) if not already implemented by the module to prevent unauthorized access. It does not render any visual output but performs background processing.
- **`controllers/front/index.php`**
  - **Class name & parent class:** `LpreminderIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a default entry point or a placeholder. In many modules, if a specific action isn’t defined, `index.php` might handle it. Given the module’s primary function, `cronjob.php` is the main operational front controller. This `index.php` might be a fallback or used for future extensions.

#### Back-Office Admin Controllers

The module does not utilize any custom Admin Controllers. All configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define any custom classes or `ObjectModel`s in the `classes/` directory. It directly interacts with PrestaShop’s core classes, notably:

- `LoyaltyModule`: To retrieve customer loyalty points and their expiry dates.
- `Customer`: To fetch customer details for email sending.
- `Mail`: To send the reminder emails.
- `Configuration`: To store and retrieve module settings.

### 4.4 JavaScript Assets (`views/js/`)

The module does not include any custom JavaScript files. All functionality is handled server-side.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not include any custom CSS files. The configuration page uses PrestaShop’s default Back Office styling.

### 4.6 Smarty Template Structure (`views/templates/`)

The module does not include any custom Smarty template files in its `views/templates/` directory.

- **Email Templates:** The module relies on PrestaShop’s default email template system. The email content for the reminder is generated using a template named `loyalty_points_reminder`. Developers can customize this email by creating or overriding the following files in their active theme’s `mails/` directory:
  - `themes/yourtheme/mails/en/loyalty_points_reminder.html` (for HTML email content)
  - `themes/yourtheme/mails/en/loyalty_points_reminder.txt` (for plain text email content)
  - Replace `en` with the appropriate language code.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration settings (e.g., `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) in the `ps_configuration` table. It queries existing PrestaShop tables like `ps_loyalty_history` and `ps_customer`.
- **Registered Hooks Table**:
  The module primarily uses the `actionFrontControllerSetMedia` hook for potential future JS/CSS inclusion (though none are present currently) and implicitly relies on the cron job mechanism for its core functionality, which isn’t a traditional PrestaShop hook but an external trigger to a front controller.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders content in the `<head>` section of front-office pages. | Not directly used for module’s core logic, but could be used for JS/CSS if needed. |
| `displayRightColumn` | Renders content in the right column of front-office pages. | Not directly used for module’s core logic. |
| `displayLeftColumn` | Renders content in the left column of front-office pages. | Not directly used for module’s core logic. |
| `displayFooter` | Renders content in the footer of front-office pages. | Not directly used for module’s core logic. |
| `displayProductExtraContent` | Renders content on the product page. | Not directly used for module’s core logic. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media (JS/CSS). | Allows the module to register its own JS/CSS assets if needed. |
| *(Cron Job Trigger)* | External server-side scheduled task (e.g., daily). | Triggers the `cronjob.php` front controller to process expiring loyalty points and send emails. This is the module’s primary operational trigger. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Loyalty points reminder” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any technical issues or questions regarding the module’s functionality.
