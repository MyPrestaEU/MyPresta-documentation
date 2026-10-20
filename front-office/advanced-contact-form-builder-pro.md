---
title: "Advanced Contact Form Builder Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Advanced Contact Form Builder Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Advanced Contact Form Builder Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x (up to 12.x as per module definition)
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and for features like webhooks or reCAPTCHA.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main screen where you set up the general behavior and default options for your contact forms.

- **Template support profile**

  - **What this setting does:** This setting helps the module adapt its visual output to better match your store’s theme. Different PrestaShop themes might have slightly different HTML structures.
  - **Effect of changing this setting:**
    - *When set to ‘Classic’ (or similar):* The module will use templates optimized for the default PrestaShop Classic theme or themes based on it. This ensures the forms look good without extra styling effort.
    - *When set to ‘Custom’ or another theme name:* The module might use specific templates or styling rules tailored for that particular theme, if available.
  - **Recommended value:** Choose the option that best matches your active PrestaShop theme. If you’re using the default Classic theme or a theme derived from it, ‘Classic’ is usually the best choice. If your forms don’t look quite right, try experimenting with this setting.
  - **Merchant scenario / example:** If your forms appear unstyled or misaligned after installation, switching this from ‘Classic’ to another available profile (if any) might resolve the issue.
- **Autoresponder email**

  - **What this setting does:** This is the email address from which automatic confirmation emails will be sent to your customers after they submit a form.
  - **Effect of changing this setting:**
    - *When set to a valid email address:* Customers will receive an immediate “Thank you for your inquiry” email from this address.
    - *When left empty:* No automatic confirmation email will be sent to the customer.
  - **Recommended value:** Use a professional email address associated with your store, e.g., `info@yourstore.com` or `noreply@yourstore.com`.
  - **Merchant scenario / example:** Setting this to `support@mystore.com` ensures customers know their message was received and provides them with a contact point for follow-up.
- **Email title (for shop owner)**

  - **What this setting does:** This defines the subject line for the email notifications you (the shop owner) receive when a customer submits a form.
  - **Effect of changing this setting:**
    - *When set to “New Inquiry from My Store”:* Your notification emails will have this subject, making them easy to identify.
  - **Recommended value:** Something clear and descriptive, like “New Contact Form Submission - [Your Shop Name]”.
  - **Merchant scenario / example:** Using “New Customer Inquiry - MyPresta.eu” helps you quickly spot important messages in your inbox.
- **Recipient email(s)**

  - **What this setting does:** This is where you specify one or more email addresses that will receive notifications when a customer submits *any* form created by this module. You can separate multiple emails with a comma.
  - **Effect of changing this setting:**
    - *When set to `sales@yourstore.com`:* All form submissions will be sent to the sales department.
    - *When set to `sales@yourstore.com, support@yourstore.com`:* Both departments will receive copies of all submissions.
  - **Recommended value:** The primary email address(es) for your customer service or sales team.
  - **Merchant scenario / example:** If you have a dedicated customer service team, you’d enter `customerservice@yourstore.com` here.
- **BCC for shop notification email**

  - **What this setting does:** Allows you to send a “Blind Carbon Copy” of the shop owner notification email to additional email addresses. These recipients will not be visible to the primary recipient.
  - **Effect of changing this setting:**
    - *When set to `manager@yourstore.com`:* The manager will receive a hidden copy of all form submission notifications.
  - **Recommended value:** Use this for internal tracking, backup, or for managers who need to monitor inquiries without being the primary contact. Leave empty if not needed.
  - **Merchant scenario / example:** Your marketing team might want to BCC themselves to track lead generation from forms without being directly involved in customer replies.
- **Yes / No (for various field visibility/requirement settings)**

  - **What this setting does:** These are general switches to enable or disable specific features or make certain fields mandatory/optional on your forms.
  - **Effect of changing this setting:**
    - *When enabled (Yes):* The feature is active (e.g., phone field is visible, attachments are allowed).
    - *When disabled (No):* The feature is inactive (e.g., phone field is hidden, attachments are not allowed).
  - **Recommended value:** Depends entirely on your business needs for each specific setting (see individual settings below).
- **GDPR Compliant**

  - **What this setting does:** Enables a checkbox on your forms where customers must explicitly agree to your privacy policy before submitting their data. This is crucial for GDPR compliance.
  - **Effect of changing this setting:**
    - *When enabled:* A mandatory checkbox appears on your forms, typically stating something like “I agree to the privacy policy.” The form cannot be submitted until this box is checked.
    - *When disabled:* No GDPR consent checkbox will appear.
  - **Recommended value:** **YES** if your store operates in regions subject to GDPR (e.g., EU) or if you want to ensure best practices for data privacy.
  - **Merchant scenario / example:** An EU-based store *must* enable this to legally collect customer data via forms.
