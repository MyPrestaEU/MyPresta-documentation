---
title: "Access to shop by customer groups - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Access to shop by customer groups PrestaShop module by MyPresta.eu."
sidebar:
  label: "Access to shop by customer groups - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Access to shop by customer groups Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Access to shop by customer groups

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the module name to access its settings.

#### **Customer Groups without access to shop**

This is the most crucial setting. It determines which customer groups will be blocked from viewing your store.

- **What this setting does:** This section displays a list of all customer groups defined in your PrestaShop store. You can select one or more groups from this list.
- **Effect of changing this setting:**
  - *When one or more groups are selected:* Any customer belonging to *any* of the selected groups will be blocked from accessing the shop’s front office. They will instead see the custom content you define below.
  - *When no groups are selected:* The module will not block any customers based on their group affiliation. All customers will have access to the shop (unless you enable the “Block access for not logged customers” option).
- **Recommended value:** Select the specific groups you wish to restrict. For example, if you have a “Wholesale Pending Approval” group, you might select it here.
- **Merchant scenario / example:** You’ve created a new customer group called “New Registrations - Pending Review.” You select this group here. Now, any new customer who registers will automatically be placed in this group and will not be able to browse your shop until you manually move them to an “Approved Customers” group.

#### **Block access for not logged customers**

This setting controls access for visitors who are not logged into your store.

- **What this setting does:** This is a simple ON/OFF switch.
- **Effect of changing this setting:**
  - *When enabled (YES):* All visitors who are not logged into a customer account will be blocked from accessing the shop. They will see the custom content page. Once they log in (and if they belong to an allowed group), they will gain access.
  - *When disabled (NO):* Unlogged visitors will have access to the shop, unless they are explicitly blocked by belonging to a “Customer Groups without access to shop.”
- **Recommended value:**
  - **YES:** If you want your entire shop to be private, requiring all visitors to log in first (e.g., a B2B store, a members-only club).
  - **NO:** If you want your shop to be publicly viewable, but only restrict specific customer groups.
- **Merchant scenario / example:** You run a wholesale-only store. You enable this setting. Now, anyone visiting your site must first log in to see your products and prices.

#### **Show login form on blocked page**

This setting determines if a login form appears on the page shown to blocked customers.

- **What this setting does:** This is a simple ON/OFF switch.
- **Effect of changing this setting:**
  - *When enabled (YES):* A standard PrestaShop login form will be displayed on the custom content page, allowing blocked customers to attempt to log in.
  - *When disabled (NO):* No login form will be shown. Customers will only see your custom message.
- **Recommended value:**
  - **YES:** If you expect blocked customers to be existing customers who simply need to log in to gain access. This improves user experience.
  - **NO:** If you want to force customers to register first, or if the access restriction is permanent for certain groups.
- **Merchant scenario / example:** You’ve blocked access for non-logged-in users. By enabling this, customers can easily log in directly from the restricted page without having to navigate to a separate login page.

#### **Allow registration on blocked page**

This setting determines if a registration link appears on the page shown to blocked customers.

- **What this setting does:** This is a simple ON/OFF switch.
- **Effect of changing this setting:**
  - *When enabled (YES):* A link to the customer registration page will be displayed on the custom content page.
  - *When disabled (NO):* No registration link will be shown.
- **Recommended value:**
  - **YES:** If you want to allow new customers to register from the restricted page.
  - **NO:** If you want to control registration separately, or if your shop is strictly for pre-approved customers.
- **Merchant scenario / example:** You run a B2B store that requires registration. You enable this setting so potential new clients can easily sign up for an account directly from the access-restricted page.

#### **Custom contents to show**

This is where you define the message and content displayed to blocked customers.

- **What this setting does:** This is a rich text editor (WYSIWYG) where you can enter text, images, HTML, and even videos. It supports multi-language content, so you can provide different messages for different languages installed in your store.
- **Effect of changing this setting:** The content you enter here will be displayed to any customer who is blocked from accessing your shop.
- **Recommended value:** Provide a clear, polite, and informative message.
- **Merchant scenario / example:**
  - *For a B2B store:* “Welcome to our Wholesale Portal! Please log in with your credentials or register for a new account to view our product catalog.”
  - *For a temporary restriction:* “Our shop is currently undergoing maintenance. We’ll be back online soon! Thank you for your patience.”
  - *For exclusive access:* “This section of our store is reserved for VIP members. Please log in or contact support for access.”

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | **Customer Groups without access to shop** | None selected | Select groups to block from viewing the shop. Customers in these groups see custom content. |
| Module Configuration | **Block access for not logged customers** | NO | YES: All non-logged visitors are blocked. NO: Non-logged visitors have access (unless in a blocked group). |
| Module Configuration | **Show login form on blocked page** | YES | YES: Displays a login form on the restricted page. NO: No login form is shown. |
| Module Configuration | **Allow registration on blocked page** | YES | YES: Displays a registration link on the restricted page. NO: No registration link is shown. |
| Module Configuration | **Custom contents to show** | Empty | Defines the message/HTML content displayed to blocked customers. Supports multi-language. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My shop is completely blocked, even for me! What do I do?**
A1: This usually happens if you’ve enabled “Block access for not logged customers” and you are not logged in, or if your admin account is somehow associated with a blocked customer group.
\* **Solution 1 (Recommended):** Log in to your PrestaShop Back Office. The module only blocks the front office. Once logged into the BO, navigate to Modules > Module Manager, find “Access to shop by customer groups,” and click “Configure.” Adjust the settings to allow your access.
\* **Solution 2 (If you can’t access BO):** If you are completely locked out, you might need to temporarily disable the module via FTP. Go to `modules/asg/` and rename the `asg.php` file (e.g., `asg.php.bak`). This will disable the module. Then, you can log into your BO and re-enable/reconfigure it. Remember to rename the file back to `asg.php` afterward.

