---
title: "Link to assign customer to group - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Link to assign customer to group PrestaShop module by MyPresta.eu."
sidebar:
  label: "Link to assign customer to group"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Link to assign customer to group Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Link to assign customer to group

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 5.6 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Configure Link to assign customer to group)

This is the main and only configuration screen for the module. Here you can define how the module behaves when assigning customers to groups.

#### **Change group to default**
-   **What this setting does:** This setting determines whether the module should also assign the customer to the "Default" customer group in addition to the group specified in the URL.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* If a customer clicks a link to be assigned to "Group X", they will also be assigned to the "Default" group. This means they will be part of both "Group X" and "Default". This can be useful if your "Default" group has certain base permissions or discounts that you always want customers to have, regardless of other groups they join.
    -   *When disabled (NO):* The customer will only be assigned to the group specified in the URL (e.g., "Group X"). They will not be automatically added to the "Default" group unless they are already part of it or another mechanism adds them.
-   **Recommended value:** **NO**. In most cases, you want to assign customers to a *specific* group without necessarily adding them to the "Default" group, especially if your "Default" group has no special meaning or if you want to manage groups more precisely. Enable this only if you have a specific reason to always include the "Default" group.
-   **Merchant scenario / example:** You have a "VIP" group with special discounts. If you enable this, a customer clicking a VIP link will be in both "VIP" and "Default". If "Default" has a 5% store-wide discount and "VIP" has a 15% discount on specific products, the customer will benefit from both where applicable. If disabled, they would only get the "VIP" benefits.

#### **Unassign customer from other groups**
-   **What this setting does:** This setting controls whether the module should remove the customer from *all other* customer groups when they are assigned to a new group via the special link.
-   **Effect of changing this setting:**
    -   *When enabled (YES):* If a customer is currently in "Group A" and "Group B", and then clicks a link to be assigned to "Group X", they will be removed from "Group A" and "Group B", and only remain in "Group X" (and potentially "Default" if the previous setting is enabled). This ensures the customer is *only* in the target group.
    -   *When disabled (NO):* The customer will be *added* to the new group ("Group X") but will *remain* in any other groups they were already part of (e.g., "Group A", "Group B"). This allows customers to be members of multiple groups simultaneously.
-   **Recommended value:** **NO**. Allowing customers to be in multiple groups offers more flexibility for complex segmentation. Only enable this if you need strict, mutually exclusive groups (e.g., a customer can only be "Retail" OR "Wholesale", never both).
-   **Merchant scenario / example:**
    -   *Enabled (YES):* You have "Standard Customer" and "Wholesale Customer" groups. A customer clicks a link to become "Wholesale". If enabled, they are removed from "Standard Customer" and only remain "Wholesale". This is ideal for clear, distinct customer types.
    -   *Disabled (NO):* You have "Newsletter Subscriber" and "Loyalty Program Member" groups. A customer clicks a link to join the "Loyalty Program". If disabled, they remain a "Newsletter Subscriber" *and* become a "Loyalty Program Member". This is ideal for additive benefits.

#### **How to Create the Special Link**
The module works by adding a special parameter to any URL in your store. The parameter format is: `?asg={group_id}`

1.  **Find the Group ID:**
    -   Go to **Customers > Groups** in your PrestaShop Back Office.
    -   Note the ID number next to the group you want to assign customers to. For example, if "Wholesale" has an ID of `3`, then `3` is your `group_id`.
2.  **Construct the Link:**
    -   Take any URL from your store (e.g., `https://yourstore.com/`)
    -   Append `?asg={group_id}` to it.
    -   **Example:** To assign a customer to group ID `3` (e.g., "Wholesale") and redirect them to your homepage: `https://yourstore.com/?asg=3`
    -   **Example:** To assign a customer to group ID `5` (e.g., "VIP") and redirect them to a specific product page: `https://yourstore.com/en/product/123-awesome-product?asg=5`

:::warning
The `asg` parameter must be the *first* parameter if there are no other parameters in the URL (i.e., use `?`). If the URL already has parameters (e.g., `https://yourstore.com/category/1-clothing?id_category=1`), you must use `&` to add the `asg` parameter: `https://yourstore.com/category/1-clothing?id_category=1&asg=3`.
:::

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Module Configuration | Change group to default | NO | If YES, customer is also added to the 'Default' group. If NO, only to the specified group. |
| Module Configuration | Unassign customer from other groups | NO | If YES, customer is removed from all other groups. If NO, customer remains in existing groups and is added to the new one. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The customer clicked the link but wasn't assigned to the group. What's wrong?**
A:
1.  **Customer not logged in:** The module only works for *logged-in* customers. If they weren't logged in, they'll just be redirected to the page without group assignment.
2.  **Incorrect Group ID:** Double-check the `group_id` in your URL against the actual ID in **Customers > Groups**.
3.  **Incorrect URL parameter:** Ensure you're using `?asg=` for the first parameter and `&asg=` for subsequent parameters.
4.  **Module not enabled:** Verify the module is installed and enabled in **Modules > Module Manager**.
5.  **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.