- **Privacy policy page**

  - **What this setting does:** If GDPR compliance is enabled, this setting allows you to link to your store’s privacy policy CMS page. The GDPR consent checkbox will typically include a link to this page.
  - **Effect of changing this setting:**
    - *When a page is selected:* The GDPR consent text will include a clickable link to your chosen privacy policy page.
    - *When no page is selected:* The GDPR consent text might appear without a link, or link to a default page, which is not ideal for compliance.
  - **Recommended value:** Select your store’s official privacy policy CMS page.
  - **Merchant scenario / example:** After enabling GDPR, you’d select the CMS page titled “Privacy Policy” from the dropdown list.
- **ReCaptcha (v2)**

  - **What this setting does:** Enables Google reCAPTCHA v2 on your forms to protect against spam and bots.
  - **Effect of changing this setting:**
    - *When enabled:* The “I’m not a robot” reCAPTCHA checkbox will appear on your forms. Users must complete this challenge before submitting.
    - *When disabled:* No reCAPTCHA protection is active.
  - **Recommended value:** **YES** to prevent spam submissions. You’ll also need to configure the Site Key and Secret Key below.
  - **Merchant scenario / example:** If you’re receiving a lot of spam through your contact forms, enabling reCAPTCHA is the first step to combat it.
- **ReCaptcha site key**

  - **What this setting does:** This is a public key provided by Google reCAPTCHA that allows your website to display the reCAPTCHA widget.
  - **Effect of changing this setting:**
    - *When correctly entered:* The reCAPTCHA widget will appear and function correctly on your forms.
    - *When incorrect or empty:* reCAPTCHA will not work, and forms might fail to submit or display errors.
  - **Recommended value:** The Site Key obtained from your Google reCAPTCHA account.
  - **Merchant scenario / example:** After creating a reCAPTCHA v2 key pair on the Google reCAPTCHA admin console, you’d copy the “Site Key” here.
- **ReCaptcha secret key**

  - **What this setting does:** This is a private key provided by Google reCAPTCHA that allows your server to verify the reCAPTCHA response. It should be kept secret.
  - **Effect of changing this setting:**
    - *When correctly entered:* Your server can successfully verify if a user passed the reCAPTCHA challenge.
    - *When incorrect or empty:* Verification will fail, and legitimate users might be unable to submit forms.
  - **Recommended value:** The Secret Key obtained from your Google reCAPTCHA account.
  - **Merchant scenario / example:** You’d copy the “Secret Key” from your Google reCAPTCHA admin console here.
- **Webhook URL (Slack/Discord)**

  - **What this setting does:** Allows you to send form submission notifications to a specified Slack or Discord channel via a webhook. This provides instant team alerts.
  - **Effect of changing this setting:**
    - *When a valid URL is entered:* Every form submission will trigger a notification to your configured Slack/Discord channel.
    - *When empty:* No webhook notifications will be sent.
  - **Recommended value:** Your Slack or Discord webhook URL. Leave empty if you don’t use these services for notifications.
  - **Merchant scenario / example:** Your customer support team uses Slack. You configure a webhook in Slack, paste the URL here, and now every new inquiry appears directly in their #customer-support channel.
- **Custom CSS (storefront)**

  - **What this setting does:** Provides a text area where you can add your own custom CSS code to style the forms on your storefront. This is useful for fine-tuning the appearance to perfectly match your brand.
  - **Effect of changing this setting:**
    - *When CSS is entered:* The styles defined here will be applied to your forms, overriding default module styles.
  - **Recommended value:** Use this only if you have specific styling needs beyond the module’s default appearance. Consult a web designer if unsure.
  - **Merchant scenario / example:** You want the form’s submit button to be a specific shade of green that matches your logo. You’d add CSS like `.cfrompro-form button[type="submit"] { background-color: #00FF00; }` here.
- **Minimum question length (characters)**

  - **What this setting does:** Sets the minimum number of characters required for the main “Question” or “Message” field in your forms.
  - **Effect of changing this setting:**
    - *When set to 10:* Customers must type at least 10 characters in the message field to submit the form.
    - *When set to 0 (or very low):* Allows very short messages.
  - **Recommended value:** 10-20 characters to encourage customers to provide enough detail.
  - **Merchant scenario / example:** To avoid vague inquiries like “Hi,” you set this to 15, ensuring customers provide a more descriptive message.
