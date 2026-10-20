---
title: "Voucher for friend - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Voucher for friend PrestaShop module by MyPresta.eu."
sidebar:
  label: "Voucher for friend - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Voucher for friend Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/voucher-for-friend/)
>
> ---


# Voucher for friend

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Voucher for friend)

This is the main configuration screen for the “Voucher for friend” module. Here you will define how the voucher sharing feature behaves and where it appears on your store.

#### **Settings & Options**

- **Display “Voucher for friend” link in my account block (fvc\_b\_position)**

  - **What this setting does:** Controls whether a link to the “Voucher for friend” page appears in the customer’s “My Account” block, which is typically found in the header or a column after a customer logs in.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* A link, usually labeled “My Vouchers” or “Voucher for a Friend,” will be visible in the customer account block, providing quick access to the sharing feature.
    - *When disabled (No):* The link will not appear in the customer account block. Customers would need to navigate to their full “My Account” page to find the link, or use another placement option.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you want to make it super easy for logged-in customers to find the feature, enable this. It’s a prominent placement for active users.
- **Display “Voucher for friend” link in my account page (fvc\_b\_position2)**

  - **What this setting does:** Determines if a link to the “Voucher for friend” page is shown on the main “My Account” page, which lists all customer-specific options.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* A dedicated link will appear on the “My Account” page, usually as an icon or text link alongside other options like “Order history” or “My addresses.”
    - *When disabled (No):* The link will not be present on the “My Account” page.
  - **Recommended value:** YES
  - **Merchant scenario / example:** This is a standard and expected place for customers to find such a feature. Enabling it ensures discoverability for all logged-in users.
- **Display “Voucher for friend” link in left/right column (fvc\_b\_position3)**

  - **What this setting does:** Controls whether a promotional block or link for “Voucher for friend” appears in the left or right columns of your store. This can be visible to both logged-in and unlogged visitors.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* A block or link will be rendered in the specified column, encouraging visitors to use or learn about the voucher sharing feature.
    - *When disabled (No):* No such block will appear in the columns.
  - **Recommended value:** YES (if you want to promote the feature widely)
  - **Merchant scenario / example:** If you want to actively promote the referral program to all visitors, including those not yet logged in, enabling this will increase visibility. You might place it in the right column on product pages to encourage sharing.
- **Number of vouchers to generate (FV\_NBC)**

  - **What this setting does:** Defines how many unique voucher codes a single customer can generate and send to friends.
  - **Effect of changing this setting:**
    - *Set to 1:* Each customer can only send one voucher to one friend.
    - *Set to 5:* Each customer can send up to five vouchers to five different friends.
    - *Set to 0 (or a very high number):* Allows unlimited voucher generations per customer.
  - **Recommended value:** 3-5 (to encourage sharing without overwhelming the system or creating too many discounts)
  - **Merchant scenario / example:** If you want to limit the number of referrals a single customer can make to prevent abuse or manage your discount budget, set a specific number like 3. If you want maximum viral spread, set a higher number or 0 for unlimited.
- **Allow unlogged users to send vouchers (FV\_UNLOGGED)**

  - **What this setting does:** Determines if visitors who are not logged into a customer account can still access the “Voucher for friend” form and send a voucher.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* Unlogged users will see the “Voucher for friend” links (if enabled in columns/footer) and can proceed to fill out the form. They will likely be prompted to enter their own email address as the referrer.
    - *When disabled (No):* Only logged-in customers can access and use the voucher sharing feature. Unlogged users clicking the link might be redirected to the login/registration page.
  - **Recommended value:** NO (to ensure only actual customers are referring, and to prevent spam/abuse)
  - **Merchant scenario / example:** If you want to strictly control who can refer and ensure that only your existing customer base is participating, disable this. If you want to allow anyone to refer, even if they haven’t purchased yet, enable it (but be mindful of potential spam).
- **Shop Email (PS\_SHOP\_EMAIL)**

  - **What this setting does:** This field typically displays your store’s default contact email address, which is used as the “sender” email for the voucher notification sent to friends. It usually pulls from your PrestaShop general settings.
  - **Effect of changing this setting:** Changing this here might override the system-wide shop email for this module’s specific emails.
  - **Recommended value:** Ensure it’s a valid, professional email address associated with your store (e.g., `info@yourstore.com`).
  - **Merchant scenario / example:** The friend receiving the voucher will see this email as the sender. It should be an address they can recognize and trust.
