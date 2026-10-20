---
title: "Ask about product - contact forms pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Ask about product - contact forms pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Ask about product - contact forms pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Ask about product - contact forms pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Ask about product - contact forms pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required for the module to function correctly, especially for features like reCAPTCHA and webhooks. These are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

This module offers extensive customization options to tailor the contact forms to your specific needs. We’ll go through each configuration screen and setting.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration area for the module, accessed directly after installation or by navigating to **Modules > Module Manager** and clicking “Configure” next to “Ask about product - contact forms pro”.

#### General Settings

- **Template support profile**

  - **What this setting does:** This setting allows you to select a pre-defined template profile that best matches your PrestaShop theme. Different themes might require different styling or structural adjustments for the form to display correctly.
  - **Effect of changing this setting:**
    - *When set to “Classic” (or similar):* The module will use templates and styling optimized for the default PrestaShop Classic theme or themes based on it.
    - *When set to a specific theme profile:* The module will load templates and CSS designed to integrate smoothly with that particular theme, ensuring better visual consistency.
  - **Recommended value:** Choose the profile that corresponds to your active PrestaShop theme. If unsure, start with “Classic” and adjust if styling issues occur.
  - **Merchant scenario / example:** If you’re using a custom theme, you might need to test different profiles or use the “Custom CSS” option to fine-tune the appearance.
- **Email title (for shop owner)**

  - **What this setting does:** This is the subject line for the email notification that *you* (the shop owner/admin) receive when a customer submits a question.
  - **Effect of changing this setting:** Changes the subject line of the internal notification emails.
  - **Recommended value:** Something clear and informative, like “New Product Question from Your Store - [Product Name]”.
  - **Merchant scenario / example:** Setting this to “URGENT: New Inquiry for [Product Name]” can help your team prioritize.
- **Recipient email(s)**

  - **What this setting does:** Specifies the email address(es) where product inquiries will be sent. You can enter multiple emails separated by commas.
  - **Effect of changing this setting:** Determines who in your organization receives the customer questions.
  - **Recommended value:** The email address of your customer service team or relevant department.
  - **Merchant scenario / example:** If you have a dedicated “[sales@yourstore.com](mailto:sales@yourstore.com)” or “[support@yourstore.com](mailto:support@yourstore.com)” address, enter it here. For larger teams, you might send it to a distribution list.
- **BCC for shop notification email**

  - **What this setting does:** Allows you to send a Blind Carbon Copy (BCC) of the shop notification email to additional email addresses. These recipients will not be visible to the primary recipient.
  - **Effect of changing this setting:** Provides a discreet way to notify other team members or archive inquiries without cluttering the primary recipient’s inbox or revealing additional recipients.
  - **Recommended value:** Leave empty unless you have a specific need for internal tracking or secondary notifications.
  - **Merchant scenario / example:** You might BCC your marketing manager to track customer interest, or an internal archive email address.
- **Autoresponder email**

  - **What this setting does:** This is the subject line for the automatic email sent *to the customer* after they submit a question.
  - **Effect of changing this setting:** Changes the subject line of the confirmation email your customers receive.
  - **Recommended value:** “Thank you for your inquiry - [Your Shop Name]”.
  - **Merchant scenario / example:** A clear auto-responder subject assures the customer their message was received.
- **Success message duration (ms)**

  - **What this setting does:** Controls how long the “Your message has been sent successfully” notification stays visible on the screen after a customer submits a form, measured in milliseconds (ms).
  - **Effect of changing this setting:**
    - *Higher value (e.g., 5000ms):* The message stays visible longer, giving customers more time to read it.
    - *Lower value (e.g., 2000ms):* The message disappears quickly.
  - **Recommended value:** 3000-5000ms (3-5 seconds) is usually a good balance.
  - **Merchant scenario / example:** If your customers are often on slower connections or need more time to process information, a longer duration might be beneficial.
- **Hide “Ask a Question” for Out-of-Stock Products (aappro\_HIDE\_OOS)**

  - **What this setting does:** If enabled, the “Ask a Question” form or button will not be displayed on product pages where the product is currently out of stock.
  - **Effect of changing this setting:**
    - *When enabled:* Prevents customers from asking about products that are unavailable, potentially reducing irrelevant inquiries for your team.
    - *When disabled:* The form remains visible regardless of stock status.
  - **Recommended value:** “Yes” to reduce inquiries about unavailable items, unless you specifically want to capture interest for restocks.
  - **Merchant scenario / example:** If you sell unique or limited-edition items that won’t be restocked, hiding the form for OOS products makes sense. If you want to gauge interest for future restocks, keep it disabled.
- **Allow only logged-in customers to ask questions (aappro\_LOGGED\_CUSTOMERS\_ONLY)**

  - **What this setting does:** Restricts the ability to submit product questions only to customers who are logged into their store accounts.
  - **Effect of changing this setting:**
    - *When enabled:* Unregistered or guest users will not see or be able to use the “Ask a Question” form. This can help reduce spam and ensure you have customer account details linked to inquiries.
    - *When disabled:* Anyone can submit a question, including guests.
  - **Recommended value:** “No” for maximum customer reach, “Yes” if you prioritize registered customer engagement and want to reduce anonymous inquiries.
  - **Merchant scenario / example:** If you run a B2B store where all interactions require an account, enabling this would be appropriate. For a general retail store, keeping it disabled is usually better for conversion.