- **Maximum question length (characters)**

  - **What this setting does:** Sets the maximum number of characters allowed for the main “Question” or “Message” field.
  - **Effect of changing this setting:**
    - *When set to 500:* Customers cannot type more than 500 characters in the message field.
  - **Recommended value:** 500-1000 characters, depending on how detailed you expect inquiries to be. Too low might frustrate users, too high might lead to overly long messages.
  - **Merchant scenario / example:** You want to prevent extremely long essays in the contact form, so you set this to 750 characters.
- **Allow image attachment**

  - **What this setting does:** Enables or disables the ability for customers to upload files (like images, PDFs) with their form submission.
  - **Effect of changing this setting:**
    - *When enabled:* A file upload field will appear on your forms.
    - *When disabled:* No file upload option will be available.
  - **Recommended value:** **YES** if customers often need to provide screenshots, order confirmations, or other documents. **NO** if you want to keep forms simple.
  - **Merchant scenario / example:** For a support form, enabling attachments allows customers to send screenshots of issues, which is very helpful.
- **Maximum attachment size (MB)**

  - **What this setting does:** If attachments are allowed, this setting defines the maximum file size (in megabytes) a customer can upload.
  - **Effect of changing this setting:**
    - *When set to 5:* Customers can upload files up to 5MB. Larger files will be rejected.
  - **Recommended value:** 2-5 MB is usually sufficient for most documents and images without overloading your server.
  - **Merchant scenario / example:** You allow attachments but want to prevent huge files, so you set the limit to 3 MB.
- **Success message duration (ms)**

  - **What this setting does:** Controls how long the “Form submitted successfully” message (often a “toast” notification) stays visible to the customer after they submit a form. Measured in milliseconds (1000 ms = 1 second).
  - **Effect of changing this setting:**
    - *When set to 3000:* The success message will disappear after 3 seconds.
    - *When set to 0:* The message might stay indefinitely or disappear immediately (depending on theme/browser).
  - **Recommended value:** 3000-5000 ms (3-5 seconds) is a good balance, giving customers enough time to read it without being intrusive.
  - **Merchant scenario / example:** You want customers to clearly see the confirmation, so you set it to 4000 ms.

### 2.2 Dedicated Admin Screens & Controller Views

The module adds new menu items under **“Advanced Contact Form Pro”** in your PrestaShop Back Office.

#### 2.2.1 Forms Management (Back Office > Advanced Contact Form Pro > Forms)

This screen allows you to create, edit, and manage all your custom contact forms.

- **Screen Name & Menu Location:** **Advanced Contact Form Pro > Forms**
- **Available Actions & Settings:**
  - **List View (Grid):** Displays a table of all your created forms, showing their name, ID, and status.
  - **Add New Form:** Click the “Add new form” button to create a brand new custom form.
  - **Edit Form:** Click the “Edit” icon next to a form in the list to modify its settings.
  - **Delete Form:** Click the “Delete” icon to remove a form.
  - **Form Configuration Fields (when adding/editing):**
    - **Form Name:** A clear internal name for your form (e.g., “Wholesale Inquiry,” “Product Support”).
    - **Shortcode:** A unique code (e.g., `[cfrompro id="1"]`) that you’ll use to embed this specific form into CMS pages or product descriptions.
    - **Form Status:** Enable/Disable the form. Disabled forms won’t appear on the storefront.
    - **Recipient Email(s) for THIS Form:** You can override the global recipient email(s) for this specific form. This is very powerful for routing inquiries.
    - **Autoresponder Email for THIS Form:** Override the global autoresponder email for this form.
    - **Email Title (for shop owner) for THIS Form:** Override the global email subject for notifications from this form.
    - **Custom Fields:** This is where you define the unique fields for *this* form. You can add text inputs, text areas, dropdowns, checkboxes, radio buttons, file uploads, and more. For each custom field, you can set:
      - **Label:** What the customer sees (e.g., “Your Company Name”).
      - **Type:** (Text, Textarea, Select, Checkbox, Radio, File, etc.).
      - **Required:** Is this field mandatory?
      - **Placeholder:** Hint text inside the input field.
      - **Options (for Select, Checkbox, Radio):** Define the choices customers can pick.
      - **Validation Rules:** (e.g., email format, number only).
    - **Floating Trigger Settings:**
      - **Enable Floating Trigger:** Show a floating button on the storefront that opens this form.
      - **Trigger Text:** What text appears on the floating button (e.g., “Contact Us”).
      - **Trigger Position:** Where the button appears (e.g., left, right, bottom-left).
      - **Trigger Icon:** Choose an icon for the button.
      - **Trigger Delay (ms):** How long to wait before the floating button appears (e.g., 2000ms = 2 seconds).
      - **Trigger Color, Text Color, Hover Color:** Customize the button’s appearance.