- **Shop Name (PS\_SHOP\_NAME)**

  - **What this setting does:** This field typically displays your store’s official name, which is used in the email subject and body when sending the voucher to a friend. It usually pulls from your PrestaShop general settings.
  - **Effect of changing this setting:** Changing this here might override the system-wide shop name for this module’s specific emails.
  - **Recommended value:** Your official store name (e.g., “My Awesome Store”).
  - **Merchant scenario / example:** The friend receiving the voucher will see this name. It should be clear and consistent with your brand.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display “Voucher for friend” link in my account block (fvc\_b\_position) | YES | Shows link in customer account block (header/column) for quick access. |
| Module Configuration | Display “Voucher for friend” link in my account page (fvc\_b\_position2) | YES | Shows link on the main “My Account” page. |
| Module Configuration | Display “Voucher for friend” link in left/right column (fvc\_b\_position3) | YES | Shows a promotional block/link in side columns for all visitors. |
| Module Configuration | Number of vouchers to generate (FV\_NBC) | 3-5 | Limits how many vouchers a single customer can send. |
| Module Configuration | Allow unlogged users to send vouchers (FV\_UNLOGGED) | NO | Restricts voucher sending to logged-in customers only. |
| Module Configuration | Shop Email (PS\_SHOP\_EMAIL) | Your Store’s Email | Sender email for voucher notifications. |
| Module Configuration | Shop Name (PS\_SHOP\_NAME) | Your Store’s Name | Store name used in voucher notification emails. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers can’t find the “Voucher for friend” link.**
A1: Go to **Modules > Module Manager > Configure** for “Voucher for friend.” Ensure that `fvc_b_position`, `fvc_b_position2`, and `fvc_b_position3` are set to “Yes” for the desired placements (My Account block, My Account page, Left/Right column). Also, check your theme’s hook assignments under **Design > Positions** to ensure the module is hooked to `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn`, or `displayRightColumn` as expected.

**Q2: Friends are not receiving the voucher emails.**
A2:
1. **Check Spam Folders:** Advise your customers to ask their friends to check their spam or junk mail folders.
2. **Shop Email Configuration:** Verify that the `PS_SHOP_EMAIL` setting in the module configuration is a valid and active email address.
3. **PrestaShop Email Settings:** Go to **Advanced Parameters > E-mail** in your PrestaShop back office. Send a test email to ensure your store’s email system is functioning correctly. If not, you might have an issue with your SMTP server configuration.
4. **Server Logs:** Your webmaster can check server mail logs for any errors related to outgoing emails.

**Q3: The voucher code isn’t working for the friend.**
A3:
1. **Check Expiration/Conditions:** Ensure the voucher hasn’t expired and that the friend’s cart meets any minimum purchase requirements or product restrictions that might be set for the generated voucher (these are usually defined in PrestaShop’s native “Cart Rules” section, which this module leverages).
2. **Correct Code Entry:** Confirm the friend is entering the code exactly as it appears (case-sensitive, no extra spaces).
3. **One-Time Use:** Most referral vouchers are one-time use. If the friend previously tried to use it, it might no longer be valid.

**Q4: The module doesn’t look right on my custom theme.**
A4: Custom themes often have unique styling that can sometimes conflict with module designs.
1. **Clear Cache:** First, try clearing your PrestaShop cache under **Advanced Parameters > Performance**.
2. **Theme Overrides:** Your webmaster may need to create CSS overrides in your theme’s stylesheet to adjust the module’s appearance. The module uses `views/css/ps16.css` for its styling, which can be a starting point for adjustments.
3. **Mobile Display:** Ensure your theme is fully responsive. If issues persist on mobile, it’s likely a CSS conflict requiring developer intervention.

**Q5: Can I change the discount amount or type of the voucher?**
A5: The module itself generates a standard PrestaShop cart rule. You would typically configure the specifics of the generated voucher (e.g., percentage discount, fixed amount, minimum purchase, specific products) within PrestaShop’s native **Catalog > Discounts > Cart Rules** section. The module creates the *mechanism* for sharing, but the *details* of the discount are managed by PrestaShop’s core discount system.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Voucher for friend” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Voucher for friend” module follows a standard PrestaShop module architecture, primarily leveraging `ModuleFrontController` for front-office interactions and the main module class for configuration and hook management. It integrates with PrestaShop’s native `CartRule` system to generate and manage discount vouchers. The module’s logic is contained within its main PHP file and dedicated front controllers, with Smarty templates handling presentation.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle the customer-facing logic for generating and managing vouchers.