#### Form Fields & Validation

- **Yes / No (aappro\_FIELD\_PHONE\_REQUIRED, aappro\_FIELD\_PHONE\_VISIBLE, aappro\_FIELD\_TOPIC\_VISIBLE, aappro\_QUOTE\_QUANTITY\_VISIBLE)**

  - **What this setting does:** These are a group of “Yes/No” switches that control the visibility and requirement of specific fields within your product inquiry forms:
    - **Phone Number Visible:** Shows the phone number field.
    - **Phone Number Required:** Makes the phone number field mandatory if visible.
    - **Topic Selection Visible:** Shows a dropdown for customers to select a topic for their question (e.g., “Shipping,” “Technical Specs,” “Availability”).
    - **Quote Quantity Visible:** Shows a field where customers can request a quote for a specific quantity of the product.
  - **Effect of changing this setting:**
    - *Enabled (Visible):* The field appears on the form.
    - *Disabled (Visible):* The field is hidden.
    - *Enabled (Required):* The customer *must* fill out the field to submit the form.
  - **Recommended value:**
    - **Phone:** Visible “No”, Required “No” (unless phone contact is critical for your business model).
    - **Topic:** Visible “Yes” (helps categorize inquiries), Required “No”.
    - **Quote Quantity:** Visible “Yes” (if you offer bulk discounts or B2B sales), Required “No”.
  - **Merchant scenario / example:** If you sell complex electronics, making “Topic Selection” visible with options like “Technical Support” or “Compatibility” would be very helpful. If you’re a wholesaler, “Quote Quantity” is essential.
- **Minimum question length (characters)**

  - **What this setting does:** Sets the minimum number of characters a customer must type into the question field before they can submit the form.
  - **Effect of changing this setting:** Prevents very short, potentially unhelpful or spammy questions.
  - **Recommended value:** 10-20 characters.
  - **Merchant scenario / example:** Setting this to 15 characters ensures customers provide enough detail beyond just “Question.”
- **Maximum question length (characters)**

  - **What this setting does:** Sets the maximum number of characters a customer can type into the question field.
  - **Effect of changing this setting:** Prevents excessively long questions that might be difficult to read or indicate a customer trying to use the form as a general chat.
  - **Recommended value:** 500-1000 characters.
  - **Merchant scenario / example:** A limit of 750 characters is usually sufficient for most product inquiries.
- **Allow image attachment**

  - **What this setting does:** Enables customers to upload an image file (e.g., a screenshot, a photo of a damaged item, or a diagram) along with their question.
  - **Effect of changing this setting:**
    - *When enabled:* An “Upload File” field appears on the form.
    - *When disabled:* No attachment option is available.
  - **Recommended value:** “Yes” can be very helpful for visual inquiries, but ensure your server can handle the storage.
  - **Merchant scenario / example:** A customer might want to attach a photo of a specific part of a product they have a question about, or a screenshot of an error they’re encountering.
- **Maximum attachment size (MB)**

  - **What this setting does:** If image attachment is enabled, this sets the maximum file size (in megabytes) allowed for each attachment.
  - **Effect of changing this setting:** Controls server load and storage usage.
  - **Recommended value:** 2-5 MB is usually sufficient for most images.
  - **Merchant scenario / example:** Setting it to 3MB prevents customers from uploading very large, high-resolution images that aren’t necessary for an inquiry.

#### Security & Compliance

- **GDPR Compliant**

  - **What this setting does:** Enables features to help your forms comply with GDPR (General Data Protection Regulation) requirements, typically by adding a checkbox for consent to data processing.
  - **Effect of changing this setting:**
    - *When enabled:* A checkbox will appear on the form, requiring customers to explicitly agree to your privacy policy before submitting their question.
    - *When disabled:* No GDPR consent checkbox is shown.
  - **Recommended value:** “Yes” if your store operates in or serves customers in regions subject to GDPR (e.g., EU).
  - **Merchant scenario / example:** If you sell to customers in Europe, enabling this is legally important.
- **Privacy policy page**

  - **What this setting does:** If GDPR compliance is enabled, this setting allows you to select the CMS page that contains your store’s privacy policy. The GDPR consent checkbox will link to this page.
  - **Effect of changing this setting:** Provides customers with easy access to your privacy policy, fulfilling a key GDPR requirement.
  - **Recommended value:** Select your dedicated Privacy Policy CMS page.
  - **Merchant scenario / example:** After enabling GDPR, you must select the correct CMS page so customers can review your data handling practices.
