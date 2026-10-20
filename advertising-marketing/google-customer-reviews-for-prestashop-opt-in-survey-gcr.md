---
title: "Google Customer Reviews for PrestaShop - opt-in & survey (GCR) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Google Customer Reviews for PrestaShop - opt-in & survey (GCR) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Google Customer Reviews for PrestaShop - opt-in & survey (GCR) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Google Customer Reviews for PrestaShop - opt-in & survey (GCR) Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Google Customer Reviews for PrestaShop - opt-in & survey (GCR)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

To access the module’s settings, go to **Modules > Module Manager**, search for “Google Customer Reviews”, and click the “Configure” button.

#### **Google Merchant ID**

- **What this setting does:** This is the unique identifier for your Google Merchant Center account. Google uses this ID to associate the reviews collected with your specific business.
- **Effect of changing this setting:**
  - *When correctly entered:* The Google Customer Reviews opt-in script will function properly, sending review data to your Google Merchant Center account.
  - *When incorrect or empty:* The opt-in script will not work, and Google will not collect reviews for your store.
- **Recommended value:** Your exact Google Merchant Center ID. You can find this ID by logging into your Google Merchant Center account (merchant.google.com) – it’s usually displayed in the top right corner.
- **Merchant scenario / example:** If your Google Merchant Center ID is `123456789`, you would enter `123456789` into this field. Without it, Google doesn’t know which merchant to attribute the reviews to.

#### **Include product GTIN list in GCR payload**

- **What this setting does:** This option controls whether the Global Trade Item Numbers (GTINs) of the products in the customer’s order are included when the opt-in data is sent to Google. GTINs (like EAN, UPC, ISBN) help Google identify specific products for product-level reviews.
- **Effect of changing this setting:**
  - *When enabled (Yes):* The module will attempt to retrieve and include the GTINs for each product in the order. This allows Google to potentially collect product-specific reviews, which can appear on product pages and in Google Shopping.
  - *When disabled (No):* Only seller reviews will be collected. Product-specific GTINs will not be sent, meaning Google will not prompt customers for reviews on individual products from that order.
- **Recommended value:** **Yes**. Including GTINs is highly recommended if you want to collect product-level reviews, which are very valuable for product visibility and trust. Ensure your products in PrestaShop have their EAN/UPC fields correctly filled.
- **Merchant scenario / example:** If you sell a “Blue T-Shirt” with EAN `1234567890123`, enabling this ensures Google knows *which* product the customer bought, allowing them to review that specific item. If disabled, Google would only ask for a general review of your store.

#### **Fallback delivery offset (days)**

- **What this setting does:** This setting determines the estimated number of days after an order is placed that the customer is expected to receive their delivery. Google uses this date to schedule when to send the review survey email.
- **Effect of changing this setting:**
  - *When set to a specific number (e.g., 7):* The module calculates the estimated delivery date by adding this number of days to the order date. Google will then send the survey email around this calculated delivery date.
  - *When set to 0 or a very low number:* Google might send the survey too early, before the customer has received their product, leading to irrelevant or negative reviews.
  - *When set to a very high number:* Google might send the survey too late, and the customer might have forgotten details of their purchase experience.
- **Recommended value:** This depends on your average shipping times. A common starting point is **7 days**. Adjust this based on your actual delivery performance.
- **Merchant scenario / example:** If your average delivery time is 5-7 business days, setting this to `7` days is appropriate. If you ship internationally and deliveries take 2-3 weeks, you might set it to `14` or `21` days. This ensures the survey arrives when the customer has had time to receive and experience the product.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Google Merchant ID | Your Merchant ID | Links collected reviews to your Google Merchant Center account. **CRITICAL for function.** |
| Module Configuration | Include product GTIN list in GCR payload | Yes | Enables collection of product-specific reviews by sending product identifiers. |
| Module Configuration | Fallback delivery offset (days) | 7 | Sets the estimated delivery date for survey scheduling. Adjust based on average shipping time. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but I don’t see the Google Customer Reviews opt-in on my order confirmation page.**
A:

1. **Check your Google Merchant ID:** Double-check that you’ve entered the correct Google Merchant ID in the module configuration. An incorrect ID will prevent the script from loading.
2. **Clear PrestaShop Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes, cached content can prevent new module scripts from appearing.
3. **Check for JavaScript Errors:** Open your browser’s developer console (usually F12) on the order confirmation page. Look for any JavaScript errors, which might indicate a conflict with another module or your theme.
4. **Verify Hook Execution:** Ensure your theme correctly calls the `displayOrderConfirmation` hook. While standard, some heavily customized themes might omit or rename hooks.

**Q: The opt-in appears, but I’m not seeing any reviews in my Google Merchant Center.**
A:

1. **Google Merchant Center Status:** Log into your Google Merchant Center account and navigate to the “Google Customer Reviews” section. Ensure the program is active and there are no issues reported. It can take some time for reviews to start appearing after initial setup.
2. **Customer Opt-in Rate:** Not every customer will opt-in to the survey. A certain percentage of customers need to agree to receive the survey email from Google.
3. **Survey Completion:** Even if a customer opts in, they still need to complete the survey sent by Google.

**Q: Can I customize the appearance of the Google Customer Reviews opt-in or badge?**
A: The appearance of the opt-in prompt and the Google Customer Reviews badge is controlled by Google and cannot be directly customized through the PrestaShop module. Google maintains a consistent brand experience for these elements. You can, however, choose where to display the badge on your site via your Google Merchant Center settings (e.g., footer, sidebar).

**Q: My products have GTINs, but I’m not getting product-level reviews.**
A:

1. **Enable GTINs in Module:** Ensure the “Include product GTIN list in GCR payload” option is set to “Yes” in the module configuration.
2. **Correct GTIN Format:** Verify that your product GTINs (EAN, UPC, ISBN) are correctly entered in your PrestaShop product pages and follow the standard formats. Incorrectly formatted GTINs might be ignored by Google.
3. **Google’s Discretion:** Even with GTINs provided, Google ultimately decides whether to prompt for product-level reviews. Factors like product popularity and review volume can influence this.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The `gcroptin` module is a lightweight PrestaShop module designed to inject the official Google Customer Reviews opt-in script into the `displayOrderConfirmation` hook. It leverages PrestaShop’s `Module` class and `Smarty` templating engine. The core logic resides in the main module file, handling configuration storage and dynamic data injection into the Smarty template. It does not introduce custom controllers, models, or complex JavaScript/CSS assets, focusing solely on the required script injection with dynamic order data.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module operates by hooking into `displayOrderConfirmation` and rendering a template directly.
- **Back-Office Admin Controllers**: None. All configuration is handled within the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` instances are defined. All logic is self-contained within `gcroptin.php`.

### 4.4 JavaScript Assets (`views/js/`)

- None. The module directly outputs the Google Customer Reviews JavaScript snippet within a Smarty template.

### 4.5 CSS Stylesheets (`views/css/`)

- None. The Google Customer Reviews opt-in UI is rendered by Google’s script and does not require custom styling from the module.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
    - **Purpose:** This template is rendered when the `displayOrderConfirmation` hook is executed. It contains the core Google Customer Reviews opt-in JavaScript snippet.
    - **Data Available:** This template receives various order-specific variables from the module, including:
      - `{$gcr_merchant_id}`: The Google Merchant Center ID configured in the back office.
      - `{$gcr_order_id}`: The PrestaShop order ID.
      - `{$gcr_currency_iso_code}`: ISO code of the order currency.
      - `{$gcr_total_paid}`: Total amount paid for the order.
      - `{$gcr_customer_email}`: Customer’s email address.
      - `{$gcr_delivery_country}`: ISO code of the delivery country.
      - `{$gcr_delivery_date}`: Calculated estimated delivery date.
      - `{$gcr_product_gtins_json}`: JSON encoded array of product GTINs (if enabled).
    - **Output:** It outputs a `<script>` tag containing the Google Customer Reviews opt-in code, dynamically populated with the order details.

### 4.7 Database Schema & Hooks Map

- **Database Tables**: The module does not create any custom database tables. It stores its configuration settings in PrestaShop’s `ps_configuration` table using keys like `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN`, and `GCROPTIN_DELIVERY_OFFSET`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayOrderConfirmation` | Executed on the order confirmation page after a successful checkout. | Injects the Google Customer Reviews opt-in JavaScript snippet with dynamic order data. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions regarding the “Google Customer Reviews for PrestaShop - opt-in & survey (GCR)” module.
