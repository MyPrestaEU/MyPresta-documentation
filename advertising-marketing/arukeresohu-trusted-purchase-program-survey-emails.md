---
title: "Arukereso.hu - trusted purchase program survey emails - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Arukereso.hu - trusted purchase program survey emails PrestaShop module by MyPresta.eu."
sidebar:
  label: "Arukereso.hu - trusted purchase program survey emails - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Arukereso.hu - trusted purchase program survey emails Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu - trusted purchase program survey emails

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main and only configuration screen for the Arukereso.hu module. You can access it by navigating to **Modules > Module Manager**, searching for “Arukereso.hu”, and clicking “Configure”.

#### 2.1.1 Arukereso.hu WebApiKey

- **What this setting does:** This is your unique identifier provided by Arukereso.hu. It’s essential for Arukereso.hu to link the survey requests coming from your PrestaShop store to your specific merchant account on their platform.
- **Effect of changing this setting:**
  - *When correctly entered:* The module can successfully communicate with Arukereso.hu’s systems, enabling the automated survey email process.
  - *When incorrect or empty:* Arukereso.hu will not be able to identify your store, and the survey emails will not be sent to your customers. The integration will fail.
- **Recommended value:** Enter the exact API Key provided to you by Arukereso.hu. This is usually found in your merchant account settings on the Arukereso.hu website.
- **Merchant scenario / example:** You register for the “Trusted Purchase Program” on Arukereso.hu. They provide you with a string of characters like `abcdef1234567890`. You copy and paste this into this field.

#### 2.1.2 Product identifier (feed ITEM\_ID)

- **What this setting does:** This setting determines which product identifier from your PrestaShop store will be sent to Arukereso.hu. Arukereso.hu uses this ID to match the purchased product with its listing on their platform, ensuring the survey is relevant.
- **Effect of changing this setting:**
  - *When set to “Product ID”:* The internal PrestaShop product ID (e.g., `123`) will be used. This is the most common and usually safest option.
  - *When set to “Product Reference”:* Your product’s reference code (e.g., `SKU-001`) will be used. This requires your product references to be unique and consistent with what Arukereso.hu expects.
  - *When set to “Product EAN13”:* The product’s EAN-13 barcode will be used. This is suitable if your EANs are consistently used and match Arukereso.hu’s product catalog.
  - *When set to “Product UPC”:* The product’s UPC code will be used. Similar to EAN13, requires consistent data.
- **Recommended value:** “Product ID” is generally the safest and most reliable option unless you have a specific reason (and verified with Arukereso.hu) to use another identifier.
- **Merchant scenario / example:** If you have a product “Red T-Shirt” with an internal ID of `15`, a reference `TSHIRT-RED`, and an EAN `1234567890123`, choosing “Product ID” will send `15` to Arukereso.hu. If you choose “Product Reference”, `TSHIRT-RED` will be sent. Ensure the chosen identifier is what Arukereso.hu expects to correctly link products.

#### 2.1.3 Require customer consent

- **What this setting does:** This crucial setting controls whether your customers must explicitly agree to participate in the Arukereso.hu survey program during checkout. This is vital for complying with data privacy regulations like GDPR.
- **Effect of changing this setting:**
  - *When enabled (“Yes”):* A checkbox or similar consent mechanism will appear during the checkout process. Only customers who tick this box will have their order data sent to Arukereso.hu for survey purposes. This ensures GDPR compliance.
  - *When disabled (“No”):* No consent option will be shown. All customers who complete an order will automatically be enrolled in the Arukereso.hu survey program. **Use with caution and only if you are certain your local regulations do not require explicit consent for this type of data sharing.**
- **Recommended value:** “Yes”. It is strongly recommended to enable this option to ensure compliance with GDPR and other privacy laws, giving customers control over their data.
- **Merchant scenario / example:** You operate in the EU. To comply with GDPR, you enable this setting. During checkout, customers see a checkbox: “Yes, I agree to receive a customer satisfaction survey from Arukereso.hu regarding my purchase.” Only if they check this box will their data be shared.

#### 2.1.4 Write errors to log.txt

