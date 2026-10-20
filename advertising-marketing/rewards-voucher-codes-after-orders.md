---
title: "Rewards - Voucher codes after orders - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Rewards - Voucher codes after orders PrestaShop module by MyPresta.eu."
sidebar:
  label: "Rewards - Voucher codes after orders - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Rewards - Voucher codes after orders Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Rewards - Voucher codes after orders

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop store to function correctly. This module does not have any unusual or additional hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Rewards - Voucher codes after orders)

This is the main configuration screen where you define the rules for generating and sending voucher codes.

#### General Settings

- **Enable module:**

  - **What this setting does:** This is the master switch for the module.
  - **Effect of changing this setting:**
    - *When enabled:* The module will actively monitor orders and generate/send vouchers according to your rules.
    - *When disabled:* The module will be inactive, and no vouchers will be generated or sent, regardless of other settings.
  - **Recommended value:** YES
  - **Merchant scenario / example:** You’ve finished setting up all your rules and are ready to launch your rewards program. Enable this to start sending vouchers. If you need to temporarily pause the program for maintenance, disable it.
- **Order States for Voucher Generation:**

  - **What this setting does:** Determines which order statuses will trigger the voucher generation process. Only orders that reach one of these selected statuses will qualify for a reward.
  - **Effect of changing this setting:**
    - *When selected:* Orders with these statuses will be checked for voucher eligibility.
    - *When unselected:* Orders with these statuses will be ignored by the module.
  - **Recommended value:** Typically “Payment accepted” and “Delivered”. You might also include “Shipped” if you want to send the voucher earlier.
  - **Merchant scenario / example:** You want to ensure customers only receive a voucher after their payment is confirmed and the order is being processed or has been delivered. Select “Payment accepted” and “Delivered” to prevent sending vouchers for cancelled or pending orders.
- **Minimum Order Total for Voucher:**

  - **What this setting does:** Sets a minimum total value (excluding shipping) that an order must meet to qualify for a voucher.
  - **Effect of changing this setting:**
    - *When set to a value (e.g., 50):* Only orders with a total greater than or equal to 50 will trigger a voucher.
    - *When set to 0 (or empty):* All orders, regardless of value, will be eligible (if other conditions are met).
  - **Recommended value:** A value that makes business sense for your average order value, or 0 if you want to reward all orders.
  - **Merchant scenario / example:** You want to encourage larger purchases. Set this to €50 so only customers spending €50 or more receive a discount, making the voucher a reward for higher-value transactions.

#### Voucher Code Settings

- **Voucher Code Prefix:**

  - **What this setting does:** A string of characters that will appear at the beginning of every generated voucher code. This helps you identify vouchers from this module.
  - **Effect of changing this setting:**
    - *When set (e.g., “REWARD”):* Codes will look like “REWARDABCD123”.
    - *When empty:* Codes will be purely random characters.
  - **Recommended value:** A short, descriptive prefix like “REWARD”, “THANKYOU”, or your store’s initials.
  - **Merchant scenario / example:** You run multiple promotions. Using “REWARD” as a prefix helps you quickly identify which vouchers came from this module in your PrestaShop discount rules.
- **Voucher Code Length:**

  - **What this setting does:** Defines the total number of characters in the generated voucher code (including the prefix).
  - **Effect of changing this setting:**
    - *When set to 10 with a “REWARD” prefix:* The random part will be 4 characters long (10 - 6 for “REWARD”).
    - *When set to a lower number:* Shorter codes, potentially easier to type but less unique.
    - *When set to a higher number:* Longer codes, more secure but harder to type.
  - **Recommended value:** 8-12 characters (including prefix) for a good balance of security and usability.
  - **Merchant scenario / example:** You want codes to be easy to remember but still unique. A length of 10-12 characters is usually sufficient.
