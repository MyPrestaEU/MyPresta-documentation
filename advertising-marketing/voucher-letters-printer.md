---
title: "Voucher & Letters Printer - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Voucher & Letters Printer PrestaShop module by MyPresta.eu."
sidebar:
  label: "Voucher & Letters Printer - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Voucher & Letters Printer Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/voucher-letters-printer/)
>
> ---


# Voucher & Letters Printer

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). No special hosting requirements beyond a typical PrestaShop setup.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Voucher & Letters Printer)

This is the main configuration screen where you’ll define the parameters for your vouchers and letters.

#### **General Settings**

- **What this setting does:** These settings control the overall behavior and appearance of the generated vouchers and letters.
- **Effect of changing this setting:** Changes here will directly impact the content and format of the documents you print.

#### **Voucher Code Generation**

- **Voucher Prefix:**

  - **What this setting does:** This text will be added to the beginning of every generated voucher code. It helps you identify the source of the voucher (e.g., “WELCOME-”, “LOYALTY-”).
  - **Effect of changing this setting:**
    - *When set to “SALE-”:* All generated codes will start with “SALE-”, like “SALE-ABC123XYZ”.
    - *When left empty:* Codes will be purely random characters, e.g., “ABC123XYZ”.
  - **Recommended value:** A short, descriptive prefix related to your campaign.
  - **Merchant scenario / example:** If you’re sending a loyalty reward, use “LOYALTY-”. For a seasonal sale, “SUMMER-”.
- **Voucher Suffix:**

  - **What this setting does:** Similar to the prefix, this text will be added to the end of every generated voucher code.
  - **Effect of changing this setting:**
    - *When set to “-2024”:* All generated codes will end with “-2024”, like “ABC123XYZ-2024”.
    - *When left empty:* Codes will not have a suffix.
  - **Recommended value:** Leave empty unless you have a specific tracking need.
  - **Merchant scenario / example:** You might use a year suffix like “-2024” for annual campaigns.
- **Voucher Code Length (excluding prefix/suffix):**

  - **What this setting does:** Determines the number of random characters in the voucher code itself, between the prefix and suffix. A longer code is more secure but harder to type.
  - **Effect of changing this setting:**
    - *When set to 8:* Codes will have 8 random characters (e.g., “ABC123XY”).
    - *When set to 12:* Codes will have 12 random characters (e.g., “ABC123XYZ456”).
  - **Recommended value:** 8-12 characters for a good balance of security and usability.
  - **Merchant scenario / example:** For a general promotion, 8 characters is usually sufficient. For high-value, exclusive vouchers, you might opt for 10-12.

#### **Voucher & Letter Content**

- **Voucher Value:**

  - **What this setting does:** This is the monetary value or percentage discount that the generated voucher will provide.
  - **Effect of changing this setting:**
    - *When set to “10”:* The voucher will grant a 10 unit discount (e.g., €10, $10).
    - *When set to “20%”:* The voucher will grant a 20% discount.
  - **Recommended value:** A value that encourages purchases without significantly impacting your margins.
  - **Merchant scenario / example:** Offer €15 off for a minimum order of €100, or 10% off the entire cart.
- **Voucher Minimum Amount:**

  - **What this setting does:** The minimum order total (before shipping) required for the customer to use the voucher.
  - **Effect of changing this setting:**
    - *When set to “50”:* Customers must spend at least €50 to use the voucher.
    - *When set to “0” or left empty:* No minimum purchase is required.
  - **Recommended value:** Set a minimum amount to ensure profitability, typically 2-3 times the voucher value.
  - **Merchant scenario / example:** If the voucher is for €10, set a minimum of €30 to encourage a larger purchase.
- **Voucher Expiry Date (Days from Generation):**

  - **What this setting does:** Defines how many days after the voucher is generated it will expire. This creates urgency.
  - **Effect of changing this setting:**
    - *When set to “30”:* The voucher will be valid for 30 days from the date it’s created.
    - *When set to “0” or left empty:* The voucher will not have an expiry date (not recommended for most campaigns).
  - **Recommended value:** 30-90 days, depending on the urgency you want to create.
  - **Merchant scenario / example:** For a quick sale, 30 days. For a loyalty reward, 90 days.
