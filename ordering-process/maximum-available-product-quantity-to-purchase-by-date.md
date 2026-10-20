---
title: "Maximum available product quantity to purchase by date - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Maximum available product quantity to purchase by date PrestaShop module by MyPresta.eu."
sidebar:
  label: "Maximum available product quantity to purchase by date"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Maximum available product quantity to purchase by date Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Maximum available product quantity to purchase by date

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
This is the main configuration screen for the module, accessed immediately after installation or by clicking "Configure" from the Module Manager.

-   **What this setting does:** This screen typically contains general settings for the module, such as enabling/disabling its core functionality or setting global preferences.
-   **Effect of changing this setting:**
    -   *When enabled:* The module's quantity limiting features will be active across your store based on the rules you define.
    -   *When disabled:* The module will cease to enforce any quantity limits, and customers will be able to purchase any available stock quantity.
-   **Recommended value:** "YES" (Enabled) to activate the module's core functionality.
-   **Merchant scenario / example:** You've just installed the module and want to start defining limits. The first step is to ensure the module is active on this screen before proceeding to define specific product limits.

### 2.2 Dedicated Admin Screen: Product Purchase Qty Limit by Date (Back Office > Catalog > Product Purchase Qty Limit by Date)
This is the primary screen where you define and manage all your product quantity limits based on date ranges.

**Screen Name & Menu Location:**
You can find this screen by navigating to **Catalog > Product Purchase Qty Limit by Date** in your PrestaShop Back Office menu.

**Available Actions & Settings:**
This screen presents a list (grid) of all existing quantity limits you've set up. You can add new limits, edit existing ones, or delete them.

#### **Listing Table Columns:**
-   **ID:** A unique identifier for each quantity limit rule.
-   **Product:** The name of the product to which the limit applies.
-   **Date from:** The start date and time when the quantity limit becomes active.
-   **Date to:** The end date and time when the quantity limit expires.
-   **Quantity:** The maximum number of units of the product that can be purchased within the specified date range.
-   **Active:** A switch (Yes/No) to enable or disable a specific limit rule without deleting it.

#### **Adding / Editing a Quantity Limit Rule:**
When you click "Add new" or edit an existing rule, you'll see a form with the following fields:

-   **Product purchase qty limit by date:** This is the main title for the form.
-   **ID Product:**
    -   **What this setting does:** This field allows you to select the specific product to which this quantity limit will apply. You'll typically use a search bar to find the product by name or ID.
    -   **Effect of changing this setting:** Determines which product's purchase quantity will be restricted by this rule.
    -   **Recommended value:** Select the exact product you intend to limit.
    -   **Merchant scenario / example:** You want to limit sales of "Summer T-Shirt" to 50 units. You would search for and select "Summer T-Shirt" here.
-   **Date from:**
    -   **What this setting does:** Defines the exact date and time when this quantity limit rule becomes active.
    -   **Effect of changing this setting:** The limit will only be enforced for purchases made on or after this date/time.
    -   **Recommended value:** Set the precise start date and time for your promotion or restriction.
    -   **Merchant scenario / example:** You want the limit to start on August 1st, 2024, at 9:00 AM.
-   **Date to:**
    -   **What this setting does:** Defines the exact date and time when this quantity limit rule expires.
    -   **Effect of changing this setting:** After this date/time, the limit will no longer be enforced, and customers can purchase any available stock.
    -   **Recommended value:** Set the precise end date and time for your promotion or restriction.
    -   **Merchant scenario / example:** You want the limit to end on August 7th, 2024, at 5:00 PM.
-   **Quantity:**
    -   **What this setting does:** Specifies the maximum number of units of the selected product that can be purchased within the "Date from" and "Date to" range.
    -   **Effect of changing this setting:** This is the actual limit enforced. If a customer tries to add more than this quantity to their cart within the active date range, they will be prevented.
    -   **Recommended value:** The specific maximum quantity you wish to allow.
    -   **Merchant scenario / example:** You want to limit purchases to 5 units per customer during the specified period. You would enter "5" here.
-   **Active (On/Off switch):**
    -   **What this setting does:** Toggles the active status of this specific quantity limit rule.
    -   **Effect of changing this setting:**
        -   *On:* The rule is active and will enforce the quantity limit during its specified date range.
        -   *Off:* The rule is inactive and will not enforce any quantity limit, even if its date range is current. This is useful for temporarily pausing a rule without deleting it.
    -   **Recommended value:** "On" for active rules, "Off" for rules you wish to temporarily disable.
    -   **Merchant scenario / example:** You've set up a limit for a Black Friday sale, but decide to postpone it. Instead of deleting the rule, you can switch it "Off" and then "On" when ready.
