---
title: "Email attachments - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Email attachments PrestaShop module by MyPresta.eu."
sidebar:
  label: "Email attachments - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Email attachments Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/email-attachments/)
>
> ---


# Email attachments

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Email attachments” module offers a straightforward configuration process, primarily through a dedicated administration screen where you manage your attachments and link them to specific email templates.

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

When you first click “Configure” after installation, you’ll be taken to the module’s main configuration page. This page primarily serves as an entry point and may contain general information or a link to the dedicated attachment management screen.

- **What this screen does:** This initial screen provides a brief overview of the module and typically directs you to the main interface for managing email attachments. It might also contain general settings if the module had any, but for this module, the core functionality is managed in a separate admin controller.
- **Effect of changing settings:** Any settings here would affect the module’s general behavior. However, for “Email attachments,” the primary action is to navigate to the dedicated “Email Attachments” management page.
- **Recommended value:** Follow the on-screen instructions, which will usually involve clicking a button or link to proceed to the attachment management area.

### 2.2 Dedicated Admin Screen: Email Attachments (Back Office > Modules > Email Attachments)

This is the main hub for managing all your email attachments. You’ll typically find a new menu item under **Modules** or **Shop Parameters** (depending on your PrestaShop version and module’s design) named “Email Attachments” or similar.

**Menu Location:** Back Office > Modules > Email attachments (or similar, check your admin menu after installation)

#### Overview of the “Email Attachments” Management Screen

This screen will present a list (a “grid” or “table”) of all the email attachments you have configured. From here, you can:

- **Add New Attachment:** Create a new attachment rule.
- **Edit Existing Attachment:** Modify the settings for an attachment you’ve already created.
- **Delete Attachment:** Remove an attachment rule.

#### Adding/Editing an Email Attachment

When you click “Add new attachment” or “Edit” an existing one, you’ll be presented with a form to define the attachment’s properties.

**Form Fields & Options:**

1. **Attachment Name:**

   - **What this setting does:** This is an internal name for your reference in the Back Office. It helps you identify the attachment rule easily.
   - **Effect of changing this setting:** Only changes the label you see in the admin list. It does not affect the file name seen by the customer.
   - **Recommended value:** A descriptive name, e.g., “Welcome Guide PDF”, “Order Confirmation T&C”, “Product Manual for New Orders”.
   - **Merchant scenario:** You have multiple attachments for different purposes; a clear name helps you distinguish them.
2. **Select Email Template(s):**

   - **What this setting does:** This crucial setting determines *which* PrestaShop email(s) this attachment will be added to. You’ll typically see a list of all standard PrestaShop email templates (e.g., `account`, `order_conf`, `shipped`, `contact_form`). You can select one or multiple templates.
   - **Effect of changing this setting:**
     - *When selected:* The attachment will be included in every email sent using the chosen template(s).
     - *When unselected:* The attachment will not be included in emails using that template.
   - **Recommended value:** Select only the relevant email templates. For example, a “Welcome Guide” should only be attached to the `account` (customer account creation) email.
   - **Merchant scenario:** You want to attach a “Returns Policy” PDF to `order_conf` (order confirmation) and `shipped` (shipping notification) emails.
