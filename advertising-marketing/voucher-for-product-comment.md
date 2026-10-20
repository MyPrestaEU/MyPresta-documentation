---
title: "Voucher for product comment - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Voucher for product comment PrestaShop module by MyPresta.eu."
sidebar:
  label: "Voucher for product comment - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Voucher for product comment Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Voucher for product comment

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop to function correctly. No specific additional extensions are needed for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area for the “Voucher for product comment” module. You’ll find all settings related to comment reminders and voucher generation here.

#### **Comment Reminder Settings**

- **Ask for permissions to send reminders**

  - **What this setting does:** If enabled, a checkbox will appear on your customer registration and identity update forms (My Account > Information) asking customers if they agree to receive comment reminders. This is important for GDPR compliance and respecting customer privacy.
  - **Effect of changing this setting:**
    - *When enabled:* Customers must explicitly opt-in to receive reminders. Only customers who check this box will receive reminder emails.
    - *When disabled:* All customers who meet other criteria (e.g., purchased products, haven’t commented) will receive reminders, without an explicit opt-in.
  - **Recommended value:** YES (Highly recommended for GDPR compliance and better customer relations).
  - **Merchant scenario / example:** You want to ensure your marketing practices are compliant with data protection regulations. Enabling this gives customers control over their communication preferences.
- **Send comment reminder**

  - **What this setting does:** This is the master switch for the comment reminder feature. If disabled, no comment reminder emails will be sent, regardless of other settings.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively send reminder emails based on your other settings.
    - *When disabled:* No reminder emails will be sent.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You’ve decided to actively collect more reviews and want to start sending reminders.
- **Remind about comments after:**

  - **What this setting does:** Defines the number of days after an order reaches a specific status (defined below) that the first comment reminder email will be sent.
  - **Effect of changing this setting:**
    - *Changing the number:* Determines the delay. A shorter delay means customers receive reminders sooner; a longer delay gives them more time before being prompted.
  - **Recommended value:** 7 days (Gives customers enough time to receive and use the product).
  - **Merchant scenario / example:** You want to give customers a week to receive their product and form an opinion before asking for a review.
- **Repeat remind**

  - **What this setting does:** If a customer still hasn’t left a comment after the initial reminder, this setting determines if and when a second reminder should be sent.
  - **Effect of changing this setting:**
    - *Setting a number (e.g., 14):* A second reminder will be sent 14 days after the *first* reminder, if no comment has been left.
    - *Setting to 0 or leaving empty:* No second reminder will be sent.
  - **Recommended value:** 14 (Provides a gentle follow-up without being too aggressive).
  - **Merchant scenario / example:** Some customers might miss the first email or simply forget. A second reminder after two weeks can catch their attention again.
- **Email title**

  - **What this setting does:** Allows you to customize the subject line of the comment reminder emails. This is crucial for email open rates.
  - **Effect of changing this setting:**
    - *Changing the text:* Directly changes the subject line customers see in their inbox.
  - **Recommended value:** “We’d love to hear your thoughts on your recent purchase!” or “Share your experience and help other shoppers!”
  - **Merchant scenario / example:** You want to make the email subject line engaging and clear, encouraging customers to open it.
- **Select order states**

  - **What this setting does:** Determines which order statuses trigger the comment reminder process. Reminders will only be sent for products from orders that have reached one of the selected statuses.
  - **Effect of changing this setting:**
    - *Selecting statuses (e.g., “Delivered”):* Reminders will only be sent for orders marked as delivered.
    - *Not selecting a relevant status:* Reminders might not be sent at the appropriate time (e.g., if you only select “Payment accepted” but products haven’t shipped yet).
  - **Recommended value:** “Delivered” (This ensures customers have received their products before being asked to review them).
  - **Merchant scenario / example:** You only want to ask for reviews once the customer has actually received their order, so you select “Delivered” and “Shipped”.
- **Group of customers (for Reminders)**

  - **What this setting does:** Allows you to target specific customer groups for comment reminders. Only customers belonging to the selected groups will receive reminders.
  - **Effect of changing this setting:**
    - *Selecting groups (e.g., “Customers”):* Only customers in the “Customers” group will receive reminders.
    - *Not selecting any group:* Reminders will be sent to all customers (unless other filters apply).
  - **Recommended value:** “Customers” (Typically, you want to remind all your regular customers).
  - **Merchant scenario / example:** You have a special “VIP” customer group and want to send them personalized reminders, or you want to exclude wholesale customers from reminders.
