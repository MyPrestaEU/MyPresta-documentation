---
title: "Import voucher from CSV - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Import voucher from CSV PrestaShop module by MyPresta.eu."
sidebar:
  label: "Import voucher from CSV - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Import voucher from CSV Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Import voucher from CSV

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually enabled by default on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the module’s main configuration screen. This is where you will upload your CSV file and define how the voucher codes should be imported and what properties they should have.

The configuration page is typically structured into several sections, guiding you through the import process.

#### **Step 1: Upload your CSV file**

- **What this setting does:** This is where you select the CSV file containing your voucher codes from your computer.
- **Effect of changing this setting:** Clicking “Browse” or “Choose File” opens a file selection dialog. Once you select a file, its name will appear next to the button, indicating it’s ready for upload.
- **Recommended value:** Select the CSV file you have prepared with your voucher codes.
- **Merchant scenario / example:** You’ve received a list of 1000 unique voucher codes from a partner like Groupon. You’ve saved these codes into a CSV file (e.g., `groupon_vouchers.csv`). You would click “Choose File” and select this file.

#### **Step 2: CSV File Settings**

This section defines how the module should interpret your CSV file.

- **CSV Separator:**

  - **What this setting does:** Specifies the character used to separate values (columns) within your CSV file. Common separators are comma (`,`), semicolon (`;`), or tab (`\t`).
  - **Effect of changing this setting:** If the wrong separator is chosen, the module will not correctly parse your file, and all data might appear in a single column or be incorrectly split.
  - **Recommended value:** Match the separator used when you created or exported your CSV file. Most spreadsheet software defaults to comma.
  - **Merchant scenario / example:** If your CSV looks like `CODE123,10,USD`, you’d choose “Comma”. If it’s `CODE123;10;USD`, you’d choose “Semicolon”.
- **Text Delimiter:**

  - **What this setting does:** Specifies the character used to enclose text values, especially those that might contain the separator character. Often, this is a double quote (`"`).
  - **Effect of changing this setting:** If your text fields contain the separator (e.g., a product name with a comma in it) and are not properly delimited, the module might misinterpret the data, leading to incorrect parsing.
  - **Recommended value:** Match the delimiter used in your CSV. Usually “Double Quote”.
  - **Merchant scenario / example:** If a voucher description is `"10% off, limited time offer"` and your separator is a comma, the double quotes ensure “10% off, limited time offer” is treated as one field.
- **Skip first line (header):**

  - **What this setting does:** If your CSV file has a header row (e.g., `Voucher Code,Discount Amount,Expiry Date`) that describes the columns, enabling this will tell the module to ignore that first line during import.
  - **Effect of changing this setting:**
    - *When enabled:* The header row is skipped, and only actual data rows are imported.
    - *When disabled:* The first line of your CSV will be treated as a voucher code or data, which is usually incorrect and can lead to errors.
  - **Recommended value:** “YES” if your CSV has a header row, “NO” if it only contains data.
  - **Merchant scenario / example:** Your CSV starts with `code,value,currency`. You would enable this to prevent “code” from being imported as an actual voucher.

#### **Step 3: Voucher Settings (General Properties)**

This section defines the common properties for all vouchers you are importing. These settings apply to *all* codes in your CSV file.

- **Name:**

  - **What this setting does:** This is the internal name for the voucher rule in your Back Office. It helps you identify the group of vouchers.
  - **Effect of changing this setting:** This name is visible only to you in the Back Office, not to customers.
  - **Recommended value:** A descriptive name, e.g., “Groupon Codes - May 2024”.
  - **Merchant scenario / example:** You’re importing codes from a “Summer Sale 2024” campaign. You’d name it “Summer Sale 2024 Vouchers”.
- **Description:**

  - **What this setting does:** An optional internal description for the voucher rule.
  - **Effect of changing this setting:** Provides more context for your team in the Back Office.
  - **Recommended value:** A brief explanation, e.g., “Unique codes for 10% off, single use, expires 31/05/2024”.
  - **Merchant scenario / example:** “Codes provided by LivingSocial for new customers.”
