---
title: "MyPazaruvaj - Pazaruvaj survey email - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the MyPazaruvaj - Pazaruvaj survey email PrestaShop module by MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - Pazaruvaj survey email - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy MyPazaruvaj - Pazaruvaj survey email Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - Pazaruvaj survey email

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5 (The module is designed to be broadly compatible across various PHP versions, up to the latest stable release supported by PrestaShop 8 and 9.)
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module. No special server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > MyPazaruvaj)

This is the main and only configuration screen for the MyPazaruvaj module. Here you will set up all the necessary parameters to connect your store with Pazaruvaj.com.

#### **Pazaruvaj.com Shop ID**

- **What this setting does:** This is your unique identifier provided by Pazaruvaj.com for your online store. It tells Pazaruvaj which shop the order data belongs to.
- **Effect of changing this setting:**
  - *When set correctly:* The module will successfully send order data to your Pazaruvaj.com shop profile.
  - *When incorrect or empty:* Pazaruvaj.com will not be able to identify your shop, and no survey emails will be sent to your customers.
- **Recommended value:** Enter the exact Shop ID provided to you by Pazaruvaj.com. This is a mandatory field.
- **Merchant scenario / example:** You’ve registered your store on Pazaruvaj.com and they’ve given you a Shop ID like `12345`. You must enter `12345` here for the integration to work.

#### **Pazaruvaj.com Product ID Field**

- **What this setting does:** This option determines which product identifier from your PrestaShop store should be sent to Pazaruvaj.com. Pazaruvaj.com uses this ID to match the purchased product with its listing on their platform.
- **Effect of changing this setting:**
  - *When set to “Product ID”:* The internal PrestaShop product ID (e.g., `id_product`) will be sent. This is usually the safest option if your Pazaruvaj.com feed uses these IDs.
  - *When set to “Product Reference”:* The product’s reference code (e.g., `reference`) will be sent. Choose this if your Pazaruvaj.com feed matches products by their reference.
  - *When set to “Product EAN13”:* The product’s EAN13 barcode will be sent. Useful if your Pazaruvaj.com feed relies on EANs.
  - *When set to “Product UPC”:* The product’s UPC code will be sent.
- **Recommended value:** “Product ID” is often the most reliable default. However, you **must** verify which identifier your product feed on Pazaruvaj.com uses to match products. If your feed uses product references, select “Product Reference”.
- **Merchant scenario / example:** If your product feed on Pazaruvaj.com uses the unique internal ID that PrestaShop assigns to each product, you should select “Product ID”. If you’ve uploaded a feed where each product is identified by a specific SKU or reference number (e.g., `REF-001`), then select “Product Reference”.

#### **Enable Consent to send data to Pazaruvaj.com**

- **What this setting does:** This switch controls whether customers must explicitly agree to their order data being sent to Pazaruvaj.com for the survey. When enabled, a checkbox appears during checkout.
- **Effect of changing this setting:**
  - *When enabled (YES):* A checkbox will appear on the checkout page. Only customers who tick this box will have their order data sent to Pazaruvaj.com. This helps with GDPR and other privacy regulations.
  - *When disabled (NO):* Order data will be sent to Pazaruvaj.com for *all* completed orders without requiring explicit customer consent. This is simpler for customers but might not comply with all privacy laws in your region.
- **Recommended value:** “YES” is generally recommended for compliance with data protection regulations (like GDPR).
- **Merchant scenario / example:** To ensure your store is fully compliant with privacy laws, you enable this setting. During checkout, your customers will see a checkbox labeled something like “I agree to share my order details with Pazaruvaj.com for a review survey.” Only if they check it will the data be sent.

#### **Show Consent on**

- **What this setting does:** If “Enable Consent” is set to YES, this option determines where the consent checkbox will be displayed on your store’s front-office.
- **Effect of changing this setting:**
  - *Header, Columns, Product, Footer:* The consent checkbox will be displayed in the selected hook area. The exact visual placement depends on your theme’s layout for that hook.
- **Recommended value:** Choose a prominent but non-intrusive location. The “Footer” or a specific “Column” (if your theme has a suitable one) are often good choices for privacy-related notices. You might need to test different options to see what looks best with your theme.
- **Merchant scenario / example:** You’ve enabled consent. You decide to show the consent checkbox in the “Footer” so it’s visible but doesn’t clutter the main checkout flow.

#### **Enable Error Log**