- **Effect of changes:**
  - Adding/editing a form makes it available for embedding or as a floating trigger.
  - Changes to custom fields directly affect what customers see and fill out on that specific form.
  - Changes to recipient emails route submissions to different departments.
- **Recommended workflow for daily store management:**
  1. Decide what kind of inquiry you want to handle (e.g., “Wholesale Application”).
  2. Go to **Forms** and click “Add new form.”
  3. Give it a clear name.
  4. Add all the specific custom fields you need (e.g., Company Name, VAT ID, Business Type, Expected Order Volume).
  5. Set a specific recipient email if this form should go to a particular team (e.g., `wholesale@yourstore.com`).
  6. Save the form. Note down its shortcode.
  7. Embed the shortcode into a relevant CMS page (e.g., “Wholesale Information”).

#### 2.2.2 Questions Management (Back Office > Advanced Contact Form Pro > Questions)

This screen serves as your inbox for all form submissions.

- **Screen Name & Menu Location:** **Advanced Contact Form Pro > Questions**
- **Available Actions & Settings:**
  - **List View (Grid):** Displays a table of all submitted questions/inquiries.
    - **Columns:** Shows information like Form Name, Customer Name, Email, Topic (if applicable), Submission Date, and Status.
  - **View Question:** Click the “View” icon (magnifying glass) next to an inquiry to see its full details.
    - **Details View:** Shows all the information submitted by the customer, including answers to custom fields, attachments (with download links), and the form it came from.
    - **Reply Section:** Allows you to reply directly to the customer from within the PrestaShop Back Office. This reply will be sent from your store’s default contact email.
    - **Change Status:** You can update the status of an inquiry (e.g., “New,” “In Progress,” “Resolved”).
  - **Delete Question:** Remove an inquiry from the list.
- **Effect of changes:**
  - Viewing a question allows you to process customer inquiries efficiently.
  - Replying from here keeps a record of communication (though the module doesn’t store the full reply history within itself, it sends a standard email).
  - Changing status helps you track the progress of each inquiry.
- **Recommended workflow for daily store management:**
  1. Regularly check this “Questions” section.
  2. For each new inquiry, click “View” to read the details.
  3. If a reply is needed, use the “Reply” feature.
  4. Update the status (e.g., to “In Progress”) to indicate it’s being handled.
  5. Once resolved, change the status to “Resolved.”

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

This file is typically a placeholder or a redirector in PrestaShop modules and doesn’t represent a direct, configurable screen for the merchant. It ensures that if someone tries to access the `controllers/admin` directory directly, they are redirected or a default action is taken, preventing directory listing vulnerabilities. Merchants will not interact with this directly.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Main Configuration** | Template support profile | Classic | Adapts form styling to your theme. |
|  | Autoresponder email | `info@yourstore.com` | Email address for customer confirmations. |
|  | Email title (for shop owner) | New Contact Form Submission | Subject line for your notification emails. |
|  | Recipient email(s) | `contact@yourstore.com` | Where all form submissions are sent (globally). |
|  | BCC for shop notification email | Empty | Hidden copy of notifications for internal tracking. |
|  | GDPR Compliant | YES | Adds mandatory privacy policy consent checkbox. |
|  | Privacy policy page | Your Privacy Policy CMS page | Links the GDPR checkbox to your policy. |
|  | ReCaptcha (v2) | YES | Enables Google reCAPTCHA for spam protection. |
|  | ReCaptcha site key | Your Google Site Key | Public key for reCAPTCHA widget. |
|  | ReCaptcha secret key | Your Google Secret Key | Private key for reCAPTCHA verification. |
|  | Webhook URL (Slack/Discord) | Empty | Sends notifications to Slack/Discord. |
|  | Custom CSS (storefront) | Empty | Add custom styles to your forms. |
|  | Minimum question length (characters) | 10-20 | Minimum characters for the main message field. |
|  | Maximum question length (characters) | 500-1000 | Maximum characters for the main message field. |
|  | Allow image attachment | YES | Enables file uploads on forms. |
|  | Maximum attachment size (MB) | 2-5 | Max size for uploaded files. |
|  | Success message duration (ms) | 3000-5000 | How long the success notification stays visible. |
| **Forms Management** | Form Name | Descriptive Name | Internal name for your custom form. |
|  | Shortcode | Auto-generated `[cfrompro id="X"]` | Code to embed the form. |
|  | Form Status | Enabled | Activates/deactivates the form. |
|  | Recipient Email(s) for THIS Form | Specific email(s) | Overrides global recipient for this form. |
|  | Custom Fields | Varies | Define unique input fields for each form. |
|  | Enable Floating Trigger | NO (or YES for specific forms) | Shows a floating button to open the form. |
|  | Trigger Text | “Contact Us” | Text on the floating button. |
|  | Trigger Position | Right/Left | Placement of the floating button. |
| **Questions Management** | View Question | N/A | Displays full details of a customer inquiry. |
|  | Reply | N/A | Send an email reply to the customer. |
|  | Change Status | New, In Progress, Resolved | Track the handling of inquiries. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My forms don’t look right, or the styling is broken.**
A:

