---
title: "Add reply to product review - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Add reply to product review PrestaShop module by MyPresta.eu."
sidebar:
  label: "Add reply to product review - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Add reply to product review Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-reply-to-product-review.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/add-reply-to-product-review/)
>
> ---


# Add reply to product review

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). This module works with the default PrestaShop product comments module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Add reply to product review” module to access its settings.

#### **Enable / Disable Module**

- **What this setting does:** This is the main switch to turn the module’s functionality on or off across your entire store.
- **Effect of changing this setting:**
  - *When enabled:* Your replies to product reviews will be visible on product pages, and you will be able to add replies in the back office.
  - *When disabled:* All module functionality will cease. Existing replies will no longer be displayed, and you won’t be able to add new ones.
- **Recommended value:** YES
- **Merchant scenario / example:** You might disable it temporarily if you are performing maintenance or if you decide to stop using the feature for a period. For normal operation, it should always be enabled.

#### **Send email notification to customer when reply is added**

- **What this setting does:** This controls whether the customer who left the original review receives an email notification when you publish a reply to their comment.
- **Effect of changing this setting:**
  - *When enabled:* An email will be sent to the customer’s registered email address, informing them that their review has received a reply from the store. This encourages them to revisit the product page and see your response.
  - *When disabled:* No email notification will be sent to the customer. They will only see your reply if they happen to revisit the product page.
- **Recommended value:** YES
- **Merchant scenario / example:** Enabling this is highly recommended. It’s a proactive way to engage customers, especially if you’re addressing a concern or thanking them for a positive review. It shows you’re attentive and value their feedback, potentially leading to increased loyalty and repeat business. If you prefer not to “bother” customers with emails, you might disable it, but you’ll lose a valuable engagement opportunity.

#### **Display replies on product page**

- **What this setting does:** This determines whether the replies you’ve added in the back office are actually shown to customers on the front-office product pages.
- **Effect of changing this setting:**
  - *When enabled:* Your replies will be visible to all visitors on the respective product pages, below the customer reviews.
  - *When disabled:* Even if you’ve written replies in the back office, they will not be displayed on the front office. This effectively hides your responses from customers, though the replies are still stored in your system.
- **Recommended value:** YES
- **Merchant scenario / example:** You should almost always have this enabled, as the primary purpose of the module is to display your engagement. You might temporarily disable it if you’re revamping your product page layout and want to hide replies during the process, or if you’re testing new content and don’t want it live yet.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable / Disable Module | YES | Turns the module’s core functionality on or off. |
| Module Configuration | Send email notification to customer when reply is added | YES | Sends an email to the customer when their review receives a reply. Boosts engagement. |
| Module Configuration | Display replies on product page | YES | Controls the visibility of your replies on the front-office product pages. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My replies aren’t showing up on the product page, even though I’ve added them in the back office.**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Add reply to product review” module is installed and enabled.
2. **Check Module Configuration:** Go to the module’s configuration page and make sure “Display replies on product page” is set to YES.
3. **Clear Cache:** Sometimes PrestaShop’s cache can prevent new content from appearing. Go to **Advanced Parameters > Performance**, scroll down to “Clear cache” and click “Clear cache”.
4. **Theme Compatibility:** If you’re using a highly customized theme, it might override the default product comments template. Contact your theme developer or a PrestaShop expert for assistance.

**Q: Customers aren’t receiving email notifications when I reply to their reviews.**
A:

1. **Check Module Configuration:** Ensure “Send email notification to customer when reply is added” is set to YES in the module’s configuration.
2. **Check PrestaShop Email Settings:** Verify that your store’s email settings are correctly configured under **Advanced Parameters > E-mail**. Send a test email from this page to confirm your mail server is working.
3. **Spam Folders:** Advise customers to check their spam or junk folders, as automated emails can sometimes be filtered.
4. **Customer Email Address:** Ensure the customer’s email address associated with the review is valid.