- **ReCaptcha (v2)**

  - **What this setting does:** Integrates Google reCAPTCHA v2 (the “I’m not a robot” checkbox) into your forms to prevent spam and bot submissions.
  - **Effect of changing this setting:**
    - *When enabled:* The reCAPTCHA checkbox appears on the form, requiring user interaction to prove they are human.
    - *When disabled:* No reCAPTCHA is used.
  - **Recommended value:** “Yes” to significantly reduce spam, especially if you experience a lot of bot submissions.
  - **Merchant scenario / example:** If you’re getting a lot of junk inquiries, enabling reCAPTCHA is a strong defense.
- **ReCaptcha site key**

  - **What this setting does:** This is the public key provided by Google when you register your website for reCAPTCHA. It’s used to display the reCAPTCHA widget on your site.
  - **Effect of changing this setting:** Essential for reCAPTCHA to function. Without it, reCAPTCHA will not appear or work.
  - **Recommended value:** Your unique reCAPTCHA site key from Google.
  - **Merchant scenario / example:** You’ll need to go to the Google reCAPTCHA admin console, register your domain, and copy this key into the module settings.
- **ReCaptcha secret key**

  - **What this setting does:** This is the private key provided by Google, used for server-side verification of the reCAPTCHA response.
  - **Effect of changing this setting:** Essential for reCAPTCHA to function securely. The module uses this key to confirm that the user actually passed the reCAPTCHA challenge.
  - **Recommended value:** Your unique reCAPTCHA secret key from Google.
  - **Merchant scenario / example:** This key should be kept confidential and never exposed in client-side code.

#### Integration & Customization

- **Webhook URL (Slack/Discord)**

  - **What this setting does:** Allows you to send notifications of new product inquiries to a webhook URL, typically used for services like Slack or Discord.
  - **Effect of changing this setting:**
    - *When a URL is provided:* New inquiries will trigger a notification to the specified chat channel.
    - *When empty:* No webhook notifications are sent.
  - **Recommended value:** Leave empty unless you actively use Slack, Discord, or another service that supports incoming webhooks for team communication.
  - **Merchant scenario / example:** Your customer service team uses Slack. You can configure an incoming webhook in Slack and paste its URL here, so every new product question immediately appears in your #customer-support channel.
- **Custom CSS (product page only)**

  - **What this setting does:** Provides a text area where you can add custom CSS rules to style the product inquiry form specifically on product pages.
  - **Effect of changing this setting:** Allows you to override default module styles or your theme’s styles to perfectly match your brand’s aesthetic without modifying module files directly.
  - **Recommended value:** Use sparingly for minor adjustments. For major styling, consider theme overrides.
  - **Merchant scenario / example:** You want to change the button color of the “Send” button to your brand’s primary color, or adjust the spacing around the form fields. You can add `.aappro-form-submit-button { background-color: #FF0000; }` here.
- **Custom Fields (aappro\_CUSTOM\_FIELDS\_JSON)**

  - **What this setting does:** This is a powerful feature that allows you to define additional, custom fields for your contact forms. You can specify field types (text, textarea, select, checkbox), labels, and whether they are required. This is typically managed via a dedicated interface, not a raw JSON field.
  - **Effect of changing this setting:** Adds new input fields to your forms, allowing you to collect more specific information from customers.
  - **Recommended value:** Add fields relevant to your products or services (e.g., “Order Number” for existing customers, “Intended Use” for B2B).
  - **Merchant scenario / example:** For a clothing store, you might add a custom field “Desired Size” if customers often ask about specific sizes not listed. For a tech store, “Current Device Model” could be useful.
- **Allow Comments (aappro\_ALLOW\_COMMENTS)**

  - **What this setting does:** This setting likely controls whether customers can leave general comments on the product page, possibly separate from the specific “Ask a Question” form.
  - **Effect of changing this setting:**
    - *When enabled:* A general comment section might appear.
    - *When disabled:* Only the structured “Ask a Question” form is available.
  - **Recommended value:** “No” if you want to keep communication focused through the structured question form. “Yes” if you want to encourage broader public discussion.
  - **Merchant scenario / example:** If you prefer direct, private inquiries over public comments, disable this.
- **PS\_STOCK\_MANAGEMENT**

  - **What this setting does:** This is a PrestaShop core setting, not directly controlled by the module, but the module might read its value. It determines if stock management is enabled globally in your store.
  - **Effect of changing this setting:** If stock management is disabled, the module’s “Hide for Out-of-Stock Products” setting might not function as expected, as products won’t have a clear stock status.
  - **Recommended value:** “Yes” for most e-commerce stores to accurately track inventory.
  - **Merchant scenario / example:** If you sell digital products, you might disable stock management. However, for physical goods, it’s crucial.
- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

  - **What these settings do:** These are PrestaShop core settings related to language. `PS_LANG_DEFAULT` sets the default front-office language, and `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` allows employees to choose their back-office language. The module uses these to ensure proper language display for forms and notifications.
  - **Effect of changing these settings:** Affects the language of the forms and notifications.
  - **Recommended value:** Set `PS_LANG_DEFAULT` to your primary store language. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` can be enabled if you have a multilingual team.
  - **Merchant scenario / example:** If your store’s primary language is French, ensure `PS_LANG_DEFAULT` is set to French.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config | Template support profile | Your Theme / Classic | Ensures correct styling and integration with your theme. |
| Main Config | Email title (for shop owner) | “New Product Question” | Subject line for internal admin notification emails. |
| Main Config | Recipient email(s) | Your Admin Email | Where customer questions are sent. |
| Main Config | BCC for shop notification email | Empty | Discreetly send copies of notifications to others. |
| Main Config | Autoresponder email | “Thank you for your inquiry” | Subject line for customer confirmation emails. |
| Main Config | Success message duration (ms) | 3000-5000 | How long the “message sent” notification stays visible. |
| Main Config | Hide for Out-of-Stock Products | Yes | Prevents questions on unavailable products. |
| Main Config | Allow only logged-in customers | No | Restricts form access to registered users. |
| Main Config | Phone Number Visible | No | Shows/hides the phone number field. |
| Main Config | Phone Number Required | No | Makes phone number mandatory if visible. |
| Main Config | Topic Selection Visible | Yes | Shows/hides a dropdown for question topics. |
| Main Config | Quote Quantity Visible | Yes (if B2B) | Shows/hides a field for quantity quote requests. |
| Main Config | Minimum question length | 15 characters | Prevents overly short questions. |
| Main Config | Maximum question length | 750 characters | Prevents overly long questions. |
| Main Config | Allow image attachment | Yes | Enables customers to upload files. |
| Main Config | Maximum attachment size (MB) | 3 MB | Limits the size of uploaded files. |
| Main Config | GDPR Compliant | Yes (if applicable) | Adds a consent checkbox for data processing. |
| Main Config | Privacy policy page | Your Privacy Policy CMS | Links the GDPR checkbox to your policy page. |
| Main Config | ReCaptcha (v2) | Yes | Integrates Google reCAPTCHA for spam protection. |
| Main Config | ReCaptcha site key | Your Google Site Key | Public key for reCAPTCHA widget display. |
| Main Config | ReCaptcha secret key | Your Google Secret Key | Private key for reCAPTCHA server-side verification. |
| Main Config | Webhook URL (Slack/Discord) | Empty | Sends notifications to external chat services. |
| Main Config | Custom CSS (product page only) | Empty | Add custom CSS to style the form. |
| Main Config | Custom Fields | Configured via AdminAapproForm | Define additional fields for your forms. |
| Main Config | Allow Comments | No | Controls general product comments vs. structured questions. |

### 2.2 Dedicated Admin Screens & Controller Views

Beyond the main configuration, this module provides dedicated sections in your PrestaShop Back Office to manage forms, questions, and custom fields.

#### 2.2.1 AdminAapproFormController: Form Management (Back Office > Modules > Ask about product > Forms)

This screen allows you to create and manage different product inquiry forms and specify where they appear in your store.

- **Screen Name & Menu Location:** **Modules > Ask about product > Forms**
- **Available Actions & Settings:**
  - **Listing Table:** Displays all your created forms with their names, status, and associated products/categories/manufacturers.
  - **Add New Form Button:** Click to create a new form.
  - **Edit/Delete Actions:** Modify or remove existing forms.
  - **Form Fields:** When adding or editing a form, you’ll configure:
    - **Form Name:** Internal name for your reference.
    - **Active:** Enable or disable the form.
    - **Display on Product Page:** Choose if this form should appear on product pages.
    - **Display on Category Page:** Choose if this form should appear on category pages.
    - **Display on Manufacturer Page:** Choose if this form should appear on manufacturer pages.
    - **Recipient Email(s) for this Form:** Override the global recipient email for this specific form. This is crucial for routing questions to specific teams.
    - **Products:** Select specific products where this form should appear.
    - **Categories:** Select specific categories where this form should appear.
    - **Manufacturers:** Select specific manufacturers where this form should appear.
    - **Custom Fields:** This is where you define the unique fields for *this specific form*. You can add text inputs, text areas, dropdowns, checkboxes, etc., and mark them as required.
- **Effect of changes:**
  - Creating a new form allows you to define a unique set of questions and routing rules.
  - Associating forms with specific products, categories, or manufacturers means that only that particular form will be displayed when a customer views an item matching those criteria.
  - Overriding recipient emails ensures that questions about, for example, “Electronics” go to the electronics department, while “Clothing” questions go to the fashion team.
  - Custom fields allow you to gather highly specific information relevant to the context of the form.
- **Recommended workflow for daily store management:**
  1. **Identify Needs:** Determine if you need different forms for different product types, departments, or customer segments.
  2. **Create Forms:** Go to **Forms** and click “Add New Form.”
  3. **Configure Routing:** Set the specific “Recipient Email(s) for this Form” to ensure questions go to the right place.
  4. **Define Scope:** Use the “Products,” “Categories,” and “Manufacturers” selectors to control where each form appears.
  5. **Add Custom Fields:** Tailor the questions asked on each form using the “Custom Fields” section to gather relevant information.
  6. **Test:** Always test your forms on the front-office to ensure they appear correctly and send emails to the right recipients.

#### 2.2.2 AdminAapproQuestionController: Question Management (Back Office > Modules > Ask about product > Questions)

This screen serves as your central hub for viewing and managing all submitted customer questions.

- **Screen Name & Menu Location:** **Modules > Ask about product > Questions**
- **Managed Table / Entity:** `aappro_question` (stores all submitted inquiries)
- **Form Fields & Columns:**
  - **Grid / Management View:** Displays a list of all submitted questions.
    - **Columns:** Typically includes: Customer Name, Customer Email, Product Name (if applicable), Question Topic, Date Submitted, Status (e.g., New, Replied, Closed).
    - **Filtering & Sorting:** Standard PrestaShop list features to filter by date, customer, product, or status.
  - **View/Reply Action:** Clicking on a question allows you to view its full details and respond to the customer.
    - **Question Details:** Shows the customer’s full message, contact information, product details, and any attachments.
    - **Reply Interface:** A text area to compose your reply, which will be sent directly to the customer’s email address.
    - **Status Update:** Option to change the question’s status (e.g., from “New” to “Replied”).
- **Effect of changes:**
  - This screen provides a centralized inbox for all product-related inquiries, making it easy to track and respond.
  - Replying directly from here ensures that the conversation history is maintained within PrestaShop and linked to the specific product.
  - Updating the status helps your team manage workload and ensures no questions are missed.
- **Recommended workflow for daily store management:**
  1. **Regularly Check:** Make it a habit to check this section daily (or multiple times a day, depending on volume).
  2. **Prioritize:** Use filters to identify urgent or unanswered questions.
  3. **View & Respond:** Click “View” on a question, read the details, and compose a clear, helpful reply.
  4. **Update Status:** After replying, change the question’s status to “Replied” or “Closed” to keep your queue organized.
  5. **Utilize Product Context:** The module automatically links the question to the product, so you have all necessary context when replying.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

This file is a standard PrestaShop practice for preventing direct directory listing in the Back Office. It typically contains a simple `header('Location: ../../index.php?controller=AdminHome');` or similar redirect, ensuring that if someone tries to access the `controllers/admin/` directory directly, they are sent back to the main admin dashboard. It does not manage any specific entity or have configurable fields.

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

- **Q: My form isn’t showing up on the product page.**

  - **A:**
    1. **Check Module Status:** Ensure the module is installed and enabled in **Modules > Module Manager**.
    2. **Check Form Configuration:** Go to **Modules > Ask about product > Forms**. Make sure the specific form you expect to see is “Active” and correctly associated with the product, category, or manufacturer you are viewing.
    3. **Hook Placement:** Verify that the module is hooked into a display area that your theme renders (e.g., `displayProductExtraContent`, `displayProductAdditionalInfo`). Sometimes themes override default hook positions.
    4. **Theme Compatibility:** If you’re using a highly customized theme, try switching to the default Classic theme temporarily to see if the form appears. If it does, there might be a conflict with your custom theme’s template files or CSS.
    5. **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear Cache**).
- **Q: I’m not receiving email notifications when a customer submits a question.**

  - **A:**
    1. **Check Recipient Emails:** Verify the “Recipient email(s)” in the main module configuration and also the specific “Recipient Email(s) for this Form” within the form’s settings (**Modules > Ask about product > Forms > Edit Form**). Ensure they are correct and typo-free.
    2. **Spam Folder:** Check your email’s spam or junk folder.
    3. **Server Mail Settings:** Ensure your PrestaShop store’s email settings are correctly configured (**Advanced Parameters > E-mail**). Send a test email from PrestaShop to confirm your server can send emails.
    4. **Hosting Provider:** Contact your hosting provider to check for any server-side email sending restrictions or issues.
    5. **Module Logs:** Check PrestaShop’s error logs (if available) or your server’s PHP error logs for any mail-related errors.
- **Q: The reCAPTCHA isn’t working or showing up.**

  - **A:**
    1. **Enable reCAPTCHA:** Ensure “ReCaptcha (v2)” is set to “Yes” in the module’s main configuration.
    2. **Keys:** Double-check that your “ReCaptcha site key” and “ReCaptcha secret key” are correctly entered and match the keys from your Google reCAPTCHA account for your domain.
    3. **Domain Registration:** Make sure your domain is correctly registered in your Google reCAPTCHA admin console.
    4. **Browser Issues:** Test in different browsers and clear browser cache. Sometimes ad-blockers can interfere with reCAPTCHA.
- **Q: How do I translate the form fields and messages into other languages?**

  - **A:**
    1. Go to **International > Translations**.
    2. Select “Installed modules translations.”
    3. Choose your theme, the language you want to translate, and then select “Ask about product - contact forms pro” from the module list.
    4. You can then translate all visible strings, field labels, and messages used by the module. Remember to save your changes.
- **Q: The form styling looks off with my custom theme.**

  - **A:**
    1. **Template Support Profile:** Try adjusting the “Template support profile” setting in the module’s main configuration to see if a different profile works better.
    2. **Custom CSS:** Use the “Custom CSS (product page only)” field in the module configuration to add specific CSS rules to override or adjust the styling. You’ll need basic CSS knowledge or a web developer for this.
    3. **Theme Overrides:** For more extensive changes, a developer might need to create theme overrides for the module’s template files (`.tpl`) or CSS files, placing them in your theme’s `modules/aappro/` directory.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Ask about product - contact forms pro” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The module follows a standard PrestaShop MVC (Model-View-Controller) pattern, extending core PrestaShop classes for its functionality. It leverages `ModuleFrontController` for front-office interactions (form submission, replies) and `AdminController` for back-office management of forms and questions. Custom `ObjectModel` classes (`AapproCustomFields`, `AapproFormMatcher`) are used to persist module-specific data. Hooks are extensively used to integrate the form into various parts of the front-office.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/index.php`
  - **Class name & parent class:** `AapproIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** Likely handles the initial rendering of the form or a trigger for the form, potentially via AJAX. It might prepare data for the form template.
- `controllers/front/question.php`
  - **Class name & parent class:** `AapproQuestionModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is responsible for processing the submission of the product inquiry form. It validates input, handles reCAPTCHA verification, processes file uploads (if enabled), saves the question to the database, sends email notifications to the shop owner, and potentially an auto-responder to the customer. It returns JSON responses for AJAX submissions.