- **Send reminders about comments for products from orders:**

  - **What this setting does:** This is a date filter. Reminders will only be sent for products purchased in orders placed *after* this specified date.
  - **Effect of changing this setting:**
    - *Setting a date:* Prevents sending reminders for very old orders, focusing on recent purchases.
    - *Leaving empty:* Reminders could potentially be sent for all past orders, which might not be desirable.
  - **Recommended value:** Set to a recent date, or the date you installed the module, to avoid spamming old customers.
  - **Merchant scenario / example:** You just installed the module and don’t want to send reminders for orders from a year ago; you only care about orders from the last 3 months.
- **Image size for product pictures**

  - **What this setting does:** Determines the size of product images included in the reminder emails.
  - **Effect of changing this setting:**
    - *Selecting a size (e.g., “home\_default”):* The product images in the email will be rendered at that specific size, affecting email layout and loading time.
  - **Recommended value:** “home\_default” or “small\_default” (A medium-sized image that looks good without making the email too heavy).
  - **Merchant scenario / example:** You want the product images in your reminder emails to be clear but not excessively large, so you choose a suitable image size defined in your theme.

#### **Voucher Generation Settings**

- **Send voucher code for comment**

  - **What this setting does:** This is the master switch for the voucher generation feature. If disabled, no vouchers will be generated or sent, even if comments are left.
  - **Effect of changing this setting:**
    - *When enabled:* The module will generate and send a unique voucher code to customers who leave a product comment.
    - *When disabled:* No vouchers will be sent.
  - **Recommended value:** YES (This is a core feature for incentivizing comments).
  - **Merchant scenario / example:** You want to reward customers for their effort in leaving a review, encouraging them to shop again.
- **Send voucher for customers that purchased product only**

  - **What this setting does:** If enabled, a voucher will *only* be sent if the customer who left the comment also purchased the product. This prevents people who haven’t bought from your store from getting vouchers just by leaving comments.
  - **Effect of changing this setting:**
    - *When enabled:* Vouchers are restricted to verified purchasers.
    - *When disabled:* Anyone who leaves a comment (e.g., a guest, or someone who didn’t buy the product) could receive a voucher.
  - **Recommended value:** YES (Highly recommended to ensure vouchers are given to actual customers and prevent abuse).
  - **Merchant scenario / example:** You want to reward loyal customers who have already made a purchase, not just anyone who leaves a comment.
- **When generate voucher?**

  - **What this setting does:** Determines when the voucher is generated and sent to the customer.
  - **Effect of changing this setting:**
    - *Option 1 (e.g., “After comment is added”):* Voucher is sent immediately after the customer submits their comment.
    - *Option 2 (e.g., “After comment is approved”):* Voucher is sent only after an administrator has manually approved the comment in the Back Office.
  - **Recommended value:** “After comment is approved” (Prevents giving vouchers for spam or inappropriate comments).
  - **Merchant scenario / example:** You moderate all product comments to maintain quality. You want to ensure only approved, valuable comments receive a voucher.
- **Generate vouchers for comments:**

  - **What this setting does:** This section allows you to define the properties of the voucher that will be generated. This includes the discount type (percentage, amount), value, minimum purchase, validity, and more.
  - **Effect of changing this setting:**
    - *Each field here (e.g., “Discount type,” “Value,” “Minimum amount”):* Directly configures the rules and benefits of the generated discount voucher.
    - *Leaving fields empty or incorrectly configured:* Could lead to invalid vouchers or vouchers that don’t meet your marketing goals.
  - **Recommended value:**
    - **Discount type:** Percentage (e.g., 10%) or Amount (e.g., $5).
    - **Value:** A reasonable incentive (e.g., 5, 10, 15).
    - **Minimum amount:** Set a minimum purchase to ensure profitability (e.g., $50).
    - **Validity:** 30 days (Encourages quick use).
    - **Description:** “Thank you for your product review!”
  - **Merchant scenario / example:** You want to offer a 10% discount on their next order, valid for 30 days, with a minimum purchase of $50, as a thank you for their review.
- **Group of customers (for Vouchers)**

  - **What this setting does:** Similar to the reminder setting, this allows you to restrict voucher generation to specific customer groups.
  - **Effect of changing this setting:**
    - *Selecting groups:* Only customers in the selected groups will receive vouchers.
    - *Not selecting any group:* Vouchers will be sent to all customers (unless other filters apply).
  - **Recommended value:** “Customers”
  - **Merchant scenario / example:** You only want to give vouchers to your standard “Customers” group, not to “Guests” or “Wholesalers”.
