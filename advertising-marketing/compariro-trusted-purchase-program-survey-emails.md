---
title: "Compari.ro - trusted purchase program survey emails - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Compari.ro - trusted purchase program survey emails PrestaShop module by MyPresta.eu."
sidebar:
  label: "Compari.ro - trusted purchase program survey emails - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Compari.ro - trusted purchase program survey emails Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - trusted purchase program survey emails

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the Compari.ro module. You can access it by navigating to **Modules > Module Manager**, searching for “Compari.ro”, and clicking the “Configure” button.

#### **1. Compari.ro WebApiKey**

- **What this setting does:** This is your unique identifier provided by Compari.ro that links your PrestaShop store to your Compari.ro merchant account. It’s essential for the “Trusted Purchase Program” to correctly attribute survey requests to your store.
- **Effect of changing this setting:**
  - *When correctly entered:* The module will be able to send order data to Compari.ro, allowing them to send survey emails to your customers.
  - *When incorrect or empty:* The integration will fail, and Compari.ro will not receive order information, meaning no survey emails will be sent.
- **Recommended value:** Enter the exact WebApiKey provided to you by Compari.ro.
- **Merchant scenario / example:** You’ve registered for the Compari.ro “Trusted Purchase Program” and received an email with your API key. You must copy and paste this key here for the integration to work.

#### **2. Product identifier (feed ITEM\_ID)**

- **What this setting does:** This setting defines which product identifier from your PrestaShop store should be used as the `ITEM_ID` when sending product information to Compari.ro. This is crucial for matching products in your Compari.ro feed with the products in your orders.
- **Effect of changing this setting:**
  - *When set to `id_product` (default):* The internal PrestaShop product ID will be used. This is generally the safest option if you don’t have a specific custom identifier.
  - *When set to `reference`:* The product’s reference code will be used. Choose this if your Compari.ro product feed uses the product reference as the `ITEM_ID`.
  - *When set to `ean13`:* The product’s EAN-13 barcode will be used. Choose this if your Compari.ro product feed uses EAN-13 as the `ITEM_ID`.
  - *When set to `upc`:* The product’s UPC code will be used. Choose this if your Compari.ro product feed uses UPC as the `ITEM_ID`.
- **Recommended value:** `id_product` (unless your Compari.ro product feed explicitly uses `reference`, `ean13`, or `upc` as the `ITEM_ID`).
- **Merchant scenario / example:** Your Compari.ro product feed uses the unique EAN-13 barcode for each product. You would select `ean13` here to ensure Compari.ro can correctly identify the products purchased by your customers.

#### **3. Require customer consent**

- **What this setting does:** This option determines whether your customers must explicitly agree to participate in the Compari.ro survey program during checkout. This is important for GDPR compliance and respecting customer privacy preferences.
- **Effect of changing this setting:**
  - *When enabled (set to “Yes”):* A checkbox will appear during the checkout process (e.g., on the payment page or checkout summary). Customers must tick this box to allow their order data to be sent to Compari.ro for survey purposes. If they do not consent, no survey email will be sent for their order.
  - *When disabled (set to “No”):* No consent checkbox will be displayed. Order data will be sent to Compari.ro for all orders, assuming the `WebApiKey` is correct.
- **Recommended value:** “Yes” if you operate in regions with strict data privacy laws (like GDPR) or if you want to give customers full control over their data sharing. “No” if you’ve determined that explicit consent is not required for your specific legal context or if you want to maximize survey participation.
- **Merchant scenario / example:** To comply with GDPR regulations, you enable this setting. During checkout, customers see a checkbox “I agree to participate in the Compari.ro Trusted Purchase Program survey.” Only customers who tick this box will receive a survey email.

#### **4. Write errors to log.txt**

- **What this setting does:** This is a debugging option that controls whether the module records any errors encountered during its operation (e.g., issues sending data to Compari.ro) into a `log.txt` file within the module’s directory.
- **Effect of changing this setting:**
  - *When enabled (set to “Yes”):* Any technical errors will be written to `compari/log.txt`. This file can be very helpful for your webmaster or MyPresta.eu support to diagnose problems.
  - *When disabled (set to “No”):* Errors will not be explicitly logged to a file. This is generally preferred for live production stores to avoid generating large log files, unless you are actively troubleshooting.
- **Recommended value:** “No” for a live production store. “Yes” if you are experiencing issues with the integration and need to debug. Remember to disable it once the issue is resolved.
- **Merchant scenario / example:** You’ve configured the module, but customers aren’t receiving survey emails. You enable “Write errors to log.txt” and then place a test order. You then check the `log.txt` file for clues about why the integration might be failing.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Compari.ro WebApiKey | Your unique API key | Links your store to Compari.ro for survey automation. **Critical for functionality.** |
| Module Configuration | Product identifier (feed ITEM\_ID) | `id_product` (or match your feed) | Specifies which product ID (internal, reference, EAN, UPC) to send to Compari.ro. |
| Module Configuration | Require customer consent | Yes (for GDPR) | Displays a consent checkbox during checkout. If unchecked, no survey email is sent. |
| Module Configuration | Write errors to log.txt | No (enable for debugging) | Logs technical errors to `compari/log.txt` for troubleshooting. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving survey emails from Compari.ro, but the module is configured.**
A1:

- **Check WebApiKey:** Double-check that your “Compari.ro WebApiKey” is entered correctly and exactly as provided by Compari.ro. Even a single typo will prevent the integration from working.
- **Check Consent Setting:** If “Require customer consent” is set to “Yes,” ensure your test customers are actually ticking the consent box during checkout.
- **Check Compari.ro Account:** Log into your Compari.ro merchant account to see if there are any error messages or if orders are being received from your store.
- **Enable Logging:** Set “Write errors to log.txt” to “Yes” in the module configuration, place a test order, and then check the `compari/log.txt` file for any error messages. This will provide specific technical details.
- **Clear Cache:** Sometimes, PrestaShop’s cache can interfere. Go to **Advanced Parameters > Performance** and click “Clear cache.”

**Q2: I enabled “Require customer consent,” but I don’t see a checkbox during checkout.**
A2:

- **Theme Compatibility:** The module uses standard PrestaShop hooks (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`) to display the consent checkbox. If your custom theme heavily modifies the checkout process, these hooks might not be rendered, or the styling might make the checkbox invisible.
- **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**).
- **Module Position:** Ensure the module is not disabled for the specific hooks it uses. While less common for a consent checkbox, it’s worth checking in **Design > Positions**.

**Q3: What if a customer changes their mind about consent after placing an order?**
A3: The module processes consent at the time of order placement. If a customer wishes to revoke consent for future surveys, they would typically need to manage this directly with Compari.ro or through your store’s general GDPR data management tools (if you have them). The module itself doesn’t offer a direct “undo” for past orders, but it does integrate with PrestaShop’s GDPR hooks for data deletion and export.

**Q4: I see a `log.txt` file growing very large. What should I do?**
A4: If you are not actively troubleshooting, set the “Write errors to log.txt” option to “No” in the module configuration. This will stop the module from writing further entries to the log file. You can then safely delete the `log.txt` file to free up space.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The `Compari` module is a straightforward PrestaShop module primarily focused on integrating with an external API (Compari.ro) based on order events. It follows a standard PrestaShop module structure, leveraging hooks to inject content (GDPR consent) and trigger actions (sending order data). It does not introduce custom controllers or complex ObjectModels, relying on PrestaShop’s core `Order` and `Customer` data. The main logic resides within the `compari.php` file, handling configuration, installation, and hook callbacks.

### 4.2 Controllers (`controllers/`)

- This module does **not** contain any custom Front-Office or Back-Office Admin Controllers. All logic is handled within the main `compari.php` file via hooks.

### 4.3 Core Classes & Models (`classes/`)

- This module does **not** contain any custom classes or ObjectModels in the `classes/` directory. All data handling is performed directly within the `compari.php` file using PrestaShop’s core `Order`, `Customer`, and `Product` entities.

### 4.4 JavaScript Assets (`views/js/`)

- This module does **not** contain any custom JavaScript files.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** contain any custom CSS files. Styling for the consent checkbox is expected to be inherited from the theme or handled by PrestaShop’s core GDPR module styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `compari/views/templates/hook/consent.tpl`:
    - **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
    - **Purpose:** Renders the GDPR consent checkbox and associated text, allowing customers to opt-in or opt-out of the Compari.ro survey program. This template is only rendered if the `COMPARI_CONSENT` configuration is enabled.
    - **Output:** A checkbox input field with a label.
  - `compari/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Hook:** `displayOrderConfirmation`
    - **Purpose:** This template is included in the `displayOrderConfirmation` hook. While it’s a template file, its primary role here is to trigger the backend logic within `hookDisplayOrderConfirmation` in `compari.php` to send order data to Compari.ro. It does not output visible content to the user.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does **not** create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table:
    - `COMPARI_FILE_LOG`: Stores the boolean value for logging errors.
    - `COMPARI_ID`: Stores the Compari.ro WebApiKey.
    - `COMPARI_PRODUCT_ID`: Stores the selected product identifier type (e.g., `id_product`, `reference`).
    - `COMPARI_CONSENT`: Stores the boolean value for requiring customer consent.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `install()` | During module installation | Sets default configuration values, registers hooks. |
| `uninstall()` | During module uninstallation | Deletes configuration values, unregisters hooks. |
| `hookDisplayGDPRConsent` | Renders on pages where GDPR consent is collected (e.g., checkout) | Displays the consent checkbox for Compari.ro survey participation. |
| `hookActionDeleteGDPRCustomer` | When a customer requests GDPR data deletion | Handles the deletion of any Compari.ro related customer data (though none is stored directly by the module, it’s a compliance hook). |
| `hookActionExportGDPRData` | When a customer requests GDPR data export | Handles the export of any Compari.ro related customer data (none stored directly). |
| `hookDisplayOrderConfirmation` | On the order confirmation page after a successful purchase | Triggers the sending of order data to Compari.ro if consent is given (or not required). |
| `hookDisplayPaymentTop` | Top of the payment step in checkout | Alternative hook for displaying the consent checkbox. |
| `hookDisplayCheckoutSummaryTop` | Top of the checkout summary step | Alternative hook for displaying the consent checkbox. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Compari.ro - trusted purchase program survey emails” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any technical issues or questions you may have.
