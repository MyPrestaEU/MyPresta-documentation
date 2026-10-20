---
title: "Vouchers Generator - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Vouchers Generator PrestaShop module by MyPresta.eu."
sidebar:
  label: "Vouchers Generator - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Vouchers Generator Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/vouchers-generator/)
>
> ---


# Vouchers Generator

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installing the module, navigate to **Modules > Module Manager** and click “Configure” next to “Vouchers Generator”. This is the main screen where you will manage all settings and generate your vouchers.

The configuration page is designed to be intuitive, allowing you to define the rules for your new vouchers and then generate them.

#### **1. Voucher Generation Settings**

This section allows you to define the core properties of the vouchers you want to generate.

- **Name:**

  - **What this setting does:** This is the name that will appear in your PrestaShop Back Office under “Catalog > Discounts > Cart Rules” for the generated batch of vouchers. It’s also the base name for the individual voucher codes (e.g., if you set “SUMMER2024”, codes might be “SUMMER2024-ABCDE”, “SUMMER2024-FGHIJ”).
  - **Effect of changing this setting:** A clear and descriptive name helps you identify the purpose of the voucher batch later.
  - **Recommended value:** Something descriptive like “Summer Sale 2024”, “New Customer Welcome”, or “Abandoned Cart Recovery”.
  - **Merchant scenario / example:** You’re running a summer promotion. You might name it “SUMMER2024”.
- **Description:**

  - **What this setting does:** An internal note for your reference, visible only in the Back Office. It helps you remember the specific details or goals of this voucher campaign.
  - **Effect of changing this setting:** Provides context for you and your team.
  - **Recommended value:** A brief explanation, e.g., “20% off all orders over $50, valid for 1 month, distributed via email newsletter.”
  - **Merchant scenario / example:** For the “SUMMER2024” campaign, you might add “20% off all products, minimum purchase $50, valid until August 31st.”
- **Highlight:**

  - **What this setting does:** If enabled, this voucher will be displayed in the cart summary for all customers, even if they haven’t entered it. This is typically used for general, public promotions.
  - **Effect of changing this setting:**
    - *When enabled:* The voucher appears automatically in the cart summary, encouraging customers to use it.
    - *When disabled:* The voucher is only applied if the customer explicitly enters the code.
  - **Recommended value:** “NO” for unique, targeted vouchers; “YES” for store-wide, public promotions.
  - **Merchant scenario / example:** If you’re giving unique codes to specific customers, disable this. If it’s a general “10% off everything” promotion, enable it.
- **Partial use:**

  - **What this setting does:** Determines if a voucher can be used multiple times if its value exceeds the order total.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer has a $50 voucher and buys a $30 item, they will have a $20 balance remaining on that same voucher for a future purchase.
    - *When disabled:* If a customer has a $50 voucher and buys a $30 item, the entire $50 voucher is consumed, and no balance remains.
  - **Recommended value:** “NO” for most promotions to encourage full use or prevent complex tracking. “YES” for gift cards or store credit.
  - **Merchant scenario / example:** For a standard discount, you’d typically disable this. For a gift voucher, you’d enable it.
- **Priority:**

  - **What this setting does:** Sets the order in which cart rules are applied if multiple rules are active. A lower number means higher priority (applied first).
  - **Effect of changing this setting:** Influences how discounts stack. If two vouchers apply, the one with higher priority is processed first.
  - **Recommended value:** Leave at default (1) unless you have complex stacking rules.
  - **Merchant scenario / example:** If you have a “Free Shipping” voucher (priority 1) and a “10% Off” voucher (priority 2), free shipping will be calculated before the percentage discount.
- **Status:**

  - **What this setting does:** Activates or deactivates the generated vouchers.
  - **Effect of changing this setting:**
    - *When enabled:* Vouchers are active and can be used by customers.
    - *When disabled:* Vouchers are inactive and cannot be used.
  - **Recommended value:** “YES” if you want the vouchers to be immediately usable. You can disable them later if needed.
  - **Merchant scenario / example:** You generate vouchers for a future sale. You might enable them on the day the sale starts.

#### **2. Voucher Conditions**

This section defines when and how the generated vouchers can be used.

- **Valid from:**

  - **What this setting does:** Sets the start date from which the vouchers become active.
  - **Effect of changing this setting:** Vouchers cannot be used before this date.
  - **Recommended value:** Today’s date if you want them active immediately, or a future date for a planned promotion.
  - **Merchant scenario / example:** Set to “2024-07-01” for a July promotion.