- **What this setting does:** This setting controls whether the module records any errors or issues it encounters during its operation into a `log.txt` file within the module’s directory.
- **Effect of changing this setting:**
  - *When enabled (“Yes”):* Any problems (e.g., failure to connect to Arukereso.hu, invalid API key issues) will be written to `arukereso/log.txt`. This is extremely helpful for troubleshooting.
  - *When disabled (“No”):* Errors will not be logged to a file. While this slightly reduces disk activity, it makes diagnosing problems much harder.
- **Recommended value:** “Yes” during initial setup and if you experience any issues. Once the module is running smoothly, you can disable it if you prefer, but it’s often best to leave it enabled for ongoing monitoring.
- **Merchant scenario / example:** You’ve configured the module, but customers aren’t receiving surveys. You enable this setting, and after a few test orders, you check `arukereso/log.txt` and find an error message indicating “Invalid API Key.” This immediately tells you where to look for the problem.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Arukereso.hu WebApiKey | Your Arukereso.hu Key | Unique identifier for your store on Arukereso.hu. **Required for integration.** |
| Module Configuration | Product identifier (feed ITEM\_ID) | Product ID | Defines which product ID (PrestaShop ID, Reference, EAN, UPC) is sent to Arukereso.hu. |
| Module Configuration | Require customer consent | Yes | Displays a consent checkbox during checkout. **Highly recommended for GDPR compliance.** |
| Module Configuration | Write errors to log.txt | Yes | Logs module errors to `arukereso/log.txt` for troubleshooting. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My customers are not receiving survey emails from Arukereso.hu. What should I check?**
A:

1. **Arukereso.hu WebApiKey:** Double-check that your API Key is correctly entered in the module configuration. Even a single typo will prevent the integration from working.
2. **Consent Setting:** If “Require customer consent” is enabled, ensure customers are actually ticking the consent box during checkout. If they don’t, no data is sent.
3. **Log File:** Enable “Write errors to log.txt” in the module configuration and check the `arukereso/log.txt` file for any error messages after a test order. This is the most direct way to diagnose issues.
4. **Arukereso.hu Account:** Log in to your Arukereso.hu merchant account and check the status of your “Trusted Purchase Program” integration. They might have specific logs or status indicators.
5. **Order Status:** Ensure the order status that triggers the survey (usually “Payment accepted” or “Delivered”) is correctly configured on Arukereso.hu’s side, and your PrestaShop orders are reaching that status.

**Q: I enabled “Require customer consent,” but I don’t see the checkbox during checkout.**
A:

1. **Theme Compatibility:** The module uses standard PrestaShop hooks (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). If your theme is heavily customized, it might not render these hooks correctly.
2. **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache).
3. **Module Position:** Go to Design > Positions and search for the hooks mentioned above. Ensure the Arukereso.hu module is listed and active in these hooks. If not, try transplanting it.
4. **Module Conflicts:** Temporarily disable other modules that modify the checkout process to rule out conflicts.

**Q: What happens if a customer requests their data to be deleted (GDPR Right to be Forgotten)?**
A: The module is designed to integrate with PrestaShop’s GDPR tools. When a customer requests data deletion via PrestaShop’s GDPR module, this Arukereso.hu module will respond to the `actionDeleteGDPRCustomer` hook, ensuring that any data related to the customer held by the module (e.g., consent records) is removed. However, it’s important to note that this module *sends* data to Arukereso.hu. You would also need to contact Arukereso.hu directly to request the deletion of that customer’s data from their systems.

**Q: Can I customize the appearance of the consent checkbox?**
A: The appearance of the consent checkbox is primarily controlled by your PrestaShop theme’s CSS. The module provides the HTML structure via its `consent.tpl` template. You can override this template in your theme or add custom CSS to style the element if you need to change its look.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Arukereso.hu module is a lightweight PrestaShop module primarily focused on integrating with the Arukereso.hu “Trusted Purchase Program.” It leverages PrestaShop’s hook system to inject a consent option during checkout and to send order data to Arukereso.hu upon order confirmation. It follows a standard PrestaShop module structure, with its core logic residing in the main module file (`arukereso.php`) and using Smarty templates for front-office display. It does not introduce custom controllers or ObjectModels, relying on PrestaShop’s `Configuration` class for settings storage.

### 4.2 Controllers (`controllers/`)

This module does **not** contain any custom Front-Office or Back-Office controllers. All logic is handled within the main `arukereso.php` module file, primarily through hook methods.

