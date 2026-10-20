---
title: "Dashboard comments / reviews moderation - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Dashboard comments / reviews moderation PrestaShop module by MyPresta.eu."
sidebar:
  label: "Dashboard comments / reviews moderation"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Dashboard comments / reviews moderation Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Dashboard comments / reviews moderation

## 1. Requirements & Compatibility
- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for PrestaShop itself and are typically available on all modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking "Configure" will take you to the module's main configuration screen. This module is designed to be very straightforward, with minimal settings, as its primary function is to display information on your dashboard.

**Screen Name:** Dashboard comments / reviews moderation Configuration

**Menu Location:** Back Office > Modules > Module Manager > Dashboard comments / reviews moderation > Configure

| Setting / Option | What this setting does | Effect of changing this setting | Recommended value | Merchant scenario / example |
|---|---|---|---|---|
| **MyPresta.eu Updates** | This section typically relates to checking for updates for MyPresta.eu modules. It might include options to enable/disable update checks or display update notifications. | *When enabled:* The module will periodically check MyPresta.eu for newer versions and notify you in the back office if an update is available. This helps you keep your module current with the latest features and bug fixes. *When disabled:* The module will not check for updates automatically. You would need to manually check for updates on MyPresta.eu. | **Enabled (Yes)** | Keeping this enabled ensures you're always aware of new versions, allowing you to benefit from improvements and security updates without manual checks. |
| **Update_ (Internal)** | This is an internal setting, likely related to the update mechanism itself. It's not typically meant for direct merchant interaction. | Changing this setting is not recommended as it could interfere with the module's ability to check for and apply updates. | **Leave as default** | This is a technical setting; store owners should not modify it. |
| **Updatev_ (Internal)** | Similar to `update_`, this is an internal version-related setting for the update mechanism. | Changing this setting is not recommended as it could interfere with the module's ability to check for and apply updates. | **Leave as default** | This is a technical setting; store owners should not modify it. |

**Important Note:** The core functionality of displaying comments and reviews on your dashboard does not require extensive configuration. Once installed, the module automatically integrates with your dashboard to show pending reviews and reported comments, assuming you have the standard PrestaShop "Product Comments" module (or a compatible alternative) installed and active.

### 2.2 Dedicated Admin Screens & Controller Views
This module does **not** introduce any new dedicated admin screens or custom controller views. Its functionality is integrated directly into the existing PrestaShop dashboard.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration Page | MyPresta.eu Updates | Enabled (Yes) | Enables automatic checks for module updates from MyPresta.eu. |
| Module Configuration Page | Update_ | Leave as default | Internal setting for update mechanism. |
| Module Configuration Page | Updatev_ | Leave as default | Internal setting for update mechanism. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I've installed the module, but I don't see any comments/reviews on my dashboard.**
**A1:**
*   **Check "Product Comments" module:** This module relies on the standard PrestaShop "Product Comments" module (or a compatible third-party review module) to function. Ensure that the "Product Comments" module is installed, enabled, and configured correctly in your store.
*   **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" in the top right. Sometimes, PrestaShop's cache needs to be refreshed for new dashboard elements to appear.
*   **Check for Pending Reviews:** Do you actually have any reviews awaiting moderation or any comments reported as abusive? The module will only display content that needs your attention. If there are no such items, the dashboard block might appear empty or not show up if there's nothing to display.

**Q2: The dashboard block looks strange or isn't styled correctly.**
**A2:**
*   **Clear Browser Cache:** Sometimes your web browser caches old CSS files. Try clearing your browser's cache or opening your back office in an incognito/private window.
*   **Check for Theme Conflicts:** While rare for dashboard modules, a highly customized admin theme could potentially conflict. If you suspect this, try temporarily switching to the default PrestaShop admin theme (if possible) to see if the issue persists. If it resolves, consult your theme developer.
*   **Clear PrestaShop Cache:** As mentioned above, clearing the Smarty cache under **Advanced Parameters > Performance** can resolve display issues.

**Q3: How do I translate the module's text into another language?**
**A3:**
*   Navigate to **International > Translations** in your PrestaShop Back Office.
*   Select "Installed modules translations" for the "Type of translation".
*   Choose your theme (e.g., "Classic") and the language you want to translate.
*   Find "Dashboard comments / reviews moderation" in the list, click "Modify," and you can then translate all available text strings.

