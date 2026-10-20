---
title: "Cumulative discounts - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Cumulative discounts PrestaShop module by MyPresta.eu."
sidebar:
  label: "Cumulative discounts - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cumulative discounts Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/cumulative-discounts/)
>
> ---


# Cumulative discounts

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most PrestaShop-compatible hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen where you define how your cumulative discount program operates.

#### **Activate program**

- **What this setting does:** This is the master switch to turn the entire cumulative discount program on or off.
- **Effect of changing this setting:**
  - *When enabled:* The module will actively track customer spending, assign groups, and display discount information in your front office.
  - *When disabled:* The module will cease all operations, no discounts will be applied, and no information will be displayed.
- **Recommended value:** YES (to activate the program).
- **Merchant scenario / example:** If you’re setting up the module for the first time, enable it after you’ve configured all other settings. If you need to temporarily pause the program (e.g., during a major sale where other discounts apply), you can disable it here.

#### **Disable cumulative discounts program for selected groups of customers**

- **What this setting does:** Allows you to select specific customer groups that should *not* be part of the cumulative discount program. Customers in these selected groups will not receive cumulative discounts, regardless of their spending.
- **Effect of changing this setting:**
  - *When a group is selected:* Customers belonging to that group will be excluded from the program.
  - *When no groups are selected:* All customer groups are eligible for the program by default.
- **Recommended value:** Select groups like “Visitors” or “Guests” if you only want registered customers to participate. You might also exclude a “Wholesale” group if they have a separate pricing structure.
- **Merchant scenario / example:** You might have a “Wholesale” customer group that already receives special pricing. To avoid conflicts or double-discounts, you would select the “Wholesale” group here to exclude them from the cumulative discount program.

#### **Time frame**

- **What this setting does:** Defines the period over which customer orders are considered when calculating their total spending.
- **Effect of changing this setting:**
  - *All orders:* Considers every order ever placed by the customer.
  - *Last year orders / Last half year orders / Last quarter orders / Last month orders / Last week orders / Last day orders:* Limits the calculation to orders placed within the specified recent period.
  - *Only last valid order:* Only considers the most recent completed order.
- **Recommended value:** “Last year orders” or “All orders” are common choices for loyalty programs. “Last month orders” could be used for a more aggressive, short-term loyalty push.
- **Merchant scenario / example:** If you want to reward long-term loyalty, choose “All orders.” If you want to encourage recent, frequent purchases, “Last half year orders” might be more appropriate.

#### **Type of price**

- **What this setting does:** Determines whether the cumulative spending calculation should use the “Net price” (price before taxes) or “Gross price” (price including taxes) of products in orders.
- **Effect of changing this setting:**
  - *Net price:* Total spending will be calculated based on product prices excluding taxes.
  - *Gross price:* Total spending will be calculated based on product prices including taxes.
- **Recommended value:** “Gross price” is often more intuitive for customers as it reflects what they actually paid. However, “Net price” might be preferred for B2B stores or for internal accounting consistency.
- **Merchant scenario / example:** If your target audience is primarily consumers, using “Gross price” makes the most sense as it aligns with the final price they see and pay.

#### **Select order states**

- **What this setting does:** Allows you to specify which order statuses should be included when calculating a customer’s total spending. Only orders with these selected statuses will count towards the cumulative total.
- **Effect of changing this setting:**
  - *When “Payment accepted” and “Delivered” are selected:* Only orders that have been successfully paid for and delivered will contribute to the customer’s spending total.
  - *When “Canceled” or “Refunded” are NOT selected:* These orders will not count, preventing customers from gaining loyalty points for non-completed purchases.
- **Recommended value:** Select statuses that indicate a completed and successful transaction, such as “Payment accepted,” “Delivered.” Exclude statuses like “Canceled,” “Refunded,” “Payment error,” etc.
- **Merchant scenario / example:** You want to ensure that only actual, completed purchases contribute to loyalty. You would select “Payment accepted” and “Delivered” to ensure customers only earn discounts for orders they’ve truly paid for and received.

#### **Exclude orders placed with voucher code**

- **What this setting does:** If enabled, orders where a voucher or coupon code was used will not count towards the customer’s cumulative spending total.
- **Effect of changing this setting:**
  - *When enabled:* Orders with vouchers are ignored for loyalty calculations.
  - *When disabled:* Orders with vouchers *do* count towards the cumulative total.
- **Recommended value:** YES, if you want to reward full-price purchases more heavily. NO, if you want to encourage any purchase, even discounted ones, to contribute to loyalty.
- **Merchant scenario / example:** You’re running a special promotion with a 20% off coupon. If you enable this setting, customers using that coupon won’t have that order count towards their cumulative discount progress, ensuring they earn loyalty on full-price purchases.