- **Highlight:**

  - **What this setting does:** Determines if the voucher is highlighted in the cart summary.
  - **Effect of changing this setting:**
    - *When enabled:* The voucher will be more prominently displayed in the cart summary, potentially drawing more attention to the discount.
    - *When disabled:* The voucher will be listed normally.
  - **Recommended value:** “NO” for general use, “YES” if you want to emphasize the discount.
  - **Merchant scenario / example:** For a special limited-time offer, you might enable “YES” to make sure customers notice the applied discount.
- **Partial use:**

  - **What this setting does:** Allows customers to use only a portion of the voucher’s value and keep the remainder for future purchases.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer has a $50 voucher and buys a $30 item, they retain a $20 balance on the voucher.
    - *When disabled:* The entire voucher value must be used in one transaction; any remaining balance is lost.
  - **Recommended value:** “NO” for most discount codes. “YES” for gift cards or store credit.
  - **Merchant scenario / example:** If you’re importing gift card codes, you’d enable “YES”. For a standard “10% off” coupon, you’d use “NO”.
- **Priority:**

  - **What this setting does:** Determines the order in which multiple vouchers are applied if a customer uses more than one. Higher priority vouchers are applied first.
  - **Effect of changing this setting:** Can influence the final discount amount if multiple vouchers interact (e.g., percentage discounts vs. fixed amount discounts).
  - **Recommended value:** “1” for highest priority, or leave at default if you don’t have complex voucher interactions.
  - **Merchant scenario / example:** If you have a “Free Shipping” voucher and a “10% off” voucher, you might give “Free Shipping” a higher priority to ensure it’s applied first, then the percentage discount.
- **Status:**

  - **What this setting does:** Activates or deactivates the voucher rule.
  - **Effect of changing this setting:**
    - *When enabled:* Vouchers imported under this rule can be used by customers.
    - *When disabled:* Vouchers cannot be used, even if valid.
  - **Recommended value:** “YES” to make the vouchers immediately usable. You can disable it later if needed.
  - **Merchant scenario / example:** You want to prepare vouchers in advance but only activate them on the launch day of a campaign. You’d set “NO” initially and then change to “YES” when ready.

#### **Step 4: Voucher Settings (Conditions)**

This section defines the conditions under which the imported vouchers can be used.

- **Minimum amount:**

  - **What this setting does:** Specifies the minimum order total (before shipping and taxes) required for the voucher to be valid.
  - **Effect of changing this setting:** Customers must meet this minimum purchase value to apply the discount.
  - **Recommended value:** “0” if no minimum is required, or a specific amount (e.g., “50.00”).
  - **Merchant scenario / example:** “Get $10 off orders over $100.” You’d set “100.00”.
- **Currency:**

  - **What this setting does:** Selects the currency for the minimum amount.
  - **Effect of changing this setting:** Ensures the minimum amount is interpreted correctly for multi-currency stores.
  - **Recommended value:** Your store’s default currency (e.g., “USD”, “EUR”).
  - **Merchant scenario / example:** If your store operates in multiple currencies, ensure this matches the currency you expect customers to use for this voucher.
- **Cumulative with other vouchers:**

  - **What this setting does:** Determines if this voucher can be combined with other active vouchers in the same order.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can use this voucher along with other valid vouchers.
    - *When disabled:* This voucher cannot be used if another voucher is already applied to the cart.
  - **Recommended value:** “NO” for most unique codes to prevent excessive discounting. “YES” for specific promotions like “free shipping” that you want to combine.
  - **Merchant scenario / example:** You’re importing “10% off” codes. You likely want “NO” to prevent customers from stacking multiple percentage discounts.
- **Expiration Date (From):**

  - **What this setting does:** Sets the start date from which the imported vouchers become valid.
  - **Effect of changing this setting:** Vouchers cannot be used before this date.
  - **Recommended value:** Today’s date or a future date for scheduled promotions.
  - **Merchant scenario / example:** You want vouchers to be active starting next Monday. You’d select next Monday’s date.
