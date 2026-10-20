---
title: "Order reference change free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order reference change free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order reference change free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order reference change free Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/order-reference-change-free/)
>
> ---


# Order reference change free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special requirements beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Order reference change free” module. You will be presented with the main configuration screen.

#### **Order Reference Format**

This is the core setting of the module, allowing you to define the pattern for your order reference numbers.

- **What this setting does:** This input field allows you to specify a template for how new order reference numbers will be generated. You can use a combination of special characters and placeholders to create your desired format.
- **Effect of changing this setting:**
  - *When set to a specific format (e.g., `[0-9]{6}`):* All new orders will receive a reference number that strictly adheres to this pattern. For example, `[0-9]{6}` would generate a 6-digit numeric reference like `123456`.
  - *When left at default (PrestaShop’s default behavior):* The module will not alter the order reference generation, and PrestaShop will use its standard alphanumeric format (e.g., `ABCDEF123`).
- **Recommended value:** This depends entirely on your business needs.
  - If you need a simple, all-numeric reference, try `[0-9]{6}` for a 6-digit number.
  - If you want a mix of uppercase letters and numbers, `[A-Z0-9]{8}` would give you an 8-character alphanumeric reference.
  - You can also include static prefixes, e.g., `MYSTORE-[0-9]{5}` would generate `MYSTORE-12345`.
- **Merchant scenario / example:**
  - **Scenario 1: All-numeric references for accounting.** Your accounting software requires all order references to be purely numeric and 8 digits long. You would set this to `[0-9]{8}`.
  - **Scenario 2: Shorter, memorable references.** You want shorter, 6-character references using only uppercase letters and numbers for easier customer communication. You would set this to `[A-Z0-9]{6}`.
  - **Scenario 3: Branded references.** You want all references to start with your brand initial followed by a 5-digit number. You would set this to `M-[0-9]{5}`.

**Available Placeholders & Characters:**
The module uses a regular expression-like syntax for defining the format:

- `[0-9]`: Represents any single digit from 0 to 9.
- `[a-z]`: Represents any single lowercase letter from a to z.
- `[A-Z]`: Represents any single uppercase letter from A to Z.
- `[a-zA-Z]`: Represents any single letter (uppercase or lowercase).
- `[A-Z0-9]`: Represents any single uppercase letter or digit.
- `{n}`: Specifies that the preceding character or group should be repeated exactly `n` times. For example, `[0-9]{6}` means 6 digits.
- `{n,m}`: Specifies that the preceding character or group should be repeated between `n` and `m` times.
- Any other character (e.g., `-`, `_`, `MYSTORE-`) will be included literally in the reference.

**Important Note:** The module ensures that the generated reference is unique. If a generated reference already exists, it will try to generate a new one until a unique reference is found.

#### **Save Button**

- **What this setting does:** This button saves all the changes you’ve made on the configuration page.
- **Effect of changing this setting:**
  - *When clicked:* Your new order reference format will be applied immediately to all *new* orders placed in your store. Existing order references will not be changed.
- **Recommended value:** Always click “Save” after making any changes to ensure they are applied.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Order Reference Format | PrestaShop default (alphanumeric) | Defines the pattern for new order reference numbers (e.g., `[0-9]{6}`, `MYSTORE-[A-Z0-9]{5}`). Affects how new orders are referenced in your store and on customer documents. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I changed the format, but old orders still have the old reference. Why?**
A: This module only affects *new* orders placed after you save the configuration. It does not retroactively change existing order references, as that could cause data inconsistencies with past records, invoices, and customer communications.

**Q: My new order references are not following the format I set.**
A:

1. **Did you click “Save”?** Ensure you clicked the “Save” button after making changes on the module configuration page.
2. **Check the format syntax:** Double-check your `Order Reference Format` string for any typos or incorrect characters. Refer to the “Available Placeholders & Characters” section above.
3. **Clear Cache:** Sometimes, PrestaShop’s cache can prevent changes from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
4. **Module conflicts:** While rare, another module that heavily modifies the order process might conflict. Try disabling other recently installed modules temporarily to see if the issue resolves.

**Q: Can I make the order reference shorter or longer?**
A: Yes, absolutely! Use the `{n}` or `{n,m}` syntax to specify the exact length or a range. For example, `[0-9]{4}` for a 4-digit number, or `[A-Z0-9]{10}` for a 10-character alphanumeric reference.

**Q: What happens if the module generates a reference that already exists?**
A: The module is designed to ensure uniqueness. If it generates a reference that is already in use, it will automatically try to generate another one until a unique reference is found. This process is usually instantaneous and ensures no two orders share the same reference.

**Q: Does this module affect SEO or my store’s performance?**
A: No, this module operates purely on the backend logic of order reference generation. It has no direct impact on your store’s SEO or front-office performance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Order reference change free” module achieves its functionality through an override of PrestaShop’s core `Order` class. Instead of directly hooking into event listeners, it modifies the default behavior of the `Order::generateReference()` method, which is responsible for creating the unique order reference. This approach ensures that the custom reference generation logic is applied whenever a new order is created, regardless of the specific front-office flow.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom front-office or back-office controllers. All configuration is handled via the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- **`refchange/override/classes/order/Order.php`**
  - **Purpose**: This file contains the override for PrestaShop’s core `Order` class. Its primary function is to replace the default `generateReference()` method with custom logic that applies the format defined in the module’s configuration.
  - **Parent Class**: Extends `OrderCore`.
  - **Key Methods**:
    - `generateReference()`: This overridden method is the heart of the module.
      - It retrieves the custom reference format from `Configuration::get('REFCHANGE_FORMAT')`.
      - If a custom format is defined, it uses a loop to generate a reference string based on the configured pattern (using `preg_match` and `rand` for character selection).
      - It then checks the `ps_orders` table to ensure the generated reference is unique. If not unique, it regenerates until a unique one is found.
      - If no custom format is defined, it falls back to the parent `OrderCore::generateReference()` method.
  - **Database Interaction**: Interacts with the `ps_orders` table to check for existing references.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files.

### 4.6 Smarty Template Structure (`views/templates/`)

This module does not include any custom Smarty template files. The configuration interface is rendered directly within the `getContent()` method of the main module file.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - `ps_configuration`: Stores the module’s configuration setting:
    - `REFCHANGE_FORMAT`: The custom order reference format string (e.g., `[0-9]{6}`).
- **Registered Hooks Table**:
  This module does not explicitly register any hooks in the `ps_hook_module` table. Its functionality is implemented through a class override, which means it modifies core behavior directly rather than responding to specific hook events.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Order reference change free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