3. **Attachment Type:**

   - **What this setting does:** This defines the source of your attachment file. The module offers different options:
     - **Upload File:** Attach an existing file from your computer.
     - **Generate PDF from CMS Page:** Create a PDF from one of your existing PrestaShop CMS pages.
     - **Create PDF from Rich Text Editor:** Design custom PDF content directly within the module using a visual editor.
   - **Effect of changing this setting:** Determines the next set of options you’ll see for specifying the attachment content.
   - **Recommended value:** Choose the type that best suits your content source.
   - **Merchant scenario:** You have a pre-made “Warranty.pdf” (Upload File), or you want to convert your “About Us” CMS page into a PDF (Generate PDF from CMS Page), or you need to write a custom “Special Offer” PDF (Create PDF from Rich Text Editor).

   **Sub-settings based on Attachment Type:**

   - **If “Upload File” is selected:**

     - **File Upload Field:**
       - **What this setting does:** Allows you to browse your computer and upload a file (e.g., PDF, JPG, DOCX).
       - **Effect of changing this setting:** The selected file will be stored on your server and used as the attachment.
       - **Recommended value:** Upload a file that is not excessively large to avoid email delivery issues. PDFs are generally preferred for documents.
       - **Merchant scenario:** Attaching your company’s “Terms and Conditions” PDF.
   - **If “Generate PDF from CMS Page” is selected:**

     - **Select CMS Page:**
       - **What this setting does:** Provides a dropdown list of all your active PrestaShop CMS pages.
       - **Effect of changing this setting:** The content of the chosen CMS page will be converted into a PDF and attached.
       - **Recommended value:** Select a CMS page with content that is suitable for a PDF document (e.g., “About Us”, “Privacy Policy”).
       - **Merchant scenario:** Automatically attaching your “Returns Policy” CMS page as a PDF to relevant emails.
   - **If “Create PDF from Rich Text Editor” is selected:**

     - **Rich Text Editor (WYSIWYG):**
       - **What this setting does:** A visual editor where you can type and format custom content, add images, links, etc. This content will then be converted into a PDF.
       - **Effect of changing this setting:** The content you create here will form the body of the attached PDF.
       - **Recommended value:** Use this for dynamic or unique content that doesn’t exist as a file or CMS page. Keep the design simple for best PDF conversion results.
       - **Merchant scenario:** Creating a custom “Thank You” message with a discount code as a PDF attachment.
4. **Attachment File Name (as seen by customer):**

   - **What this setting does:** This is the name of the file that the customer will see in their email client when they receive the attachment.
   - **Effect of changing this setting:** Changes how the file appears in the customer’s inbox.
   - **Recommended value:** A clear, descriptive, and professional file name (e.g., `Your-Order-Confirmation.pdf`, `Warranty-Information.pdf`). Include the file extension (e.g., `.pdf`).
   - **Merchant scenario:** You uploaded `my_internal_doc_v2.pdf`, but you want the customer to see `Product-Guide.pdf`.
5. **Active:**

   - **What this setting does:** A simple ON/OFF switch to enable or disable this specific attachment rule.
   - **Effect of changing this setting:**
     - *When enabled:* The attachment rule is active and will be applied to selected emails.
     - *When disabled:* The attachment rule is inactive and will not add files to emails.
   - **Recommended value:** Set to “YES” when you want the attachment to be sent.
   - **Merchant scenario:** You’re testing an attachment and want to temporarily disable it without deleting the configuration.

#### 2.2.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Email Attachments (Admin Controller)** | Attachment Name | Descriptive text | Internal label for easy identification in BO. |
|  | Select Email Template(s) | Specific templates (e.g., `order_conf`) | Determines which emails receive the attachment. |
|  | Attachment Type | Varies (Upload File, CMS Page, Rich Text) | Defines the source of the attachment content. |
|  | *If Upload File:* File Upload Field | N/A | Uploads an existing file from your computer. |
|  | *If Generate PDF from CMS Page:* Select CMS Page | Specific CMS page | Converts chosen CMS page content to PDF. |
|  | *If Create PDF from Rich Text Editor:* Rich Text Editor | Custom content | Creates a PDF from content entered in the editor. |
|  | Attachment File Name | Descriptive filename (e.g., `document.pdf`) | The name customers see in their email client. |
|  | Active | YES | Enables/disables the attachment rule. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My attachments are not being sent, or customers report not receiving them.**