- **Voucher Value Type:**

  - **What this setting does:** Determines if the voucher offers a percentage discount or a fixed amount.
  - **Effect of changing this setting:**
    - *Percentage:* The voucher will deduct a percentage of the order total.
    - *Fixed Amount:* The voucher will deduct a specific monetary value.
  - **Recommended value:** Depends on your marketing strategy. Percentage is good for encouraging larger orders, fixed amount is simpler and clearer.
  - **Merchant scenario / example:** You want to give 10% off the next order, so you select “Percentage”. If you want to give a flat €5 discount, select “Fixed Amount”.
- **Voucher Value:**

  - **What this setting does:** The actual discount value. This will be a percentage (e.g., 10) or a fixed amount (e.g., 5.00) depending on the “Voucher Value Type” setting.
  - **Effect of changing this setting:**
    - *When set to 10 and “Percentage”:* Customers get 10% off.
    - *When set to 5.00 and “Fixed Amount”:* Customers get €5 off.
  - **Recommended value:** A value that makes the offer attractive but is sustainable for your business.
  - **Merchant scenario / example:** You decide to offer a 15% discount, so you enter “15” here after selecting “Percentage” above.
- **Minimum Order Total for Voucher Usage:**

  - **What this setting does:** Sets a minimum purchase amount required for the customer to be able to use the generated voucher code.
  - **Effect of changing this setting:**
    - *When set to 20:* The customer must spend at least €20 on their next order to apply the voucher.
    - *When set to 0 (or empty):* The voucher can be used on any order, regardless of its value.
  - **Recommended value:** A value slightly higher than your average order value to encourage upselling, or 0 if you want maximum usability.
  - **Merchant scenario / example:** You want to ensure the voucher encourages a new purchase, not just a small add-on. Set this to €25, so the customer needs to buy something substantial to use their €5 voucher.
- **Voucher Validity (Days):**

  - **What this setting does:** Defines how many days the generated voucher code will be valid from the date it’s created.
  - **Effect of changing this setting:**
    - *When set to 30:* The voucher will expire 30 days after it’s sent.
    - *When set to 0 (or empty):* The voucher will be valid indefinitely (not recommended, as it removes urgency).
  - **Recommended value:** 30-90 days to create urgency without being too restrictive.
  - **Merchant scenario / example:** You want customers to use their voucher within a reasonable timeframe. Set this to 60 days to give them two months to make another purchase.
- **Apply Voucher to Specific Customer Groups:**

  - **What this setting does:** Allows you to restrict the usage of the generated voucher to specific customer groups (e.g., “VIP Customers”, “Wholesalers”).
  - **Effect of changing this setting:**
    - *When selected:* Only customers belonging to the chosen groups can use the voucher.
    - *When unselected (or all groups selected):* Any customer can use the voucher.
  - **Recommended value:** Leave all selected unless you have a specific segmentation strategy.
  - **Merchant scenario / example:** You want to offer a special discount only to your “Registered Customers” group. Select only that group here.
- **Apply Voucher to Specific Products/Categories:**

  - **What this setting does:** Allows you to restrict the voucher’s applicability to certain products or product categories.
  - **Effect of changing this setting:**
    - *When selected:* The voucher will only apply to items from the chosen products/categories.
    - *When unselected (or none selected):* The voucher applies to all products in the cart.
  - **Recommended value:** Leave unselected for general store-wide discounts. Use this for targeted promotions.
  - **Merchant scenario / example:** You want to promote a specific new collection. You can configure the voucher to only apply to products within that category.
- **Exclude Discounted Products:**

  - **What this setting does:** If enabled, the voucher cannot be used on products that are already on sale or have a specific price.
  - **Effect of changing this setting:**
    - *When enabled:* Prevents “stacking” discounts, ensuring customers don’t get double discounts.
    - *When disabled:* Vouchers can be applied to already discounted items.
  - **Recommended value:** YES, to protect your profit margins.
  - **Merchant scenario / example:** You’re running a store-wide 20% sale. You don’t want customers to use their reward voucher on top of that, effectively giving them 30% off. Enable this to prevent it.