**Q2: The custom content looks plain or doesn’t match my theme.**
A2: The custom content area uses a basic template.
\* **Solution:** You can use the rich text editor to add HTML, inline CSS, or images to style your message. For more advanced styling, a webmaster can modify the `custom.css` file or the `custom-contents.tpl` template (see developer section). Ensure your custom content is well-formatted and responsive.

**Q3: Why isn’t the login/registration form showing up?**
A3: Check the module configuration:
\* Make sure “Show login form on blocked page” is set to YES.
\* Make sure “Allow registration on blocked page” is set to YES.
\* Also, ensure that customer registration is generally enabled in your PrestaShop settings (Customers > Settings > Enable account creation).

**Q4: I’ve made changes, but they don’t appear on the front office.**
A4: PrestaShop uses caching, which can sometimes delay the display of changes.
\* **Solution:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office. Click “Clear cache” (or “Clear Smarty cache” in older versions). This should refresh your front office.

**Q5: How do I manage which customers are in which groups?**
A5: You manage customer groups through the standard PrestaShop interface:
\* Go to **Customers > Customers** to edit individual customer accounts and assign them to groups.
\* Go to **Customers > Groups** to create new groups or edit existing ones.
\* Remember that a customer can belong to multiple groups. If a customer belongs to *any* group that you’ve marked as “without access,” they will be blocked.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Access to shop by customer groups” module (`asg`) operates primarily by hooking into the `displayHeader` event. This allows it to execute its logic very early in the page load process, before any content is rendered. If a customer is determined to be restricted, the module takes control, prevents further rendering of the standard PrestaShop page, and instead displays its custom access page. It leverages PrestaShop’s configuration system for settings and Smarty for templating.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers. All logic is encapsulated within the main module file (`asg.php`) and executed via hooks or the `getContent()` method for configuration.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` entities. It directly interacts with PrestaShop’s core `Customer`, `Group`, and `Configuration` classes.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- **`asg/views/css/custom.css`**
  - **Scope:** Front-office customer styling for the restricted access page.
  - **Main UI components and containers it styles:** This file provides basic styling for the custom content wrapper, login form, and registration link on the restricted access page. It ensures the displayed content is centered and readable.
  - **Key CSS class selectors developers can override:**
    - `.asg_wrapper`: The main container for the entire restricted content.
    - `.asg_content`: The div containing the custom HTML message.
    - `.asg_login_form`: The container for the login form.
    - `.asg_registration_link`: The container for the registration link.
    - Standard PrestaShop form elements within the login form.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None explicitly defined as hook templates. The module directly renders templates based on its internal logic.
- **Admin templates (`views/templates/admin/`)**:
  - **`asg/views/admin.tpl`**: This template is rendered by the `getContent()` method in `asg.php`. It contains the HTML structure for the module’s configuration form in the PrestaShop Back Office. It includes the customer group selection, toggle switches for login/registration, and the rich text editor for custom content.
- **Front-office templates (`views/templates/front/`)**:
  - **`asg/views/custom-contents.tpl`**: This is the primary template rendered when a customer is blocked. It displays the custom content defined in the module configuration. It conditionally includes `login-form.tpl` and `registration-link.tpl` based on module settings.
  - **`asg/views/login-form.tpl`**: This template contains the HTML for the standard PrestaShop customer login form. It’s included within `custom-contents.tpl` if the “Show login form” option is enabled.
  - **`asg/views/registration-link.tpl`**: This template contains the HTML for the link to the customer registration page. It’s included within `custom-contents.tpl` if the “Allow registration” option is enabled.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table (or `_configuration` depending on prefix) using keys such as:
    - `ASG_ALLOWREGAUTH`: Boolean for allowing registration.
    - `ASG_SHOWLOGINFORM`: Boolean for showing login form.
    - `ASG_CCONTENTS`: Multilingual field for custom content (HTML).
    - `ASG_WHATTOSHOW`: Serialized array of customer group IDs that are blocked.
    - `ASG_BLOCK_NOT_LOGGED`: Boolean for blocking non-logged users.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed very early in the front-office page load, within the `<head>` section. | This is the primary hook used by the module. It checks customer login status and group affiliation. If a customer is restricted, it immediately terminates the standard PrestaShop rendering process and outputs the custom access page (`custom-contents.tpl`). |
| `actionCustomerGroupsUpdate` | Executed when customer groups are updated. | Used to clear the module’s internal cache related to customer groups, ensuring that changes to group assignments are immediately reflected. |
| `actionObjectCustomerAddAfter` | Executed after a new customer is added. | Used to clear the module’s internal cache related to customer groups, ensuring that new customers are correctly evaluated for access. |
| `actionObjectCustomerUpdateAfter` | Executed after an existing customer is updated. | Used to clear the module’s internal cache related to customer groups, ensuring that changes to customer group assignments are immediately reflected. |

## 5. Official Support & Updates

For official updates, bug fixes, and dedicated developer support for the “Access to shop by customer groups” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is committed to providing timely assistance and ensuring the module’s compatibility with the latest PrestaShop versions.