- **Expiration Date (To):**

  - **What this setting does:** Sets the end date after which the imported vouchers are no longer valid.
  - **Effect of changing this setting:** Vouchers cannot be used after this date.
  - **Recommended value:** A future date corresponding to the end of your promotion.
  - **Merchant scenario / example:** Your campaign ends on December 31st. You’d select December 31st.
- **Quantity:**

  - **What this setting does:** Defines the total number of times *each individual voucher code* can be used.
  - **Effect of changing this setting:**
    - *Set to 1:* Each code in your CSV can be used only once (most common for unique codes).
    - *Set to >1:* Each code can be used multiple times up to this limit.
  - **Recommended value:** “1” for unique, single-use codes (e.g., from Groupon).
  - **Merchant scenario / example:** For 1000 unique Groupon codes, you’d set this to “1” so each customer can only use their specific code once.
- **Quantity per user:**

  - **What this setting does:** Defines how many times *a single customer* can use *any* voucher from this imported batch.
  - **Effect of changing this setting:**
    - *Set to 1:* A customer can only use one voucher from this batch, even if they have multiple unique codes.
    - *Set to >1:* A customer can use multiple vouchers from this batch, up to this limit.
  - **Recommended value:** “1” for most unique code campaigns to prevent a single customer from using many codes.
  - **Merchant scenario / example:** You want each customer to benefit from only one “welcome” voucher. You’d set this to “1”.

#### **Step 5: Voucher Settings (Actions)**

This section defines what kind of discount the imported vouchers will provide.

- **Free shipping:**

  - **What this setting does:** If enabled, the voucher will grant free shipping for the order.
  - **Effect of changing this setting:**
    - *When enabled:* Shipping costs are waived when the voucher is applied.
    - *When disabled:* Shipping costs are calculated normally.
  - **Recommended value:** “NO” unless the primary purpose of these vouchers is free shipping.
  - **Merchant scenario / example:** You’re importing codes for a “Free Shipping Weekend” promotion. You’d enable “YES”.
- **Apply a discount:**

  - **What this setting does:** Determines the type and value of the discount applied by the voucher.
  - **Effect of changing this setting:** This is the core discount mechanism.
  - **Recommended value:** Choose one of the options below based on your promotion.
  - **Merchant scenario / example:** You want to give 10% off.
  - **Percentage:**

    - **What this setting does:** Applies a percentage discount to the order.
    - **Effect of changing this setting:** The `Value` field will be interpreted as a percentage (e.g., `10` for 10%).
    - **Recommended value:** Select this for percentage-based discounts.
    - **Merchant scenario / example:** For a “15% off” promotion, select “Percentage” and enter `15` in the `Value` field.
  - **Amount:**

    - **What this setting does:** Applies a fixed monetary discount to the order.
    - **Effect of changing this setting:** The `Value` field will be interpreted as a fixed amount in your chosen currency (e.g., `10.00` for $10 off).
    - **Recommended value:** Select this for fixed amount discounts.
    - **Merchant scenario / example:** For a “$20 off” promotion, select “Amount” and enter `20.00` in the `Value` field.
  - **None:**

    - **What this setting does:** If selected, the voucher will not apply any monetary or percentage discount. This is typically used when the voucher’s only action is “Free shipping” or “Send a gift”.
    - **Effect of changing this setting:** No discount value is applied.
    - **Recommended value:** Only select “None” if you are using “Free shipping” or “Send a gift” as the primary action.
    - **Merchant scenario / example:** If you only want to offer free shipping, you’d select “None” here and enable “Free shipping” above.
- **Value:**

  - **What this setting does:** The actual numerical value of the discount. Its interpretation depends on whether “Percentage” or “Amount” is selected above.
  - **Effect of changing this setting:** Directly controls the size of the discount.
  - **Recommended value:** A numerical value (e.g., `10` for 10% or $10).
  - **Merchant scenario / example:** If you chose “Percentage” and want 15% off, enter `15`. If you chose “Amount” and want $20 off, enter `20.00`.
