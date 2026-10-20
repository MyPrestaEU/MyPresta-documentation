---
title: "Happy Birthday Coupon - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Happy Birthday Coupon PrestaShop module by MyPresta.eu."
sidebar:
  label: "Happy Birthday Coupon - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Happy Birthday Coupon Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Happy Birthday Coupon

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. Ensure your server’s cron job functionality is enabled for automated coupon sending.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Happy Birthday Coupon)

This is the main configuration screen where you define how your birthday coupons will be generated and sent.

#### General Settings

- **Days before customer’s birthday to send coupon (bp\_daysbefore)**

  - **What this setting does:** This determines how many days *before* a customer’s actual birthday the coupon email will be sent.
  - **Effect of changing this setting:**
    - *When set to 0:* The coupon will be sent on the customer’s birthday.
    - *When set to 7:* The coupon will be sent 7 days before the customer’s birthday. This gives them a week to plan a purchase.
  - **Recommended value:** `7` days. This provides customers with enough time to browse your store and make a purchase decision, rather than receiving it on the day itself when they might be busy.
  - **Merchant scenario / example:** You want customers to receive their birthday treat a week in advance so they have time to use it for a special birthday purchase. Setting this to `7` ensures they get the email with ample time.
- **Enable newsletter option (bpro\_nletter)**

  - **What this setting does:** This controls whether the birthday coupon functionality is tied to the customer’s newsletter subscription status.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Only customers who are subscribed to your newsletter will receive a birthday coupon.
    - *When disabled (NO):* All customers with a valid birth date in their account will receive a birthday coupon, regardless of their newsletter subscription.
  - **Recommended value:** `NO`. To maximize the impact and reach, it’s generally better to send birthday coupons to all customers with a birth date, as it’s a personal gesture. However, if you want to reward newsletter subscribers specifically, set it to `YES`.
  - **Merchant scenario / example:** You want to reward all your loyal customers on their birthday, not just those subscribed to your newsletter. You would set this to `NO`.
- **Customer Groups to include (birthdaypro\_groups)**

  - **What this setting does:** This allows you to select specific customer groups that are eligible to receive birthday coupons.
  - **Effect of changing this setting:**
    - *When specific groups are selected:* Only customers belonging to these chosen groups will receive birthday coupons.
    - *When no groups are selected (or all are selected):* All customers (subject to other settings like newsletter option) will be eligible.
  - **Recommended value:** Select `Customer` and any other groups you wish to include. Avoid selecting `Visitor` or `Guest` as they typically don’t have accounts with birth dates.
  - **Merchant scenario / example:** You have a “VIP Customers” group and a “Wholesale” group. You only want to send birthday coupons to your regular “Customer” group and “VIP Customers,” but not to your wholesale partners. You would select “Customer” and “VIP Customers” from the list.
- **List of customers (Informational)**

  - **What this setting does:** This is not a setting to change, but an informational section that likely displays a list of customers who have received or are eligible for birthday coupons. It helps you monitor the module’s activity.
  - **Effect of changing this setting:** No direct effect as it’s a display-only feature.
  - **Recommended value:** N/A
  - **Merchant scenario / example:** You want to quickly see which customers have birth dates recorded and might be receiving coupons soon.

#### Voucher Settings (Advanced Personalization)

The module allows extensive customization of the generated vouchers. These settings mirror the standard PrestaShop cart rule (voucher) options.

- **Voucher Code Prefix:** (e.g., `BIRTHDAY-`)

  - **What this setting does:** Defines a prefix for all generated birthday coupon codes.
  - **Effect of changing this setting:** All unique codes will start with this prefix, making them easily identifiable.
  - **Recommended value:** `BIRTHDAY-` or `BDP-`.
  - **Merchant scenario / example:** You want to easily distinguish birthday coupons from other promotions in your order history.
- **Discount Type:** (e.g., Percentage, Amount, Free Shipping)

  - **What this setting does:** Determines the type of discount the coupon provides.
  - **Effect of changing this setting:**
    - *Percentage:* Applies a percentage discount to the order.
    - *Amount:* Applies a fixed monetary discount.
    - *Free Shipping:* Provides free shipping.
  - **Recommended value:** `Percentage` or `Amount`, depending on your marketing strategy.
  - **Merchant scenario / example:** You want to offer a 15% discount for birthdays. You would select `Percentage` and set the value to `15`.
- **Discount Value:** (e.g., `15` for percentage, `10.00` for amount)

  - **What this setting does:** The actual value of the discount.
  - **Effect of changing this setting:** Directly impacts the discount applied to the customer’s order.
  - **Recommended value:** A value that is attractive but also profitable for your store (e.g., `10` for 10% or `5.00` for $5).
  - **Merchant scenario / example:** Following the above, you’d enter `15` here.