- `controllers/front/reply.php`
  - **Class name & parent class:** `AapproReplyModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller likely handles the customer-facing reply mechanism, if the module allows customers to view replies on the front-office or provides a specific link for reply viewing. It would fetch the question and associated replies.

#### Back-Office Admin Controllers

- `controllers/admin/AdminAapproForm.php`
  - **Class name & parent class:** `AdminAapproFormController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Manages custom inquiry forms. Accessible via **Modules > Ask about product > Forms**. It handles the CRUD operations for `AapproFormMatcher` objects, including defining form names, activation status, associated products/categories/manufacturers, and custom fields.
- `controllers/admin/AdminAapproQuestion.php`
  - **Class name & parent class:** `AdminAapproQuestionController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Manages submitted customer questions. Accessible via **Modules > Ask about product > Questions**. It provides a list view of questions, allows viewing full question details, and offers an interface to reply to customers and update question status.
- `controllers/admin/index.php`
  - **Class name & parent class:** Not a functional controller.
  - **Responsibility:** Standard PrestaShop security file to prevent directory listing. It typically redirects to the admin dashboard.

### 4.3 Core Classes & Models (`classes/`)

- `classes/AapproCustomFields.php`
  - **What database table it interacts with:** Likely `ps_aappro_custom_field` (or similar).
  - **Extends ObjectModel:** Yes, it extends `ObjectModel`.
  - **`$definition` fields:** Would define fields such as `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (for select fields, often JSON-encoded), `position`, `active`.
  - **Key public methods and business logic:** Methods for saving, retrieving, and deleting custom field definitions associated with specific forms. Logic for parsing and rendering custom field data.