- **Apply discount to:**

  - **What this setting does:** Determines what the discount is applied to.
  - **Effect of changing this setting:**
    - *Order (without shipping):* Discount applies to the total product value in the cart.
    - *Specific product:* Discount applies only to a particular product you specify.
    - *Cheapest product:* Discount applies to the lowest-priced product in the cart.
    - *Selected products:* Discount applies to a selection of products.
  - **Recommended value:** “Order (without shipping)” for general discounts.
  - **Merchant scenario / example:** For a general “10% off everything” campaign, choose “Order (without shipping)”. If it’s “10% off all T-shirts”, you’d select “Selected products” and then choose your T-shirt category/products.
- **Send a gift:**

  - **What this setting does:** If enabled, the voucher will add a specific product to the customer’s cart as a free gift.
  - **Effect of changing this setting:**
    - *When enabled:* You will be prompted to select a product to be added as a gift.
    - *When disabled:* No gift is added.
  - **Recommended value:** “NO” unless you are running a “buy X get Y free” type of promotion.
  - **Merchant scenario / example:** “Buy any product, get a free keychain.” You’d enable “YES” and select the keychain product.

After configuring all settings, you will typically find a “Save” or “Import” button. Click this to initiate the import process. The module will then read your CSV file and create the corresponding voucher rules in your PrestaShop database based on the settings you’ve defined.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Upload CSV file | Your prepared CSV | Selects the file containing voucher codes. |
|  | CSV Separator | Comma (`,`) | Character separating columns in your CSV. Must match your file. |
|  | Text Delimiter | Double Quote (`"`) | Character enclosing text fields in your CSV. Must match your file. |
|  | Skip first line (header) | YES (if header exists) | Ignores the first row of your CSV if it’s a header. |
|  | **Voucher Settings (General)** |  |  |
|  | Name | Descriptive name | Internal name for the voucher rule in BO. |
|  | Description | Optional text | Internal description for the voucher rule. |
|  | Highlight | NO | Highlights voucher in cart summary. |
|  | Partial use | NO | Allows partial use of voucher value. YES for gift cards. |
|  | Priority | 1 | Order of application for multiple vouchers. |
|  | Status | YES | Activates/deactivates the voucher rule. |
|  | **Voucher Settings (Conditions)** |  |  |
|  | Minimum amount | 0 | Minimum order total for voucher validity. |
|  | Currency | Store’s default | Currency for the minimum amount. |
|  | Cumulative with other vouchers | NO | Allows combining with other vouchers. |
|  | Expiration Date (From) | Today’s date | Start date for voucher validity. |
|  | Expiration Date (To) | Future date | End date for voucher validity. |
|  | Quantity | 1 | Total uses per *individual* voucher code. |
|  | Quantity per user | 1 | Total uses per *customer* from this batch. |
|  | **Voucher Settings (Actions)** |  |  |
|  | Free shipping | NO | Grants free shipping. |
|  | Apply a discount | Percentage / Amount | Type of discount (percentage or fixed amount). |
|  | Value | Numerical value | The actual discount value (e.g., 10 for 10% or $10). |
|  | Apply discount to | Order (without shipping) | What the discount applies to (order, specific product, etc.). |
|  | Send a gift | NO | Adds a free product as a gift. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I imported my CSV, but the vouchers aren’t working or aren’t showing up.**
A:

1. **Check Module Status:** Ensure the module itself is enabled in **Modules > Module Manager**.
2. **Check Voucher Status:** Go to **Catalog > Discounts > Cart Rules** (or **Price Rules > Cart Rules** in older versions). Find the voucher rule created by the import (it will have the “Name” you specified during configuration). Ensure its “Status” is set to “YES” (active).
3. **Expiration Dates:** Double-check the “Expiration Date (From)” and “Expiration Date (To)” settings. If the current date is outside this range, the vouchers won’t work.
4. **Minimum Amount:** Verify if the customer’s cart meets the “Minimum amount” condition you set.
5. **Voucher Codes:** Ensure the codes in your CSV are exactly as customers are entering them (case-sensitive, no extra spaces).