### 4.3 Core Classes & Models (`classes/`)

This module does **not** define any custom classes or ObjectModels in the `classes/` directory. It operates directly within the `arukereso.php` file, using standard PrestaShop classes and functions.

### 4.4 JavaScript Assets (`views/js/`)

This module does **not** include any custom JavaScript files. All front-office interaction (e.g., consent checkbox) is handled via standard HTML forms and server-side processing.

### 4.5 CSS Stylesheets (`views/css/`)

This module does **not** include any custom CSS files. Any styling for the consent checkbox or other elements would be inherited from the active PrestaShop theme.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `arukereso/views/templates/hook/consent.tpl`
  - **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (depending on theme and PrestaShop version, one of these will render the consent).
  - **Purpose:** This template renders the HTML for the customer consent checkbox during the checkout process. It typically includes a label, the checkbox input, and potentially a link to the privacy policy or more information about Arukereso.hu.
  - **Output:** A small form element allowing the customer to opt-in to the survey program.
- `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`
  - **Purpose:** This template is rendered on the order confirmation page after a successful purchase. It might display a message to the customer confirming their participation in the survey program (if consent was given) or provide information about the upcoming survey.
  - **Output:** A small informational block on the order confirmation page.

#### Admin templates (`views/templates/admin/`)

This module does **not** contain any custom admin templates beyond what is rendered by `getContent()` in the main module file.

#### Front-office templates (`views/templates/front/`)

This module does **not** contain any dedicated standalone front-office page templates.

### 4.7 Database Schema & Hooks Map

#### Database Tables

This module does **not** create any custom database tables. All its configuration settings are stored in PrestaShop’s `ps_configuration` table using the following keys:

- `ARUKERESO_FILE_LOG`: Stores the boolean value for logging errors.
- `ARUKERESO_ID`: Stores the Arukereso.hu WebApiKey.
- `ARUKERESO_PRODUCT_ID`: Stores the chosen product identifier type (e.g., ‘id\_product’, ‘reference’).
- `ARUKERESO_CONSENT`: Stores the boolean value for requiring customer consent.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: A standard PrestaShop configuration key, not directly managed by this module but potentially used for language handling in the back office.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayGDPRConsent` | During checkout, typically near privacy policy consent. | Renders the customer consent checkbox for Arukereso.hu survey participation. |
| `actionDeleteGDPRCustomer` | Triggered when a customer requests data deletion via PrestaShop’s GDPR module. | Handles the deletion of any customer-specific data stored by the module (e.g., consent status). |
| `actionExportGDPRData` | Triggered when a customer requests data export via PrestaShop’s GDPR module. | Provides any customer-specific data stored by the module for export. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Renders an informational message to the customer and, crucially, sends the order data to Arukereso.hu’s API if consent is given. |
| `displayPaymentTop` | At the top of the payment section during checkout. | Alternative hook for rendering the customer consent checkbox, depending on theme. |
| `displayCheckoutSummaryTop` | At the top of the checkout summary section. | Alternative hook for rendering the customer consent checkbox, depending on theme. |
| `DisplayGDPRConsent` | (Alias/Older version of `displayGDPRConsent`) | Renders the customer consent checkbox. |
| `DisplayPaymentTop` | (Alias/Older version of `displayPaymentTop`) | Renders the customer consent checkbox. |
| `DisplayOrderConfirmation` | (Alias/Older version of `displayOrderConfirmation`) | Renders info and sends order data. |
| `ActionDeleteGDPRCustomer` | (Alias/Older version of `actionDeleteGDPRCustomer`) | Handles customer data deletion. |
| `ActionExportGDPRData` | (Alias/Older version of `actionExportGDPRData`) | Handles customer data export. |
| `DisplayCheckoutSummaryTop` | (Alias/Older version of `displayCheckoutSummaryTop`) | Renders the customer consent checkbox. |

The module’s core logic for sending order data to Arukereso.hu resides within the `hookDisplayOrderConfirmation` method in `arukereso.php`. This method checks for customer consent (if required) and then constructs and sends an HTTP request to the Arukereso.hu API with the order details.

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any technical issues or questions you may have regarding the Arukereso.hu - trusted purchase program survey emails module.