- **Exclude Shipping:**

  - **What this setting does:** Determines if the voucher discount applies to the shipping cost of the order.
  - **Effect of changing this setting:**
    - *When enabled:* The voucher only reduces the product total, not the shipping fee.
    - *When disabled:* The voucher can reduce the total order value, including shipping.
  - **Recommended value:** YES, as shipping costs are often fixed and not part of your product margin.
  - **Merchant scenario / example:** You offer free shipping above a certain threshold. You want the voucher to only affect product prices, not the shipping cost. Enable this.
- **Voucher for Nth Order:**

  - **What this setting does:** This is a powerful feature that allows you to specify for which order number (1st, 2nd, 3rd, etc.) a customer receives a voucher.
  - **Effect of changing this setting:**
    - *When set to 1:* Only the customer’s very first order will trigger a voucher.
    - *When set to 2:* Only their second order will trigger a voucher.
    - *When set to 0 (or empty):* Every qualifying order will trigger a voucher (if other conditions are met).
  - **Recommended value:** 1 for a “welcome back” offer, or 0 for a general loyalty program. You can also create multiple rules (see section 4.2) for different Nth orders.
  - **Merchant scenario / example:** You want to give a special “thank you” to first-time buyers. Set this to “1”. For a general loyalty program, leave it at “0” or create specific rules for 2nd, 3rd, etc., orders.

#### Email Template Settings

- **Email Subject:**

  - **What this setting does:** The subject line of the email that customers receive containing their voucher code.
  - **Effect of changing this setting:** This is what customers see in their inbox. A compelling subject line increases open rates.
  - **Recommended value:** Something engaging like “Your Special Discount for Your Next Order!” or “Thank You! Here’s a Gift From Us.”
  - **Merchant scenario / example:** You want to make it clear this is a reward. Set the subject to “Your Exclusive Voucher from [Your Store Name]!”
- **Email Content:**

  - **What this setting does:** The main body of the email. You can use placeholders like `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}` to personalize the message.
  - **Effect of changing this setting:** This is where you communicate the value of the voucher and how to use it. A clear, friendly message encourages usage.
  - **Recommended value:** A welcoming message, clear instructions, and all relevant voucher details.
  - **Merchant scenario / example:** “Dear {customer\_name}, thank you for your recent purchase! As a token of our appreciation, here is a {voucher\_value} discount code for your next order: **{voucher\_code}**. This voucher is valid for {validity\_days} days and can be used on orders over {min\_order\_total}. Happy shopping!”
- **Send email to customer:**

  - **What this setting does:** Controls whether the email containing the voucher is actually sent to the customer.
  - **Effect of changing this setting:**
    - *When enabled:* Customers receive the email.
    - *When disabled:* Vouchers are still generated (if enabled), but customers do not receive an email notification. You would then need to communicate the voucher code through another channel.
  - **Recommended value:** YES, as email is the primary delivery method for this module.
  - **Merchant scenario / example:** You’ve set up everything and want customers to receive their rewards. Enable this. If you’re testing or prefer to manually send codes, you might disable it temporarily.

#### Cron Job Settings

- **Cron Job URL:**
  - **What this setting does:** This is a unique URL that, when accessed, triggers the module to check for new qualifying orders and generate/send vouchers.
  - **Effect of changing this setting:** This URL is crucial for the module’s automation. It needs to be called regularly.
  - **Recommended value:** Do NOT change this URL. Copy it and set it up in your hosting control panel.
  - **Merchant scenario / example:** You copy this URL and paste it into your hosting provider’s cron job manager (e.g., cPanel, Plesk) to run every 15-30 minutes. This ensures vouchers are sent out promptly after orders are processed.

### 2.2 Dedicated Admin Screen: Rewards List (Back Office > Rewards > Rewards List)

This screen provides a comprehensive overview of all the voucher codes that have been generated by the module. It acts as a log and management interface for your reward program.