**Q: My CSV file isn’t parsing correctly. All data is in one column, or columns are mixed up.**
A: This is almost always due to incorrect “CSV Separator” or “Text Delimiter” settings.

1. **Open your CSV file** in a plain text editor (like Notepad, Sublime Text, VS Code, or even Excel/Google Sheets but then save as CSV again).
2. **Identify the separator:** Look at how values are separated. Is it a comma (`,`), semicolon (`;`), or tab? Select the correct one in the module settings.
3. **Identify the delimiter:** Look for characters enclosing text, usually double quotes (`"`). If present, ensure “Text Delimiter” is set to “Double Quote”.
4. **Header Row:** If your CSV has a header, make sure “Skip first line (header)” is set to “YES”.

**Q: I imported vouchers, but now I want to delete them or disable them.**
A:

1. Go to **Catalog > Discounts > Cart Rules** (or **Price Rules > Cart Rules**).
2. Find the voucher rule you created with the module (using the “Name” you assigned).
3. You can either:
   - **Disable:** Click the green checkmark next to the rule to turn it into a red “X”. This deactivates all vouchers under that rule.
   - **Delete:** Select the rule and use the bulk actions or click the delete icon to remove the entire rule and all associated voucher codes.

Deleting a cart rule is permanent and cannot be undone.

**Q: Can I update existing vouchers with this module?**
A: No, this module is designed for importing *new* vouchers. It does not have functionality to update existing voucher codes or cart rules. If you need to modify an existing voucher, you must do so manually via **Catalog > Discounts > Cart Rules**.

**Q: Why are my imported vouchers not cumulative with other discounts?**
A: Check the “Cumulative with other vouchers” setting in the module configuration. If you set it to “NO” (which is often recommended for unique codes), then customers will not be able to use these vouchers alongside other active discounts in their cart. If you want them to be cumulative, set this to “YES” during import.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Import voucher from CSV” module.

### 4.1 Architecture Overview

The `importvoucher` module is a standard PrestaShop module primarily focused on Back Office functionality. It leverages PrestaShop’s core `CartRule` and `CartRuleProduct` ObjectModels to create and manage discount codes. The module’s main logic resides within its primary PHP file, handling file uploads, CSV parsing, and database interactions. It does not introduce complex MVC patterns with dedicated front or admin controllers but rather uses the `getContent()` method for its configuration interface.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers in the `controllers/front` or `controllers/admin` directories. All administrative logic, including the configuration form and the CSV import process, is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom classes in a `classes/` directory. It directly interacts with PrestaShop’s core `CartRule` and `CartRuleProduct` ObjectModels to create and manage discount codes.

