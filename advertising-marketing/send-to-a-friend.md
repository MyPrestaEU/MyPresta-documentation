---
title: "Send to a friend - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Send to a friend PrestaShop module by MyPresta.eu."
sidebar:
  label: "Send to a friend - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Send to a friend Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/send-to-a-friend/)
>
> ---


# Send to a friend

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Send to a friend” module. Here you can control how the feature behaves and appears on your product pages.

#### General Settings

- **What this setting does:** This section contains the core settings to enable or disable the module and control its basic functionality.
- **Effect of changing this setting:**
  - *When enabled:* The “Send to a friend” link/button and functionality will appear on your product pages as configured.
  - *When disabled:* The feature will be completely hidden from your store, and no emails can be sent through it.
- **Recommended value:** **YES** (Enabled) to allow customers to use the feature.
- **Merchant scenario / example:** If you want to temporarily disable the feature for maintenance or a specific marketing campaign, you would switch this to “NO”. Otherwise, keep it “YES” to leverage word-of-mouth marketing.

#### Display Options

- **What this setting does:** These options control where the “Send to a friend” link or button will appear on your product pages. The module utilizes PrestaShop’s hook system to place the feature in different areas.
- **Effect of changing this setting:**
  - *Selecting a hook (e.g., `displayProductButtons`):* The “Send to a friend” link will be rendered in that specific area of your product page.
  - *Not selecting any hook:* The feature might not appear at all, or it might appear in a default location if your theme has specific fallback rendering.
- **Recommended value:** `displayProductButtons` or `displayProductActions` are common and recommended hooks as they place the link close to the “Add to Cart” button, making it easily discoverable. You might also consider `displayFooterProduct` if you prefer it at the bottom of the product details.
- **Merchant scenario / example:** If you want the “Send to a friend” link to be highly visible and near the main call-to-action, choose `displayProductButtons`. If you prefer it to be less prominent, perhaps at the bottom of the product information, select `displayFooterProduct`. Experiment with different hooks to see what looks best with your theme.

#### Email Template & Content

- **What this setting does:** This section allows you to customize the subject and content of the email that is sent to the friend.
- **Effect of changing this setting:**
  - *Changing the subject:* The email subject line will reflect your custom text, making it more engaging or branded.
  - *Changing the content:* The body of the email will include your custom message, allowing you to personalize the recommendation. You can use placeholders like `{product_name}` and `{product_link}` which will be automatically replaced with the actual product details.
- **Recommended value:** Use a clear, inviting subject line (e.g., “Check out this product from {your\_shop\_name}!”) and a friendly, informative message in the body. Always include `{product_name}` and `{product_link}` to ensure the friend knows what is being recommended and how to find it.
- **Merchant scenario / example:** You could customize the email to say: “Hi {friend\_name}, {customer\_name} thought you might like this product from My Awesome Store! It’s called {product\_name} and you can find it here: {product\_link}. Happy shopping!”

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable/Disable Module | Enabled | Controls whether the “Send to a friend” feature is active on your store. |
| Module Configuration | Display Hook | `displayProductButtons` | Determines where the “Send to a friend” link appears on product pages. |
| Module Configuration | Email Subject | “Check out this product!” | Customizes the subject line of the email sent to the friend. |
| Module Configuration | Email Content | “Hi {friend\_name}, {customer\_name} thought you might like this product: {product\_name}. You can find it here: {product\_link}” | Customizes the body of the email, including dynamic product details. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: The “Send to a friend” link isn’t showing up on my product pages. What should I do?**
A:

1. **Check Module Status:** Go to **Modules > Module Manager** and ensure the “Send to a friend” module is installed and enabled.
2. **Verify Configuration:** Go to the module’s configuration page and make sure the module is “Enabled” and that you have selected at least one “Display Hook” (e.g., `displayProductButtons`).
3. **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions).
4. **Theme Compatibility:** If you’re using a custom theme, it might not be explicitly designed to render all PrestaShop hooks. Try switching to the default PrestaShop theme temporarily to see if the link appears. If it does, your theme might require a small modification by a webmaster to display the chosen hook.

**Q: My customers are sending emails, but they aren’t being received by their friends.**
A:

1. **Check Spam Folders:** Ask the friend to check their spam or junk mail folder.
2. **Verify Email Settings:** Ensure your PrestaShop store’s email settings are correctly configured under **Advanced Parameters > E-mail**. Test sending a general email from PrestaShop to confirm your mail server is working.
3. **Module Logs (Developer Check):** A developer can check PrestaShop’s mail logs (if enabled) or server error logs for issues related to sending emails.

**Q: Can I change the text of the “Send to a friend” link or form fields?**
A: Yes, you can translate or modify the text strings (labels, button text, etc.) of the module using PrestaShop’s translation tool. Go to **International > Translations**, select “Installed modules translations”, choose your theme, and then select the “Send to a friend” module. You can then edit all the visible text.

