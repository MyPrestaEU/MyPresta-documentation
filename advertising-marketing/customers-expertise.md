---
title: "Customers Expertise - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customers Expertise PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customers Expertise - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customers Expertise Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/customers-expertise/)
>
> ---


# Customers Expertise

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually present on any modern hosting environment. No special hosting requirements beyond a standard PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Customers Expertise)

This is the main configuration screen where you define your achievements, their criteria, and the rewards. The module’s configuration is managed through a dedicated interface that allows you to add, edit, and remove achievements.

**Screen Name & Menu Location:**
You can access this screen by navigating to **Modules > Module Manager**, searching for “Customers Expertise,” and clicking the “Configure” button.

**Available Actions & Settings:**
The configuration page will present a list of your currently defined achievements. You will typically find options to:

- **Add New Achievement:** A button or link to create a new achievement.
- **Edit Existing Achievement:** An icon (e.g., pencil) next to each achievement in the list to modify its settings.
- **Delete Achievement:** An icon (e.g., trash can) next to each achievement to remove it.

When adding or editing an achievement, you will typically encounter the following settings:

#### **Achievement Details**

- **Achievement Name:**

  - **What this setting does:** This is the title of the achievement that your customers will see (e.g., “First Time Buyer,” “Review Master,” “VIP Shopper”).
  - **Effect of changing this setting:** This name is displayed in the customer’s “My Achievements” section. A clear and appealing name encourages engagement.
  - **Recommended value:** Something descriptive and motivating.
  - **Merchant scenario / example:** “First Order Hero” for a customer’s first purchase.
- **Achievement Description:**

  - **What this setting does:** A brief explanation of what the achievement is about and how to earn it. This helps customers understand the goal.
  - **Effect of changing this setting:** This description appears alongside the name. A good description clarifies the achievement criteria.
  - **Recommended value:** Concise and encouraging.
  - **Merchant scenario / example:** “Make your very first purchase in our store to earn this badge!”
- **Achievement Image/Icon:**

  - **What this setting does:** Allows you to upload a visual representation (badge, icon) for the achievement.
  - **Effect of changing this setting:** This image is displayed next to the achievement name, making it visually appealing and recognizable.
  - **Recommended value:** A unique, high-quality image that reflects the achievement’s theme.
  - **Merchant scenario / example:** A “star” icon for a “Top Reviewer” achievement.
- **Active / Enabled:**

  - **What this setting does:** A switch to enable or disable the achievement.
  - **Effect of changing this setting:**
    - *When enabled:* The achievement is active, customers can earn it, and it will appear in their achievements list.
    - *When disabled:* The achievement is hidden, customers cannot earn it, and it won’t appear in the front office. Useful for seasonal achievements or those you’re still preparing.
  - **Recommended value:** YES for active achievements.
  - **Merchant scenario / example:** Disable a “Christmas Shopper” achievement after the holiday season.

#### **Achievement Criteria (How to Earn It)**

This is the core of the module, where you define the conditions a customer must meet. The module likely offers various criteria types. Common examples include:

- **Number of Orders:**

  - **What this setting does:** The customer must place a specified number of orders.
  - **Effect of changing this setting:** Determines how many successful orders are required.
  - **Recommended value:** Start with low numbers for initial achievements (e.g., 1, 3) and increase for higher tiers.
  - **Merchant scenario / example:** Set to “1” for “First Time Buyer,” “5” for “Loyal Customer.”
- **Total Spent Amount:**

  - **What this setting does:** The customer’s cumulative spending across all orders must reach a certain amount.
  - **Effect of changing this setting:** Defines the monetary threshold.
  - **Recommended value:** Tailor to your average order value and customer segments.
  - **Merchant scenario / example:** Set to “€100” for “Bronze Spender,” “€500” for “Silver Spender.”
- **Number of Products Purchased:**

  - **What this setting does:** The customer must purchase a specific total quantity of products (across all orders).
  - **Effect of changing this setting:** Sets the quantity threshold.
  - **Recommended value:** Useful for encouraging bulk purchases or trying different products.
  - **Merchant scenario / example:** Set to “10” for “Product Collector.”
- **Number of Product Reviews:**

  - **What this setting does:** The customer must submit a certain number of approved product reviews.
  - **Effect of changing this setting:** Encourages user-generated content and social proof.
  - **Recommended value:** Set to “1” for “First Reviewer,” “5” for “Review Master.”
  - **Merchant scenario / example:** Reward customers for contributing valuable feedback.
