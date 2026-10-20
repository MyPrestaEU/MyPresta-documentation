---
title: "CMS pages for groups - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the CMS pages for groups PrestaShop module by MyPresta.eu."
sidebar:
  label: "CMS pages for groups - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy CMS pages for groups Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/cms-pages-for-groups/)
>
> ---


# CMS pages for groups

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > CMS pages for groups)

This is the main configuration screen where you will manage which customer groups can access specific CMS pages.

When you first access the configuration page, you will see a list of all your existing CMS pages. For each CMS page, you will find options to control its visibility.

**Overall Page Structure:**
The configuration page displays a table. Each row in the table represents one of your CMS pages. For each CMS page, you will see:

- **Page Name:** The title of your CMS page (e.g., “About Us”, “Terms and Conditions”).
- **Customer Groups:** A list of checkboxes, one for each customer group defined in your PrestaShop store (e.g., “Visitor”, “Guest”, “Customer”, “Wholesale”).

**What this setting does:**
For each CMS page, you select the customer groups that are **allowed** to view that specific page. If a customer is not part of any of the selected groups for a given page, they will be denied access to that page.

**Effect of changing this setting:**

- **When a group is checked for a CMS page:** Customers belonging to this group will be able to view the CMS page normally.
- **When a group is unchecked for a CMS page:** Customers belonging to this group will **not** be able to view the CMS page. If they try to access it, they will be redirected to a “Page Not Found” error.
- **If no groups are selected for a CMS page:** This means the page is effectively hidden from *all* customers, as no group has permission to view it. This might be useful for pages under construction or internal-only content.
- **If all groups are selected for a CMS page:** This means the page is visible to everyone, effectively reverting to PrestaShop’s default behavior for that specific page.

**Recommended value:**
This depends entirely on your business needs.

- For standard pages like “About Us” or “Contact Us,” you’ll likely check all groups.
- For specific legal terms for B2B, you might only check your “Wholesale” group.
- For a “VIP Club Benefits” page, you might only check your “VIP Customer” group.

**Merchant scenario / example:**
Let’s say you have three customer groups: “Visitor” (not logged in), “Customer” (standard registered users), and “Wholesale” (B2B clients).

1. **Scenario 1: “About Us” Page**

   - **Purpose:** General information for everyone.
   - **Action:** Check “Visitor”, “Customer”, and “Wholesale” for the “About Us” page.
   - **Result:** Everyone can see the “About Us” page.
2. **Scenario 2: “Wholesale Terms & Conditions” Page**

   - **Purpose:** Specific legal terms only for your B2B clients.
   - **Action:** Check only “Wholesale” for the “Wholesale Terms & Conditions” page.
   - **Result:** Only customers in the “Wholesale” group can view this page. “Visitor” and “Customer” groups will be denied access.
3. **Scenario 3: “Loyalty Program Details” Page**

   - **Purpose:** Information for registered customers about their loyalty points.
   - **Action:** Check “Customer” and “Wholesale” (assuming wholesale clients can also be part of the loyalty program) for the “Loyalty Program Details” page.
   - **Result:** Only logged-in customers (standard or wholesale) can view this page. Visitors will be denied access.

**Saving Your Changes:**
After making your selections for all CMS pages, remember to click the **“Save”** button (usually at the bottom of the page) to apply your changes.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **CMS Page Name** (e.g., “About Us”) | Varies by page | Controls which customer groups can view this specific CMS page. |
|  | Checkbox for **“Visitor”** group | Varies | If checked, non-logged-in users can view the page. |
|  | Checkbox for **“Guest”** group | Varies | If checked, users who checked out as guest can view the page. |
|  | Checkbox for **“Customer”** group | Varies | If checked, standard registered customers can view the page. |
|  | Checkbox for **“Wholesale”** group (or any custom group) | Varies | If checked, customers in this specific group can view the page. |
|  | **Save Button** | N/A | Applies all selected visibility settings to the CMS pages. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve restricted a CMS page, but it still appears in my footer/header menu. Why?**
A1: This module controls *access* to the page content, not its visibility in navigation menus. If you want to hide the link itself from certain groups, you’ll need to either:
\* Manually remove the link from your theme’s template files (e.g., `footer.tpl`, `header.tpl`).
\* Use a menu management module that offers group-based visibility for menu items.
\* If a customer clicks a restricted link, they will still be denied access to the page content.

**Q2: A customer is logged in, but they still can’t see a page I’ve allowed for their group. What’s wrong?**
A2:
\* **Clear Cache:** Always start by clearing your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” (or “Clear Smarty cache” in older versions).
\* **Verify Group Assignment:** Double-check that the customer is indeed assigned to the correct customer group(s) that you’ve allowed for the CMS page. You can check this in **Customers > Customers** by editing the customer’s profile.
\* **Module Configuration:** Revisit the module’s configuration page and ensure the correct group checkbox is ticked for that specific CMS page.
\* **Browser Cache:** Ask the customer to clear their browser cache or try accessing the page in an incognito/private browsing window.