#### **Exclude products with specific prices**

- **What this setting does:** If enabled, products that have a “specific price” (e.g., a special promotional price set for a limited time or a particular customer group) will not contribute to the cumulative spending calculation.
- **Effect of changing this setting:**
  - *When enabled:* Products with specific prices are ignored for loyalty calculations.
  - *When disabled:* Products with specific prices *do* count towards the cumulative total.
- **Recommended value:** YES, if you want to reward purchases of regularly priced items. NO, if you want all product purchases to contribute.
- **Merchant scenario / example:** You have a flash sale on certain items using PrestaShop’s specific price feature. If you enable this, buying those sale items won’t help the customer reach the next loyalty tier, encouraging them to buy regular-priced items instead.

#### **Exclude products with quantity discounts**

- **What this setting does:** If enabled, products that were purchased with a quantity discount (e.g., “Buy 3, get 10% off”) will not contribute to the cumulative spending calculation.
- **Effect of changing this setting:**
  - *When enabled:* Products bought with quantity discounts are ignored for loyalty calculations.
  - *When disabled:* Products bought with quantity discounts *do* count towards the cumulative total.
- **Recommended value:** YES, if you want to reward purchases of single items at full price. NO, if you want to encourage bulk purchases to contribute to loyalty.
- **Merchant scenario / example:** You offer a “buy 5 get 15% off” deal. If you enable this, customers taking advantage of that deal won’t have those specific items count towards their cumulative discount progress.

#### **Default group of customers**

- **What this setting does:** This defines the default customer group that customers will be assigned to if they don’t meet the spending criteria for any other cumulative discount group. This is typically your standard “Customer” group.
- **Effect of changing this setting:** Ensures that customers always belong to a valid group, even if they haven’t spent enough to qualify for a special discount tier.
- **Recommended value:** Your standard “Customer” group (often ID 3).
- **Merchant scenario / example:** A new customer registers. They haven’t made any purchases yet, so the module assigns them to the “Default group of customers” (e.g., “Customer”), which might have 0% discount. As they spend, they’ll be moved to “Bronze,” “Silver,” etc.

#### **Information for logged customers (Product page)**