- **Check “Template support profile”:** Go to **Modules > Module Manager > Advanced Contact Form Builder Pro > Configure** and ensure the “Template support profile” matches your current PrestaShop theme (e.g., ‘Classic’ for the default theme).
- **Clear Smarty Cache:** Go to **Advanced Parameters > Performance**, scroll down to “Cache,” and click “Clear cache.” Sometimes old styling files can get stuck.
- **Custom CSS:** If you’ve added custom CSS, double-check it for errors. Temporarily remove it to see if it’s causing the issue.
- **Theme Conflicts:** If the issue persists, your theme might have a conflict. Contact your theme developer or MyPresta.eu support.

**Q: I’m not receiving email notifications when a form is submitted.**
A:

- **Check Recipient Emails:** Go to **Modules > Module Manager > Advanced Contact Form Builder Pro > Configure** and verify the “Recipient email(s)” are correct. Also, check the individual form settings under **Advanced Contact Form Pro > Forms** to see if a specific form overrides the global recipient.
- **Check Spam Folder:** The emails might be going to your spam or junk folder.
- **Server Mail Settings:** Ensure your PrestaShop store’s email settings are correctly configured (**Advanced Parameters > E-mail**). Test sending a regular email from PrestaShop.
- **Hosting Provider:** Your hosting provider might have email sending limits or issues. Check your server logs or contact them.

**Q: reCAPTCHA isn’t working, or forms won’t submit with reCAPTCHA enabled.**
A:

- **Verify Keys:** Double-check your “ReCaptcha site key” and “ReCaptcha secret key” under the module’s main configuration. Ensure there are no typos and they correspond to a reCAPTCHA v2 setup on your Google account.
- **Domain Registration:** Make sure the domain name of your store is correctly registered in your Google reCAPTCHA account.
- **Network Issues:** Temporarily disable reCAPTCHA to see if forms submit. If they do, the issue is definitely with the reCAPTCHA setup or communication with Google’s servers.

**Q: How do I translate the form fields and messages into other languages?**
A:

- **PrestaShop Translation System:** Go to **International > Translations**.
- **Type of Translation:** Select “Installed modules translations.”
- **Select your theme:** Choose your current theme.
- **Select your language:** Choose the language you want to translate.
- **Module:** Select “cfrompro” (the module’s technical name).
- You will then see a list of all translatable strings from the module, including field labels, success messages, and error messages. Translate them and save.

**Q: My floating trigger button isn’t appearing.**
A:

- **Enable Trigger:** Go to **Advanced Contact Form Pro > Forms**, edit the form you want to trigger, and ensure “Enable Floating Trigger” is set to YES.
- **Trigger Delay:** Check the “Trigger Delay (ms)” setting. If it’s a high number, you might just need to wait longer for it to appear.
- **Theme Conflicts:** Some themes might have CSS that hides the button or JavaScript that interferes. Check your browser’s developer console for errors.
- **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The **Advanced Contact Form Builder Pro** module (`cfrompro`) follows a standard PrestaShop MVC (Model-View-Controller) pattern, extending core PrestaShop classes for its functionality. It leverages `ObjectModel` for managing custom forms and submitted questions, uses dedicated Admin Controllers for Back Office management, and integrates with various PrestaShop hooks for front-office display and backend actions. Custom fields are managed through a dedicated class and stored as JSON.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `cfrompro/controllers/front/index.php`
  - **Class Name:** `CfromproIndexModuleFrontController` (likely, based on file name)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This controller is likely responsible for handling the initial display of a form if it’s accessed via a direct URL (though most forms are embedded or opened via AJAX). It might also handle the initial rendering of the floating trigger or the modal containing the form.