- **Limit the number of emails**

  - **What this setting does:** This is a safety feature to prevent your server from sending too many emails in a short period, which could lead to your emails being marked as spam or your hosting provider imposing limits.
  - **Effect of changing this setting:**
    - *When enabled:* The module will respect the “Emails limit” setting.
    - *When disabled:* No email sending limit will be applied by the module itself.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You have a large number of pending reminders and want to send them out gradually to avoid overwhelming your mail server.
- **Emails limit:**

  - **What this setting does:** Specifies the maximum number of emails (reminders or vouchers) the module can send in a single execution cycle (e.g., when the cron job runs).
  - **Effect of changing this setting:**
    - *Setting a number (e.g., 50):* The module will send a maximum of 50 emails per cron job run. If there are more, they will be sent in subsequent runs.
  - **Recommended value:** 50-100 (Adjust based on your hosting provider’s email sending limits and server capacity).
  - **Merchant scenario / example:** Your hosting provider allows 100 emails per hour. You set this limit to 50 to stay well within their guidelines.

#### **Product Filters (for Reminders & Vouchers)**

- **Enable filters**

  - **What this setting does:** Activates additional filtering options for both reminders and vouchers, allowing you to specify which products or manufacturers are eligible.
  - **Effect of changing this setting:**
    - *When enabled:* The “Manufacturers” filter becomes active.
    - *When disabled:* No product-specific filters will be applied.
  - **Recommended value:** NO (Unless you have a specific need to filter).
  - **Merchant scenario / example:** You only want to send reminders or vouchers for products from certain manufacturers.
- **Manufacturers**

  - **What this setting does:** If “Enable filters” is active, this allows you to select specific manufacturers. Reminders and vouchers will only be sent for products from the selected manufacturers.
  - **Effect of changing this setting:**
    - *Selecting manufacturers:* Narrows down the scope of the module’s operation to only products from those brands.
  - **Recommended value:** Leave all unselected (unless you have a specific need).
  - **Merchant scenario / example:** You are running a promotion with a specific brand and only want to incentivize comments for their products.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Ask for permissions to send reminders | YES | Ensures GDPR compliance; customers opt-in for reminders. |
| Module Configuration | Send comment reminder | YES | Master switch for sending reminder emails. |
| Module Configuration | Remind about comments after: | 7 days | Delay (in days) after order status change for first reminder. |
| Module Configuration | Repeat remind | 14 days | Delay (in days) after first reminder for a second one (0 for none). |
| Module Configuration | Email title (Reminder) | Customizable | Subject line for reminder emails. |
| Module Configuration | Select order states | Delivered | Order statuses that trigger reminder process. |
| Module Configuration | Group of customers (Reminder) | Customers | Restricts reminders to selected customer groups. |
| Module Configuration | Send reminders about comments for products from orders: | Recent date / Empty | Date filter for eligible orders. |
| Module Configuration | Image size for product pictures | home\_default | Size of product images in reminder emails. |
| Module Configuration | Send voucher code for comment | YES | Master switch for generating and sending vouchers. |
| Module Configuration | Send voucher for customers that purchased product only | YES | Restricts vouchers to actual purchasers. |
| Module Configuration | When generate voucher? | After comment is approved | Timing of voucher generation (after submission or approval). |
| Module Configuration | Generate vouchers for comments: (Voucher properties) | Customizable | Defines the discount type, value, validity, etc., of the voucher. |
| Module Configuration | Group of customers (Voucher) | Customers | Restricts vouchers to selected customer groups. |
| Module Configuration | Limit the number of emails | YES | Enables email sending rate limiting. |
| Module Configuration | Emails limit: | 50-100 | Max emails sent per cron job run. |
| Module Configuration | Enable filters | NO | Activates product/manufacturer filtering. |
| Module Configuration | Manufacturers | All unselected | Filters eligible products by manufacturer. |

### 2.2 Dedicated Admin Screens & Controller Views

The module adds several dedicated screens to your PrestaShop Back Office for managing reminders, vouchers, and unsubscribed customers. You can find these under the **“Voucher for comment”** menu item, usually located under **“Catalog”** or **“Marketing”**.

#### **4.2.1 AdminComRemCommentsController: Comment Reminders Management**