**Q: Can I assign a customer to multiple groups with one link?**
A: No, the `asg` parameter only supports assigning to one group at a time. However, if "Unassign customer from other groups" is set to NO, the customer will be *added* to the new group while retaining membership in their existing groups.

**Q: Does this module affect SEO?**
A: No, this module has no direct impact on your store's SEO. The `asg` parameter is a dynamic parameter that search engines typically ignore.

**Q: What happens if a customer clicks the link multiple times?**
A: If the customer is already in the target group, nothing changes. If they are not, they will be assigned to it. The module is designed to handle this gracefully without errors.

**Q: I want to remove a customer from a group using a link. Is that possible?**
A: No, this module is designed only for *assigning* customers to groups. It does not provide functionality to remove customers from groups via a URL. You would need to do this manually in the Back Office or use another module/custom development.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Link to assign customer to group" module (`assigntogroup`) is a lightweight PrestaShop module primarily designed to intercept front-office requests and modify customer group assignments based on a URL parameter. It leverages PrestaShop's hook system (`displayHeader`) to execute its logic early in the page load process, ensuring group changes are applied before the page content is rendered. It does not introduce custom controllers, models, or complex JavaScript/CSS. Its core functionality resides within the main module class.

### 4.2 Controllers (`controllers/`)
-   **Front-Office Controllers**: None. The module's logic is executed via a hook, not a dedicated front controller.
-   **Back-Office Admin Controllers**: None. All configuration is handled within the main module's `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
-   No custom classes or ObjectModels are defined within the `classes/` directory. The module directly interacts with PrestaShop's core `Customer` and `Group` ObjectModels.

### 4.4 JavaScript Assets (`views/js/`)
-   No JavaScript files are included with this module.

### 4.5 CSS Stylesheets (`views/css/`)
-   No CSS files are included with this module.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Purpose**: This template is used to render the module's configuration form in the PrestaShop Back Office. It's rendered by the `getContent()` method of the main module class.
        *   **Content**: Contains the HTML structure for the two configuration switches (`asg_unassign`, `asg_default`) and the form submission button. It uses PrestaShop's standard helper form elements.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   The module does not create any custom SQL tables.
    *   It stores its configuration settings in the `ps_configuration` table:
        *   `PS_ASG_UNASSIGN`: Stores the value of the "Unassign customer from other groups" setting (0 or 1).
        *   `PS_ASG_DEFAULT`: Stores the value of the "Change group to default" setting (0 or 1).

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Executed early in the front-office page load, within the `<head>` section. | This is the primary hook used by the module. It checks for the `asg` URL parameter, verifies if a customer is logged in, and then performs the group assignment logic based on the module's configuration settings (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`). |

### 4.8 Main Module PHP File (`assigntogroup/assigntogroup.php`)

This is the central file for the module, containing its installation, uninstallation, configuration, and core logic.

-   **Class Name**: `Assigntogroup`
-   **Parent Class**: `Module`
-   **Key Methods**:
    *   `__construct()`: Initializes module metadata (name, tab, version, author, etc.).
    *   `install()`:
        *   Registers the `displayHeader` hook.
        *   Sets default configuration values for `PS_ASG_UNASSIGN` (0) and `PS_ASG_DEFAULT` (0) in `ps_configuration`.
        *   Returns `true` on success.
    *   `uninstall()`:
        *   Unregisters the `displayHeader` hook.
        *   Deletes configuration values `PS_ASG_UNASSIGN` and `PS_ASG_DEFAULT` from `ps_configuration`.
        *   Returns `true` on success.
    *   `getContent()`:
        *   Handles the module's Back Office configuration form submission.
        *   Updates `PS_ASG_UNASSIGN` and `PS_ASG_DEFAULT` in `ps_configuration` based on user input.
        *   Renders the configuration form using `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()`:
        *   **Core Logic**: This method is executed on every front-office page load.
        *   Checks if the `asg` GET parameter is present and is a valid integer representing a `id_group`.
        *   Verifies if a customer is logged in (`$this->context->customer->isLogged()`).
        *   Retrieves the target `Group` object.
        *   Retrieves the current `Customer` object.
        *   Based on `PS_ASG_UNASSIGN` and `PS_ASG_DEFAULT` configuration:
            *   Manages the customer's group associations (`$customer->updateGroup()`).
            *   Adds the customer to the specified group.
            *   Optionally removes the customer from other groups.
            *   Optionally adds the customer to the default group.
        *   Redirects the user to the current URL without the `asg` parameter to prevent re-processing on refresh.

## 5. Official Support & Updates
For the latest updates, bug fixes, and official support for the "Link to assign customer to group" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist you with any issues or questions regarding the module's functionality.