- **Letter Header Text:**

  - **What this setting does:** This is the main title or greeting that will appear at the top of your personalized letter.
  - **Effect of changing this setting:**
    - *When set to “Dear Valued Customer,”:* This will be the opening line of every letter.
    - *When set to “A Special Offer Just For You!”:* This will be the prominent heading.
  - **Recommended value:** A warm, personal greeting.
  - **Merchant scenario / example:** “Hello [Customer Name],” (if you plan to manually insert names or use a mail merge tool later) or “Thank You for Being a Loyal Customer!”
- **Letter Body Text:**

  - **What this setting does:** This is the main content of your letter, where you explain the offer, thank the customer, and provide any other relevant information. You can use placeholders for dynamic content (though the module itself doesn’t offer direct placeholders, you’d typically use a mail merge tool for this after export).
  - **Effect of changing this setting:** This text will form the core message of your physical letter.
  - **Recommended value:** Clear, concise, and persuasive text that explains the voucher’s benefits and encourages redemption.
  - **Merchant scenario / example:** “As a token of our appreciation, please enjoy [Voucher Value] off your next purchase of [Minimum Amount]. Use code: [Voucher Code]. Valid until [Expiry Date].”
- **Letter Footer Text:**

  - **What this setting does:** This text appears at the bottom of your letter, typically for your store’s contact information, website, or a closing remark.
  - **Effect of changing this setting:** This will be the closing section of your letter.
  - **Recommended value:** Your store’s website, contact email, or a friendly closing like “Sincerely, The [Your Store Name] Team.”
  - **Merchant scenario / example:** “Visit us at [www.yourstore.com](http://www.yourstore.com) for more amazing products!”

#### **Printing & Design Options**

- **Print Voucher Code on Letter:**

  - **What this setting does:** A simple switch to include the generated voucher code directly within the printed letter.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The unique voucher code will be automatically inserted into the letter body wherever you specify (or at a default position if not specified in the body text).
    - *When disabled (NO):* The voucher code will not be printed on the letter. You might choose this if you’re printing separate voucher cards.
  - **Recommended value:** YES, for convenience and to ensure the customer has the code.
  - **Merchant scenario / example:** If you want a single document for the customer, enable this.
- **Text Color (for Letter/Voucher):**

  - **What this setting does:** Allows you to choose the color of the text on your printed documents.
  - **Effect of changing this setting:** Changes the ink color used for the text.
  - **Recommended value:** Black or a dark, readable color that contrasts well with white paper.
  - **Merchant scenario / example:** Use your brand’s primary text color for consistency.
- **Background Color (for Voucher Section):**

  - **What this setting does:** If you’re printing vouchers directly on the letter, this sets a background color for the voucher code area to make it stand out.
  - **Effect of changing this setting:** Creates a colored box behind the voucher code.
  - **Recommended value:** A light, subtle color that doesn’t obscure the text, or leave it white if you prefer.
  - **Merchant scenario / example:** A light grey or a pastel version of your brand color to highlight the voucher.
- **Font Size (for Letter/Voucher):**

  - **What this setting does:** Controls the size of the text on your printed documents.
  - **Effect of changing this setting:**
    - *When set to “12px”:* Text will be standard readable size.
    - *When set to “16px”:* Text will be larger, easier to read for some.
  - **Recommended value:** 10-14px for body text, slightly larger for headings.
  - **Merchant scenario / example:** If your target audience includes older demographics, a slightly larger font size might be beneficial.

#### **Customer Selection & Generation**

- **Select Customers:**

  - **What this setting does:** This section allows you to choose which customers will receive the personalized letters and vouchers. You can select specific customers from a list.
  - **Effect of changing this setting:** Only the selected customers will have vouchers generated for them, and their details will be used for the letters.
  - **Recommended value:** Select customers based on your campaign goals (e.g., new customers, loyal customers, inactive customers).
  - **Merchant scenario / example:** Select all customers who haven’t purchased in the last 6 months to re-engage them.
- **Generate Vouchers & Letters Button:**

  - **What this setting does:** After configuring all settings and selecting customers, clicking this button will initiate the process of generating the unique voucher codes and preparing the personalized letters for printing.
  - **Effect of changing this setting:** This action creates new cart rules (vouchers) in your PrestaShop store and generates the printable documents.
  - **Recommended value:** Click only after reviewing all settings carefully.
  - **Merchant scenario / example:** Once a campaign is planned, click this to prepare the mailing.

#### **Configuration Quick Reference Table**

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | Voucher Prefix | `LOYALTY-` | Text at start of voucher code. Helps identify campaign. |
| Main Config | Voucher Suffix | Empty | Text at end of voucher code. Useful for tracking. |
| Main Config | Voucher Code Length | 8-12 | Number of random characters in code. Affects security/usability. |
| Main Config | Voucher Value | `10` (e.g., €10 or 10%) | Discount amount or percentage. |
| Main Config | Voucher Minimum Amount | `0` (or 2-3x voucher value) | Minimum order for voucher use. Ensures profitability. |
| Main Config | Voucher Expiry Date (Days) | `30-90` | Days until voucher expires. Creates urgency. |
| Main Config | Letter Header Text | `Dear Valued Customer,` | Main greeting/title of the letter. |
| Main Config | Letter Body Text | (Custom message) | Main content of the letter, explaining the offer. |
| Main Config | Letter Footer Text | `www.yourstore.com` | Closing remarks, contact info. |
| Main Config | Print Voucher Code on Letter | YES | Includes voucher code directly on the letter. |
| Main Config | Text Color | Black | Color of all text on printed documents. |
| Main Config | Background Color | White (or light grey) | Background color for the voucher code area. |
| Main Config | Font Size | `12px` | Size of text on printed documents. |
| Main Config | Select Customers | (Specific selection) | Choose which customers receive the mailing. |
| Main Config | Generate Vouchers & Letters | (Button click) | Creates vouchers and printable documents. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I generated vouchers, but they don’t seem to be working on my store.**
A1: After generating, the module creates “Cart Rules” in PrestaShop.
1. **Check Cart Rules:** Go to **Catalog > Discounts > Cart Rules** in your Back Office. Ensure the generated vouchers are listed there and are “Enabled.”
2. **Check Conditions:** Verify the voucher’s conditions (minimum amount, expiry date, customer restrictions) match what you intended. If a customer tries to use a voucher that doesn’t meet the criteria, it won’t apply.
3. **Clear Cache:** Sometimes PrestaShop’s cache can prevent new settings from taking effect immediately. Go to **Advanced Parameters > Performance** and click “Clear cache.”

**Q2: The printed letters don’t look right, or the colors are off.**
A2:
1. **Check Module Settings:** Revisit the module configuration page. Double-check your “Text Color,” “Background Color,” and “Font Size” settings. Ensure you’ve selected colors that print well.
2. **Printer Settings:** The final output quality heavily depends on your physical printer. Check your printer’s ink levels, paper type, and print quality settings. Try printing a test page from another application.
3. **Browser Print Preview:** When you initiate printing from your browser, use the print preview feature to see how it will look before consuming ink and paper. Adjust browser print settings (e.g., margins, headers/footers) if necessary.

**Q3: Can I translate the letter content into different languages for international customers?**
A3: The module’s current version does not offer built-in multi-language fields for the letter content directly within its configuration. You would need to:
1. **Generate for each language:** Configure the module with the letter content in one language, generate the letters for the relevant customers, then repeat the process for other languages and customer groups.
2. **Manual Translation:** If you export the customer data and voucher codes, you could use a separate mail merge tool to create multi-language letters.

**Q4: I want to send letters to customers from a specific country only. How can I do this?**
A4: The module’s “Select Customers” feature allows you to pick individual customers. If you need to filter by country or other criteria, you would typically:
1. **Export Customer Data:** Go to **Customers > Customers** in your Back Office and use the export feature to get a list of all your customers.
2. **Filter Externally:** Use a spreadsheet program (like Excel or Google Sheets) to filter your customer list by country or any other desired criteria.
3. **Manual Selection:** Go back to the module and manually select the filtered customers from the list. This can be tedious for large lists.
4. **Developer Customization (Advanced):** For very large or complex filtering needs, a developer could extend the module to add more advanced customer filtering options.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Voucher & Letters Printer” module.

### 4.1 Architecture Overview

The “Voucher & Letters Printer” module is a standard PrestaShop module primarily operating within the Back Office. It leverages PrestaShop’s `Module` class for its core functionality and `Configuration` class for storing settings. The module’s main purpose is to generate `CartRule` objects (vouchers) and then render printable HTML content based on module settings and selected customer data. It does not introduce custom database tables or complex `ObjectModel` structures beyond what PrestaShop already provides for `CartRule` and `Customer`.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration and logic are handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes in the `classes/` directory. It directly interacts with PrestaShop’s core classes, primarily:

- `Module`: The base class for the module itself.
- `Configuration`: For storing and retrieving module settings.
- `Customer`: To retrieve customer data for letter personalization.
- `CartRule`: To create and manage the generated voucher codes.

### 4.4 JavaScript Assets (`views/js/`)

- **`voucherletter/js/jscolor/jscolor.js`**

  - **Scope:** Back-office.
  - **Description:** This is a third-party JavaScript library for an advanced color picker. It allows the admin user to visually select colors for text and background within the module’s configuration form.
  - **Functionality:** Binds to input fields with specific classes (e.g., `jscolor`) to display a color palette and update the input value with the chosen hexadecimal color code.
- **`voucherletter/js/script.js`**

  - **Scope:** Back-office (module configuration page).
  - **Description:** Contains custom JavaScript logic specific to the module’s configuration form.
  - **Functionality:**
    - Likely handles AJAX requests for generating vouchers and letters (though the module dossier implies `getContent()` handles the full process, this script might assist with form submission or dynamic updates).
    - Could include validation logic for form fields (e.g., ensuring voucher value is a number).
    - Might manage the display/hide of certain form elements based on other selections.
    - Potentially triggers the print functionality in the browser after the letter content is generated.

### 4.5 CSS Stylesheets (`views/css/`)

The module dossier indicates no custom CSS files are present in `views/css/`. Styling for the Back Office configuration would rely on PrestaShop’s default admin theme CSS. Any styling for the *printed output* would be inline CSS generated by the PHP code or very basic HTML styling.

### 4.6 Smarty Template Structure (`views/templates/`)

The module dossier indicates no custom `.tpl` files are present in `views/templates/`. This suggests that:

- The Back Office configuration form is likely rendered directly within the `getContent()` method using PrestaShop’s `HelperForm` or by concatenating HTML strings.
- The printable letter content is generated dynamically as an HTML string within the PHP code and then outputted for the browser’s print function.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create any custom database tables.
  - It stores its configuration settings in PrestaShop’s `ps_configuration` table. Configuration keys would typically follow a pattern like `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE`, etc.
  - It creates new entries in the `ps_cart_rule` and related tables (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) when generating vouchers.
- **Registered Hooks Table**:
  The module dossier indicates that the module does not register any front-office hooks (Header, Columns, Product, Footer). This confirms its primary function as a Back Office tool for generating physical mail.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionModuleInstall` | During module installation | Sets up default configuration values in `ps_configuration`. |
| `actionModuleUninstall` | During module uninstallation | Cleans up configuration values from `ps_configuration`. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “Voucher & Letters Printer” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to help you with any issues or questions you may have.