- **A:** First, check if the attachment rule is “Active” in the module’s configuration.
- **A:** Ensure you’ve selected the correct email template(s) for the attachment. Test by triggering one of those emails yourself (e.g., place a test order, create a new customer account).
- **A:** Check your PrestaShop email settings (Shop Parameters > Email) to ensure emails are being sent correctly in general. Try sending a test email from PrestaShop.
- **A:** The attachment file might be too large, causing email providers to reject the email. Try a smaller file size.
- **A:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear Cache).

**Q2: The PDF generated from my CMS page looks strange or has formatting issues.**

- **A:** PDF generation from HTML can sometimes be tricky. Ensure your CMS page content is clean HTML without complex JavaScript or highly dynamic elements.
- **A:** Try simplifying the layout of your CMS page. Avoid overly complex CSS or very wide images that might not fit well on a standard PDF page.
- **A:** If issues persist, consider creating a dedicated PDF file externally and using the “Upload File” option instead.

**Q3: Can I attach different files based on the product ordered or customer group?**

- **A:** This module, in its standard configuration, attaches files to *all* emails of a selected type, regardless of specific product or customer group. For more advanced, conditional attachments, custom development or a more specialized module might be required.

**Q4: How do I translate the content of a PDF created with the Rich Text Editor for different languages?**

- **A:** When using the Rich Text Editor, you should see language tabs (e.g., English, French, Spanish) if your PrestaShop store supports multiple languages. You will need to enter and format the content for each language separately within the editor. The module will then attach the correct language version based on the customer’s selected language.

**Q5: Where are the uploaded files stored on my server?**

- **A:** Uploaded files are typically stored within the module’s directory or a designated upload folder within the module. You generally don’t need to interact with these files directly via FTP, as the module manages them.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters working with the “Email attachments” module.

### 4.1 Architecture Overview

The “Email attachments” module (`mattach`) extends PrestaShop’s core email functionality by overriding the `Mail` class. This allows it to inject custom attachments into outgoing emails without modifying core files directly. It follows a standard PrestaShop MVC pattern for its Back Office management interface, utilizing an `AdminController` to manage `mailfile` entities which represent the attachment configurations. PDF generation is handled internally, either by converting CMS content or rich text editor input.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - This module does **not** contain any dedicated front-office controllers. All its operations are performed in the Back Office or by overriding core classes during email dispatch.
- **Back-Office Admin Controllers**:

  - `mattach/controllers/admin/AdminMailAttachments.php`

    - **Class Name**: `AdminMailAttachmentsController`
    - **Parent Class**: `ModuleAdminController`
    - **Responsibility**: This is the primary controller for managing email attachment rules. It handles the CRUD (Create, Read, Update, Delete) operations for the `mailfile` entity. It displays a list of configured attachments, provides forms for adding/editing them, and manages file uploads, CMS page selection, and rich text editor content for PDF generation. It uses PrestaShop’s `HelperList` for the grid view and `HelperForm` for the add/edit forms.
    - **Managed Table / Entity**: `mailfile` (custom table for module’s data).
    - **Associated Config Keys**: `PS_LANG_DEFAULT` (used for multi-language fields).
  - `mattach/controllers/admin/index.php`

    - **Class Name**: (No explicit class, typically a placeholder or redirect)
    - **Responsibility**: This file is often a security measure (to prevent direct directory listing) or a simple redirect within PrestaShop’s admin structure. It does not contain active controller logic for the module’s functionality.

### 4.3 Core Classes & Models (`classes/`)

- `mattach/override/classes/index.php`

  - **Responsibility**: Standard PrestaShop security file to prevent directory listing.
- `mattach/override/classes/Mail.php`

  - **Class Name**: `Mail` (overrides PrestaShop’s core `Mail` class)
  - **Parent Class**: `MailCore`
  - **Responsibility**: This is the most critical part of the module’s functionality. By overriding the `Mail` class, the module intercepts the `send()` method. Within the overridden `send()` method, it checks if any attachment rules are configured for the specific email template being sent. If matches are found, it retrieves the attachment data (uploaded file path, generated PDF content), creates the necessary `Swift_Attachment` objects, and adds them to the email before it is dispatched. This ensures attachments are seamlessly included in all relevant outgoing emails.
  - **Database Interaction**: Interacts with the module’s custom `mailfile` table to fetch attachment configurations.
  - **Key Public Methods**: Overrides `send()` to inject attachment logic.