**Q: Can I edit or delete a reply after I’ve posted it?**
A: Yes, you should be able to edit or delete replies from the PrestaShop back office, typically within the product comments management section where you initially added the reply. Look for an “Edit” or “Delete” option next to your reply.

**Q: Does this module work with custom product review modules?**
A: This module is designed to work with the *default* PrestaShop product comments module. If you are using a third-party product review module (e.g., from an external marketplace), compatibility is not guaranteed. You may need to contact MyPresta.eu support for custom integration options.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Add reply to product review” module (`reviewsreply`) is a straightforward PrestaShop module primarily extending the `Module` class. Its core functionality revolves around enhancing the existing product comments system by allowing store administrators to add replies. It integrates with the front-office display via a hook template and manages its configuration through the standard `getContent()` method. The module does not introduce complex MVC patterns with dedicated controllers or custom `ObjectModel` classes but rather leverages PrestaShop’s configuration and templating system.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom Front-Office or Back-Office Admin Controllers. All administrative configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or `ObjectModel` definitions in a `classes/` directory. Its logic is contained within the main `reviewsreply/index.php` file.

### 4.4 JavaScript Assets (`views/js/`)

This module does not contain any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- **`reviewsreply/views/css/reviewsreply.css`**
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:** This stylesheet is responsible for the visual presentation of the store’s replies to product comments on the product page. It likely targets specific CSS classes added by the `displayProductComment.tpl` template to differentiate replies from original comments (e.g., background color, border, font style, author label).
  - **Key CSS class selectors developers can override in their theme:** Developers can inspect the rendered HTML on the product page to identify the specific classes used by the module (e.g., `.reviewsreply-reply-container`, `.reviewsreply-author`, `.reviewsreply-content`) and override them in their theme’s `custom.css` or `theme.css` to match their store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`reviewsreply/views/templates/hook/displayProductComment.tpl`**
    - **Hook:** This template is likely hooked into `displayProductComment` (or a similar hook provided by the default `productcomments` module) or directly injected into the product page template to render the reply section.
    - **Visual Block Output:** This template is responsible for rendering the actual reply from the store owner for each product comment. It will contain the logic to display the reply text, potentially the author (e.g., “Store Owner” or “My Store”), and a timestamp. It will also include the necessary HTML structure and CSS classes for styling as defined in `reviewsreply.css`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create its own custom SQL tables. It likely stores the replies directly within the existing `ps_product_comment` table or a related table, possibly by adding a new column (e.g., `reply_text`, `reply_date`, `reply_employee_id`) or by using a specific `id_parent` or `type` field to link replies to original comments.
  - Configuration settings are stored in `ps_configuration` with keys such as `REVIEWSREPLY_ENABLED`, `REVIEWSREPLY_SEND_EMAIL`, `REVIEWSREPLY_DISPLAY_FRONT`.
- **Registered Hooks Table**:

  | Hook Name | Execution Timing | Technical Purpose |
  | --- | --- | --- |
  | `displayProductComment` | Executed within the product comments section on the product page. | Injects the module’s template (`displayProductComment.tpl`) to display the store owner’s reply below each customer review. |
  | `actionProductCommentAdd` | Triggered after a new product comment is added. | (Potentially) To prepare for replies or related actions, though the module’s primary function is replying *to* existing comments. |
  | `actionProductCommentReply` | (Hypothetical/Internal) Triggered when a reply is added/saved in the BO. | To send email notifications to the customer if enabled. |
  | `displayBackOfficeHeader` | Executed in the `<head>` section of Back Office pages. | (Potentially) To include module-specific CSS or JS for admin forms, though none are listed in the inventory. |
  | `displayHeader` | Executed in the `<head>` section of front-office pages. | (Potentially) To include module-specific CSS (`reviewsreply.css`) or JS for the front office. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and dedicated technical support for the “Add reply to product review” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist merchants and developers with any issues or questions related to the module’s functionality and integration.