-   **Save button:**
    -   **What this setting does:** Saves all the changes you've made to the quantity limit rule.
    -   **Effect of changing this setting:** Applies the new or updated rule to your store's product quantity enforcement.

**Effect of changes:**
-   **Adding a new rule:** A new quantity limit will be created and will become active (if set to "On") during its specified date range, restricting purchases of the selected product.
-   **Modifying an existing rule:** The changes (e.g., product, dates, quantity, active status) will immediately update how the limit is enforced.
-   **Deleting a rule:** The quantity limit will be permanently removed, and no restrictions will apply to that product for that date range (unless other rules exist).

**Recommended workflow for daily store management:**
1.  **Plan your promotions/restrictions:** Before setting up, decide which products need limits, what the maximum quantities should be, and the exact start/end dates and times.
2.  **Navigate to "Product Purchase Qty Limit by Date":** Go to **Catalog > Product Purchase Qty Limit by Date**.
3.  **Add new rules:** Click "Add new" for each product you want to limit. Carefully fill in the Product, Date from, Date to, Quantity, and ensure "Active" is "On".
4.  **Review and adjust:** Regularly check your list of rules to ensure they are still relevant and correctly configured. Use the "Active" switch to temporarily disable rules if needed.
5.  **Monitor customer feedback:** Pay attention to any customer inquiries related to quantity limits to ensure the rules are clear and functioning as intended.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact The module "Maximum available product quantity to purchase by date" by MyPresta.eu is a powerful tool for controlling product availability. It allows you to set specific maximum purchase quantities for a product within a defined date and time range. This is crucial for managing limited stock, creating urgency for promotions, or managing special product availability.

## 3. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required. These are common and usually enabled by default on most PrestaShop-compatible hosting environments.

## 4. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 4.1 Module Configuration Page (Back Office > Modules > Configure)
This is the initial configuration screen you encounter after installing the module or by clicking "Configure" from the Module Manager.

-   **What this setting does:** This page typically contains a simple switch to enable or disable the module's overall functionality.
-   **Effect of changing this setting:**
    -   *When enabled:* The module will actively check and enforce the product quantity limits you define.
    -   *When disabled:* The module will be inactive, and no quantity limits will be applied, regardless of any rules you have set up.
-   **Recommended value:** "YES" (Enabled) to ensure the module is active and enforcing your quantity rules.
-   **Merchant scenario / example:** After installation, you must ensure this setting is enabled to start using the module's features. If you ever need to temporarily suspend all quantity limits (e.g., during a site maintenance window), you can disable it here.

### 4.2 Dedicated Admin Screen: Product Purchase Qty Limit by Date (Back Office > Catalog > Product Purchase Qty Limit by Date)
This is the central hub for creating, managing, and reviewing all your date-based product quantity limits.

**Screen Name & Menu Location:**
You can access this screen by navigating to **Catalog > Product Purchase Qty Limit by Date** in your PrestaShop Back Office menu.

**Available Actions & Settings:**
This screen displays a list of all existing quantity limit rules. From here, you can add new rules, edit existing ones, or delete them.

#### **Listing Table Columns:**
-   **ID:** A unique internal identifier for each specific quantity limit rule. Useful for technical reference.
-   **Product:** The name of the product that this specific rule applies to. This helps you quickly identify which product is being limited.
-   **Date from:** The exact date and time (e.g., "2024-08-01 09:00:00") when this quantity limit begins to be enforced.
-   **Date to:** The exact date and time (e.g., "2024-08-07 17:00:00") when this quantity limit stops being enforced.
-   **Quantity:** The maximum number of units of the specified product a customer can purchase within the "Date from" and "Date to" period.
-   **Active:** A simple "Yes" or "No" indicator (often a toggle switch) showing if the rule is currently enabled.

#### **Adding / Editing a Quantity Limit Rule:**
When you click the "Add new" button or click to edit an existing rule, a form will appear with the following fields:

-   **Product purchase qty limit by date:** This is the title of the form, indicating you are defining a new or editing an existing limit.
-   **ID Product:**
    -   **What this setting does:** This is a search field where you type the name or ID of the product you want to apply the limit to. As you type, suggestions will appear, allowing you to select the correct product.
    -   **Effect of changing this setting:** Directly links this quantity limit rule to a specific product in your catalog.
    -   **Recommended value:** Always select the exact product you intend to limit.
    -   **Merchant scenario / example:** You're running a special on "Organic Coffee Beans." You would type "Organic Coffee Beans" and select it from the dropdown.
-   **Date from:**
    -   **What this setting does:** Allows you to pick the precise calendar date and time when this quantity restriction should begin. It typically includes a date picker and a time selector.
    -   **Effect of changing this setting:** The module will only start enforcing the quantity limit for purchases made on or after this specific date and time.
    -   **Recommended value:** Set this to the exact start of your promotional period or when the restriction should take effect.
    -   **Merchant scenario / example:** You want a limit to start at the beginning of a business day, so you set it to "2024-09-01 00:00:00".
-   **Date to:**
    -   **What this setting does:** Allows you to pick the precise calendar date and time when this quantity restriction should end. Similar to "Date from," it includes a date picker and time selector.
    -   **Effect of changing this setting:** After this specific date and time, the quantity limit defined in this rule will no longer be active, and customers can purchase any available stock.
    -   **Recommended value:** Set this to the exact end of your promotional period or when the restriction should be lifted.
    -   **Merchant scenario / example:** You want the limit to end at the close of a business day, so you set it to "2024-09-07 23:59:59".
-   **Quantity:**
    -   **What this setting does:** This is a numerical input field where you specify the maximum number of units of the selected product that a single customer can purchase within the defined "Date from" and "Date to" range.
    -   **Effect of changing this setting:** This value is the core of the restriction. If a customer attempts to add more than this quantity to their cart (or already has more in their cart) during the active period, the module will intervene.
    -   **Recommended value:** The specific maximum quantity you want to allow. For example, "1" for a one-per-customer limit, or "10" for a bulk purchase limit.
    -   **Merchant scenario / example:** To ensure fair distribution of a limited-edition item, you set the quantity to "2" per customer.
-   **Active (On/Off switch):**
    -   **What this setting does:** This is a toggle switch (often labeled "On" and "Off") that controls whether this specific quantity limit rule is currently active and enforced by the module.
    -   **Effect of changing this setting:**
        -   *On:* The rule is active and will apply its quantity limit during its specified date range.
        -   *Off:* The rule is inactive and will not apply any quantity limit, even if its date range is current. This is useful for preparing rules in advance or temporarily pausing them without deleting.
    -   **Recommended value:** "On" for rules you want to be active, "Off" for rules you are preparing or have temporarily suspended.
    -   **Merchant scenario / example:** You've created a rule for a holiday sale, but the holiday is still a month away. You can set it to "Off" until closer to the date, then switch it "On" when ready.
-   **Save button:**
    -   **What this setting does:** Commits all the changes you've made in the form to the database.
    -   **Effect of changing this setting:** The new or updated quantity limit rule will immediately be applied to your store's product quantity enforcement.

**Effect of changes:**
-   **Adding a new rule:** A new restriction will be created. If marked "Active" and within its date range, it will immediately start limiting purchases for the specified product.
-   **Modifying an existing rule:** Any changes to the product, dates, quantity, or active status will be instantly reflected in how the module enforces limits.
-   **Deleting a rule:** The quantity limit will be permanently removed, and the product will no longer be subject to that specific restriction for that date range.

**Recommended workflow for daily store management:**
1.  **Identify products for limits:** Determine which products require quantity restrictions (e.g., new arrivals, sale items, high-demand products).
2.  **Define parameters:** For each product, decide the maximum quantity, and the precise start and end dates/times for the restriction.
3.  **Create rules:** Navigate to **Catalog > Product Purchase Qty Limit by Date** and click "Add new." Fill in all fields carefully, ensuring the dates and times are accurate. Set "Active" to "On."
4.  **Review and test:** After creating rules, test them on your front office (e.g., try to add more than the allowed quantity to your cart) to ensure they are working as expected.
5.  **Monitor and adjust:** Keep an eye on your sales and inventory. If a promotion is extended or stock changes, update the "Date to" or "Quantity" fields of your rules as needed. Use the "Active" toggle to temporarily disable rules without deleting them if circumstances change.

### 4.3 Configuration Quick Reference Table

| Screen / View                                       | Setting / Option                     | Default / Recommended | Purpose & Impact