### 4.4 JavaScript Assets (`views/js/`)

- `mattach/views/templates/admin/js/mattach.js`
  - **Scope**: Back-office (AdminMailAttachmentsController).
  - **Functionality**: This script likely handles the dynamic behavior of the attachment configuration form. This could include:
    - Showing/hiding specific input fields based on the selected “Attachment Type” (e.g., showing the file upload field only when “Upload File” is chosen).
    - AJAX calls for fetching CMS page lists or other dynamic data.
    - Initialization of the rich text editor (e.g., TinyMCE or CKEditor) for the “Create PDF from Rich Text Editor” option.
    - Client-side validation or UI enhancements for the attachment management interface.

### 4.5 CSS Stylesheets (`views/css/`)

- This module does **not** appear to contain any custom CSS files in the provided inventory. It likely relies on PrestaShop’s default Back Office styling for its configuration forms and lists.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - This module does **not** contain any specific hook templates in the provided inventory. Its front-office impact is solely through email attachments, not visual elements.
- **Admin templates (`views/templates/admin/`)**:

  - `mattach/views/templates/admin/orderstates.tpl`
    - **Purpose**: This template’s name suggests it might be used to display or manage order states in relation to attachments, or perhaps to select order states for conditional attachments (though the module description doesn’t explicitly state this advanced feature). It could be part of the `AdminMailAttachmentsController` form, potentially for selecting which order state changes trigger an email with an attachment.
  - `mattach/lib/searchTool/views/scripts.tpl`
    - **Purpose**: This template likely contains JavaScript or Smarty logic related to a search or filtering tool used within the admin interface, possibly for searching through email templates or CMS pages. It’s a utility template for enhancing the admin UI.
- **Front-office templates (`views/templates/front/`)**:

  - This module does **not** contain any front-office templates.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_mailfile`: This is the primary custom table created by the module to store each email attachment configuration.
    - `id_mailfile`: Primary key.
    - `name`: Internal name of the attachment rule.
    - `file_name`: The actual file name (or generated name) of the attachment.
    - `file_path`: Path to the uploaded file or where the generated PDF is temporarily stored.
    - `file_type`: Type of attachment (e.g., ‘upload’, ‘cms’, ‘editor’).
    - `id_cms`: If `file_type` is ‘cms’, stores the ID of the CMS page.
    - `content`: If `file_type` is ‘editor’, stores the rich text content (multi-language).
    - `mail_templates`: A serialized array or comma-separated string of email template names (e.g., `account`, `order_conf`) to which this attachment applies.
    - `active`: Boolean (0 or 1) indicating if the attachment rule is active.
  - `ps_mailfile_lang`: Companion table for multi-language fields like `content` (if `file_type` is ‘editor’).
    - `id_mailfile`: Foreign key to `ps_mailfile`.
    - `id_lang`: Language ID.
    - `content`: Translated rich text content.
- **Registered Hooks Table**:

  - The module primarily operates by overriding the core `Mail` class, which is a more direct and powerful method than relying solely on hooks for email modification. While it might register some standard hooks for module installation/uninstallation or Back Office menu integration, its core attachment injection logic is in the `Mail` override.
  - **`install()` method**:
    - Registers the module in the Back Office menu.
    - Creates the `ps_mailfile` and `ps_mailfile_lang` database tables.
    - Installs the `Mail` class override.
  - **`uninstall()` method**:
    - Removes the module from the Back Office menu.
    - Drops the `ps_mailfile` and `ps_mailfile_lang` database tables.
    - Uninstalls the `Mail` class override.

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Email attachments” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the module’s functionality and configuration.