- `cfrompro/controllers/front/question.php`
  - **Class Name:** `CfromproQuestionModuleFrontController` (likely)
  - **Parent Class:** `ModuleFrontController`
  - **Responsibility:** This is the core controller for processing form submissions. It receives POST data from the forms, performs validation (including reCAPTCHA, field length, required fields, attachment size), saves the submitted data (question and custom fields) to the database, sends email notifications to the shop owner and autoresponder to the customer, and potentially triggers the webhook. It returns JSON responses for AJAX submissions (e.g., success/error messages).

#### Back-Office Admin Controllers

- `cfrompro/controllers/admin/AdminCfromproForm.php`
  - **Class Name:** `AdminCfromproFormController`
  - **Parent Class:** `ModuleAdminController`
  - **Tab Name:** “Forms” under “Advanced Contact Form Pro”
  - **Managed Entity:** `CfromproForm` (hypothetical `ObjectModel` for forms)
  - **Responsibility:** Manages the CRUD (Create, Read, Update, Delete) operations for custom forms. It defines the list view (grid) for forms and the form structure for adding/editing a form. This controller handles the saving of form settings, including the complex JSON structure for custom fields.
- `cfrompro/controllers/admin/AdminCfromproQuestion.php`
  - **Class Name:** `AdminCfromproQuestionController`
  - **Parent Class:** `ModuleAdminController`
  - **Tab Name:** “Questions” under “Advanced Contact Form Pro”
  - **Managed Entity:** `CfromproQuestion` (hypothetical `ObjectModel` for submitted questions)
  - **Responsibility:** Manages the CRUD operations for submitted questions. It displays the list of inquiries, allows viewing individual question details, and provides functionality to reply to customers and change the status of an inquiry.
- `cfrompro/controllers/admin/index.php`
  - **Class Name:** (None, typically)
  - **Parent Class:** (None, typically)
  - **Responsibility:** This is a standard PrestaShop practice to prevent direct directory listing. It usually contains a simple `header('Location: ../../index.php?controller=AdminHome');` or similar to redirect to the Back Office dashboard. It does not represent a functional controller for the module’s logic.

### 4.3 Core Classes & Models (`classes/`)