**Q4: I clicked "Configure" but only see update settings, not the moderation tools.**
**A4:** The "Configure" button for this module leads to its minimal settings page, primarily for update management. The actual moderation tools (the list of comments/reviews) are displayed directly on your main PrestaShop dashboard, usually in one of the "Dashboard Zone" areas. Navigate to your main "Dashboard" (the first page you see after logging in) to find the module's output.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview
The "Dashboard comments / reviews moderation" module (`dashcomments`) is a lightweight PrestaShop module designed to extend the Back Office dashboard. It leverages PrestaShop's hook system to inject a custom block into the dashboard, displaying pending product reviews and reported comments. It does not introduce new database tables or complex `ObjectModel` structures, instead relying on existing data from the `ps_product_comment` module. Its primary function is presentation and interaction with existing data via AJAX.

### 4.2 Controllers (`controllers/`)
This module does **not** include any custom front-office or back-office controllers. All interactions are handled either directly within the main module class (`dashcomments.php`) or via AJAX calls processed by the module's `ajaxProcess` methods.

### 4.3 Core Classes & Models (`classes/`)
This module does **not** define any custom classes or models in the `classes/` directory. It directly interacts with PrestaShop's core functionalities and, implicitly, with the `ProductComment` class from the `ps_product_comments` module (if installed).

### 4.4 JavaScript Assets (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Scope:** Back-office (Dashboard).
    *   **Purpose:** Handles AJAX interactions for moderating comments and reviews directly from the dashboard widget.
    *   **Key Functionality:**
        *   Binds click event listeners to "Approve," "Disapprove," and "Delete" buttons within the dashboard widget.
        *   Sends AJAX requests to the module's `ajaxProcess` methods (e.g., `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`) to perform moderation actions.
        *   Updates the DOM (removes the moderated comment row, updates counts) upon successful AJAX response.
        *   May include logic for handling "report as abusive" actions if implemented for the comments themselves.
        *   Uses `$.ajax` for asynchronous communication.

### 4.5 CSS Stylesheets (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Scope:** Back-office (Dashboard).
    *   **Purpose:** Provides styling for the dashboard widget that displays pending comments and reviews.
    *   **Key Styling:**
        *   Styles for the comment list, individual comment rows, action buttons (approve, disapprove, delete), and potentially counters for pending items.
        *   Ensures the widget integrates visually with the PrestaShop 1.7+/8+ back-office theme.
        *   **Key CSS Class Selectors:** Developers can inspect the generated HTML for specific classes (e.g., `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`) to override or extend styling in their custom admin themes.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Scope:** Back-office (Dashboard).
    *   **Hook:** `displaydashboardZoneTwo` (or `dashboardZoneTwo` in older versions).
    *   **Purpose:** This template is responsible for rendering the HTML structure of the comments/reviews moderation widget on the PrestaShop dashboard.
    *   **Content:**
        *   Displays a list of product comments that are pending approval.
        *   Displays a list of product comments that have been reported as abusive.
        *   For each comment, it typically shows the product name, customer name, comment content, rating, and action buttons (Approve, Disapprove, Delete).
        *   Includes logic to iterate over `$pending_comments` and `$reported_comments` variables passed from the module.
        *   Contains the necessary HTML elements and data attributes for the `dashcomments.js` script to attach its event listeners and perform AJAX actions.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**: This module does not create any custom database tables. It relies on the `ps_product_comment` table (and related tables like `ps_product_comment_grade`, `ps_product_comment_criterion`) which are created by the official `ps_product_comments` module.
-   **Configuration Records**:
    *   `PS_DASHCOMMENTS_UPDATES`: Stores the status of update checks.
    *   `PS_DASHCOMMENTS_UPDATE_`: Internal update flag.
    *   `PS_DASHCOMMENTS_UPDATEV_`: Internal version flag for updates.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting up its media assets (CSS/JS). | Used to register the module's `dashcomments.js` and `dashcomments.css` files for the Back Office dashboard. |
| `displaydashboardZoneTwo` | Renders content in the second zone of the PrestaShop Back Office dashboard. | This is the primary hook used to display the comments/reviews moderation widget. |
| `dashboardZoneTwo` | (Legacy hook, similar to `displaydashboardZoneTwo`) | Provides compatibility for older PrestaShop versions or alternative dashboard layouts to display the widget. |

## 5. Official Support & Updates
For official support, module updates, and any further assistance, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). You can download the latest versions of the module from your order history and access our dedicated support channels for any technical queries or issues.
