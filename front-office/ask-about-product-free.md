---
title: "Ask about product free - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Ask about product free PrestaShop module by MyPresta.eu."
sidebar:
  label: "Ask about product free - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Ask about product free Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/ask-about-product-free/)
>
> ---


# Ask about product free

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Ask about product free” module, where you control its behavior and appearance.

- **Menu Location:** Back Office > Modules > Module Manager > “Ask about product free” > Configure

#### Settings & Options:

1. **Display product summary inside popup**

   - **What this setting does:** Controls whether a small summary of the product (like its name and image) is shown within the “Ask about product” popup form.
   - **Effect of changing this setting:**
     - *When enabled (Yes):* The popup form will include a brief overview of the product the customer is inquiring about. This helps the customer confirm they are asking about the correct item and provides context for you when you receive the email.
     - *When disabled (No):* The popup form will only contain the fields for the customer’s name, email, and question, without any product-specific summary.
   - **Recommended value:** **Yes**.
   - **Merchant scenario / example:** Enabling this helps avoid confusion. A customer might have multiple tabs open and forget which product they’re asking about. The summary confirms it for them and for you.
2. **Enabled**

   - **What this setting does:** This is the master switch to activate or deactivate the entire “Ask about product” feature on your storefront.
   - **Effect of changing this setting:**
     - *When enabled (Yes):* The “Ask about product” button will appear on product pages, and the popup form will be functional.
     - *When disabled (No):* The “Ask about product” button will be hidden from product pages, and customers will not be able to use this feature.
   - **Recommended value:** **Yes** (to use the module).
   - **Merchant scenario / example:** You might disable it temporarily if you’re performing maintenance or if you prefer to handle all inquiries through a different channel for a period.
3. **GDPR Compliant**

   - **What this setting does:** Activates a checkbox on the “Ask about product” form, requiring customers to explicitly agree to your privacy policy before submitting their question. This helps your store comply with GDPR and other data protection regulations.
   - **Effect of changing this setting:**
     - *When enabled (Yes):* A mandatory checkbox will appear on the form, typically stating something like “I agree to the privacy policy.” The customer must check this box to submit their question.
     - *When disabled (No):* The privacy policy checkbox will not be displayed, and customers can submit their questions without explicit consent.
   - **Recommended value:** **Yes**.
   - **Merchant scenario / example:** If your store operates in regions with strict data protection laws (like the EU), enabling this is crucial for legal compliance.
4. **Privacy policy page**

   - **What this setting does:** If “GDPR Compliant” is enabled, this setting allows you to select which CMS (Content Management System) page from your store will be linked as your privacy policy.
   - **Effect of changing this setting:**
     - *When a page is selected:* The “I agree to the privacy policy” text in the popup form will include a clickable link to the chosen CMS page, allowing customers to easily review your policy.
     - *When no page is selected (or GDPR Compliant is No):* No link will be provided, or the GDPR feature will not be active.
   - **Recommended value:** Select your store’s official privacy policy page.
   - **Merchant scenario / example:** You must have a dedicated CMS page outlining your data handling practices. This setting ensures customers can easily access it.
5. **Email title**

   - **What this setting does:** Defines the subject line for the email you receive when a customer submits a question through the form.
   - **Effect of changing this setting:**
     - *When set to a specific title (e.g., “New Product Question”):* All incoming emails from this module will use this subject line, making them easy to identify in your inbox.
     - *When left default:* The module will use its default subject line, which might be less descriptive.
   - **Recommended value:** Something clear and descriptive, like “New Product Question from [Your Store Name]”.
   - **Merchant scenario / example:** A clear subject line helps you quickly prioritize and respond to customer inquiries, especially if you receive many emails daily.
6. **Recipient of the email from the form**

   - **What this setting does:** Specifies the email address(es) where customer questions submitted through the “Ask about product” form will be sent.
   - **Effect of changing this setting:**
     - *When one or more email addresses are entered (separated by commas):* The module will send all customer inquiries to these specified addresses.
     - *When left empty:* The module might default to the store’s main contact email, or the feature might not work correctly.
   - **Recommended value:** Your customer service email address (e.g., `support@yourstore.com`) or a dedicated email for product inquiries. You can add multiple emails separated by commas if multiple team members need to receive these.
   - **Merchant scenario / example:** Directing these emails to the right team ensures prompt responses, improving customer satisfaction.