- **Screen Name & Menu Location:** **Rewards List** (found under a new “Rewards” menu item in your PrestaShop Back Office, or potentially under “Catalog” or “Marketing” depending on your PrestaShop version and theme).
- **Available Actions & Settings:**
  - **Table Columns:** You’ll see a table with the following columns:
    - **ID:** The unique identifier for the reward entry.
    - **Order ID:** The ID of the PrestaShop order that triggered this reward.
    - **Customer:** The name of the customer who received the voucher.
    - **Email:** The customer’s email address.
    - **Order reference:** The unique reference number of the order.
    - **Reward code:** The actual voucher code generated and sent to the customer.
    - **Generation date:** The date and time when the voucher was generated.
  - **Filtering & Searching:** You can typically filter or search by any of these columns (e.g., search for a specific customer email, order ID, or voucher code) to find specific reward entries.
  - **No “Add/Edit” buttons:** This screen is primarily for viewing generated rewards. Vouchers are automatically created based on your configuration, not manually added here.
- **Effect of changes:** This screen is a read-only log. Changes to the module’s configuration (Section 4.1) will affect *future* voucher generations, but existing entries here reflect past events.
- **Recommended workflow for daily store management:**
  - Periodically check this list to monitor the activity of your rewards program.
  - If a customer claims they didn’t receive a voucher, you can quickly look up their order here, find the “Reward code”, and confirm its generation date. You can then manually provide the code to the customer if needed.
  - Use the filtering options to analyze which orders are triggering rewards or to troubleshoot specific customer inquiries.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable module | YES | Master switch for the module’s functionality. |
|  | Order States for Voucher Generation | Payment accepted, Delivered | Defines which order statuses trigger voucher generation. |
|  | Minimum Order Total for Voucher | 0 (or your desired value) | Minimum order value for an order to qualify for a voucher. |
|  | Voucher Code Prefix | REWARD (or your choice) | Prefix for generated voucher codes. |
|  | Voucher Code Length | 8-12 | Total length of the voucher code. |
|  | Voucher Value Type | Percentage / Fixed Amount | Choose between a percentage or fixed amount discount. |
|  | Voucher Value | Your desired value (e.g., 10 or 5.00) | The actual discount value of the voucher. |
|  | Minimum Order Total for Voucher Usage | 0 (or your desired value) | Minimum order value required to *use* the voucher. |
|  | Voucher Validity (Days) | 30-90 | How many days the voucher is valid after generation. |
|  | Apply Voucher to Specific Customer Groups | All selected | Restricts voucher usage to selected customer groups. |
|  | Apply Voucher to Specific Products/Categories | None selected | Restricts voucher usage to selected products/categories. |
|  | Exclude Discounted Products | YES | Prevents vouchers from applying to already discounted items. |
|  | Exclude Shipping | YES | Prevents vouchers from reducing shipping costs. |
|  | Voucher for Nth Order | 0 (or 1 for first order) | Specifies for which order number (1st, 2nd, etc.) a voucher is generated. |
|  | Email Subject | Your Special Discount! | Subject line of the email containing the voucher. |
|  | Email Content | Personalized message with placeholders | Body of the email, including voucher details. |
|  | Send email to customer | YES | Controls whether the voucher email is sent to the customer. |
|  | Cron Job URL | Do NOT change | Essential URL for automated voucher generation. |
| **Rewards List** | ID, Order ID, Customer, Email, Order reference, Reward code, Generation date | N/A (read-only) | Displays a log of all generated vouchers for monitoring and troubleshooting. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers aren’t receiving voucher emails. What should I check?**
A:

1. **Module Enabled?** Double-check that “Enable module” is set to YES in the module configuration.
2. **Order Statuses:** Ensure the order’s status matches one of the “Order States for Voucher Generation” you selected.
3. **Cron Job:** Verify your cron job is set up correctly and running regularly on your hosting. The “Cron Job URL” must be called for the module to process orders.
4. **Email Sending Enabled:** Make sure “Send email to customer” is set to YES.
5. **Spam Folder:** Ask customers to check their spam or junk folders.
6. **PrestaShop Email Settings:** Check your PrestaShop’s main email configuration (Advanced Parameters > E-mail) to ensure emails are being sent successfully from your store.

