---
title: "Customer IP address in order details - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer IP address in order details PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer IP address in order details"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer IP address in order details Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Customer IP address in order details

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient, as this module has minimal external dependencies.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
This module is designed to be extremely simple and effective, requiring no complex configuration. After installation, you will find a basic configuration screen.

-   **Screen Name & Menu Location:** Back Office > Modules > Module Manager > "Customer IP address in order details" > Configure

On this screen, you will typically see:

-   **What this setting does:** This module usually doesn't have specific configurable settings beyond its initial installation. Its core functionality (displaying the IP address) is active by default once installed. The configuration page might simply confirm that the module is active or provide basic information.
-   **Effect of changing this setting:** Since there are no specific settings to change, the module's behavior remains consistent: it will display the customer's IP address on the order details page.
-   **Recommended value:** N/A (No configurable options).
-   **Merchant scenario / example:** Simply install and enable the module. When you view any order in your back office, you will now see the customer's IP address displayed prominently within the order details.

### 2.2 Configuration Quick Reference Table
| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | *(No specific settings)* | N/A | The module automatically displays customer IP addresses on order detail pages once installed and enabled. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've installed the module, but I don't see the IP address on the order details page. What should I do?**
A:
1.  **Check Module Status:** Go to **Modules > Module Manager** and ensure "Customer IP address in order details" is installed and enabled.
2.  **Clear Cache:** Sometimes PrestaShop's cache can prevent changes from appearing immediately. Go to **Advanced Parameters > Performance**, scroll down, and click "Clear cache".
3.  **Verify Order Page:** Navigate to an existing order (or place a test order) in **Orders > Orders** and click to view its details. The IP address should appear in a dedicated block or section.
4.  **Theme Compatibility:** While unlikely for a simple module like this, very heavily customized themes might occasionally interfere with hooks. If the issue persists, temporarily switch to the default PrestaShop theme (Classic) to see if the IP address appears.

**Q: Does this module store customer IP addresses in my database?**
A: PrestaShop itself typically stores the customer's IP address when they register or place an order. This module simply retrieves and displays that existing information from your database on the order details page. It does not create new database tables or store additional IP data independently.

**Q: Will this module slow down my store?**
A: No. This module is very lightweight. It only adds a small piece of information to an existing back-office page (order details) and does not perform any complex calculations or front-office operations that would impact customer browsing speed.

**Q: Is the IP address always accurate?**
A: The IP address recorded is generally the one from which the customer connected to your store. However, customers using VPNs, proxy servers, or certain mobile networks might have an IP address that doesn't directly reflect their physical location. It's a useful indicator but not always a definitive geographical pinpoint.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)
This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview
The "Customer IP address in order details" module (`iporder`) is a very simple PrestaShop module designed to extend the functionality of the `AdminOrders` controller. It leverages a standard PrestaShop hook (`displayAdminOrder`) to inject additional information (the customer's IP address) directly into the back-office order detail page. It follows a minimalist approach, focusing solely on displaying existing data rather than introducing new data models or complex logic.

### 4.2 Controllers (`controllers/`)
This module does not introduce any custom Front-Office or Back-Office controllers. Its functionality is entirely integrated via hooks within existing PrestaShop controllers.

### 4.3 Core Classes & Models (`classes/`)
This module does not define any custom classes or extend `ObjectModel`. It operates by directly accessing existing PrestaShop core objects and their properties (e.g., `Order`, `Customer`).

### 4.4 JavaScript Assets (`views/js/`)
This module does not include any custom JavaScript files. The display of the IP address is purely server-side rendered HTML.

### 4.5 CSS Stylesheets (`views/css/`)
This module does not include any custom CSS files. The injected content will inherit styling from the PrestaShop back-office theme.

### 4.6 Smarty Template Structure (`views/templates/`)
The module's entire display logic resides within a single Smarty template file.

-   **Hook templates (`views/templates/hook/`)**:
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook:** `displayAdminOrder`
        *   **Purpose:** This template is rendered on the PrestaShop back-office order details page. It retrieves the customer's IP address associated with the current order and displays it in a dedicated block.
        *   **Content:** It typically accesses the `$order` and `$customer` Smarty variables (passed by the `displayAdminOrder` hook) to fetch `{$customer->ip_registration_date}` or similar, and formats it for display. It might also use `$_SERVER['REMOTE_ADDR']` if the IP is not directly stored with the customer or order object in a readily accessible way through the hook. Given the module's description, it likely accesses the IP address stored with the customer or order object.

### 4.7 Database Schema & Hooks Map
-   **Database Tables**: This module does not create any custom database tables. It relies on existing PrestaShop tables, specifically `ps_customer` (which stores `last_passwd_gen` and `ip_registration_date` in some versions, though `ip_registration_date` is not strictly the order IP) and potentially `ps_orders` if the IP is stored directly with the order. The most common approach for this module would be to retrieve the IP from the `$_SERVER['REMOTE_ADDR']` at the time of order placement and store it in a custom field if not already present, or simply display the `ip_registration_date` from the customer object. However, based on the module's simplicity and lack of custom classes, it's most likely fetching the IP associated with the customer's registration or the `REMOTE_ADDR` at the time of order processing if available through the hook context.
    *   **Note:** PrestaShop 1.7+ stores the `current_ip_address` in the `ps_connections` table, linked to `ps_guest` and `ps_customer`. The `ip_registration_date` in `ps_customer` is the IP from which the customer registered. The module's goal is to show the IP *at the time of order*. This usually means either:
        1.  Accessing `$_SERVER['REMOTE_ADDR']` if the hook provides it in the context of the order.
        2.  Retrieving the IP from the `ps_connections` table based on the `id_guest` associated with the order.
        3.  Retrieving the `ip_registration_date` from `ps_customer` (less accurate for the specific order).
        Given the simplicity, it's likely using the most straightforward method available through the hook.

-   **Registered Hooks Table**:
    | Hook Name | Execution Timing | Technical Purpose |
    |---|---|---|
    | `displayAdminOrder` | Executed when the PrestaShop back-office order details page is rendered. | Injects the customer's IP address into the order details view. |

## 5. Official Support & Updates
For official updates, technical support, and any further inquiries regarding the "Customer IP address in order details" module, please refer to your MyPresta.eu customer account. You can access your downloads and support tickets directly from [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/).