- **Minimum Amount:**

  - **What this setting does:** Sets a minimum purchase amount required for the coupon to be valid.
  - **Effect of changing this setting:** Encourages customers to spend more to qualify for the discount.
  - **Recommended value:** A reasonable amount that encourages upselling without being prohibitive.
  - **Merchant scenario / example:** You want customers to spend at least $50 to use their birthday coupon. You would set this to `50.00`.
- **Validity Period:** (e.g., `30` days)

  - **What this setting does:** Defines how many days the coupon is valid from the date it’s sent.
  - **Effect of changing this setting:** Creates urgency for the customer to use the coupon.
  - **Recommended value:** `30` days. This gives customers a good window to use their gift without feeling rushed.
  - **Merchant scenario / example:** You want customers to use their birthday coupon within a month of receiving it. You would set this to `30`.
- **Apply to Specific Products/Categories:**

  - **What this setting does:** Allows you to restrict the coupon’s use to certain products or categories.
  - **Effect of changing this setting:** Can be used to promote specific items or clear old stock.
  - **Recommended value:** Leave empty unless you have a specific promotional goal.
  - **Merchant scenario / example:** You only want the birthday coupon to be valid for items in your “New Arrivals” category.
- **Other Voucher Options:** (e.g., cumulative with other vouchers, gift products, etc.)

  - **What this setting does:** The module likely exposes other advanced cart rule options from PrestaShop, such as whether the voucher can be combined with other discounts, if it applies to specific carriers, or if it offers a free gift.
  - **Effect of changing this setting:** Gives you fine-grained control over the voucher’s behavior and restrictions.
  - **Recommended value:** Configure based on your specific promotional strategy. Be careful with cumulativity to avoid excessive discounts.
  - **Merchant scenario / example:** You want to ensure the birthday coupon cannot be combined with other ongoing promotions. You would disable the “Cumulative with other vouchers” option.

#### Email Template Settings

- **Email Subject:** (e.g., `Happy Birthday from {shop_name}! Here's a gift for you!`)

  - **What this setting does:** Defines the subject line of the birthday email.
  - **Effect of changing this setting:** This is the first thing customers see; a compelling subject increases open rates.
  - **Recommended value:** Something warm, personal, and clearly indicating a gift. Use `{shop_name}` and `{customer_firstname}` if available.
  - **Merchant scenario / example:** You want a catchy subject line that makes customers feel special.
- **Email Content:** (HTML editor)

  - **What this setting does:** Allows you to customize the full content of the birthday email.
  - **Effect of changing this setting:** This is where you convey your birthday wishes, explain the discount, and encourage shopping.
  - **Recommended value:** Include a warm greeting, clearly state the discount code and its value, explain how to use it, and add a call to action. Use placeholders like `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
  - **Merchant scenario / example:** You want to write a heartfelt message, include your brand’s logo, and clearly show the discount code.

#### Cron Job Information

- **Cron Job URL:** (e.g., `http://yourstore.com/modules/birthdaypro/controllers/front/cron.php?token=YOUR_SECURE_TOKEN`)
  - **What this setting does:** This displays the URL you need to set up as a cron job on your server. This cron job is essential for the module to automatically check for upcoming birthdays and send coupons.
  - **Effect of changing this setting:** This is not a setting to change, but an instruction. If the cron job is not set up correctly, no birthday coupons will be sent automatically.
  - **Recommended value:** Set up a cron job to run this URL once every 24 hours (e.g., daily at midnight).
  - **Merchant scenario / example:** You’ve configured all settings, but no emails are being sent. The first thing to check is if your hosting provider has correctly set up the cron job using this URL.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Days before customer’s birthday to send coupon | `7` | Sends coupon X days before birthday, encouraging planned purchases. |
| Module Configuration | Enable newsletter option | `NO` | Determines if only newsletter subscribers receive coupons. `NO` for wider reach. |
| Module Configuration | Customer Groups to include | `Customer` (and others as needed) | Restricts coupon sending to specific customer segments. |
| Module Configuration | Voucher Code Prefix | `BIRTHDAY-` | Adds a unique prefix to generated coupon codes for easy identification. |
| Module Configuration | Discount Type | `Percentage` or `Amount` | Defines the nature of the discount (e.g., 15% off, $10 off). |
| Module Configuration | Discount Value | `10` (for 10%) or `5.00` (for $5) | The actual value of the discount. |
| Module Configuration | Minimum Amount | (Empty or specific value) | Sets a minimum order value for the coupon to be valid. |
| Module Configuration | Validity Period | `30` days | How long the coupon is valid from the send date, creating urgency. |
| Module Configuration | Apply to Specific Products/Categories | (Empty or specific selection) | Restricts coupon use to certain products or categories. |
| Module Configuration | Other Voucher Options | (As per strategy) | Fine-grained control over voucher behavior (e.g., cumulativity). |
| Module Configuration | Email Subject | `Happy Birthday from {shop_name}!` | The subject line of the birthday email. |
| Module Configuration | Email Content | (Custom HTML) | The body of the birthday email, including greetings and coupon details. |
| Module Configuration | Cron Job URL | (Displayed URL) | Essential for automated daily checks and coupon sending. Must be set up on server. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving birthday emails. What should I check first?**
A1:

1. **Cron Job:** The most common reason. Ensure the cron job URL provided in the module configuration is correctly set up on your hosting server to run daily. Without it, the module cannot automatically send emails.
2. **Customer Birth Dates:** Verify that your customers actually have their birth dates entered in their PrestaShop accounts. The module relies on this data.
3. **Email Configuration:** Check your PrestaShop email settings (Advanced Parameters > E-mail) to ensure your store can send emails successfully. Test sending a general email from PrestaShop.
4. **Spam Folders:** Advise customers to check their spam or junk folders.
5. **Module Settings:** Double-check “Days before customer’s birthday,” “Enable newsletter option,” and “Customer Groups to include” to ensure customers are eligible.

**Q2: The discount code is not working for my customers.**
A2:

1. **Voucher Validity:** Check the “Validity Period” setting in the module. Has the coupon expired?
2. **Minimum Amount:** Does the customer’s cart meet the “Minimum Amount” requirement set for the voucher?
3. **Product/Category Restrictions:** If you applied restrictions, is the customer trying to purchase an eligible product?
4. **Cumulative with other vouchers:** If you disabled this, ensure the customer isn’t trying to combine it with another discount.
5. **Typos:** Ask the customer to double-check for any typos when entering the code.

**Q3: How do I change the look and feel of the birthday email?**
A3: You can fully customize the email content using the HTML editor in the “Email Content” setting on the module’s configuration page. You can add your logo, change fonts, colors, and layout. Make sure to use the available placeholders (like `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) to personalize the message.

**Q4: Can I send different birthday coupons to different customer groups?**
A4: The Happy Birthday Coupon module, in its standard configuration, sends one type of coupon based on the settings you define. To send different coupons to different groups (e.g., a 10% discount for regular customers and a 20% discount for VIPs), you would need to either:
a) Manually create and send separate vouchers for specific groups (defeating the automation).
b) Use PrestaShop’s native “Cart Rules” for specific groups and manage them manually.
c) Consider advanced customization or a more complex marketing automation solution if this is a critical requirement.

**Q5: The module seems to be running, but I don’t see any evidence of coupons being generated in PrestaShop’s “Cart Rules” section.**
A5: The module generates unique cart rules (vouchers) dynamically when a customer’s birthday approaches. These are actual PrestaShop cart rules. You should be able to see them in **Catalog > Discounts > Cart Rules** (or **Price Rules > Cart Rules** in older versions). Look for rules with the prefix you defined (e.g., `BIRTHDAY-`). If they are not appearing, re-check your cron job setup and module configuration.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the Happy Birthday Coupon module.

### 4.1 Architecture Overview

The Happy Birthday Coupon module (`birthdaypro`) follows a standard PrestaShop module architecture, leveraging `Module` as its base. It primarily functions through a cron job that triggers a front controller to identify eligible customers and generate PrestaShop `CartRule` objects. The module does not extend `ObjectModel` for its own data but relies on existing PrestaShop customer data and `CartRule` functionality. It uses a custom voucher engine and an autocomplete search tool, likely for back-office customer selection or testing.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are designed to be accessed externally, primarily via cron jobs.

- **`controllers/front/cron.php`**

  - **Class name & parent class:** `BirthdayproCronModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the core logic for automated coupon generation and sending. It is designed to be called by a server-side cron job.
    - It fetches customer birth dates.
    - Determines which customers are eligible based on `bp_daysbefore`, `bpro_nletter`, and `birthdaypro_groups` configuration.
    - For each eligible customer, it generates a unique PrestaShop `CartRule` (voucher) with the configured parameters.
    - Sends a birthday email containing the voucher code to the customer.
    - Includes a security token check to prevent unauthorized access.
- **`controllers/front/index.php`**

  - **Class name & parent class:** `BirthdayproIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller likely serves as a placeholder or a simple entry point, possibly for testing or for handling requests that don’t match other specific front controllers. In many modules, an `index.php` in a controller directory is a fallback or a basic “hello world” type of controller. It might not have significant business logic.

#### Back-Office Admin Controllers

The module does not appear to have dedicated custom Admin Controllers based on the provided inventory. All back-office configuration is handled within the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes or models in the `classes/` directory. The module likely leverages PrestaShop’s native `Customer`, `CartRule`, and `Mail` classes directly. The “voucherengine” and “searchTool” mentioned in JS/CSS paths suggest internal helper classes or functions within `birthdaypro.php` or its included libraries, rather than standalone `classes/` files.

### 4.4 JavaScript Assets (`views/js/`)

- **`lib/searchTool/views/js/autocomplete.js`**

  - **Scope:** Likely Back-office.
  - **Details:** This script provides autocomplete functionality, probably for searching customers or products within the module’s configuration or a related admin interface. It would bind to input fields, make AJAX requests to a backend endpoint (possibly the main module file or a dedicated admin controller if one existed), and display suggestions.
- **`lib/voucherengine/script.js`**

  - **Scope:** Likely Back-office.
  - **Details:** This script is part of the module’s “voucher engine.” It likely handles dynamic form elements related to voucher creation within the module’s configuration page. This could include showing/hiding fields based on discount type selection, validating input for voucher values, or interacting with other voucher-related settings.

### 4.5 CSS Stylesheets (`views/css/`)

- **`lib/searchTool/views/css/autocomplete.css`**

  - **Scope:** Likely Back-office.
  - **Details:** Provides styling for the autocomplete suggestions dropdown and possibly the input field itself, ensuring it integrates visually with the PrestaShop back office.
- **`lib/voucherengine/ps16.css`**

  - **Scope:** Likely Back-office.
  - **Details:** This stylesheet provides specific styling for the voucher configuration elements, potentially targeting PrestaShop 1.6 back-office aesthetics. It might include styles for form groups, input fields, and labels related to the voucher settings.
- **`views/css/css.css`**

  - **Scope:** Likely Back-office.
  - **Details:** A general stylesheet for the module, potentially containing styles for the main configuration page (`admin.tpl`) or any custom elements introduced by the module in the back office. It might include basic layout, button, or alert styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`lib/searchTool/views/scripts.tpl`**

  - **Scope:** Back-office.
  - **Details:** This template likely includes JavaScript code or Smarty variables needed for the `autocomplete.js` script to function correctly, such as AJAX URLs, language strings, or initial data. It would be included in the main admin configuration template.
- **`views/templates/admin.tpl`**

  - **Scope:** Back-office.
  - **Details:** This is the primary template for the module’s configuration page, rendered by the `getContent()` method in `birthdaypro.php`. It contains the HTML structure for all the settings described in Section 4.1, including form fields, buttons, and potentially includes for other templates like `scripts.tpl`.
- **`views/templates/script.tpl`**

  - **Scope:** Back-office.
  - **Details:** Similar to `scripts.tpl` in the `searchTool` library, this template likely contains module-specific JavaScript or Smarty variables that are injected into the back-office configuration page. It might handle dynamic behavior or data passing for the voucher engine.
- **`views/templates/test.tpl`**

  - **Scope:** Back-office or internal testing.
  - **Details:** This template’s purpose is less clear from the name alone. It could be a template used for internal testing during development, a debug output template, or a simple placeholder. It’s unlikely to be part of the standard merchant-facing configuration.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom database tables based on the provided inventory.
  - It stores its configuration settings (e.g., `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) in PrestaShop’s `ps_configuration` table.
  - It interacts with existing PrestaShop tables: `ps_customer` (for birth dates), `ps_cart_rule` (for creating vouchers), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing / Context | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Typically used for adding CSS, JS, or meta tags. The module description mentions it, but its primary function is cron-based, so this hook might be used for minimal front-end setup or not actively used for core functionality. |
| `displayRightColumn` | In the right column of front-office pages. | Displays content in the right sidebar. Unlikely to be used by this module given its background operation. |
| `displayLeftColumn` | In the left column of front-office pages. | Displays content in the left sidebar. Unlikely to be used by this module given its background operation. |
| `displayFooter` | In the footer section of every front-office page. | Displays content in the footer. Unlikely to be used by this module given its background operation. |
| `displayProductButtons` / `displayProductExtraContent` (or similar Product hooks) | On the product page. | Unlikely to be used by this module. |
| `actionValidateOrder` | After an order has been successfully validated. | Could potentially be used to track coupon usage or customer behavior after a birthday coupon is applied, though not explicitly listed as a core function. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | When a customer account is created or updated. | Could be used to check for birth date entry or trigger initial setup for new customers, though the cron job is the primary trigger. |
| (Implicit) Cron Job Execution | Daily, via external server cron. | **CRITICAL:** This is the primary “hook” for the module’s core functionality, triggering `controllers/front/cron.php` to process birthdays and send emails. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Happy Birthday Coupon module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to ensuring your module functions optimally and helps you achieve your e-commerce goals.