**Q: Vouchers are being generated, but they don’t seem to work for customers.**
A:

1. **Voucher Validity:** Check the “Voucher Validity (Days)” setting. Has the voucher expired?
2. **Minimum Order Total for Usage:** Does the customer’s current cart meet the “Minimum Order Total for Voucher Usage”?
3. **Customer Groups:** Is the customer part of the “Apply Voucher to Specific Customer Groups” selected?
4. **Product/Category Restrictions:** Are the products in the customer’s cart eligible based on “Apply Voucher to Specific Products/Categories”?
5. **Excluded Discounted Products:** Is the customer trying to use the voucher on an already discounted product, and “Exclude Discounted Products” is enabled?
6. **Typos:** Ask the customer to double-check the voucher code for any typos.

**Q: I want to offer different vouchers for different order numbers (e.g., 1st, 2nd, 5th order). How do I do this?**
A: The module’s description indicates support for “many kind of actions like: voucher for first order, voucher for second order, fifth, sixth etc.” This implies the module has a mechanism to define multiple rules based on the Nth order.

- **Check for Multiple Rule Tabs:** Look for additional tabs or sections within the module’s configuration that allow you to “Add New Rule” or define separate configurations for different “Nth Order” values. If such an interface exists, you would create a separate rule for each Nth order with its specific voucher settings.
- **If only one “Voucher for Nth Order” field exists:** If the module only presents a single “Voucher for Nth Order” field on the main configuration page, it means you can only set *one* such rule at a time. To implement a tiered system, you would need to manually change this setting after a certain period or consider if the module’s current version supports this advanced functionality through a less obvious interface. For most users, setting it to `0` (every order) or `1` (first order only) is the primary use case.

**Q: The module is slowing down my Back Office / Front Office.**
A: This module primarily operates in the background via a cron job and has minimal impact on front-office performance. If you notice slowdowns:

1. **Clear Cache:** Go to **Advanced Parameters > Performance** and clear your PrestaShop cache.
2. **Check Server Resources:** Monitor your server’s CPU and memory usage, especially when the cron job runs. If your server is underpowered, even simple tasks can cause slowdowns.
3. **Other Modules:** Temporarily disable other recently installed modules to see if there’s a conflict.