7. **ReCaptcha protection (v2)**

   - **What this setting does:** Integrates Google reCAPTCHA v2 (the “I’m not a robot” checkbox) into the “Ask about product” form to protect against spam and automated submissions.
   - **Effect of changing this setting:**
     - *When enabled (Yes):* The reCAPTCHA checkbox will appear on the form, requiring customers to pass the challenge before submitting.
     - *When disabled (No):* The form will not have reCAPTCHA protection, making it potentially vulnerable to spam bots.
   - **Recommended value:** **Yes**.
   - **Merchant scenario / example:** If you’re receiving a lot of spam inquiries through the form, enabling reCAPTCHA is essential to filter out illegitimate messages.
8. **reCaptcha site key**

   - **What this setting does:** This is the public key provided by Google reCAPTCHA that allows your website to display the reCAPTCHA widget. You get this key when you register your site with Google reCAPTCHA.
   - **Effect of changing this setting:**
     - *When correctly entered:* The reCAPTCHA widget will display and function correctly on your form.
     - *When incorrect or empty:* reCAPTCHA will not work, and you might see an error message or the form won’t submit.
   - **Recommended value:** The site key obtained from your Google reCAPTCHA account.
   - **Merchant scenario / example:** You need to register your domain with Google reCAPTCHA (v2) to get both a site key and a secret key.
9. **reCaptcha secret key**

   - **What this setting does:** This is the private key provided by Google reCAPTCHA that allows your server to verify the reCAPTCHA response. It’s used for server-side validation.
   - **Effect of changing this setting:**
     - *When correctly entered:* Your server can successfully verify if a customer has passed the reCAPTCHA challenge.
     - *When incorrect or empty:* Even if the reCAPTCHA widget displays, the form submission will fail validation, and the question won’t be sent.
   - **Recommended value:** The secret key obtained from your Google reCAPTCHA account.
   - **Merchant scenario / example:** This key is crucial for the security aspect of reCAPTCHA, ensuring that only legitimate submissions are processed.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Display product summary inside popup | Yes | Shows product details in the popup for clarity. |
| Module Configuration | Enabled | Yes | Activates/deactivates the “Ask about product” feature. |
| Module Configuration | GDPR Compliant | Yes | Adds a privacy policy agreement checkbox to the form. |
| Module Configuration | Privacy policy page | Select your CMS Privacy Policy page | Links to your store’s privacy policy for GDPR. |
| Module Configuration | Email title | “New Product Question from [Your Store Name]” | Sets the subject line for incoming question emails. |
| Module Configuration | Recipient of the email from the form | Your customer service email (e.g., `support@yourstore.com`) | Specifies where customer questions are sent. |
| Module Configuration | ReCaptcha protection (v2) | Yes | Enables Google reCAPTCHA to prevent spam. |
| Module Configuration | reCaptcha site key | Your Google reCAPTCHA Site Key | Public key for displaying the reCAPTCHA widget. |
| Module Configuration | reCaptcha secret key | Your Google reCAPTCHA Secret Key | Private key for server-side reCAPTCHA validation. |

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminAapfreeQuestionController (Back Office > Ask about product > Questions)

This dedicated administration screen allows you to view and manage all the questions submitted through the “Ask about product” form.

- **Screen Name & Menu Location:** Back Office > **Ask about product** (new menu item) > **Questions**
- **Available Actions & Settings:**
  - **Listing Table:** This screen displays a table of all submitted questions. Each row typically shows:
    - **ID:** Unique identifier for the question.
    - **Customer Name:** The name provided by the customer.
    - **Customer Email:** The email address provided by the customer.
    - **Product Name:** The name of the product the question is about.
    - **Question:** A snippet or the full text of the customer’s question.
    - **Date Added:** When the question was submitted.
    - **Status:** (e.g., New, Answered, Pending) - *Note: The module dossier does not explicitly state a status field, but it’s a common feature for such lists. If not present, it will simply list all questions.*
  - **View Details:** You can usually click on a question in the list to view its full details, including the complete question text and potentially the product link.
  - **Delete:** Options to delete individual questions or potentially bulk delete selected questions.
- **Effect of changes:**
  - **Viewing questions:** Allows you to review all customer inquiries in one centralized location within your PrestaShop back office, even if you also receive them via email.
  - **Deleting questions:** Removes the question record from your database. This is useful for cleaning up old or irrelevant inquiries.
- **Recommended workflow for daily store management:**
  1. Regularly check this “Questions” list (or your email inbox, as configured) for new inquiries.
  2. Prioritize and respond to questions promptly to maintain good customer service.
  3. After responding, you might delete the question from this list to keep it tidy, or if the module supports it, mark it as “Answered.”