- **Valid to:**

  - **What this setting does:** Sets the end date after which the vouchers expire.
  - **Effect of changing this setting:** Vouchers cannot be used after this date.
  - **Recommended value:** A reasonable expiry date for your promotion (e.g., 1 week, 1 month, end of season).
  - **Merchant scenario / example:** Set to “2024-07-31” for a July promotion.
- **Minimum amount:**

  - **What this setting does:** The minimum total purchase amount (before shipping and taxes) required for the voucher to be valid.
  - **Effect of changing this setting:** If the customer’s cart total is below this amount, the voucher cannot be applied.
  - **Recommended value:** Set to a value that encourages higher average order values, or 0 if no minimum is required.
  - **Merchant scenario / example:** Set to “50.00” to offer a discount only on orders over $50.
- **Total available:**

  - **What this setting does:** The total number of times *all* generated vouchers in this batch can be used across *all* customers.
  - **Effect of changing this setting:** Once this limit is reached, no more vouchers from this batch can be used, even if individual codes still have uses left.
  - **Recommended value:** A high number (e.g., 99999) if you want individual code limits to apply, or a specific number for a limited-time, total-use campaign.
  - **Merchant scenario / example:** If you generate 100 unique codes, and set “Total available” to 50, only the first 50 uses across all codes will be valid.
- **Total available for each user:**

  - **What this setting does:** The maximum number of times *each individual customer* can use *any* of the vouchers from this batch.
  - **Effect of changing this setting:** Prevents a single customer from repeatedly using different codes from the same batch.
  - **Recommended value:** “1” for most unique voucher campaigns to ensure each customer gets one use. “0” for unlimited uses per customer (not recommended for unique codes).
  - **Merchant scenario / example:** Set to “1” to ensure each customer can only benefit from one of your generated codes.

#### **3. Voucher Actions**

This section defines what the voucher actually does when applied.

- **Free shipping:**

  - **What this setting does:** Determines if the voucher grants free shipping.
  - **Effect of changing this setting:**
    - *When enabled:* Shipping costs are waived for orders using this voucher.
    - *When disabled:* Standard shipping costs apply.
  - **Recommended value:** “NO” unless it’s a specific free shipping promotion.
  - **Merchant scenario / example:** For a “Free Shipping Weekend” promotion, you’d enable this.
- **Apply a discount:**

  - **What this setting does:** This is where you define the actual discount amount or percentage.
  - **Effect of changing this setting:** Determines the monetary value of the discount.
  - **Recommended value:** Choose one type of discount (percentage, amount, or specific product) and fill in the details.
  - **Merchant scenario / example:** You want to offer 15% off.
  - **Percentage:**

    - **What this setting does:** Applies a percentage discount to the order total.
    - **Effect of changing this setting:** Reduces the order total by the specified percentage.
    - **Recommended value:** A common percentage like 5, 10, 15, 20.
    - **Merchant scenario / example:** Enter “15” for 15% off.
  - **Amount:**

    - **What this setting does:** Applies a fixed monetary discount to the order total.
    - **Effect of changing this setting:** Reduces the order total by the specified amount.
    - **Recommended value:** A fixed amount like 5.00, 10.00, 25.00.
    - **Merchant scenario / example:** Enter “10.00” for $10 off.
  - **Apply discount to:**

    - **What this setting does:** Specifies which part of the order the discount applies to.
    - **Effect of changing this setting:**
      - *Order (excluding shipping):* Discount applies to the product total only.
      - *Specific product:* Discount applies only to a particular product or selection of products.
      - *Cheapest product:* Discount applies to the lowest-priced item in the cart.
      - *Selected products:* Discount applies to a specific list of products you define.
    - **Recommended value:** “Order (excluding shipping)” for general discounts.
    - **Merchant scenario / example:** For a general 15% off, choose “Order (excluding shipping)”. If you want 20% off only on “T-Shirts”, you’d select “Selected products” and then choose the T-shirt category/products.
- **Send a gift:**

  - **What this setting does:** Allows you to automatically add a specific product as a free gift when the voucher is used.
  - **Effect of changing this setting:**
    - *When enabled:* A chosen product is added to the customer’s cart for free.
    - *When disabled:* No free gift is provided.
  - **Recommended value:** “NO” unless it’s a specific gift-with-purchase promotion.
  - **Merchant scenario / example:** You want to give a free “Key Chain” with every order over $100. You’d enable this and select the Key Chain product.