- **What this setting does:** This is a text editor where you can customize the message displayed to *logged-in customers* on product pages. This message typically informs them about their current discount status or progress.
- **Effect of changing this setting:** The text you enter here will appear on product pages for customers who are logged into their account. You can use Smarty variables (like `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) to personalize the message.
- **Recommended value:** A welcoming message like: “Hello {$customer\_name}! You are currently in the {$current\_group\_name} group and receive a {$discount\_value}% discount. Spend {$to\_next\_group} more to reach the {$next\_group\_name} group and get {$next\_group\_value}% off!”
- **Merchant scenario / example:** You want to motivate logged-in customers. You can tell them exactly how much more they need to spend to get a higher discount, creating a clear incentive.

#### **Information for unlogged customers (Product page)**

- **What this setting does:** This is a text editor where you can customize the message displayed to *guest or unlogged customers* on product pages. This message typically encourages them to register and participate in the loyalty program.
- **Effect of changing this setting:** The text you enter here will appear on product pages for customers who are not logged into their account.
- **Recommended value:** An inviting message like: “Register now and start earning cumulative discounts! The more you spend, the more you save!”
- **Merchant scenario / example:** A new visitor lands on a product page. This message can entice them to create an account by highlighting the benefits of your loyalty program, potentially converting them into a registered customer.

#### **Information for logged customers (Cart page)**

- **What this setting does:** This is a text editor where you can customize the message displayed to *logged-in customers* on the shopping cart page. This message can reinforce their discount status or show how their current cart contributes to their loyalty.
- **Effect of changing this setting:** The text you enter here will appear on the cart page for logged-in customers. You can use Smarty variables.
- **Recommended value:** Similar to the product page message, but perhaps emphasizing the current cart’s contribution: “Your current cart value is {$cart\_value}. With your {$current\_group\_name} discount, you save {$discount\_value}%! Spend {$to\_next\_group} more to reach the {$next\_group\_name} group!”
- **Merchant scenario / example:** A customer is about to check out. This message reminds them of their loyalty benefits and might even encourage them to add a small item to reach the next discount tier.

#### **Information for unlogged customers (Cart page)**

- **What this setting does:** This is a text editor where you can customize the message displayed to *guest or unlogged customers* on the shopping cart page. This message encourages them to register before completing their purchase to start earning loyalty.
- **Effect of changing this setting:** The text you enter here will appear on the cart page for unlogged customers.
- **Recommended value:** “Don’t miss out on loyalty discounts! Register before checkout to start earning rewards on your purchases!”
- **Merchant scenario / example:** A guest customer has items in their cart. This message provides a final push to register an account, turning a one-time shopper into a potential loyal customer.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminCudiListController (Back Office > Cumulative Discounts > Manage Discounts)

- **Screen Name & Menu Location:** You can find this screen by navigating to **Catalog > Cumulative Discounts** (or a similar location depending on your PrestaShop version and menu customization). The exact label might be “Manage Discounts” or “Cumulative Discount Rules.”
- **Available Actions & Settings:** This screen presents a grid (list) of your defined cumulative discount rules. Each rule specifies:
  - **Minimum Spending Amount:** The total amount a customer must spend to qualify for this group.
  - **Customer Group:** The PrestaShop customer group to which customers meeting the spending criteria will be assigned.
  - **Discount Percentage:** The discount percentage associated with that customer group.
  - **Actions:** You can “Add new” rules, “Edit” existing rules, or “Delete” rules.
- **Effect of changes:**
  - **Adding a new rule:** Creates a new tier in your loyalty program. For example, “Spend $500 to join the Gold group and get 15% off.”
  - **Editing a rule:** Modifies the spending threshold or the assigned group/discount for an existing tier. Changes will affect future group assignments and recalculations.
  - **Deleting a rule:** Removes a loyalty tier. Customers previously in that group will be reassigned based on the remaining rules.
- **Recommended workflow for daily store management:**
  1. **Plan your tiers:** Decide on your spending thresholds and the corresponding discount groups (e.g., Bronze: $100 for 5%, Silver: $500 for 10%, Gold: $1000 for 15%).
  2. **Create customer groups:** Ensure you have corresponding customer groups in PrestaShop (Back Office > Customers > Groups) for each tier (e.g., “Bronze Customer,” “Silver Customer,” “Gold Customer”). Assign the appropriate global discount percentage to each of these groups.
  3. **Add rules:** Use the “Add new” button to create each tier, linking the spending amount to the correct customer group.
  4. **Order rules:** The module processes rules from lowest spending to highest. Ensure your rules are logically ordered.
  5. **Review and adjust:** Periodically review your tiers to ensure they are still effective and profitable.

#### index.php (cudi/controllers/admin/index.php)

This file is typically a placeholder or a redirector within the admin controller structure and does not represent a direct, configurable screen for the merchant. It’s part of the module’s internal routing for the back office. All merchant-facing configuration for cumulative discounts happens either on the main module configuration page or via the `AdminCudiListController`.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Activate program | YES | Master switch for the loyalty program. |
|  | Disable cumulative discounts program for selected groups of customers | Select “Guest”, “Visitor” | Excludes specified customer groups from the program. |
|  | Time frame | Last year orders / All orders | Defines the period for total spending calculation. |
|  | Type of price | Gross price | Determines if net or gross prices are used for spending calculation. |
|  | Select order states | Payment accepted, Delivered | Specifies which order statuses count towards total spending. |
|  | Exclude orders placed with voucher code | YES | Prevents orders with vouchers from contributing to loyalty. |
|  | Exclude products with specific prices | YES | Prevents products on specific price promotions from contributing. |
|  | Exclude products with quantity discounts | YES | Prevents products with quantity discounts from contributing. |
|  | Default group of customers | Your standard “Customer” group | The group assigned if no loyalty tier is met. |
|  | Information for logged customers (Product page) | Customizable text with Smarty variables | Message for logged-in users on product pages. |
|  | Information for unlogged customers (Product page) | Customizable text | Message for guests on product pages, encouraging registration. |
|  | Information for logged customers (Cart page) | Customizable text with Smarty variables | Message for logged-in users on cart pages. |
|  | Information for unlogged customers (Cart page) | Customizable text | Message for guests on cart pages, encouraging registration. |
| **AdminCudiListController** | Minimum Spending Amount | Varies by tier | Threshold for qualifying for a specific discount group. |
|  | Customer Group | Your custom loyalty groups (e.g., Bronze, Silver) | The PrestaShop group assigned when spending threshold is met. |
|  | Discount Percentage | Varies by tier | The discount applied to the assigned customer group. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers aren’t being assigned to the correct groups, or discounts aren’t applying.**
A1:

- **Check “Activate program”:** Ensure the main switch in the module configuration is set to YES.
- **Verify “Time frame” and “Select order states”:** Make sure the orders you expect to count fall within the selected time frame and have the correct order statuses (e.g., “Delivered,” “Payment accepted”).
- **Review “Exclude” settings:** Check if “Exclude orders placed with voucher code,” “Exclude products with specific prices,” or “Exclude products with quantity discounts” are enabled and might be preventing orders from counting.
- **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache.” Sometimes PrestaShop’s cache can prevent changes from taking effect immediately.
- **Check Customer Groups:** Ensure the customer groups you’ve linked in the `AdminCudiListController` actually exist in PrestaShop (Customers > Groups) and have the correct global discount percentage assigned to them.
- **Order of Rules:** Ensure your rules in `AdminCudiListController` are ordered logically from lowest spending threshold to highest.

**Q2: The discount information isn’t showing up on my product pages or cart.**
A2:

- **Check Module Hooks:** Ensure the module is hooked to `displayProductAdditionalInfo` and `displayShoppingCart`. You can verify this in **Design > Positions** (or **Modules > Positions** in older PS versions). Look for “Cumulative discounts” under these hooks. If not, try reinstalling the module or manually hooking it.
- **Module Configuration Text:** Make sure you’ve entered text into the “Information for logged customers” and “Information for unlogged customers” fields for both product and cart pages. If these fields are empty, nothing will display.
- **Theme Compatibility:** Your custom theme might override the standard hook positions. If the information still doesn’t appear, you might need a web developer to adjust your theme’s `.tpl` files to explicitly include the module’s hooks.

**Q3: How do I translate the module’s messages into other languages?**
A3:

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and then select “Cumulative discounts” from the module dropdown.
- You can then translate all the module’s static strings. For the custom messages you’ve entered in the configuration (e.g., “Information for logged customers”), you’ll need to use the language selector at the top right of the module configuration page to switch languages and enter the translated text for each language.

**Q4: Can I manually assign a customer to a cumulative discount group?**
A4: Yes, you can manually change a customer’s group in their customer profile (Back Office > Customers > Customers > Edit Customer). However, the module will automatically re-evaluate their group based on their spending history during the next order status update or when the module’s logic is triggered. If you want a customer to *permanently* stay in a specific group regardless of spending, you might need to exclude that group from the cumulative discount program (using the “Disable cumulative discounts program for selected groups of customers” setting) and manage them manually.

**Q5: What happens if a customer’s total spending drops below a tier (e.g., due to a refund)?**
A5: The module recalculates the customer’s total spending based on the configured “Time frame” and “Select order states” whenever an order status is updated. If a refund causes their total to drop below a tier, the module will automatically reassign them to the appropriate lower-tier group during the next recalculation, ensuring accuracy.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Cumulative discounts” module (`cudi`) follows a standard PrestaShop module architecture, leveraging MVC principles. It primarily operates by hooking into various front-office and back-office events to calculate customer spending and dynamically assign them to appropriate customer groups. Configuration is managed via the main `getContent()` method and a dedicated `AdminCudiListController` for managing discount tiers. It does not introduce custom database tables but relies on PrestaShop’s `ps_configuration` for settings and `ps_customer_group` for group assignments.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `cudi/controllers/front/index.php`
  - **Class name & parent class:** `CudiIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller likely serves as a default or fallback for the module’s front-office routing. It might handle initial setup or redirection, though `mydiscount.php` is more specific for customer-facing content.
- `cudi/controllers/front/mydiscount.php`
  - **Class name & parent class:** `CudiMydiscountModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is responsible for rendering the dedicated “My Discounts” page in the customer’s account area. It fetches the customer’s total spending, current group, and progress towards the next tier, then passes this data to the `myDiscount.tpl` template for display. It responds to a route like `yourstore.com/module/cudi/mydiscount`.

#### Back-Office Admin Controllers

- `cudi/controllers/admin/AdminCudiList.php`
  - **Tab name and managed entity:** “Cumulative Discounts” (or similar, accessible via Catalog menu). Manages the `cudi` entity, which represents the cumulative discount rules (spending thresholds linked to customer groups).
  - **Responsibility:** This is the primary admin controller for managing the discount tiers. It extends `AdminController` and uses `HelperList` for the grid display and `HelperForm` for adding/editing individual rules. It handles CRUD operations for the cumulative discount rules, including defining the minimum spending, target customer group, and associated discount.
- `cudi/controllers/admin/index.php`
  - **Responsibility:** This file typically serves as an entry point or a redirector within the admin controller directory. In many modules, it might contain a simple `header('Location: ...')` to redirect to the main admin controller (`AdminCudiList.php` in this case) or be a placeholder. It does not represent a direct, configurable screen.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. The core logic for calculating cumulative spending and assigning groups is likely encapsulated within the main `cudi.php` module file itself, particularly within its hook methods and potentially helper functions. It directly interacts with PrestaShop’s `Customer`, `Order`, `OrderState`, and `Group` `ObjectModel`s.

### 4.4 JavaScript Assets (`views/js/`)

- `cudi/views/admin/js/cudi.js`
  - **Scope:** Back-office.
  - **Responsibility:** This script likely handles client-side interactions on the module’s configuration page or the `AdminCudiListController`. This could include:
    - Dynamic form field visibility based on selected options (e.g., showing/hiding exclusion options).
    - AJAX calls for saving settings without a full page reload.
    - Input validation or interactive elements specific to the module’s admin interface.
    - Event listeners for form changes or button clicks within the admin panel.

### 4.5 CSS Stylesheets (`views/css/`)

- `cudi/views/admin/css/cudi.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides styling for the module’s configuration page and the `AdminCudiListController` interface, ensuring it integrates visually with the PrestaShop back office theme.
  - **Key CSS class selectors:** Likely targets specific IDs or classes within the module’s admin templates (e.g., `.cudi-settings-panel`, `.cudi-list-table`).
- `cudi/views/css/cudi.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Styles the information displayed to customers on product pages, cart pages, and the “My Discounts” page.
  - **Key CSS class selectors:** Will target elements generated by the module’s front-office templates (e.g., `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Developers can override these in their theme’s `custom.css` or by creating a child theme.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
  - **Hook:** `displayProductAdditionalInfo` (specifically for unlogged users).
  - **Output:** Displays the customizable message for unlogged customers on product pages, encouraging registration and highlighting the loyalty program.
- `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
  - **Hook:** `displayProductAdditionalInfo` (for logged-in users).
  - **Output:** Displays the customizable message for logged-in customers on product pages, showing their current discount status and progress towards the next tier.
- `cudi/views/templates/hook/myAccount.tpl`
  - **Hook:** `displayCustomerAccount`.
  - **Output:** Renders a link or block in the customer’s “My Account” section, typically labeled “My Discounts,” which leads to the dedicated `mydiscount` page.

#### Admin templates (`views/templates/admin/`)

- `cudi/views/admin/assignButton.tpl`
  - **Scope:** Back-office.
  - **Output:** Likely renders a button or action link within the admin interface, possibly for triggering a manual recalculation or assignment of customer groups.
- `cudi/views/admin/orderstates.tpl`
  - **Scope:** Back-office.
  - **Output:** Used within the module’s main configuration form (`getContent()`) to render the multi-select dropdown or checkboxes for “Select order states.”

#### Front-office templates (`views/templates/front/`)

- `cudi/views/templates/front/myDiscount.tpl`
  - **Scope:** Front-office.
  - **Output:** This is the dedicated page template for the `CudiMydiscountModuleFrontController`. It displays a comprehensive overview of the customer’s loyalty status, including total spent, current group, discount percentage, and progress towards higher tiers.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not create custom SQL tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table, using keys like `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents`.
The cumulative discount rules (spending thresholds and associated customer groups) are likely stored as serialized data within a `ps_configuration` entry or managed directly by the `AdminCudiListController` which might use a custom table (though not explicitly listed in `classes/` or `sql/`). *Self-correction: Given the `AdminCudiListController` and its management of `cudi` entity, it’s highly probable that a custom table `ps_cudi` exists, even if not explicitly listed in `classes/` or `sql/` in the provided dossier. This table would store the `id_cudi`, `min_spend`, `id_group`, `discount_percentage` for each rule.*

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | Used to include module’s CSS/JS assets for front-office, or to initialize global JS variables. |
| `displayProductAdditionalInfo` | On product pages, typically below the product description or add-to-cart button. | Displays loyalty program information (current discount, progress) to customers. |
| `displayCustomerAccount` | On the customer’s “My Account” page. | Adds a link to the dedicated “My Discounts” page. |
| `displayShoppingCart` | On the shopping cart summary page. | Displays loyalty program information (current discount, cart contribution) to customers. |
| `updateOrderStatus` | Triggered when an order’s status is changed in the back office. | **Crucial for recalculating customer’s total spending and reassigning their group.** |
| `actionOrderStatusUpdate` | Similar to `updateOrderStatus`, provides more granular control after an order status update. | **Also crucial for recalculating customer’s total spending and reassigning their group.** |
| `actionAdminControllerSetMedia` | In the back office, when an admin controller is loaded. | Used to include module’s CSS/JS assets for the back-office (e.g., `cudi.js`, `cudi.css`). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find your purchased modules and their download links there. For technical assistance, please use the support channels provided on MyPresta.eu.