#### index.php (aapfree/controllers/admin/index.php)

This file is typically a placeholder or a redirector within the `controllers/admin` directory and doesn’t represent a distinct, configurable screen for the merchant. It’s a standard PrestaShop practice to have an `index.php` in subdirectories to prevent directory listing, or it might contain basic routing logic. It does not manage a specific table or entity for direct merchant interaction.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: The “Ask about product” button isn’t showing up on my product pages.**

- **A:** First, check if the module is “Enabled” in its configuration settings (Back Office > Modules > Module Manager > Ask about product free > Configure). If it is, try clearing your PrestaShop cache (Advanced Parameters > Performance > Clear cache). Sometimes, theme conflicts or specific custom theme structures can prevent the button from appearing. If it’s still missing, contact your webmaster or MyPresta.eu support.

**Q2: I’m not receiving any emails when customers submit questions.**

- **A:**
  1. Verify the “Recipient of the email from the form” setting in the module configuration. Ensure the email address(es) are correct and separated by commas if there are multiple.
  2. Check your spam/junk folder in the recipient email inbox.
  3. Ensure your store’s email settings are correctly configured in PrestaShop (Advanced Parameters > E-mail). Test sending a general email from PrestaShop to confirm your mail server is working.
  4. If ReCAPTCHA is enabled, ensure both the “reCaptcha site key” and “reCaptcha secret key” are correctly entered. Incorrect keys will prevent submissions.

**Q3: The reCAPTCHA isn’t working, or I see an error message.**

- **A:** This usually means your reCAPTCHA keys are incorrect or not properly configured with Google.
  1. Go to the Google reCAPTCHA admin console and ensure your domain is correctly registered for reCAPTCHA v2.
  2. Copy the “Site Key” and “Secret Key” exactly as provided by Google and paste them into the module’s configuration fields.
  3. Clear your PrestaShop cache after making changes.

**Q4: How do I change the text on the “Ask about product” button or the popup form?**

- **A:** You can translate the module’s text strings directly within PrestaShop. Go to **International > Translations**, select “Installed modules translations”, choose your theme, and then select “Ask about product free”. You’ll find all translatable strings there, including button labels, form field labels, and confirmation messages.

**Q5: The popup looks strange or doesn’t display correctly on my mobile phone.**

- **A:** While the module is designed to be responsive, custom themes can sometimes override or conflict with its styling.
  1. Clear your browser cache and PrestaShop cache.
  2. If the issue persists, it’s likely a CSS conflict with your theme. Your webmaster or a developer would need to inspect the page using browser developer tools to identify and resolve the CSS conflict.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Ask about product free” module follows a standard PrestaShop MVC (Model-View-Controller) pattern, primarily focusing on front-office interaction and back-office administration of submitted questions. It leverages PrestaShop’s hook system for integration into product pages and uses dedicated front controllers for AJAX requests and form submission. The back-office component provides a simple list management interface for questions.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/index.php`
    - **Class name & parent class:** `AapfreeIndexModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This controller likely handles the initial display logic for the module’s front-office component, possibly rendering the button or preparing data for the popup. It might also serve as a catch-all for module-specific front-office routes.
  - `controllers/front/question.php`
    - **Class name & parent class:** `AapfreeQuestionModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility:** This is the core controller for handling the “Ask about product” form submission. It receives POST data from the popup form, validates inputs (including reCAPTCHA if enabled), processes the question, sends the email to the configured recipients, and stores the question in the database. It returns JSON responses for AJAX requests (e.g., success/error messages).
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminAapfreeQuestion.php`
    - **Class name & parent class:** `AdminAapfreeQuestionController` extending `ModuleAdminController`.
    - **Tab name and managed entity:** This controller creates and manages the “Questions” tab under the “Ask about product” menu in the PrestaShop Back Office. It’s responsible for displaying a list (grid) of all submitted questions, allowing administrators to view details and delete entries. It interacts with the `AapfreeQuestion` `ObjectModel` (if one exists, otherwise directly with the database).
  - `controllers/admin/index.php`
    - **Class name & parent class:** Not a functional controller in the traditional sense.
    - **Tab name and managed entity:** This file is a standard PrestaShop security measure to prevent directory listing. It typically contains a simple `header('Location: ../../index.php?controller=AdminHome');` or similar redirect, or just `<?php exit;`. It does not manage any specific entity or provide a configurable screen.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module might handle database interactions directly within its controllers or the main module file, or it might use a generic `ObjectModel` for `aapfreequestion` if it’s implicitly defined.