- **Screen Name & Menu Location:** **Voucher for comment > Comment Reminders**
- **Available Actions & Settings:** This screen displays a list of all pending, sent, or failed comment reminders. You’ll see details like the customer’s name, email, the product they need to comment on, the order ID, the date the reminder was sent (or is scheduled), and its current status.
  - **Grid / Management view:** You can view, filter, and search through the list of reminders. This allows you to monitor the module’s activity.
  - **Bulk Actions:** Depending on the module version, you might be able to manually send reminders or delete entries.
- **Effect of changes:** This screen is primarily for monitoring. Deleting an entry here would prevent a scheduled reminder from being sent. Manually sending a reminder would trigger an email to the customer.
- **Recommended workflow for daily store management:** Periodically check this screen to ensure reminders are being sent as expected. If you notice a customer hasn’t received a reminder, you can investigate or manually trigger it.

#### **4.2.2 AdminComUnsubController: Unsubscribed Customers**

- **Screen Name & Menu Location:** **Voucher for comment > Unsubscribed Customers**
- **Available Actions & Settings:** This screen lists customers who have opted out of receiving comment reminders (if the “Ask for permissions” setting is enabled). You’ll see their customer ID and email address.
  - **Grid / Management view:** Allows you to view and manage the list of unsubscribed customers.
- **Effect of changes:** Removing a customer from this list would make them eligible to receive reminders again (assuming they meet other criteria and haven’t explicitly opted out elsewhere).
- **Recommended workflow for daily store management:** This is a compliance-related screen. You generally won’t need to interact with it daily, but it’s important to know where to find and manage customer opt-out preferences.

#### **4.2.3 AdminComVouCommentsController: Voucher for Comments Management**

- **Screen Name & Menu Location:** **Voucher for comment > Vouchers for Comments**
- **Available Actions & Settings:** This screen provides a comprehensive list of all vouchers generated by the module in response to product comments. You’ll see details such as the customer who received the voucher, the product they commented on, the generated voucher code, its value, validity, and whether it has been used.
  - **Grid / Management view:** You can filter, search, and sort vouchers. This is useful for tracking the effectiveness of your incentive program.
  - **Associated Config Keys:** The display and filtering options here might be influenced by `cvo_filters` and `cvo_fil_manuf` from the main configuration.
- **Effect of changes:** This screen is primarily for monitoring. You can see which vouchers have been issued and if they’ve been redeemed.
- **Recommended workflow for daily store management:** Review this screen to track how many vouchers are being issued and their redemption rates. This data can help you evaluate the success of your review incentive program.

#### **4.2.4 index.php (Admin Controller Placeholder)**

- **Screen Name & Menu Location:** This `index.php` file typically serves as a placeholder or a redirect within the module’s `controllers/admin` directory, ensuring that direct access to the directory doesn’t expose sensitive information. It doesn’t represent a user-facing screen in the PrestaShop Back Office.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving reminder emails. What should I check?**
A1:

- **Module Enabled:** Ensure “Send comment reminder” is set to YES in the module configuration.
- **Order Statuses:** Verify that the orders in question have reached one of the “Select order states” you’ve chosen (e.g., “Delivered”).
- **Reminder Delay:** Check “Remind about comments after:” to ensure enough days have passed since the order status change.
- **Cron Job:** The module relies on PrestaShop’s cron job to send emails. Ensure your cron job is set up correctly and running regularly on your server. You can usually find cron job instructions in your hosting panel or PrestaShop’s “Advanced Parameters > Information” section.
- **Email Configuration:** Check your PrestaShop email settings (Advanced Parameters > E-mail) to ensure emails are being sent correctly from your store in general.
- **Customer Opt-in:** If “Ask for permissions to send reminders” is enabled, ensure the customers have actually opted in.
- **Email Limits:** Check “Limit the number of emails” and “Emails limit” settings. If the limit is reached, emails will be sent in the next cron run.
- **Spam Folders:** Ask customers to check their spam or junk folders.

**Q2: Vouchers are not being sent after comments are left.**
A2:

- **Module Enabled:** Ensure “Send voucher code for comment” is set to YES.
- **Voucher Generation Timing:** Check “When generate voucher?”. If it’s set to “After comment is approved,” ensure the comments have actually been approved in your PrestaShop Back Office (Catalog > Product Comments, if you use the default module, or your third-party review module).
- **Purchaser Only:** If “Send voucher for customers that purchased product only” is enabled, verify that the customer who left the comment actually purchased that specific product.
- **Voucher Configuration:** Double-check all settings under “Generate vouchers for comments” to ensure a valid voucher can be created (e.g., discount value, validity).
- **Email Configuration & Cron Job:** Similar to reminder issues, ensure your email settings and cron job are working.

