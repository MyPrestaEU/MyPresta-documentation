---
title: "Get notification about product review - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Get notification about product review PrestaShop module by MyPresta.eu."
sidebar:
  label: "Get notification about product review"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Get notification about product review Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/get-notification-about-product-review/)
>
> ---


# Get notification about product review

## 1. Requirements & Compatibility

-   **Supported PrestaShop Versions**: PrestaShop 1.7.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
-   **Prerequisite**: This module requires our free product reviews addon to be installed and active. It extends the functionality of that module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main and only configuration screen for this module. This screen allows you to define which email address receives the notifications.

#### **Email address to send notifications**
-   **What this setting does:** This is the most crucial setting. It determines the email address where all review-related notifications will be sent.
-   **Effect of changing this setting:**
    -   *When a valid email is entered:* All alerts (new review, reported comment, useful vote) will be sent to this specific email address.
    -   *When left empty or an invalid email is entered:* You will not receive any notifications, effectively disabling the module's core function.
-   **Recommended value:** Your primary business email address, or an email address regularly monitored by your customer service or marketing team.
-   **Merchant scenario / example:** If your customer service team handles all customer interactions, you might enter `customerservice@yourstore.com` here. If you, as the owner, want to be personally informed, use your direct email address.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Module Configuration | Email address to send notifications | Your primary business email | Specifies the email recipient for all review-related alerts (new review, reported comment, useful vote). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I'm not receiving any email notifications. What should I do?**
A:
1.  **Check the email address:** Go to **Modules > Module Manager > Configure** for "Get notification about product review" and ensure the email address entered is correct and free of typos.
2.  **Check your spam folder:** Notifications might sometimes be filtered into your spam or junk folder. Add the sender's email address (usually your store's default email) to your safe senders list.
3.  **Verify PrestaShop email settings:** Ensure your PrestaShop store's email settings are correctly configured and sending emails in general. You can test this by creating a new customer account or placing a test order. Go to **Advanced Parameters > E-mail** in your back office.
4.  **Contact your hosting provider:** If PrestaShop's emails aren't working at all, there might be an issue with your server's mail function. Your hosting provider can help diagnose this.
5.  **Ensure the prerequisite module is installed:** This module extends our free product reviews addon. Make sure that module is installed and working correctly.

**Q: Can I send notifications to multiple email addresses?**
A: The module's current design allows for only one email address to be configured. If you need to send to multiple recipients, you can set up an email forwarding rule in your email client or server (e.g., forward emails from the configured address to a group alias).

**Q: Does this module work with any product review system?**
A: No, this module is specifically designed to work as an extension of **MyPresta.eu's free product reviews addon**. It will not provide notifications for other third-party review modules.

**Q: I've updated my PrestaShop theme, and now the notifications aren't working.**
A: This module does not have any front-office components, so a theme change should not directly affect its notification functionality. Re-check the email configuration in the module and your PrestaShop email settings as described above. If the issue persists, it's likely unrelated to the theme and points to a server or PrestaShop core email issue.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Get notification about product review" module (`reviewsalerts`) is a lightweight PrestaShop module designed to extend the functionality of the core `productcomments` module (or a similar review module, specifically MyPresta.eu's free product reviews addon). It primarily operates by hooking into relevant actions triggered by the review system and sending email notifications based on these events. It follows a simple event-driven pattern, leveraging PrestaShop's hook system without introducing complex MVC structures or custom database tables.

### 4.2 Controllers (`controllers/`)
This module does not contain any custom front-office or back-office controllers. All logic is encapsulated within the main module file and executed via hooks.

### 4.3 Core Classes & Models (`classes/`)
This module does not define any custom classes or `ObjectModel` instances. Its functionality is contained within the main `reviewsalerts` class.

### 4.4 JavaScript Assets (`views/js/`)
This module does not include any JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)
This module does not include any CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)
This module does not include any custom Smarty template files for front-office display or back-office configuration. The configuration form is generated dynamically by `getContent()` in the main module file.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**: This module does not create any custom database tables. It stores its single configuration setting (the notification email address) in the standard `ps_configuration` table.
    *   **Configuration Key**: `REVIEWSALERTS_EMAIL`

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | After a new product review (comment) has been successfully added to the database. | Triggers an email notification to the configured address, informing the merchant about the new review. |
| `actionObjectProductCommentReportAfter` | After a product review has been successfully reported by a customer. | Triggers an email notification to the configured address, informing the merchant that a review has been reported. |
| `actionObjectProductCommentUsefulAfter` | After a customer marks a product review as "useful." | Triggers an email notification to the configured address, informing the merchant that a review's usefulness has been voted on. |

The module's `install()` method registers these hooks, and the corresponding `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()`, and `hookActionObjectProductCommentUsefulAfter()` methods handle the email sending logic.

The email sending is typically handled by PrestaShop's `Mail::Send()` function, utilizing the store's configured email templates and settings. The module would likely construct the email content dynamically based on the context of the triggered action (e.g., review content, product name, reporter's details).

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Get notification about product review" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality and configuration.