- **`controllers/front/index.php`**

  - **Class Name:** `FriendvoucherIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller is likely responsible for displaying the initial “Voucher for friend” form where a customer enters their friend’s details. It handles the submission of this form, validates input, generates the `CartRule` (voucher), and sends the email notification to the friend. It also manages the logic for limiting the number of vouchers a customer can send.
  - **Routes:** Responds to a URL like `yourstore.com/module/friendvoucher/index`.
- **`controllers/front/myvoucher.php`**

  - **Class Name:** `FriendvoucherMyvoucherModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller is responsible for displaying the customer’s personal “My Vouchers” page, typically accessed from the “My Account” section. It lists the vouchers the customer has already sent and potentially provides options to view their status or send new ones.
  - **Routes:** Responds to a URL like `yourstore.com/module/friendvoucher/myvoucher`.

#### Back-Office Admin Controllers

This module does not appear to have dedicated custom Admin Controllers. All back-office configuration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, this module does not define custom classes or `ObjectModel`s in a `classes/` directory. It likely uses PrestaShop’s core `CartRule` class for voucher management and `Customer` for user data.

### 4.4 JavaScript Assets (`views/js/`)

- **`lib/voucherengine/script.js`**
  - **Scope:** Front-office.
  - **Details:** This script likely handles client-side interactions on the “Voucher for friend” form. This could include:
    - Form validation (e.g., checking for valid email formats, required fields).
    - AJAX submissions of the voucher request to the `index.php` front controller.
    - Displaying success or error messages to the user without a full page reload.
    - Potentially dynamic updates to the form based on user input.
    - Any interactive elements related to the voucher generation process.

### 4.5 CSS Stylesheets (`views/css/`)

- **`lib/voucherengine/ps16.css`**
  - **Scope:** Front-office customer styling.
  - **Details:** This stylesheet provides the visual styling for the “Voucher for friend” forms, links, and display blocks in the front office. It likely contains styles for:
    - The voucher sharing form elements (input fields, buttons).
    - The “My Vouchers” list on the customer account page.
    - The promotional blocks in the left/right columns.
    - Basic layout and typography to ensure readability.
  - **Key CSS class selectors developers can override:** Developers should inspect the rendered HTML to identify specific class names (e.g., `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) to target for theme integration and customization.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

The module does not explicitly list templates in a `hook/` subdirectory, but the templates listed below are typically rendered via hooks.

- **`views/templates/front/footer.tpl`**

  - **Hook:** `displayFooter`
  - **Outputs:** A link or block related to “Voucher for friend” in the store’s footer.
- **`views/templates/front/leftcolumn.tpl`**

  - **Hook:** `displayLeftColumn`
  - **Outputs:** A promotional block or link for “Voucher for friend” in the left sidebar of the store.
- **`views/templates/front/rightcolumn.tpl`**

  - **Hook:** `displayRightColumn`
  - **Outputs:** A promotional block or link for “Voucher for friend” in the right sidebar of the store.

#### Admin templates (`views/templates/admin/`)

This module does not appear to have custom admin templates. The configuration is likely rendered directly by the `getContent()` method using PrestaShop’s helper forms.

#### Front-office templates (`views/templates/front/`)

These templates are rendered by the module’s front controllers.

- **`views/templates/front/my-account.tpl`**

  - **Hook:** `displayCustomerAccount` (or `displayMyAccountBlock`)
  - **Outputs:** A link or icon on the customer’s main “My Account” page, directing them to the `myvoucher.php` controller.
- **`views/templates/front/my-voucher.tpl`**

  - **Controller:** `FriendvoucherMyvoucherModuleFrontController`
  - **Outputs:** The dedicated page displaying a list of vouchers the customer has sent, their status, and potentially a form to send new ones.

### 4.7 Database Schema & Hooks Map

#### Database Tables

This module does not appear to create custom SQL tables. It likely stores its configuration in `ps_configuration` and leverages PrestaShop’s core `ps_cart_rule` and `ps_cart_rule_lang` tables for the generated vouchers.

#### Registered Hooks Table

The module registers itself to various hooks to display its content and functionality.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displaymyAccountBlock` | Renders in the customer account block (header/column) after login. | Displays a quick link to the voucher page for logged-in users. |
| `displayrightColumn` | Renders content in the right sidebar. | Displays a promotional block/link for the voucher feature. |
| `displayLeftColumn` | Renders content in the left sidebar. | Displays a promotional block/link for the voucher feature. |
| `displayFooter` | Renders content in the store’s footer. | Displays a link to the voucher page in the footer. |
| `displaycustomerAccount` | Renders content on the customer’s main “My Account” page. | Displays a dedicated link/icon for the voucher feature on the account page. |
| `actionValidateOrder` | Executed after an order is successfully validated. | (Potential) Could be used to trigger actions related to referrer rewards or tracking successful referrals, though not explicitly confirmed by file inventory. |

## 5. Official Support & Updates

For official support, module updates, and any further assistance, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). You can access your purchased modules, download the latest versions, and submit support tickets directly from your account.