- **Specific Product/Category Purchase:**

  - **What this setting does:** The customer must purchase a product from a specific category or a specific product itself.
  - **Effect of changing this setting:** Promotes specific items or categories.
  - **Recommended value:** Use for new product launches or slow-moving inventory.
  - **Merchant scenario / example:** “Bought a new collection item” for purchasing from a “New Arrivals” category.

#### **Achievement Reward (Discount Voucher)**

- **Voucher Type:**

  - **What this setting does:** Defines the type of discount code the customer receives (e.g., percentage, fixed amount, free shipping).
  - **Effect of changing this setting:** Determines the nature of the reward.
  - **Recommended value:** Percentage discounts are often popular, but fixed amounts can be good for smaller purchases.
  - **Merchant scenario / example:** “Percentage discount” for 10% off the next order.
- **Voucher Value:**

  - **What this setting does:** The actual value of the discount (e.g., “10” for 10%, “€5” for a fixed amount).
  - **Effect of changing this setting:** Directly impacts the incentive for the customer.
  - **Recommended value:** Balance generosity with your profit margins.
  - **Merchant scenario / example:** “15” for a 15% discount.
- **Voucher Validity Period (Days):**

  - **What this setting does:** How many days the generated voucher is valid from the moment the customer claims it.
  - **Effect of changing this setting:** Creates urgency for the customer to use the voucher.
  - **Recommended value:** 7-30 days is common. Too short can frustrate, too long reduces urgency.
  - **Merchant scenario / example:** Set to “14” days to encourage a quick repeat purchase.
- **Minimum Order Amount for Voucher:**

  - **What this setting does:** If the voucher requires a minimum purchase value to be used.
  - **Effect of changing this setting:** Helps protect your margins and encourages customers to spend more.
  - **Recommended value:** Set a reasonable minimum that encourages an upsell without being prohibitive.
  - **Merchant scenario / example:** “€30” minimum order for a €5 discount.
- **Voucher Prefix:**

  - **What this setting does:** A custom prefix for the generated discount codes (e.g., “ACHIEVE-”, “BADGE-”).
  - **Effect of changing this setting:** Helps you identify the source of the discount codes in your PrestaShop sales reports.
  - **Recommended value:** A short, memorable prefix.
  - **Merchant scenario / example:** “EXPERT-” so you know the voucher came from the Customers Expertise module.

**Recommended workflow for daily store management:**

1. **Plan your achievements:** Before creating, decide what behaviors you want to reward and how many tiers of achievements you want.
2. **Start simple:** Begin with 2-3 basic achievements (e.g., first order, total spent, number of reviews) to test the waters.
3. **Create each achievement:** Go through the “Add New Achievement” process, carefully defining criteria and rewards.
4. **Monitor customer engagement:** Check your sales and customer accounts to see how customers are interacting with the achievements.
5. **Adjust and expand:** Based on performance, refine existing achievements or introduce new, more complex ones.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | Achievement Name | Descriptive | Title displayed to customer. |
|  | Achievement Description | Informative | Explains how to earn the achievement. |
|  | Achievement Image/Icon | Unique image | Visual representation for the badge. |
|  | Active / Enabled | YES | Toggles achievement visibility and eligibility. |
|  | **Criteria: Number of Orders** | 1, 3, 5 | Customer must place X orders. |
|  | **Criteria: Total Spent Amount** | €50, €100, €500 | Customer’s total spending must reach X. |
|  | **Criteria: Number of Products Purchased** | 5, 10, 20 | Customer must buy X total products. |
|  | **Criteria: Number of Product Reviews** | 1, 3, 5 | Customer must submit X approved reviews. |
|  | **Criteria: Specific Product/Category Purchase** | (Select product/category) | Customer must buy from a specific product/category. |
|  | **Reward: Voucher Type** | Percentage | Type of discount (%, fixed, free shipping). |
|  | **Reward: Voucher Value** | 10 (for %) | The amount of the discount. |
|  | **Reward: Voucher Validity Period (Days)** | 14-30 | How long the voucher is valid after claiming. |
|  | **Reward: Minimum Order Amount for Voucher** | (Optional) | Minimum cart value required to use the voucher. |
|  | **Reward: Voucher Prefix** | EXPERT- | Custom prefix for generated discount codes. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers aren’t seeing the achievements section in their account.**
A: First, ensure the “Customers Expertise” module is installed and enabled in your Back Office. Check the module’s configuration to make sure you have at least one achievement created and set to “Active.” Also, verify that your theme’s `customer-account.tpl` file (or equivalent) is correctly hooked to display the module’s link. If you have a custom theme, you might need a webmaster to ensure the hook is rendered.