- `classes/AapproFormMatcher.php`
  - **What database table it interacts with:** Likely `ps_aappro_form` (or similar).
  - **Extends ObjectModel:** Yes, it extends `ObjectModel`.
  - **`$definition` fields:** Would define fields such as `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (JSON-encoded array of product IDs), `categories` (JSON-encoded array of category IDs), `manufacturers` (JSON-encoded array of manufacturer IDs), `display_product`, `display_category`, `display_manufacturer`.
  - **Key public methods and business logic:** Methods for managing form configurations, including saving associations with products/categories/manufacturers, and retrieving the correct form based on the current context (product ID, category ID).

### 4.4 JavaScript Assets (`views/js/`)

- `aappro/lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office.
  - **Description:** Provides autocomplete functionality for selecting products, categories, or manufacturers when configuring forms in `AdminAapproFormController`. Binds to input fields to suggest entities as the user types, improving UX for form association.
- `aappro/views/aappro.js`
  - **Scope:** Front-office.
  - **Description:** Main front-office script for the module.
    - **Event listeners:** Binds click events to “Ask a Question” buttons/links, submit events to the inquiry forms.
    - **DOM manipulation:** Handles showing/hiding the form (e.g., in a modal or expanding section), displaying success/error messages (toast notifications).
    - **AJAX calls:** Submits form data asynchronously to `AapproQuestionModuleFrontController`, handles reCAPTCHA response, and updates the UI based on the server’s JSON response.
    - **Validation:** May include client-side validation for form fields (e.g., min/max length).
- `aappro/views/js/admin-button-style.js`
  - **Scope:** Back-office.
  - **Description:** Likely provides interactive elements or previews for configuring button styles (e.g., color pickers, size sliders) within the module’s configuration or form management screens.