#### **4. Voucher Generation**

This is the final step where you define how many codes to generate and then execute the generation.

- **Number of vouchers to generate:**

  - **What this setting does:** Specifies how many unique voucher codes you want the module to create.
  - **Effect of changing this setting:** Determines the quantity of individual discount codes that will be added to your PrestaShop Cart Rules.
  - **Recommended value:** The exact number of unique codes you need for your campaign (e.g., 100 for an email list, 500 for a social media giveaway).
  - **Merchant scenario / example:** You need 250 unique codes for a marketing campaign. Enter “250”.
- **Generate Vouchers Button:**

  - **What this setting does:** This button initiates the process of creating all the vouchers based on the settings you’ve configured above.
  - **Effect of changing this setting:** Clicking this button will create the specified number of unique cart rules in your PrestaShop store. A confirmation message will appear, and you will be able to download a CSV/Excel file containing the generated codes.
  - **Recommended value:** Click this only after you are absolutely sure all your settings are correct.
  - **Merchant scenario / example:** After reviewing all settings for your “SUMMER2024” campaign and setting the number of vouchers to 250, you click “Generate Vouchers”.

#### **5. MyPresta.eu Updates & Information**

This section typically contains information about the module’s version, update availability, and links to MyPresta.eu.

- **MyPresta.eu Updates / Update Check:**
  - **What this setting does:** Allows the module to check for new versions available from MyPresta.eu.
  - **Effect of changing this setting:** Helps you keep your module up-to-date with the latest features and bug fixes.
  - **Recommended value:** Keep this enabled to receive notifications about updates.
  - **Merchant scenario / example:** You see a notification that a new version is available, ensuring you have the most stable and feature-rich version.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Name | Descriptive text | Internal name for the voucher batch. |
| Module Configuration | Description | Optional text | Internal notes for campaign details. |
| Module Configuration | Highlight | NO | Display voucher in cart summary (YES for public, NO for private). |
| Module Configuration | Partial use | NO | Allow voucher to be used multiple times if value > order. |
| Module Configuration | Priority | 1 | Order of application for multiple cart rules (lower = higher priority). |
| Module Configuration | Status | YES | Activate/deactivate the generated vouchers. |
| Module Configuration | Valid from | Current date | Start date for voucher validity. |
| Module Configuration | Valid to | Future date | End date for voucher validity. |
| Module Configuration | Minimum amount | 0.00 | Minimum purchase required for voucher use. |
| Module Configuration | Total available | High number (e.g., 99999) | Total uses for ALL vouchers in this batch. |
| Module Configuration | Total available for each user | 1 | Max uses per customer for any voucher in this batch. |
| Module Configuration | Free shipping | NO | Grant free shipping with voucher. |
| Module Configuration | Apply a discount | YES | Enable discount application. |
| Module Configuration | Percentage | (e.g., 10) | Percentage discount. |
| Module Configuration | Amount | (e.g., 10.00) | Fixed monetary discount. |
| Module Configuration | Apply discount to | Order (excluding shipping) | Scope of the discount (order, specific product, etc.). |
| Module Configuration | Send a gift | NO | Add a free product as a gift. |
| Module Configuration | Number of vouchers to generate | (e.g., 100) | Quantity of unique codes to create. |
| Module Configuration | Generate Vouchers Button | Click when ready | Initiates voucher creation and CSV export. |
| Module Configuration | MyPresta.eu Updates | YES | Check for module updates. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I generated vouchers, but they don’t seem to work in the front office.**
A1:

- **Check Status & Dates:** Go to “Catalog > Discounts > Cart Rules” in your PrestaShop Back Office. Find the vouchers you generated. Ensure their “Status” is set to “Yes” and that the “Valid from” and “Valid to” dates are current.
- **Minimum Amount:** Verify if the customer’s cart meets the “Minimum amount” requirement set for the voucher.
- **Conditions:** Double-check any other conditions you set (e.g., specific products, customer groups).
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache).

**Q2: Can I edit the generated vouchers after they’ve been created?**
A2: Yes, once generated, each voucher becomes a standard “Cart Rule” in PrestaShop. You can go to “Catalog > Discounts > Cart Rules” in your Back Office, find the individual vouchers (they will usually share the same base name you provided), and edit their properties (e.g., expiry date, discount amount, conditions) individually. However, it’s generally better to get all settings right before generation.