- **`CartRule` (PrestaShop Core Class):**

  - Interacts with the `ps_cart_rule` database table.
  - The module populates properties of `CartRule` objects (e.g., `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) based on the configuration and CSV data.
  - The `add()` method of `CartRule` is used to persist the new voucher rules to the database.
- **`CartRuleProduct` (PrestaShop Core Class):**

  - Interacts with the `ps_cart_rule_product_rule_group` and `ps_cart_rule_product_rule` tables.
  - Used when the “Apply discount to: Selected products” option is chosen, to link the cart rule to specific products, categories, or manufacturers.

### 4.4 JavaScript Assets (`views/js/`)

- `importvoucher/lib/voucherengine/script.js`:
  - **Scope:** Back-office.
  - **Purpose:** This script likely handles dynamic interactions on the module’s configuration page. This could include:
    - Showing/hiding fields based on selected options (e.g., showing “Value” input only when “Percentage” or “Amount” discount type is selected).
    - AJAX calls for form validation or processing.
    - Date picker initialization for “Expiration Date (From)” and “Expiration Date (To)”.
    - Potentially client-side CSV parsing previews or error handling.
  - **Interaction:** Binds event listeners to form elements (e.g., `change` events on radio buttons, `click` on buttons).

### 4.5 CSS Stylesheets (`views/css/`)

- `importvoucher/lib/voucherengine/ps16.css`:

  - **Scope:** Back-office (likely for PrestaShop 1.6 compatibility, but may be loaded on newer versions for general styling).
  - **Purpose:** Provides styling for the module’s configuration interface, ensuring it integrates visually with the PrestaShop 1.6 Back Office theme. May contain general form element styling, layout adjustments, and specific class-based styles for module components.
  - **Key Selectors:** Likely targets generic form elements (`.form-group`, `.control-label`, `.form-control`) and potentially module-specific wrappers (e.g., `#module_form_importvoucher`).
- `importvoucher/views/css/css.css`:

  - **Scope:** Back-office.
  - **Purpose:** Contains general or specific styling rules for the module’s configuration page. This might override or extend `ps16.css` for newer PrestaShop versions or provide unique styling for custom elements within the module’s template.
  - **Key Selectors:** Similar to `ps16.css`, focusing on the module’s UI elements. Developers should inspect this file for specific class names to override in their custom admin themes if necessary.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for rendering its Back Office configuration interface.

- **`importvoucher/views/backoffice.tpl`**:

  - **Scope:** Admin template.
  - **Purpose:** This is likely the main template file rendered by the `getContent()` method. It acts as the container for the entire module configuration form, including all settings, input fields, and buttons. It probably includes other partial templates.
  - **Content:** Contains the HTML structure for the module’s configuration page, including form tags, fieldsets, and potentially calls to include other `.tpl` files.
- **`importvoucher/views/csv.tpl`**:

  - **Scope:** Admin template.
  - **Purpose:** This template likely handles the display of the CSV file upload section and related settings (separator, delimiter, skip header). It’s a partial template included within `backoffice.tpl`.
- **`importvoucher/views/csv_file.tpl`**:

  - **Scope:** Admin template.
  - **Purpose:** A more granular partial template, possibly specifically for the file input field itself, or for displaying information about the uploaded CSV file.
- **`importvoucher/views/file_settings.tpl`**:

  - **Scope:** Admin template.
  - **Purpose:** This template probably renders the “CSV File Settings” section, including inputs for CSV separator, text delimiter, and the “skip first line” checkbox.

### 4.7 Database Schema & Hooks Map

- **Database Tables:**
  The module does not create custom database tables. It interacts directly with PrestaShop’s core tables related to cart rules:

  - `ps_cart_rule`: Stores the main properties of each discount rule (name, code, dates, minimum amount, etc.).
  - `ps_cart_rule_lang`: Stores language-specific fields for cart rules (e.g., `name` if it’s multilingual).
  - `ps_cart_rule_product_rule_group`: Used when applying discounts to specific products/categories.
  - `ps_cart_rule_product_rule`: Defines the actual product rules within a group.
  - `ps_cart_rule_product_rule_exclusion`: For excluding specific products from a rule.
  - `ps_cart_rule_carrier`: For carrier restrictions.
  - `ps_cart_rule_country`: For country restrictions.
  - `ps_cart_rule_group`: For customer group restrictions.
  - `ps_cart_rule_shop`: For multi-store context.
- **Registered Hooks Table:**
  The module’s primary function is in the Back Office configuration. While the module description mentions “Front-Office Hooks: Header, Columns, Product, or Footer”, the provided file inventory and typical functionality of an import module suggest it does not actively render content in these front-office hooks. These mentions might be generic or refer to where the *effects* of the imported vouchers are seen (e.g., a voucher applied in the cart, which is part of the checkout flow, potentially influenced by hooks).

  The module primarily uses the following hook for its Back Office interface:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renders in the `<head>` section of Back Office pages. | Used to include CSS and JavaScript assets for the module’s configuration page. |
  | `moduleRoutes` (PrestaShop 1.7+) | When module routes are initialized. | If the module had custom front controllers, this hook would define their URLs. (Not applicable here as no custom front controllers are present). |

  The module’s core logic for *creating* vouchers does not rely on specific PrestaShop hooks but rather on direct calls to `CartRule` methods triggered by the form submission in `getContent()`.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Import voucher from CSV” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