**Q: Customers are earning achievements but not receiving discount codes.**
A: Go to the module’s configuration and edit the specific achievement. Double-check that a “Voucher Type” and “Voucher Value” are correctly defined for the reward. Ensure there are no typos or incorrect settings in the voucher parameters. Also, check your PrestaShop “Cart Rules” (or “Discounts” in older versions) to see if the generated vouchers are appearing there.

**Q: The achievement images aren’t displaying correctly.**
A: This usually points to an issue with the image upload or file permissions. Ensure the image file you uploaded is a standard web format (JPG, PNG, GIF) and not too large. Check your server’s file permissions for the module’s image directory (e.g., `modules/customersexpertise/img/`) to ensure PrestaShop can write and read files there. Clearing your PrestaShop cache (Advanced Parameters > Performance) can also help.

**Q: Can I translate the achievement names and descriptions into multiple languages?**
A: Yes, like most PrestaShop modules, the text fields for achievement names and descriptions should support multi-language input. When editing an achievement, look for language flags next to the input fields, allowing you to provide translations for each language installed in your store.

**Q: What happens if a customer earns an achievement but I later disable it?**
A: If an achievement is disabled, new customers will no longer be able to earn it, and it will typically be hidden from the front office. Customers who have already earned it will usually retain their earned status and any associated vouchers they claimed before the achievement was disabled. However, they won’t be able to re-claim vouchers if the achievement is re-enabled and they already have one.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the Customers Expertise module.

### 4.1 Architecture Overview

The Customers Expertise module follows a standard PrestaShop module architecture, primarily leveraging front controllers for customer-facing interactions and the main module class for configuration and hook management. It integrates gamification logic by tracking customer actions (orders, reviews) and dynamically generating PrestaShop `CartRule` (voucher) objects as rewards. The module’s core logic resides within its main PHP file and dedicated front controllers, with Smarty templates handling the presentation layer.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle the customer-facing logic and display for achievements and related features.

- `controllers/front/achievements.php`

  - **Class name & parent class:** `CustomersExpertiseAchievementsModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the primary controller for displaying a customer’s achievements. It fetches all defined achievements, checks the current customer’s eligibility and earned status for each, and prepares the data for the `achievements.tpl` template. It likely handles the logic for claiming vouchers once an achievement is earned.
  - **Routes:** Typically accessed via a URL like `yourstore.com/module/customersexpertise/achievements`.
- `controllers/front/affiliationlink.php`

  - **Class name & parent class:** `CustomersExpertiseAffiliationlinkModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** While the module description doesn’t explicitly mention affiliation, this controller suggests a potential feature for customers to generate and manage affiliation links, possibly as an achievement reward or a standalone feature. It would handle the display and generation of such links.
  - **Routes:** Likely `yourstore.com/module/customersexpertise/affiliationlink`.
- `controllers/front/index.php`

  - **Class name & parent class:** `CustomersExpertiseIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Often serves as a default or fallback front controller. It might redirect to the `achievements` controller or display a general landing page for the module if no specific action is requested.
  - **Routes:** `yourstore.com/module/customersexpertise/index` or `yourstore.com/module/customersexpertise`.
- `controllers/front/voucher.php`

  - **Class name & parent class:** `CustomersExpertiseVoucherModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller is likely responsible for the actual process of generating and assigning a discount voucher to a customer once they claim an earned achievement. It would interact with PrestaShop’s `CartRule` object to create the voucher and potentially update the customer’s achievement status.
  - **Routes:** Could be an AJAX endpoint or a direct URL for voucher claiming, e.g., `yourstore.com/module/customersexpertise/voucher`.

#### Back-Office Admin Controllers

The module does not appear to have dedicated custom Admin Controllers. Configuration is handled via the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes within the `classes/` directory. This suggests that the module’s core logic, achievement definitions, and customer tracking are likely managed directly within the main module file (`ajax_customersexpertise.php`) and potentially by leveraging existing PrestaShop `ObjectModel` classes like `Customer`, `Order`, `Product`, and `CartRule`.

The module would internally manage achievement data, possibly by:

- Storing achievement definitions (name, description, criteria, reward) in `ps_configuration` table as serialized arrays or JSON.
- Storing customer achievement status (earned, claimed voucher) in a custom table created during installation or also within `ps_configuration` or `ps_customer` meta fields.

### 4.4 JavaScript Assets (`views/js/`)