**Q3: How do I get the list of generated voucher codes?**
A3: Immediately after clicking the “Generate Vouchers” button, the module will prompt you to download a CSV/Excel file containing all the unique codes. If you missed this, you can’t re-download the list directly from the module. You would need to manually export the “Cart Rules” from “Catalog > Discounts > Cart Rules” in PrestaShop, or access the database directly (developer task). It’s crucial to save the CSV file immediately after generation.

**Q4: The module says “MyPresta.eu Updates” but doesn’t show a new version.**
A4: This means your module is currently up-to-date with the latest official version available from MyPresta.eu. No action is required.

**Q5: My custom theme doesn’t display the voucher input field correctly.**
A5: The Vouchers Generator module doesn’t add front-office elements. The voucher input field is a standard PrestaShop feature. If it’s not displaying correctly, it’s likely an issue with your custom theme’s styling or template overrides for the cart/checkout pages. You would need to consult your theme developer or a webmaster to adjust the CSS or TPL files related to the `displayCart` or `displayPaymentTop` hooks where the voucher field typically appears.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Vouchers Generator module (`vouchers`) is a standard PrestaShop module primarily operating within the Back Office. It leverages PrestaShop’s core `CartRule` functionality to create multiple discount codes efficiently. The module’s main logic resides in its `vouchers.php` file, handling configuration and the generation process. It does not introduce complex MVC patterns or custom database tables but rather interacts directly with PrestaShop’s existing `CartRule` object model.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module does not add any custom front-office controllers. All front-office interactions related to vouchers are handled by PrestaShop’s native `CartController` or `OrderController`.
- **Back-Office Admin Controllers**: None. The module’s configuration and generation logic are entirely contained within the `getContent()` method of the main module class, which is rendered by the standard `AdminModulesController`.

### 4.3 Core Classes & Models (`classes/`)

- None. The module does not define any custom classes or extend `ObjectModel`. It directly utilizes PrestaShop’s native `CartRule` class for creating and managing vouchers.

### 4.4 JavaScript Assets (`views/js/`)

- `vouchers/lib/voucherengine/script.js`
  - **Scope:** Back-office.
  - **Purpose:** This script likely contains client-side logic for the module’s configuration page. This could include:
    - Form validation before voucher generation.
    - AJAX calls to the module’s `getContent()` method for dynamic updates or processing.
    - UI enhancements or interactions specific to the voucher generation form.
    - Potentially handling the download of the generated CSV file.
  - **Event Listeners:** Likely binds to form submission events, input change events, and button clicks on the module configuration page.
  - **DOM Manipulation:** May show/hide elements based on user selections (e.g., showing specific product selection fields if “Apply discount to: Specific product” is chosen).

### 4.5 CSS Stylesheets (`views/css/`)

- `vouchers/lib/voucherengine/ps16.css`
  - **Scope:** Back-office admin form styling.
  - **Purpose:** Provides specific styling for the module’s configuration interface, potentially to ensure consistent appearance across different PrestaShop versions (e.g., adapting to PrestaShop 1.6’s specific admin theme structure).
  - **Main UI components:** Styles form fields, buttons, and layout elements within the module’s `getContent()` output.
  - **Key CSS class selectors:** Developers can inspect the module’s configuration page in the browser to identify specific classes (e.g., `.vouchers-generator-form`, `.mypresta-update-block`) that can be overridden in a custom admin theme if necessary.

### 4.6 Smarty Template Structure (`views/templates/`)

- `vouchers/views/pdf.tpl`
  - **Scope:** Back-office / Utility.
  - **Purpose:** This template is likely used for generating a printable or downloadable PDF document containing the list of generated vouchers. While the module description mentions CSV/Excel export, a PDF template suggests an alternative or additional output format for the voucher list, possibly for printing physical vouchers.
  - **Usage:** It would be rendered when the module needs to present the generated voucher codes in a structured, printable format. It would receive an array of voucher data (code, value, expiry, etc.) from the PHP logic.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It interacts with PrestaShop’s native `ps_cart_rule` and `ps_cart_rule_lang` tables to store the generated vouchers.
  - Configuration settings (like `vg_counter`, `mypresta_updates`) are stored in the `ps_configuration` table.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is initialized and its media (JS/CSS) are being set. | Used by the module to include its Back Office JavaScript (`script.js`) and CSS (`ps16.css`) files specifically on its configuration page, ensuring they are loaded only when needed. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the Vouchers Generator module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