**Q: The pop-up form looks strange or is not styled correctly on my mobile device.**
A:

1. **Clear Browser Cache:** Ask the customer to clear their browser cache on their mobile device.
2. **Theme Conflicts:** Custom themes can sometimes override or conflict with module styling. While the module includes its own CSS (`send2friend.css`), your theme’s CSS might be taking precedence. A webmaster can inspect the page using browser developer tools to identify and resolve CSS conflicts.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters.

### 4.1 Architecture Overview

The “Send to a friend” module (`send2friend`) is a standard PrestaShop module implementing the MVC pattern. It primarily uses front controllers for AJAX requests, Smarty templates for rendering the form, and hooks to integrate into the product page. It does not introduce custom database tables or complex ObjectModels, relying on PrestaShop’s core mail functionality.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- **`controllers/front/AjaxSend.php`**
  - **Class Name:** `Send2FriendAjaxSendModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller handles the AJAX request initiated when a user submits the “Send to a friend” form. It receives the sender’s name, friend’s name, friend’s email, and the product ID. It then constructs and sends the email using PrestaShop’s `Mail::Send()` method. It returns a JSON response indicating success or failure.
- **`controllers/front/index.php`**
  - **Class Name:** `Send2FriendIndexModuleFrontController`
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This is a placeholder or default front controller. In many modules, this might handle a dedicated front-office page. For “Send to a friend,” its primary role might be to ensure the module’s front-office assets are loaded or to serve as a base for other front controllers. Given the module’s functionality, the `AjaxSend` controller is the more active one.

### 4.3 Core Classes & Models (`classes/`)

The module does not contain any custom classes or models in the `classes/` directory. It leverages PrestaShop’s core functionalities, particularly `Mail` for sending emails and `Product` for retrieving product information.

### 4.4 JavaScript Assets (`views/js/`)

- **`views/js/send2friend.js`**
  - **Scope:** Front-office.
  - **Details:** This script is responsible for the front-end interaction of the “Send to a friend” feature.
    - It likely attaches an event listener to the “Send to a friend” link/button to open the modal or display the form.
    - It handles the form submission, collecting data (sender name, friend name, friend email, product ID).
    - It sends an AJAX request to the `AjaxSend.php` front controller.
    - It processes the JSON response from the server (success/error) and provides feedback to the user (e.g., “Email sent successfully!” or “Error sending email.”).
    - It might include logic for form validation (e.g., checking for valid email formats).
    - It uses jQuery for DOM manipulation and AJAX calls, common in PrestaShop front-office.

### 4.5 CSS Stylesheets (`views/css/`)

- **`views/css/send2friend.css`**
  - **Scope:** Front-office customer styling.
  - **Details:** This stylesheet provides the basic visual styling for the “Send to a friend” link, the pop-up modal (if used), and the form fields within it.
    - It defines styles for the button/link, input fields, labels, and any success/error messages.
    - Key CSS class selectors developers can override in their theme would typically include classes like `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input`, etc. Developers can inspect the rendered HTML to find the exact classes used.

### 4.6 Smarty Template Structure (`views/templates/`)

- **`views/templates/hook/send2friend-extra.tpl`**
  - **Scope:** Front-office.
  - **Hook Rendering:** This template is designed to be rendered in various product page hooks (e.g., `displayProductButtons`, `displayProductActions`, `displayFooterProduct`).
  - **Visual Block:** It outputs the HTML structure for the “Send to a friend” link/button and the associated modal or inline form. This includes the input fields for names and email addresses, and the submit button. It also contains the necessary hidden fields (like `product_id`) and potentially the structure for displaying success/error messages.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The “Send to a friend” module does not create any custom database tables. It stores its configuration settings (like enabled status, chosen hook, email subject, and content) in PrestaShop’s `ps_configuration` table.

- **`ps_configuration`**: Stores module settings with keys typically prefixed by `SEND2FRIEND_`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to load module’s CSS and JavaScript assets globally. |
| `displayProductButtons` | Near the “Add to Cart” button on product pages. | Common placement for the “Send to a friend” link. |
| `displayProductActions` | Another common hook near product actions. | Alternative placement for the “Send to a friend” link. |
| `displayFooterProduct` | At the bottom of the product information block. | Less prominent placement for the “Send to a friend” link. |
| `displayRightColumnProduct` | In the right column of the product page (if enabled by theme). | Possible placement for the “Send to a friend” link. |
| `displayLeftColumnProduct` | In the left column of the product page (if enabled by theme). | Possible placement for the “Send to a friend” link. |

The module’s `install()` method registers these hooks, and the `uninstall()` method unregisters them. The specific hook chosen by the merchant in the configuration determines which one is actively used to display the template.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Send to a friend” module, please refer to your MyPresta.eu customer account. You can download the newest versions and access support resources directly from [MyPresta.eu](https://mypresta.eu).