- `aappro/views/js/admin-form-layout.js`
  - **Scope:** Back-office.
  - **Description:** Handles the dynamic layout and interaction for creating/editing forms in `AdminAapproFormController`, especially for managing custom fields. This might include adding/removing custom field rows, reordering fields, and managing field type-specific options.
- `aappro/views/js/admin-icon-picker-data.js`
  - **Scope:** Back-office.
  - **Description:** Contains data (e.g., an array of icon classes or SVG paths) for an icon picker interface used in the back-office, possibly for custom field icons or form display options.
- `aappro/views/js/admin-icon-picker.js`
  - **Scope:** Back-office.
  - **Description:** Implements the icon picker UI logic, allowing administrators to select icons from a predefined set, likely used in conjunction with `admin-icon-picker-data.js`.

### 4.5 CSS Stylesheets (`views/css/`)

- `aappro/lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the autocomplete dropdowns and input fields used in the admin form configuration (e.g., for selecting products/categories).
- `aappro/views/aappro.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Core styling for the product inquiry forms, buttons, modals, success/error messages (toast notifications), and any other front-office elements rendered by the module.
  - **Key CSS class selectors:** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
- `aappro/views/css/admin-button-style.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the button configuration elements within the module’s admin interface.
- `aappro/views/css/admin-custom-fields.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the dynamic custom field management interface in `AdminAapproFormController`, ensuring a clear and usable layout for adding/editing custom fields.
- `aappro/views/css/admin-form-layout.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** General layout and styling for the form creation/editing screens in the admin panel, providing a consistent look and feel.
- `aappro/views/css/admin-icon-picker.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Styles for the icon picker interface used in the admin panel.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `aappro/views/aappro-extra-forms.tpl`
  - **Hook:** `displayProductExtraContent` or similar.
  - **Output:** Renders additional forms or content blocks related to the product, potentially including the inquiry form itself or a trigger for it.
- `aappro/views/aappro-extra-trigger.tpl`
  - **Hook:** `displayProductButtons`, `displayProductAdditionalInfo`.
  - **Output:** Renders a button or link (e.g., “Ask a Question”) that triggers the display of the inquiry form, often in a modal or a hidden section.
- `aappro/views/aappro-extra.tpl`
  - **Hook:** `displayProductExtraContent`, `displayProductAdditionalInfo`.
  - **Output:** A general template for extra content on the product page, potentially wrapping the form or its trigger.
- `aappro/views/aappro-faq-tab-title.tpl`
  - **Hook:** `displayProductTab`.
  - **Output:** Renders the title for a product tab (e.g., “Ask a Question” or “FAQ”) that, when clicked, reveals the form content.
- `aappro/views/aappro-faq-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Output:** Renders the actual content of the product tab, which would be the inquiry form itself.
- `aappro/views/aappro-form-body.tpl`
  - **Hook:** Internal include.
  - **Output:** The core HTML structure for the inquiry form fields (name, email, question, custom fields, reCAPTCHA, GDPR checkbox). This is likely included by other templates.
- `aappro/views/aappro-form-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Output:** Similar to `aappro-faq-tab.tpl`, specifically for rendering the form within a product tab.
- `aappro/views/aappro-product-embed.tpl`
  - **Hook:** `displayProductAdditionalInfo`, `displayReassurance`.
  - **Output:** Embeds the inquiry form directly into the product page content, rather than in a tab or modal.
- `aappro/views/classic/` (and `views/partials/`)
  - These directories contain theme-specific templates (for the Classic theme) and reusable partials. They mirror the structure of the main `views/` directory but are optimized or specifically styled for the Classic theme.
  - `aappro-custom-field-single.tpl`: Renders a single custom field based on its type.
  - `aappro-custom-fields.tpl`: Iterates and renders all custom fields for a form.
  - `aappro-field-fragment.tpl`: A reusable fragment for rendering common form field elements.

#### Admin templates (`views/templates/admin/`)

- `aappro/views/templates/admin/button_style_block.tpl`
  - **Purpose:** Renders the interface for configuring button styles within the admin panel.
- `aappro/views/templates/admin/conversation_reply.tpl`
  - **Purpose:** Renders the reply interface when viewing a customer question in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/custom_fields_block.tpl`
  - **Purpose:** Renders the dynamic interface for adding, editing, and managing custom fields within `AdminAapproFormController`.
- `aappro/views/templates/admin/form_layout_block.tpl`
  - **Purpose:** Renders general layout options for forms in the admin panel.
- `aappro/views/templates/admin/question_extras.tpl`
  - **Purpose:** Displays additional details or actions related to a specific question in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/question_product_preview.tpl`
  - **Purpose:** Renders a small preview of the product associated with a question in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/topic_options_block.tpl`
  - **Purpose:** Renders the configuration interface for defining available topics for the “Topic Selection” dropdown.
- `aappro/views/templates/admin/view_question.tpl`
  - **Purpose:** The main template for displaying a single customer question and its details in `AdminAapproQuestionController`.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_aappro_form`: Stores the definitions of each custom inquiry form created by the merchant.

  - `id_aappro_form` (PK)
  - `name` (VARCHAR)
  - `active` (TINYINT)
  - `recipient_emails` (TEXT)
  - `products` (TEXT, JSON-encoded array of product IDs)
  - `categories` (TEXT, JSON-encoded array of category IDs)
  - `manufacturers` (TEXT, JSON-encoded array of manufacturer IDs)
  - `display_product` (TINYINT)
  - `display_category` (TINYINT)
  - `display_manufacturer` (TINYINT)