**Q: Can I customize the email template further?**
A: Yes, the module provides “Email Subject” and “Email Content” fields with placeholders for basic customization. For advanced design changes (e.g., adding your store’s logo, changing fonts/colors), you would typically need to modify the module’s email template files directly. This usually requires a webmaster or developer. The module’s internal structure suggests it uses `lib/emailTemplatesManager`, which might offer more advanced template management within the module itself, but the primary configuration is via the text fields.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Rewards - Voucher codes after orders” module follows a standard PrestaShop module architecture, leveraging MVC principles where applicable. Its core functionality revolves around a cron job mechanism that periodically checks for qualifying orders and, upon finding them, generates PrestaShop `CartRule` objects (vouchers) and dispatches emails. The module extends `Module` for its main functionality and uses `AdminController` for its Back Office management interface. It also incorporates several utility libraries for email template management and search functionality.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/cronJob.php`
  - **Class Name:** `OrdercouponsCronJobModuleFrontController` (likely, based on file name)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is designed to be accessed via the Cron Job URL provided in the module configuration. When invoked, it triggers the main logic within the `cronjob.php` module file to process orders, generate vouchers, and send emails. It typically does not render any front-office content but executes background tasks.
- `controllers/front/index.php`
  - **Class Name:** `OrdercouponsIndexModuleFrontController` (likely)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This is often a placeholder or a simple redirect controller. In many modules, `index.php` in a controller directory simply ensures that direct access to the directory doesn’t result in a directory listing, or it might contain minimal logic for a default front-office view if the module had one. For this module, it’s unlikely to have significant front-office rendering responsibility.

#### Back-Office Admin Controllers

- `controllers/admin/AdminOrderCouponsRewards.php`
  - **Class Name:** `AdminOrderCouponsRewardsController`
  - **Parent Class:** `ModuleAdminController` (or `AdminController` in older versions)
  - **Tab Name:** “Rewards List” (under a “Rewards” menu item)
  - **Managed Entity:** `orewards_list` (likely a custom database table for logging generated rewards).
  - **Responsibility:** This controller manages the “Rewards List” in the PrestaShop Back Office. It displays a list of all generated voucher codes, associated order IDs, customer details, and generation dates. It uses `HelperList` for rendering the table and provides filtering capabilities. It does not allow manual creation or editing of rewards, as they are automatically generated.
- `controllers/admin/index.php`
  - **Class Name:** `AdminOrdercouponsIndexController` (likely)
  - **Parent Class:** `ModuleAdminController` (or `AdminController`)
  - **Responsibility:** Similar to the front-office `index.php`, this is likely a placeholder or a default controller for the admin section, ensuring directory protection or providing a fallback view. The primary admin functionality is handled by `AdminOrderCouponsRewards.php`.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes in the `classes/` directory. This suggests that the module’s core logic for voucher generation might be directly within the main `cronjob.php` module file or leverages PrestaShop’s built-in `CartRule` (Discount) `ObjectModel` and its associated methods.

- **`CartRule` Interaction:** The module would directly interact with PrestaShop’s `CartRule` class to create new discount codes. This involves setting properties like `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping`, etc., based on the module’s configuration.
- **Custom Table `orewards_list`:** Although no `ObjectModel` is explicitly listed, the `AdminOrderCouponsRewardsController` manages `orewards_list`. This strongly implies a custom database table `ps_orewards_list` (or similar prefix) exists to log the generated rewards. The controller would directly query this table or use a simple data access layer.

### 4.4 JavaScript Assets (`views/js/`)

- `ordercoupons/js/script.js`
  - **Scope:** Likely Back-office.
  - **Responsibility:** General JavaScript for the module’s configuration page or admin screens. This could include form validation, AJAX calls for saving settings, dynamic UI updates, or event listeners for specific configuration options.
- `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Scope:** Back-office.
  - **Responsibility:** Manages the email template editing interface. This script would handle the dynamic insertion of placeholders, rich text editing capabilities, preview functionality, and saving of email content.
- `ordercoupons/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Responsibility:** Provides autocomplete functionality for input fields, likely used for selecting specific products, categories, or customer groups within the module’s configuration forms. It would handle AJAX requests to fetch search results and display them to the user.
- `ordercoupons/lib/voucherengine/script.js`
  - **Scope:** Back-office.
  - **Responsibility:** Specific JavaScript related to the voucher generation engine. This might include logic for dynamic calculation of voucher code length, validation of voucher values, or interaction with the `CartRule` settings in the configuration form.

### 4.5 CSS Stylesheets (`views/css/`)

- `ordercoupons/css.css`
  - **Scope:** Primarily Back-office, potentially some front-office if the module had visible elements. Given the module’s nature, it’s mostly for admin styling.
  - **Main UI components:** General styling for the module’s configuration page and the “Rewards List” table.
  - **Key CSS class selectors:** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
- `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Scope:** Back-office.
  - **Main UI components:** Styles for the email template editor interface, including text areas, buttons, and preview sections.
  - **Key CSS class selectors:** `.email-template-editor`, `.template-preview`.