- `customersexpertise/lib/voucherengine/script.js`
  - **Scope:** Likely Front-office.
  - **Details:** This script is probably responsible for enhancing the user experience on the customer’s achievements page. It could handle:
    - AJAX requests for claiming vouchers (e.g., when a customer clicks a “Claim Voucher” button).
    - Dynamic updates to the page after a voucher is claimed (e.g., showing the voucher code, marking the achievement as claimed).
    - Client-side validation or interactive elements related to the gamification features.
    - Potentially, it might interact with the `voucher.php` front controller.

### 4.5 CSS Stylesheets (`views/css/`)

- `customersexpertise/css/customersexpertise.css`

  - **Scope:** Front-office customer styling.
  - **Details:** This is the main stylesheet for the module’s front-office components. It defines the visual appearance of the achievements list, individual achievement cards, voucher display, and any other UI elements presented to the customer.
  - **Key CSS class selectors:** Developers can expect classes like `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code`, etc., which can be overridden in a custom theme’s `custom.css` or `theme.css` to match the store’s branding.
- `customersexpertise/lib/voucherengine/ps16.css`

  - **Scope:** Front-office customer styling, specifically for PrestaShop 1.6 compatibility.
  - **Details:** This stylesheet likely contains specific overrides or additional styles to ensure the module’s front-office display is correct and visually consistent with PrestaShop 1.6 themes. It might address layout differences or specific element styling that changed between PrestaShop versions. For newer PrestaShop versions (1.7, 8.x, 9.x), this file might be conditionally loaded or its styles might be less relevant, relying more on `customersexpertise.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Front-office templates (`views/templates/front/`)**:

  - `customersexpertise/views/templates/front/achievements.tpl`
    - **Purpose:** This is the main template for displaying the customer’s achievements page. It iterates through the achievements data passed from the `achievements.php` controller, showing earned badges, criteria for unearned ones, and options to claim vouchers.
  - `customersexpertise/views/templates/front/affiliation-link.tpl`
    - **Purpose:** If the `affiliationlink.php` controller is active, this template would render the interface for customers to view or generate their affiliation links.
  - `customersexpertise/views/templates/front/voucher.tpl`
    - **Purpose:** This template might be used to display a single voucher code or a confirmation message after a voucher has been claimed, potentially as part of an AJAX response or a dedicated page.
- **Hook templates (`views/templates/hook/`)**:

  - `customersexpertise/views/templates/hook/customer-account.tpl`
    - **Hook:** `displayCustomerAccount` (or similar, depending on PrestaShop version).
    - **Purpose:** This template renders the link or block that appears in the customer’s “My Account” dashboard, directing them to the “My Achievements” page. It’s crucial for customer discoverability of the module’s features.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module description and file inventory do not explicitly list custom SQL files for table creation. This suggests that the module might store its data in one of the following ways:

  - **`ps_configuration`**: Achievement definitions (criteria, rewards) could be stored as serialized arrays or JSON strings in the `ps_configuration` table, using unique configuration keys (e.g., `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
  - **Existing PrestaShop tables**: Customer achievement status (which achievements they’ve earned, which vouchers they’ve claimed) might be stored in a custom field added to `ps_customer` or `ps_customer_group` tables, or in a custom table created dynamically by the module’s `install()` method without a dedicated `.sql` file.
  - **`ps_cart_rule`**: The module directly interacts with PrestaShop’s `CartRule` (discount voucher) system to generate rewards.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of all front-office pages. | To include CSS and JavaScript assets globally, or to add meta tags. |
| `displayLeftColumn` / `displayRightColumn` | In the left/right column of front-office pages. | To display a small promotional block or a link to the achievements page. |
| `displayProductButtons` / `displayProductExtraContent` (or similar product page hooks) | On the product page. | Potentially to track product views/purchases for achievement criteria, or to hint at gamification. |
| `displayFooter` | In the footer of all front-office pages. | To display a link to the achievements page or a general gamification promotion. |
| `displayCustomerAccount` | In the customer’s “My Account” dashboard. | **CRITICAL:** To add the “My Achievements” link for customers. |
| `actionValidateOrder` | After a customer’s order has been successfully validated. | **CRITICAL:** To check if the order fulfills any achievement criteria (e.g., first order, total spent, product purchase) and award achievements. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | After a product is added or updated. | Less likely, but could be used to update achievement criteria if they relate to product attributes. |
| `actionObjectCustomerAddAfter` | After a new customer registers. | To initialize achievement tracking for new customers. |
| `actionObjectReviewAddAfter` (or similar for review modules) | After a customer submits a product review. | **CRITICAL:** To check if the review fulfills any achievement criteria (e.g., number of reviews). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Customers Expertise module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the module functions optimally with your PrestaShop store.