- `ps_aappro_custom_field`: Stores the definitions of custom fields associated with each form.

  - `id_aappro_custom_field` (PK)
  - `id_aappro_form` (FK to `ps_aappro_form`)
  - `name` (VARCHAR)
  - `type` (VARCHAR, e.g., ‘text’, ‘textarea’, ‘select’, ‘checkbox’)
  - `label` (TEXT, multi-language)
  - `required` (TINYINT)
  - `options` (TEXT, JSON-encoded for select/radio options)
  - `position` (INT)
  - `active` (TINYINT)
- `ps_aappro_question`: Stores each submitted customer question.

  - `id_aappro_question` (PK)
  - `id_product` (FK to `ps_product`)
  - `id_customer` (FK to `ps_customer`, if logged in)
  - `id_aappro_form` (FK to `ps_aappro_form`)
  - `customer_name` (VARCHAR)
  - `customer_email` (VARCHAR)
  - `customer_phone` (VARCHAR, if enabled)
  - `topic` (VARCHAR, if enabled)
  - `quantity_request` (INT, if enabled)
  - `question_text` (TEXT)
  - `attachment_path` (VARCHAR, if enabled)
  - `custom_fields_data` (TEXT, JSON-encoded array of custom field values)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
  - `status` (VARCHAR, e.g., ‘new’, ‘replied’, ‘closed’)
- `ps_aappro_question_reply`: Stores replies from the admin to customer questions.

  - `id_aappro_question_reply` (PK)
  - `id_aappro_question` (FK to `ps_aappro_question`)
  - `id_employee` (FK to `ps_employee`)
  - `reply_text` (TEXT)
  - `date_add` (DATETIME)
- **Configuration Records (in `ps_configuration` table):**

  - `aappro_TITLE`
  - `aappro_AUTORESPONDER`
  - `aappro_FIELD_PHONE_REQUIRED`
  - `aappro_FIELD_PHONE_VISIBLE`
  - `aappro_FIELD_TOPIC_VISIBLE`
  - `aappro_QUOTE_QUANTITY_VISIBLE`
  - `aappro_WEBHOOK_URL`
  - `aappro_Q_LEN_MIN`
  - `aappro_Q_LEN_MAX`
  - `aappro_ATTACHMENT_ENABLE`
  - `aappro_ATTACHMENT_MAX_MB`
  - `aappro_SHOP_MAIL_BCC`
  - `aappro_TOAST_MS`
  - `aappro_FLOAT_DELAY_MS`
  - `aappro_THEME_SUPPORT`
  - `aappro_CUSTOM_CSS`
  - `aappro_CUSTOM_FIELDS_JSON` (likely deprecated in favor of `ps_aappro_custom_field` table)
  - `aappro_recaptcha`
  - `aappro_GDPR`
  - `aappro_GDPRCMS`
  - `aappro_recaptcha_sitekey`
  - `aappro_ALLOW_COMMENTS`
  - `aappro_recaptcha_secretkey`
  - `aappro_emailslist`
  - `aappro_HIDE_OOS`
  - `aappro_LOGGED_CUSTOMERS_ONLY`

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Registers CSS/JS assets, initializes global JS variables, or renders hidden elements for module functionality. |
| `displayFooter` | At the bottom of every page, before `</body>`. | Can be used to inject modal HTML, floating buttons, or scripts that need to run after page load. |
| `displayProductExtraContent` | In the “extra content” block on product pages (often below description). | Renders the inquiry form or a trigger for it, often as a full block. |
| `displayProductAdditionalInfo` | In the product information block, typically near price/add-to-cart. | Renders a smaller trigger or a compact form directly within the main product info. |
| `displayProductButtons` | Near the “Add to Cart” button. | Renders a button or link to open the inquiry form. |
| `displayProductTab` | For adding a new tab title on the product page. | Renders the “Ask a Question” or “FAQ” tab title. |
| `displayProductTabContent` | For adding content to a new tab on the product page. | Renders the actual inquiry form within its dedicated product tab. |
| `displayReassurance` | In the reassurance block (e.g., “secure payment,” “free shipping”). | Can be used to inject a small “Ask a Question” link or icon within the reassurance block. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media assets are being set. | Registers module-specific CSS and JS for the back-office controllers (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | After an order has been successfully validated. | (Not directly used by this module’s core function, but could be used for follow-up questions post-purchase if extended). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Ask about product - contact forms pro” module, please refer to your customer account at MyPresta.eu. Our support team is available to assist with any technical issues or questions regarding module functionality. Always ensure you are running the latest compatible version of the module for optimal performance and security.