- `ordercoupons/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Main UI components:** Styling for the autocomplete dropdowns and input fields.
  - **Key CSS class selectors:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
- `ordercoupons/lib/voucherengine/ps16.css`
  - **Scope:** Back-office.
  - **Main UI components:** Specific styling adjustments for PrestaShop 1.6 compatibility or specific elements related to the voucher engine, ensuring consistent look and feel across different PS versions.
  - **Key CSS class selectors:** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

The inventory does not list any templates directly under `views/templates/hook/`. This confirms that the module does not render any visual content directly into standard PrestaShop hooks like `displayHeader`, `displayRightColumn`, `displayFooter`, etc. Its front-office interaction is purely via email.

#### Admin templates (`views/templates/admin/`)

- `ordercoupons/views/templates/admin/admin.tpl`
  - **Purpose:** The main template for the module’s configuration page (accessed via `getContent()` in `cronjob.php`). It would contain the form structure for all the settings described in Section 4.1.
- `ordercoupons/views/templates/admin/customerGroups.tpl`
  - **Purpose:** A partial template likely used within `admin.tpl` to render the selection interface for “Apply Voucher to Specific Customer Groups”.
- `ordercoupons/views/templates/admin/orderstates.tpl`
  - **Purpose:** A partial template likely used within `admin.tpl` to render the selection interface for “Order States for Voucher Generation”.
- `ordercoupons/views/templates/admin/scripts.tpl`
  - **Purpose:** A partial template used to include JavaScript files or inline JavaScript specific to the admin configuration page. This is a common practice to keep JS separate from the main HTML structure.

#### Front-office templates (`views/templates/front/`)

The inventory does not list any templates directly under `views/templates/front/`. This is consistent with the module’s behavior of not displaying front-office content.

#### Library Templates

- `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Purpose:** These templates are part of the `emailTemplatesManager` library and are used to render the interface for managing and editing email templates within the module’s configuration. `mainForm.tpl` would likely be the primary entry point, with others being partials for specific UI elements.
- `ordercoupons/lib/searchTool/views/scripts.tpl`
  - **Purpose:** A template to include JavaScript files or inline scripts for the `searchTool` library, specifically for the autocomplete functionality.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- **`ps_configuration`**: The module stores its configuration settings (e.g., `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) in the standard PrestaShop `ps_configuration` table.
- **`ps_orewards_list` (Implied Custom Table)**: Based on the `AdminOrderCouponsRewardsController` managing `orewards_list`, it is highly probable that the module creates a custom database table, likely named `ps_orewards_list`, to log each generated voucher.
  - **Schema (Likely Fields):**
    - `id_orewards_list` (PRIMARY KEY, INT)
    - `id_order` (INT)
    - `id_customer` (INT)
    - `customer_email` (VARCHAR)
    - `order_reference` (VARCHAR)
    - `reward_code` (VARCHAR)
    - `date_add` (DATETIME)

#### Registered Hooks Table

The module’s description mentions “Front-Office Hooks: Header, Columns, Product, or Footer”. However, the file inventory and module’s core function (emailing vouchers) suggest these are likely *not* used for displaying content, but perhaps for internal processing or asset loading if the module had any front-end components. Given the module’s nature, the most critical hooks are action hooks.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionValidateOrder` | After an order has been successfully validated and saved to the database. | This is the most likely hook for the module to detect new orders that need to be processed for voucher generation. The module would listen to this event to identify potential candidates. |
| `actionOrderStatusPostUpdate` | After an order’s status has been changed in the Back Office. | Crucial for the module to check if an order has reached one of the configured “Order States for Voucher Generation” (e.g., “Payment accepted”, “Delivered”). This is where the cron job would likely trigger the voucher generation logic. |
| `displayBackOfficeHeader` | Renders content in the `<head>` section of the Back Office. | Used to include module-specific CSS and JavaScript files for the admin configuration pages and the “Rewards List” screen. |
| `moduleRoutes` | Allows modules to define custom friendly URLs. | Less likely for this module, but possible if it needed a specific route for its cron job or other internal processes. |
| `displayHeader` | Renders content in the `<head>` section of the front office. | If the module needed to load any global JS/CSS for potential future front-end features, or for tracking purposes. (Unlikely for current functionality). |
| `displayRightColumn` / `displayLeftColumn` | Renders content in the side columns of the front office. | Not used for this module’s current functionality. |
| `displayFooter` | Renders content in the footer of the front office. | Not used for this module’s current functionality. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Rewards - Voucher codes after orders” module, please refer to your customer account at MyPresta.eu. You can download the newest versions from your order history and access dedicated support channels for any technical assistance or inquiries.