- `cfrompro/classes/CfromproCustomFields.php`
  - **Class Name:** `CfromproCustomFields`
  - **Parent Class:** (Likely `ObjectModel` or a custom base class for handling complex data)
  - **Database Table:** (Likely `ps_cfrompro_form` if it stores custom field definitions within the form object, or a separate `ps_cfrompro_custom_field` table if fields are standalone entities). The module dossier indicates `cfrompro_form` and `cfrompro_question` as managed tables, suggesting custom fields are likely serialized within the `cfrompro_form` table.
  - **`$definition` fields:** If it extends `ObjectModel`, it would define fields related to custom field properties (e.g., `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Given the module description, it’s more probable that custom fields are stored as a JSON string within the `cfrompro_form` table, and this class provides helper methods to parse, validate, and render these fields.
  - **Key public methods and business logic:**
    - Methods for adding, editing, and deleting custom field definitions within a form.
    - Methods for rendering custom fields in the front-office template.
    - Methods for validating submitted custom field data.
    - Methods for serializing/deserializing custom field configurations to/from JSON.

### 4.4 JavaScript Assets (`views/js/`)

- `cfrompro/views/cfrompro.js`
  - **Scope:** Front-office.
  - **Responsibility:** This is the main front-office JavaScript file. It likely handles:
    - Displaying and managing the floating trigger button (click events, delays).
    - Opening and closing the form modal/popup.
    - AJAX submission of forms (collecting data, sending to `question.php` controller).
    - Displaying success/error messages (toast notifications).
    - Client-side validation of form fields.
    - Integration with reCAPTCHA v2 (rendering the widget, getting the response token).
    - Dynamic updates based on custom field types (e.g., showing/hiding options for dropdowns).
- `cfrompro/views/js/admin-button-style.js`
  - **Scope:** Back-office (AdminCfromproFormController).
  - **Responsibility:** Provides JavaScript functionality for styling the floating trigger button within the form configuration interface. This might include color pickers, icon previews, and real-time updates to a preview of the button.
- `cfrompro/views/js/admin-form-layout.js`
  - **Scope:** Back-office (AdminCfromproFormController).
  - **Responsibility:** Handles the dynamic layout and management of custom fields within the form creation/editing interface. This would include:
    - Adding new custom fields (dynamically generating HTML for different field types).
    - Reordering fields (drag-and-drop).
    - Editing field properties (label, type, required, options).
    - Removing fields.
    - Serializing the custom field configuration into a JSON string before saving the form.
- `cfrompro/views/js/admin-icon-picker-data.js`
  - **Scope:** Back-office (AdminCfromproFormController).
  - **Responsibility:** Contains the data (e.g., an array of icon classes or SVG paths) used by the icon picker for the floating trigger button.
- `cfrompro/views/js/admin-icon-picker.js`
  - **Scope:** Back-office (AdminCfromproFormController).
  - **Responsibility:** Implements the user interface and logic for selecting an icon for the floating trigger button. It uses the data from `admin-icon-picker-data.js` to display available icons and updates the selected icon in the form.

### 4.5 CSS Stylesheets (`views/css/`)

- `cfrompro/views/cfrompro.css`
  - **Scope:** Front-office customer styling.
  - **Responsibility:** Provides the core styling for the contact forms, floating trigger, modal popups, and success/error messages on the storefront. It defines general layout, typography, colors, and responsiveness.
  - **Key CSS class selectors:** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
- `cfrompro/views/css/admin-button-style.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Styles the elements related to configuring the floating trigger button within the Back Office (e.g., color pickers, icon preview areas).
- `cfrompro/views/css/admin-custom-fields.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Styles the interface for managing custom fields within the form builder (e.g., drag-and-drop handles, field configuration panels).
- `cfrompro/views/css/admin-form-layout.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides general layout and styling for the form creation/editing page in the Back Office.
- `cfrompro/views/css/admin-icon-picker.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Styles the icon selection interface for the floating trigger button.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
  - **Hook:** `displaydashboardZoneTwo` (or similar dashboard hook).
  - **Output:** A block on the PrestaShop dashboard displaying recent form submissions, providing a quick overview for the merchant.

#### Admin templates (`views/templates/admin/`)

- `cfrompro/views/templates/admin/button_style_block.tpl`
  - **Scope:** AdminCfromproFormController (form edit page).
  - **Output:** HTML for the section where the merchant configures the floating trigger button’s appearance (colors, text, icon).
- `cfrompro/views/templates/admin/conversation_reply.tpl`
  - **Scope:** AdminCfromproQuestionController (question view page).
  - **Output:** HTML for the reply form and status update section when viewing a submitted question.
- `cfrompro/views/templates/admin/custom_fields_block.tpl`
  - **Scope:** AdminCfromproFormController (form edit page).
  - **Output:** The main container and controls for adding, editing, and arranging custom fields within a form. This template likely works in conjunction with `admin-form-layout.js`.
- `cfrompro/views/templates/admin/form_layout_block.tpl`
  - **Scope:** AdminCfromproFormController (form edit page).
  - **Output:** General layout structure for the form configuration page, wrapping other blocks like custom fields and button styles.
- `cfrompro/views/templates/admin/question_extras.tpl`
  - **Scope:** AdminCfromproQuestionController (question view page).
  - **Output:** Displays additional details related to a submitted question, such as attachments or specific metadata.
- `cfrompro/views/templates/admin/question_form_profile.tpl`
  - **Scope:** AdminCfromproQuestionController (question view page).
  - **Output:** Displays details about the form from which the question was submitted.
- `cfrompro/views/templates/admin/topic_options_block.tpl`
  - **Scope:** AdminCfromproFormController (form edit page).
  - **Output:** If the module supports predefined topics, this template would render the options for configuring them.

#### Front-office templates (`views/templates/front/` and root `views/`)

- `cfrompro/views/cfrompro-extra-forms.tpl`
  - **Hook:** Likely `displayFooter` or `actionOutputHTMLBefore` for rendering forms that are not embedded directly but appear in modals.
  - **Output:** Contains the HTML structure for forms that are intended to be displayed in a modal window, often triggered by a floating button.
- `cfrompro/views/cfrompro-extra-trigger.tpl`
  - **Hook:** Likely `displayHeader` or `actionOutputHTMLBefore` for rendering the floating trigger button.
  - **Output:** The HTML for the floating button that, when clicked, opens a contact form.
- `cfrompro/views/cfrompro-form-body.tpl`
  - **Scope:** Used by other templates (e.g., `cfrompro-extra-forms.tpl`) or directly when embedding a form via shortcode.
  - **Output:** The core HTML structure for a single contact form, including fields, labels, reCAPTCHA, GDPR checkbox, and submit button. This template is dynamically populated with custom fields.
- `cfrompro/views/classic/cfrompro-extra-forms.tpl`
  - **Scope:** Theme-specific override for `cfrompro-extra-forms.tpl`.
  - **Output:** Same as `cfrompro-extra-forms.tpl` but specifically tailored for the Classic theme’s HTML structure.
- `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
  - **Scope:** Theme-specific override for `cfrompro-extra-trigger.tpl`.
  - **Output:** Same as `cfrompro-extra-trigger.tpl` but specifically tailored for the Classic theme.
- `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
  - **Scope:** Included by `cfrompro-form-body.tpl`.
  - **Output:** Renders the HTML for a single custom field based on its type (text, textarea, select, etc.).
- `cfrompro/views/partials/cfrompro-custom-fields.tpl`
  - **Scope:** Included by `cfrompro-form-body.tpl`.
  - **Output:** Iterates through the custom field definitions for a form and renders each one using `cfrompro-custom-field-single.tpl`.
- `cfrompro/views/partials/cfrompro-field-fragment.tpl`
  - **Scope:** Included by `cfrompro-form-body.tpl` or `cfrompro-custom-field-single.tpl`.
  - **Output:** A reusable fragment of HTML for common field elements like labels, error messages, or wrappers.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_cfrompro_form`: Stores the definitions of each custom contact form created by the module.
  - `id_cfrompro_form`: Primary key.
  - `name`: Internal name of the form.
  - `shortcode`: Unique identifier for embedding.
  - `active`: (boolean) Form status.
  - `recipient_emails`: (text) Overridden recipient emails for this form.
  - `autoresponder_email`: (text) Overridden autoresponder email for this form.
  - `email_title`: (text) Overridden email subject for this form.
  - `custom_fields_json`: (text/JSON) Serialized JSON string containing the definitions of all custom fields for this form (type, label, required, options, validation, etc.).
  - `trigger_enabled`: (boolean) Whether the floating trigger is active for this form.
  - `trigger_text`: (text) Text on the floating trigger.
  - `trigger_position`: (text) Position of the floating trigger.
  - `trigger_icon`: (text) Icon class for the trigger.
  - `trigger_delay_ms`: (int) Delay for trigger appearance.
  - `trigger_color`, `trigger_text_color`, `trigger_hover_color`: (text) Styling for the trigger.
- `ps_cfrompro_question`: Stores each submitted question/inquiry.
  - `id_cfrompro_question`: Primary key.
  - `id_cfrompro_form`: Foreign key to `ps_cfrompro_form`.
  - `customer_name`: Name of the submitting customer.
  - `customer_email`: Email of the submitting customer.
  - `customer_phone`: Phone number (if visible/required).
  - `topic`: Selected topic (if visible/required).
  - `message`: The main question/message content.
  - `submitted_data_json`: (text/JSON) Serialized JSON string containing all submitted custom field values.
  - `attachments`: (text/JSON) Path(s) to uploaded files.
  - `ip_address`: IP address of the submitter.
  - `date_add`: Submission timestamp.
  - `status`: (int/text) Status of the inquiry (e.g., 0=New, 1=In Progress, 2=Resolved).
- `ps_configuration`: Module settings are stored here with keys like `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Before HTML output is sent to the browser. | Injecting floating trigger HTML, modal forms, or custom CSS/JS globally. |
| `displaydashboardZoneTwo` | Renders content in the second zone of the PrestaShop dashboard. | Displaying a summary of recent form submissions in the Back Office. |
| `actionAdminControllerSetMedia` | When an Admin Controller is setting its media (JS/CSS). | Enqueueing Back Office specific JS (`admin-button-style.js`, `admin-form-layout.js`, etc.) and CSS (`admin-button-style.css`, `admin-custom-fields.css`, etc.) for the module’s configuration pages. |
| `displayHeader` | In the `<head>` section of the front-office. | Enqueueing front-office specific JS (`cfrompro.js`) and CSS (`cfrompro.css`), and potentially reCAPTCHA scripts. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the **Advanced Contact Form Builder Pro** module.