**Q3: The module is sending too many emails, or emails are being delayed.**
A3:

- **Emails Limit:** Go to the module configuration and ensure “Limit the number of emails” is enabled and “Emails limit” is set to a reasonable number (e.g., 50-100). This prevents your server from being overloaded.
- **Cron Job Frequency:** If your cron job runs very frequently (e.g., every minute), and you have a high email limit, it could send many emails quickly. Adjust the cron job frequency or the email limit.
- **Hosting Limits:** Contact your hosting provider to understand their email sending limits per hour/day. Adjust the module’s “Emails limit” accordingly.

**Q4: How do I translate the module’s texts or email templates?**
A4:

- **Back Office Translation:** Go to **International > Translations**.
- **Type of translation:** Select “Installed modules translations.”
- **Select your theme:** Choose your current theme.
- **Select your language:** Choose the language you want to translate.
- **Module:** Find “Voucher for product comment” in the list.
- You can then edit the text strings for the module’s configuration, front-office elements (like the opt-in checkbox), and email templates. Remember to save your changes.

**Q5: The module’s front-office checkbox (for permissions) doesn’t look right on my theme.**
A5:

- **Theme Compatibility:** Custom themes sometimes require minor CSS adjustments for new module elements.
- **Clear Cache:** First, try clearing your PrestaShop cache (Advanced Parameters > Performance > Clear cache).
- **Contact Support:** If the issue persists, it might require a small CSS tweak. Contact MyPresta.eu support with screenshots and your theme name.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Voucher for product comment” module for developers and webmasters.

### 4.1 Architecture Overview

The module follows a standard PrestaShop module architecture, leveraging MVC patterns where appropriate. It integrates with PrestaShop’s core through hooks for front-office display and back-office actions. It uses custom AdminControllers for managing its data entities (reminders, vouchers, unsubscribes) and a FrontController for cron job execution. Configuration is managed via `Configuration::get()` and `Configuration::updateValue()`. The module does not appear to use custom `ObjectModel` classes, instead likely managing its data directly or through existing PrestaShop entities (like `CartRule` for vouchers).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `comvou/controllers/front/CronJob.php`
  - **Class name & parent class:** `ComvouCronJobModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is designed to be executed via a cron job. It handles the background tasks of the module, such as checking for eligible orders, sending comment reminders, and generating/sending vouchers based on new comments. It typically does not render a visual page but performs actions and exits. It’s the heart of the module’s automation.

#### Back-Office Admin Controllers

- `comvou/controllers/admin/AdminComRemComments.php`

  - **Tab name and managed entity:** “Comment Reminders” (under “Voucher for comment” menu). Manages `cvor` (Comment Voucher Order Reminder) entities, which represent scheduled or sent reminders.
  - **Responsibility:** Provides a list (grid view) of all comment reminders. It allows administrators to view the status of reminders, filter them, and potentially perform actions like manually sending a reminder or deleting an entry. It extends `AdminController` and uses `HelperList` for display.
- `comvou/controllers/admin/AdminComUnsub.php`

  - **Tab name and managed entity:** “Unsubscribed Customers” (under “Voucher for comment” menu). Manages `cunsub` (Comment Unsubscribe) entities.
  - **Responsibility:** Displays a list of customers who have unsubscribed from comment reminders. This controller provides an interface to view and manage these opt-out preferences, typically using `HelperList`.
- `comvou/controllers/admin/AdminComVouComments.php`

  - **Tab name and managed entity:** “Vouchers for Comments” (under “Voucher for comment” menu). Manages `cvov` (Comment Voucher Order Voucher) entities, representing generated vouchers.
  - **Responsibility:** Presents a list of all vouchers generated by the module, detailing which customer received it, for which product, the voucher code, its value, and usage status. It uses `HelperList` for display and allows filtering. The display might incorporate logic based on `cvo_filters` and `cvo_fil_manuf` configuration keys.
- `comvou/controllers/admin/index.php`

  - **Tab name and managed entity:** Not a direct user-facing screen.
  - **Responsibility:** This is a standard security measure in PrestaShop. It typically contains `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` to prevent directory listing and redirect to the shop’s root.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module might be handling its data directly within the main `comvou.php` file or its controllers, potentially using existing PrestaShop `ObjectModel`s (like `Order`, `Customer`, `Product`, `CartRule`) and direct database queries for its custom data storage (e.g., for reminders and voucher records).

### 4.4 JavaScript Assets (`views/js/`)

- `comvou/lib/voucherengine/script.js`
  - **Scope:** Likely Back-office.
  - **Details:** This script is probably associated with the voucher generation settings within the module’s configuration or the AdminComVouComments controller. It could handle dynamic form elements, validation, or AJAX interactions related to voucher creation parameters (e.g., showing/hiding fields based on discount type, calculating values). It might also be used for general UI enhancements in the module’s admin pages.

### 4.5 CSS Stylesheets (`views/css/`)

- `comvou/lib/voucherengine/ps16.css`
  - **Scope:** Back-office admin form styling.
  - **Details:** This stylesheet provides specific styling for the module’s configuration page and potentially its custom admin controller views, ensuring they look consistent with PrestaShop 1.6’s back-office design. It might contain rules for form layouts, input fields, buttons, and grid displays. Developers overriding this would target specific IDs or classes used by the module’s admin templates.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `comvou/views/templates/hook/form.tpl`

  - **Hook:** Potentially `displayAdditionalCustomerFormFields` or `displayCustomerAccountForm`.
  - **Output:** This template likely renders the “Ask for permissions to send reminders” checkbox on the customer registration or identity update forms in the front office. It would contain the HTML for the checkbox and its associated label.
- `comvou/views/templates/hook/header.tpl`

  - **Hook:** `displayHeader`
  - **Output:** This template is typically used to include CSS or JavaScript files that need to be loaded in the `<head>` section of the front-office pages. It might conditionally load assets based on module settings or the current page.
- `comvou/views/templates/hook/identity.tpl`

  - **Hook:** Potentially `displayCustomerAccountForm` or similar hooks on the customer identity page.
  - **Output:** Similar to `form.tpl`, this template likely renders the opt-in checkbox specifically on the customer’s “My Account > Information” page, allowing existing customers to manage their reminder preferences.

#### Admin templates (`views/templates/admin/`)

- `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

  - **Purpose:** This template is used by `AdminComRemCommentsController` for rendering the form (if any) to add/edit a comment reminder, or more likely, to customize the display of the list helper.