- **What this setting does:** This switch controls whether the module records any errors encountered during the data transfer process to Pazaruvaj.com.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will save details of any failed data submissions to a log file. This is invaluable for troubleshooting if surveys aren’t being sent.
  - *When disabled (NO):* No error information will be recorded, making it harder to diagnose issues.
- **Recommended value:** “YES” is highly recommended, especially during initial setup and for ongoing monitoring.
- **Merchant scenario / example:** You’re not sure if the integration is working perfectly. You enable the error log. If Pazaruvaj.com isn’t receiving data, you can check the log to see if there are any specific error messages, like an invalid Shop ID or connection issues.

#### **Clear Error Log**

- **What this setting does:** This button allows you to delete all entries from the module’s error log.
- **Effect of changing this setting:**
  - *When clicked:* All previously recorded errors are permanently removed from the log file.
- **Recommended value:** Use this after you’ve reviewed and resolved any issues, or if the log file becomes too large.
- **Merchant scenario / example:** You’ve fixed an issue with your Pazaruvaj.com Shop ID. You click “Clear Error Log” to start fresh and ensure only new, relevant errors are recorded.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Config | Pazaruvaj.com Shop ID | Your Pazaruvaj ID (Mandatory) | Unique identifier for your shop on Pazaruvaj.com. Essential for data transfer. |
| Module Config | Pazaruvaj.com Product ID Field | Product ID (Verify with Pazaruvaj feed) | Determines which PrestaShop product identifier (ID, Reference, EAN13, UPC) is sent to Pazaruvaj.com for product matching. |
| Module Config | Enable Consent to send data to Pazaruvaj.com | YES (For compliance) | Requires customer consent via a checkbox during checkout before sending data to Pazaruvaj.com. |
| Module Config | Show Consent on | Footer (Test for best placement) | Specifies the front-office hook where the consent checkbox will appear if enabled. |
| Module Config | Enable Error Log | YES (For troubleshooting) | Activates logging of any errors during data submission to Pazaruvaj.com. |
| Module Config | Clear Error Log | N/A (Button) | Deletes all entries from the module’s error log. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are not receiving survey emails from Pazaruvaj.com. What should I check?**
A:

1. **Pazaruvaj.com Shop ID:** Double-check that your “Pazaruvaj.com Shop ID” in the module configuration is absolutely correct and matches the ID provided by Pazaruvaj.com.
2. **Error Log:** Enable the “Error Log” in the module configuration and check for any recorded errors after a test order. This will often pinpoint the exact problem.
3. **Consent Setting:** If “Enable Consent to send data to Pazaruvaj.com” is enabled, ensure customers are actually ticking the checkbox during checkout. If they don’t, data won’t be sent.
4. **Order Status:** Ensure the order reaches a “Payment accepted” or similar final status in PrestaShop, as the module typically triggers on successful order completion.
5. **Pazaruvaj.com Account:** Log into your Pazaruvaj.com account to see if there are any issues or warnings on their end regarding your shop or data feed.

**Q: The consent checkbox isn’t showing up on my checkout page.**
A:

1. **“Enable Consent” Setting:** First, ensure “Enable Consent to send data to Pazaruvaj.com” is set to YES in the module configuration.
2. **“Show Consent on” Setting:** Check which hook you’ve selected for “Show Consent on.” If your theme doesn’t actively display content in that specific hook (e.g., a custom `displayMyCustomHook`), the checkbox won’t appear. Try switching to a common hook like `displayFooter` or `displayHeader` to test.
3. **Theme Compatibility:** Some highly customized themes might override standard hook placements. If the issue persists, you might need a webmaster to inspect your theme’s template files.
4. **Smarty Cache:** Clear your PrestaShop Smarty cache under **Advanced Parameters > Performance** (Force compilation and clear cache).

**Q: I changed a setting, but nothing happened on my store.**
A: After making any changes in the module configuration, always clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, then click “Clear cache” and optionally “Force compilation” if you’re making template-related changes. Your browser’s cache might also need clearing (Ctrl+F5 or Cmd+R).

**Q: Can I customize the text of the consent checkbox?**
A: Yes, the text for the consent checkbox is translatable. You can modify it through PrestaShop’s translation system:

1. Go to **International > Translations**.
2. Select “Installed modules translations”.
3. Choose your theme, the language, and then select “MyPazaruvaj”.
4. You will find the string related to the consent message there and can edit it.

**Q: What if I have multiple shops (multistore) enabled?**
A: The module should be configured individually for each shop in a multistore environment. Ensure you select the correct shop context in the PrestaShop back office before configuring the module for that specific shop. Each shop will likely have its own unique Pazaruvaj.com Shop ID.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the MyPazaruvaj module.