- **Implicit Model (likely):** Given the `AdminAapfreeQuestionController` manages a table, there is an implicit `AapfreeQuestion` model, even if not explicitly in `classes/`. This model would map to the `_aapfree_question` database table.
  - **Database table:** `ps_aapfree_question` (or similar, based on module prefix).
  - **Extends `ObjectModel`:** Yes, implicitly.
  - **`$definition` fields (expected):** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 JavaScript Assets (`views/js/`)

- `aapfree/views/aapfree.js`
  - **Scope:** Front-office.
  - **Event listeners:**
    - Binds click events to the “Ask about product” button (`.aapfree-button`).
    - Binds submit events to the “Ask about product” form within the popup (`#aapfree-form`).
    - Handles events related to the reCAPTCHA widget (if enabled).
  - **DOM manipulation:**
    - Opens and closes the modal popup (`#aapfree-modal`).
    - Populates product summary data into the popup.
    - Displays success or error messages to the user after form submission.
    - Manages form field states (e.g., disabling submit button during AJAX).
  - **AJAX calls:**
    - Sends form data to the `AapfreeQuestionModuleFrontController` (e.g., `index.php?fc=module&module=aapfree&controller=question`).
    - Processes JSON responses from the server.
  - **External SDK calls:** Initializes and renders Google reCAPTCHA v2 widget if `aapfree_recaptcha` is enabled, using the `aapfree_recaptcha_sitekey`.

### 4.5 CSS Stylesheets (`views/css/`)

- `aapfree/views/aapfree.css`
  - **Scope:** Front-office customer styling.
  - **Main UI components and containers it styles:**
    - The “Ask about product” button (`.aapfree-button`).
    - The modal popup container (`#aapfree-modal`).
    - The form elements within the popup (input fields, textareas, labels, checkboxes).
    - Success and error message displays.
    - Responsive adjustments for different screen sizes.
  - **Key CSS class selectors developers can override:** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Developers can override these styles in their theme’s `custom.css` or by using PrestaShop’s theme customization features.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `aapfree/views/aapfree-extra.tpl`
    - **Hook:** `displayProductAdditionalInfo` (or similar product page hook like `displayProductButtons`, `displayProductActions`).
    - **Visual block output:** This template is responsible for rendering the “Ask about product” button on the product page. It also contains the HTML structure for the modal popup form, which is initially hidden and shown via JavaScript. It includes placeholders for product summary, form fields, GDPR checkbox, and reCAPTCHA.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_aapfree_question`:
    - `id_aapfree_question` (INT, PRIMARY KEY, AUTO\_INCREMENT)
    - `id_product` (INT, Foreign Key to `ps_product`)
    - `customer_name` (VARCHAR)
    - `customer_email` (VARCHAR)
    - `question_text` (TEXT)
    - `date_add` (DATETIME)
    - (Potentially other fields like `ip_address`, `status`, `id_customer` if implemented)
  - **Configuration Records (in `ps_configuration`):**
    - `AAPFREE_TITLE`: Email subject line.
    - `AAPFREE_GDPR`: GDPR compliance status (0/1).
    - `AAPFREE_GDPRCMS`: ID of the CMS page for privacy policy.
    - `AAPFREE_SUMMARY`: Display product summary status (0/1).
    - `AAPFREE_RECAPTCHA`: reCAPTCHA protection status (0/1).
    - `AAPFREE_RECAPTCHA_SITEKEY`: Google reCAPTCHA site key.
    - `AAPFREE_RECAPTCHA_SECRETKEY`: Google reCAPTCHA secret key.
    - `AAPFREE_EMAILSLIST`: Comma-separated list of recipient emails.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayProductAdditionalInfo` | On product pages, typically below the product description or price. | Renders the “Ask about product” button and the hidden modal popup structure. |
| `actionAdminControllerSetMedia` | When an admin controller loads its assets (CSS/JS). | Injects module-specific CSS (`aapfree.css`) and JavaScript (`aapfree.js`) into the Back Office for the `AdminAapfreeQuestionController`. |
| `displayHeader` | In the `<head>` section of every front-office page. | Potentially used to load global JavaScript variables, CSS, or the Google reCAPTCHA API script if reCAPTCHA is enabled. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Ask about product free” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our team is dedicated to ensuring the smooth operation and continued enhancement of your module.