**Q3: Can I display a custom message instead of a “Page Not Found” error when access is denied?**
A3: This module, in its current version, redirects to the standard PrestaShop “Page Not Found” page. Customizing this would require theme modifications or an additional module that specifically handles custom error pages based on access denial.

**Q4: Will this module slow down my store?**
A4: No, the module is very lightweight. It overrides a core PrestaShop controller to check customer group permissions before loading a CMS page. This check is efficient and should not noticeably impact your store’s performance.

**Q5: I’ve updated PrestaShop, and now the module isn’t working. What should I do?**
A5:
\* **Check Module Version:** Ensure you have the latest version of the “CMS pages for groups” module from your MyPresta.eu account, compatible with your new PrestaShop version.
\* **Reinstall/Reconfigure:** Sometimes, after a major PrestaShop update, modules might need to be reinstalled or reconfigured. Try uninstalling and then reinstalling the module (your settings should be preserved, but always backup first). Then, re-check your settings in the module’s configuration page.
\* **Clear Cache:** Always clear your PrestaShop cache after any update or module change.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “CMS pages for groups” module operates by overriding the core `CmsController` in PrestaShop’s front office. This allows it to intercept requests for CMS pages *before* they are rendered and apply custom access logic based on customer group permissions configured in the module’s back office. The module stores its configuration directly in the `ps_configuration` table.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `groupscms/override/controllers/front/CmsController.php`
    - **Class name & parent class**: `CmsController` (overrides the core `CmsController`)
    - **Responsibility**: This is the critical component. It extends the original `CmsController` to add a `init()` method. Inside `init()`, it retrieves the current CMS page’s ID and checks the module’s configuration (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`) to determine which customer groups are allowed access. If the current customer (or visitor) is not in an allowed group, it redirects them to the “Page Not Found” page (`$this->redirect_after = '404';`). This ensures that unauthorized users cannot view restricted CMS content.
- **Back-Office Admin Controllers**: None. The module’s configuration is handled directly within the `getContent()` method of the main module file.

### 4.3 Core Classes & Models (`classes/`)

None. The module does not define custom `ObjectModel` classes. It directly interacts with existing PrestaShop `CMS` and `Group` objects and stores its configuration in `ps_configuration`.

### 4.4 JavaScript Assets (`views/js/`)

None. The module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- `groupscms/css.css`
  - **Scope**: Back-office admin form styling.
  - **Main UI components and containers it styles**: This stylesheet is likely used to style the module’s configuration table in the PrestaShop back office, ensuring it looks consistent with the PrestaShop admin theme. It might define styles for the table rows, checkboxes, or labels within the module’s configuration form.
  - **Key CSS class selectors developers can override in their theme**: Specific selectors would be found within the file, but typically they would target elements within the module’s `getContent()` output, such as `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox`, etc.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**: None. The module does not render content via standard front-office hooks.
- **Admin templates (`views/templates/admin/`)**:

  - `groupscms/admin.tpl`
    - **Purpose**: This template is rendered by the `getContent()` method of the main module file (`groupscms.php`). It generates the entire configuration interface for the module in the PrestaShop back office. This includes the table listing all CMS pages and the checkboxes for each customer group.
  - `groupscms/cms.tpl`
    - **Purpose**: This template is likely an include or a partial used within `admin.tpl` to render individual rows or sections related to CMS pages within the configuration table. It would contain the loop for displaying each CMS page and its associated group checkboxes.
- **Front-office templates (`views/templates/front/`)**: None. The module does not add new front-office templates. It controls access to existing CMS page templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All configuration data is stored in the `ps_configuration` table.

  - **Configuration Keys**:
    - `CMSG_CMS_ID_[CMS_ID]`: Stores a comma-separated string of `group_id` values for each CMS page. For example, `CMSG_CMS_ID_12` might store `"1,2,3"` indicating that groups with IDs 1, 2, and 3 have access to CMS page with ID 12.
    - `groupscms_many_page`: (Likely an internal flag or legacy setting, not directly user-configurable).
    - `mypresta_updates`, `update_`, `updatev_`: These are common keys used by MyPresta.eu modules for update checks and version tracking.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Executed when an Admin Controller is setting its media (CSS/JS). | Used by the module to include its `css.css` stylesheet for the back-office configuration page. |
| `displayBackOfficeHeader` | Executed in the `<head>` section of the Back Office. | Often used for including global admin CSS/JS or for update checks. The module might use this for its update mechanism. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “CMS pages for groups” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