### 4.1 Architecture Overview

The MyPazaruvaj module follows a standard PrestaShop module architecture, primarily utilizing the `Module` class and its `install()`, `uninstall()`, and `getContent()` methods for configuration. Its core functionality is event-driven, leveraging PrestaShop hooks to intercept order confirmation events and display optional consent. Data submission to Pazaruvaj.com is handled directly within the module’s main PHP file, without dedicated front or admin controllers, making it a lightweight and efficient solution.

### 4.2 Controllers (`controllers/`)

This module does not utilize dedicated front-office or back-office controllers. All configuration logic is handled within the `getContent()` method of the main module file, and front-office display logic is managed directly via hook templates.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or extend `ObjectModel`. All logic is contained within the main `MyPazaruvaj` class defined in `mypazaruvaj/index.php`.

The main class `MyPazaruvaj` extends `Module` and contains:

- `__construct()`: Sets module properties (name, tab, version, author, need\_instance, ps\_versions\_compliancy, bootstrap).
- `install()`: Registers necessary hooks (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), creates configuration entries, and initializes the error log file.
- `uninstall()`: Unregisters hooks and deletes configuration entries.
- `getContent()`: Renders the module’s back-office configuration form, handles form submissions, and updates configuration values.
- `hookDisplayOrderConfirmation()`: The primary hook for data submission. It retrieves order details, customer information, and product data, then constructs and sends the request to Pazaruvaj.com. It also handles the optional consent check.
- `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()`: These hooks are used to display the consent checkbox if enabled and configured to appear in these locations. They render the `consent.tpl` template.
- `_clearLog()`: Internal method to clear the error log file.
- `_writeLog()`: Internal method to write messages to the error log file.
- `_displayForm()`: Internal method to render the configuration form using PrestaShop’s `HelperForm`.

### 4.4 JavaScript Assets (`views/js/`)

This module does not include any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

This module does not include any custom CSS files. Any styling for the consent checkbox would rely on the theme’s default form element styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `mypazaruvaj/views/templates/hook/consent.tpl`:
    - **Purpose:** Renders the optional consent checkbox for sending data to Pazaruvaj.com.
    - **Rendered in hooks:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (depending on module configuration).
    - **Variables:** Typically checks for `$consent_enabled` and displays a form input.
    - **Output:** A simple HTML checkbox and label.
  - `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Purpose:** This template is likely a placeholder or used for internal module logic that doesn’t output visible content directly to the customer. The primary data submission logic for `displayOrderConfirmation` is handled in the PHP hook method itself, not necessarily via a template output. It might be used to pass variables or trigger JS if the module had any. In this module’s context, it’s primarily the PHP hook method that performs the action.
- **Admin templates (`views/templates/admin/`)**:

  - This module does not use dedicated admin templates. The configuration form is generated programmatically using `HelperForm` within `getContent()`.
- **Front-office templates (`views/templates/front/`)**:

  - This module does not include any dedicated front-office templates beyond the hook templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not create any custom SQL tables.
  - It stores its configuration settings in the standard PrestaShop `ps_configuration` table.
    - `MYPAZARUVAJ_SHOP_ID`: Stores the Pazaruvaj.com Shop ID.
    - `MYPAZARUVAJ_PRODUCT_ID_FIELD`: Stores the selected product ID field (e.g., ‘id\_product’, ‘reference’).
    - `MYPAZARUVAJ_CONSENT_ENABLED`: Boolean (0 or 1) for enabling/disabling consent.
    - `MYPAZARUVAJ_CONSENT_HOOK`: Stores the name of the hook where consent is displayed.
    - `MYPAZARUVAJ_ERROR_LOG_ENABLED`: Boolean (0 or 1) for enabling/disabling the error log.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayOrderConfirmation` | After a customer successfully completes an order. | **Primary hook for data submission.** Retrieves order and product details, constructs the Pazaruvaj.com request, and sends it. Checks for consent if enabled. |
| `displayHeader` | In the `<head>` section or top of every page. | Renders `consent.tpl` if configured to show consent here. |
| `displayFooter` | In the footer section of every page. | Renders `consent.tpl` if configured to show consent here. |
| `displayLeftColumn` | In the left sidebar column (if active in theme). | Renders `consent.tpl` if configured to show consent here. |
| `displayRightColumn` | In the right sidebar column (if active in theme). | Renders `consent.tpl` if configured to show consent here. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the MyPazaruvaj module.