- `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

  - **Purpose:** This template is used by `AdminComVouCommentsController` for rendering the form (if any) to add/edit a voucher entry, or to customize the display of the list helper for generated vouchers.
- `comvou/views/templates/admin/orderstates.tpl`

  - **Purpose:** This template is likely used within the main module configuration (`getContent()`) to render the multi-select list of order statuses, allowing the merchant to choose which statuses trigger reminders.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module description and code analysis suggest that the module stores its custom data (reminders, vouchers, unsubscribes) in dedicated database tables. While specific SQL files are not listed, the `AdminComRemCommentsController`, `AdminComUnsubController`, and `AdminComVouCommentsController` imply the existence of tables like:

- `ps_cvor`: Stores records related to comment reminders (e.g., customer ID, product ID, order ID, reminder status, last sent date).
- `ps_cunsub`: Stores records of customers who have unsubscribed from reminders (e.g., customer ID, email).
- `ps_cvov`: Stores records of generated vouchers (e.g., customer ID, product ID, generated `id_cart_rule`, voucher code, status).
- Configuration values are stored in `ps_configuration` with keys like `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | When an AdminController is initialized and its media (JS/CSS) is being set. | To inject module-specific JS/CSS into the Back Office. |
| `actionOrderStatusUpdate` | After an order’s status has been updated. | To detect when an order reaches a “delivered” or relevant status, triggering the reminder process. |
| `actionCustomerAccountAdd` | After a new customer account is created. | To check for initial opt-in preferences for new customers. |
| `displayHeader` | In the `<head>` section of front-office pages. | To include front-office CSS/JS or meta tags. |
| `displayCustomerAccountForm` | On the customer’s “My Account > Information” page. | To display the opt-in checkbox for existing customers. |
| `displayAdditionalCustomerFormFields` | On the customer registration form. | To display the opt-in checkbox for new customer registrations. |
| `validateCustomerFormFields` | When a customer form (registration/identity) is submitted. | To process the opt-in checkbox selection and save the customer’s preference. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional technical support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Ensure you are running the latest compatible version of the module for your PrestaShop store to benefit from all improvements and security patches.
