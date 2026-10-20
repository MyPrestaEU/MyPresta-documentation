---
title: "Product expert - Specialist Business Cards - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Product expert - Specialist Business Cards PrestaShop module by MyPresta.eu."
sidebar:
  label: "Product expert - Specialist Business Cards - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product expert - Specialist Business Cards Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/product-expert-specialist-business-cards/)
>
> ---


# Product expert - Specialist Business Cards

## 1. Requirements & Compatibility

To ensure smooth operation of the “Product expert - Specialist Business Cards” module, please review the following requirements:

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions such as cURL, JSON, and OpenSSL are required and typically available on most modern hosting environments. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Product expert - Specialist Business Cards” module offers extensive configuration options across several screens in your PrestaShop Back Office.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > Configure Product expert - Specialist Business Cards)

This is the main configuration screen for general module settings, accessible directly after installation or by clicking “Configure” from the Module Manager.

- **Enable/Disable Module:**

  - **What this setting does:** This is the master switch for the module’s functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module’s features (expert cards, assignments) will be active on your front office.
    - *When disabled:* All module functionality will be hidden from the front office, and expert cards will not appear.
  - **Recommended value:** YES (unless you are temporarily disabling it for maintenance).
  - **Merchant scenario / example:** You might disable it if you’re performing a major theme update and want to ensure no conflicts, then re-enable it once testing is complete.
- **Display Experts On Product Page:**

  - **What this setting does:** Controls whether expert cards are shown on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled:* Experts assigned to products, categories, brands, or suppliers will appear on the relevant product pages.
    - *When disabled:* Experts will not be displayed on product pages, regardless of their assignments.
  - **Recommended value:** YES (this is a core feature of the module).
  - **Merchant scenario / example:** If you only want to use experts for B2B inquiries on a dedicated page and not directly on product listings, you might disable this.
- **Display Experts In Hook:**

  - **What this setting does:** Allows you to select a specific PrestaShop hook where the expert cards will be displayed. Common hooks include `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
  - **Effect of changing this setting:** The expert cards will render in the chosen location on your product pages or other pages where the hook is active.
  - **Recommended value:** `displayProductExtraContent` or `displayProductButtons` are often good choices for product pages, as they are usually prominent. Experiment to find the best fit for your theme.
  - **Merchant scenario / example:** If your theme has a dedicated “extra content” tab or section, `displayProductExtraContent` might be ideal. If you want experts near the “Add to Cart” button, `displayProductButtons` could work.
- **Enable Contact Form:**

  - **What this setting does:** Determines if a contact form is available for customers to message experts directly.
  - **Effect of changing this setting:**
    - *When enabled:* A “Contact Expert” button or link will appear on the expert card, opening a form for customers to send a message.
    - *When disabled:* The contact form option will be removed from expert cards.
  - **Recommended value:** YES (highly recommended for customer engagement).
  - **Merchant scenario / example:** Enabling this allows customers to ask specific questions about a product directly to the expert, leading to more informed purchases.
- **GDPR Compliance for Contact Form:**

  - **What this setting does:** If the contact form is enabled, this setting adds a checkbox for customers to consent to data processing, crucial for GDPR compliance.
  - **Effect of changing this setting:**
    - *When enabled:* A mandatory checkbox will appear on the contact form, requiring customer consent before sending a message.
    - *When disabled:* No GDPR consent checkbox will be shown.
  - **Recommended value:** YES (essential for legal compliance in many regions).
  - **Merchant scenario / example:** Always enable this if your target audience is in the EU or any region with similar data protection laws.
- **Default Expert Card Layout:**

  - **What this setting does:** Allows you to select a predefined or custom layout for how individual expert business cards are displayed. This includes options for photo placement, text alignment, and overall card design.
  - **Effect of changing this setting:** Changes the visual appearance of all expert cards across your store, unless overridden by a specific expert’s settings.
  - **Recommended value:** Choose a layout that best fits your store’s aesthetic. You can preview different options.
  - **Merchant scenario / example:** You might choose a “Modern” layout for a sleek, minimalist store, or a “Classic” layout for a more traditional feel.
- **Default Experts List Layout:**

  - **What this setting does:** Determines how multiple expert cards are arranged when more than one expert is displayed (e.g., in a grid, list, or carousel).
  - **Effect of changing this setting:** Controls the overall presentation of multiple experts on a page.
  - **Recommended value:** “Grid” for a compact display, “Carousel” for space-saving and interactive browsing, or “List” for a more detailed, stacked view.
  - **Merchant scenario / example:** If you have many experts for a category, a “Carousel” can save space. If you only have one or two, a “Grid” might look cleaner.
- **Show Expert Search Tool:**

  - **What this setting does:** Enables a search bar that allows customers to find experts by name or specialty.
  - **Effect of changing this setting:**
    - *When enabled:* A search input field will appear, usually near the expert cards, allowing customers to filter experts.
    - *When disabled:* The expert search tool will not be visible.
  - **Recommended value:** YES (improves usability, especially with many experts).
  - **Merchant scenario / example:** If you have a large team of specialists, enabling the search tool helps customers quickly find the right person.
- **Expert Search Tool Hook:**

  - **What this setting does:** Specifies where the expert search tool will be displayed in your front office.
  - **Effect of changing this setting:** The search bar will appear in the chosen hook location.
  - **Recommended value:** `displayTop` or `displayNav` for global visibility, or `displayLeftColumn`/`displayRightColumn` if you want it alongside other filters.
  - **Merchant scenario / example:** Placing it in `displayTop` makes it easily accessible from any page, similar to a product search.

### 2.2 Dedicated Admin Screen: Experts (Back Office > Product Expert > Experts)

This screen is where you manage individual expert profiles, create new experts, and edit existing ones.

- **Screen Name & Menu Location:** **Product Expert > Experts**
- **Available Actions & Settings:**

  - **Experts List (Grid View):** Displays a table of all your created experts. You can see their name, role, status (active/inactive), and actions like “Edit” or “Delete.”
  - **“Add New Expert” Button:** Clicking this button takes you to a form to create a new expert profile.
  - **Edit/Delete Actions:** For each expert in the list, you can click “Edit” to modify their details or “Delete” to remove them.
  - **Bulk Actions:** Allows you to select multiple experts and perform actions like “Enable,” “Disable,” or “Delete” them simultaneously.
- **Expert Creation/Edit Form:**

  - **Name:** The full name of your expert.
  - **Role/Title:** Their professional title or role (e.g., “Senior Sales Manager,” “Technical Support Specialist,” “Fashion Advisor”).
  - **Short Bio:** A brief description of their expertise or background. This helps customers understand their qualifications.
  - **Photo:** Upload a professional photo of the expert. This is crucial for building trust and personal connection.
  - **Contact Links:**
    - **Email:** Expert’s email address.
    - **Phone:** Expert’s phone number.
    - **WhatsApp:** WhatsApp number (will generate a direct chat link).
    - **LinkedIn:** Link to their LinkedIn profile.
    - **Other Custom Links:** You can add additional custom links with icons (e.g., a link to their personal blog, a specific product portfolio).
  - **Active:** A switch to enable or disable the expert.
    - *When enabled:* The expert will be available for assignment and display.
    - *When disabled:* The expert will not appear on the front office, even if assigned.
  - **Expert Card Layout Override:** Allows you to select a specific card layout for *this individual expert*, overriding the global default set in the module configuration. This is useful for highlighting certain experts or matching their personal brand.
  - **Assignments (Products, Categories, Brands, Suppliers):** This is where you link experts to specific store entities.
    - **Products:** Search and select individual products this expert is associated with.
    - **Categories:** Select categories where this expert’s card should appear on products within those categories.
    - **Brands:** Select specific brands this expert specializes in.
    - **Suppliers:** Select suppliers whose products this expert can advise on.
    - *Effect of changes:* When a customer views a product that matches any of these assignments, the expert’s card will be displayed. If multiple experts are assigned, all relevant experts will be shown according to the list layout.
- **Effect of changes:**

  - Adding a new expert makes them available for assignment to products, categories, etc.
  - Editing an expert updates their displayed information and contact details across the store.
  - Deleting an expert removes them and their assignments from your store.
  - Changing assignments immediately affects which expert cards appear on which product pages.
- **Recommended workflow for daily store management:**

  1. **Create New Experts:** When a new team member joins or a new specialization is needed, create their profile here.
  2. **Assign Experts:** Regularly review your product catalog and assign relevant experts to new products, categories, or brands.
  3. **Update Profiles:** Keep expert photos, bios, and contact details up-to-date.
  4. **Deactivate/Reactivate:** Use the “Active” switch to temporarily hide an expert (e.g., if they are on leave) without deleting their profile.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable/Disable Module | YES | Master switch for module functionality. |
|  | Display Experts On Product Page | YES | Show expert cards on product pages. |
|  | Display Experts In Hook | `displayProductExtraContent` | Choose where expert cards appear on product pages. |
|  | Enable Contact Form | YES | Allow customers to message experts directly. |
|  | GDPR Compliance for Contact Form | YES | Add consent checkbox to contact form. |
|  | Default Expert Card Layout | (Choose based on theme) | Visual style of individual expert cards. |
|  | Default Experts List Layout | Grid / Carousel | How multiple expert cards are arranged. |
|  | Show Expert Search Tool | YES | Enable a search bar for experts. |
|  | Expert Search Tool Hook | `displayTop` / `displayNav` | Where the expert search tool appears. |
| **Product Expert > Experts** | Add New Expert | N/A | Create new expert profiles. |
|  | Edit Expert | N/A | Modify expert details (name, role, bio, photo, contacts). |
|  | Active (Expert Status) | YES | Enable/disable individual expert visibility. |
|  | Expert Card Layout Override | N/A | Override global card layout for a specific expert. |
|  | Assign to Products | N/A | Link expert to specific products. |
|  | Assign to Categories | N/A | Link expert to products within specific categories. |
|  | Assign to Brands | N/A | Link expert to products of specific brands. |
|  | Assign to Suppliers | N/A | Link expert to products from specific suppliers. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

Here are some common questions and troubleshooting tips for store owners using the “Product expert - Specialist Business Cards” module:

**Q1: My expert cards are not showing up on the product page.**

- **A:** First, check if the module is **enabled** in **Modules > Module Manager**.
- **A:** Next, go to the module’s configuration page and ensure “Display Experts On Product Page” is set to **YES**.
- **A:** Verify that you have actually **assigned** an expert to the specific product, its category, brand, or supplier in **Product Expert > Experts > [Edit Expert] > Assignments**.
- **A:** Check the “Active” switch for the individual expert in **Product Expert > Experts**. If they are inactive, they won’t show.
- **A:** Clear your PrestaShop cache: Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right. Sometimes, old cached content prevents new module elements from appearing.

**Q2: The expert cards look strange or don’t match my theme’s design.**

- **A:** The module provides a “Default Expert Card Layout” and “Default Experts List Layout” in its configuration. Experiment with different options to see which one best integrates with your theme.
- **A:** If you have a custom theme, it might have specific CSS that conflicts with the module’s styling. You might need a web developer to inspect the CSS and make minor adjustments.
- **A:** Ensure your theme is up-to-date. Outdated themes can sometimes cause display issues with newer modules.

**Q3: The contact form isn’t sending emails.**

- **A:** First, ensure “Enable Contact Form” is set to **YES** in the module’s configuration.
- **A:** Verify that the expert’s email address is correctly entered in their profile (**Product Expert > Experts > [Edit Expert]**).
- **A:** Check your PrestaShop email settings (**Advanced Parameters > E-mail**). Send a test email from PrestaShop to ensure your store’s email configuration is working correctly. If PrestaShop can’t send emails, neither can the module.
- **A:** Check your server’s mail logs for any errors. This might require assistance from your hosting provider.

**Q4: How do I translate the module’s text into other languages?**

- **A:** Go to **International > Translations** in your PrestaShop Back Office.
- **A:** Select “Installed modules translations,” choose your theme, and then select the “Product expert - Specialist Business Cards” module.
- **A:** You can then translate all the module’s strings into your desired languages. Remember to save your changes.

**Q5: I want to display experts in a different location than the available hooks.**

- **A:** The module provides a selection of standard PrestaShop hooks. If you need to display experts in a very specific, non-standard location (e.g., inside a custom tab or a unique section of your product page template), this will require custom theme development. A web developer would need to manually call the module’s hook function directly in your theme’s `.tpl` files.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture and codebase of the “Product expert - Specialist Business Cards” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The “Product expert - Specialist Business Cards” module follows a standard PrestaShop MVC (Model-View-Controller) pattern, heavily leveraging `ObjectModel` for data persistence. It introduces custom admin controllers for managing experts and their assignments, and front controllers for AJAX interactions and displaying expert information. The module uses a robust class structure for managing expert card layouts, styles, and presentation logic, allowing for high customizability. It integrates with various PrestaShop hooks to inject its content dynamically into the front office.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class Name:** `ProductexpertAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles AJAX requests from the front office. This typically includes processing the expert contact form submissions, dynamic loading of expert data, or any other interactive elements that require server-side communication without a full page reload. It returns JSON responses.
- `controllers/front/index.php`
  - **Class Name:** `ProductexpertIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** A placeholder or default front controller. In many modules, this might handle a dedicated module page if one exists, or simply redirect if its primary function is via hooks or AJAX. For this module, its primary role is likely minimal, with `ajax.php` handling most front-end interactions.

#### Back-Office Admin Controllers

- `controllers/admin/AdminProductExpertController.php`
  - **Class Name:** `AdminProductExpertController` (extends `ModuleAdminController`)
  - **Tab Name:** “Experts” under the “Product Expert” menu.
  - **Managed Entity:** `ProductExpertExpert` (via `classes/ProductExpertExpert.php`).
  - **Responsibility:** This is the main administration controller for managing individual expert profiles. It handles the listing of experts (using `HelperList`), and the creation/editing forms for experts (using `HelperForm`). It manages the CRUD operations for expert data, including their name, role, bio, photo, contact links, and most importantly, their assignments to products, categories, brands, and suppliers. It also manages the layout overrides for individual expert cards.
- `controllers/admin/index.php`
  - **Class Name:** (No specific class, often a redirect or security measure)
  - **Responsibility:** This file is typically a security measure to prevent direct directory listing or access. It often contains a simple `header('Location: ../../index.php'); exit;` or similar to redirect to the main admin panel. It does not manage a specific entity or form.

### 4.3 Core Classes & Models (`classes/`)

This module has a rich set of classes for managing its complex features, especially around expert card layouts and configurations.

- `classes/ProductExpertExpert.php`
  - **Database Table:** `ps_productexpert_expert`
  - **Extends:** `ObjectModel`
  - **`$definition` fields:** Defines the schema for expert profiles (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Handles multi-language fields if applicable.
  - **Key Public Methods:** Methods for saving, retrieving, and deleting expert data. Includes logic for handling photo uploads and associations.
- `classes/ProductExpertExpertLinks.php`
  - **Database Table:** `ps_productexpert_expert_link`
  - **Extends:** `ObjectModel`
  - **`$definition` fields:** Defines the schema for expert contact links (id\_expert\_link, id\_expert, type, value, icon, position).
  - **Key Public Methods:** Manages the various contact links (email, phone, WhatsApp, LinkedIn, custom) associated with an expert.
- `classes/ProductExpertExpertPhoto.php`
  - **Database Table:** `ps_productexpert_expert_photo`
  - **Extends:** `ObjectModel`
  - **`$definition` fields:** Manages expert photo details (id\_photo, filename, mime\_type, size).
  - **Key Public Methods:** Handles the storage and retrieval of expert profile images.
- `classes/ProductExpertConfig.php`
  - **Database Table:** `ps_configuration` (stores configuration values)
  - **Extends:** (Likely not `ObjectModel`, but a utility class)
  - **Key Public Methods:** Provides static methods for getting and setting module-specific configuration values (e.g., `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
- `classes/ProductExpertResolver.php`
  - **Extends:** (Likely a custom class)
  - **Key Public Methods:** Contains the core logic for determining which experts should be displayed for a given product based on its category, brand, supplier, and direct product assignments. It resolves the expert list for the front office.
- `classes/ProductExpertListPresenter.php`
  - **Extends:** (Likely a custom class)
  - **Key Public Methods:** Responsible for preparing the data of resolved experts into a format suitable for display in the Smarty templates, applying selected list layouts (grid, carousel, list).
- `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
  - **Extends:** (Likely custom classes)
  - **Responsibility:** A complex set of classes dedicated to managing the visual design and structure of expert business cards. This includes defining layout elements, styles, gradients, and handling built-in presets as well as custom layouts saved by the user. This is the core of the “Visual Business Card Designer” functionality.
- `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
  - **Extends:** (Likely custom classes)
  - **Responsibility:** Helper classes for rendering the complex UI elements in the Back Office configuration forms, particularly for the layout studio and general module settings.
- `classes/PeCompatibility.php`
  - **Extends:** (Likely a utility class)
  - **Key Public Methods:** Provides methods to handle compatibility issues across different PrestaShop versions (e.g., differences in hook names, API calls, or deprecated functions).
- `classes/ProductExpertInstallSamples.php`
  - **Extends:** (Likely a utility class)
  - **Key Public Methods:** Contains logic for installing sample data (e.g., sample experts, layouts) during module installation to provide a quick start for merchants.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Front-office.
  - **Description:** Provides autocomplete functionality for the expert search tool, suggesting expert names or specialties as the user types.
- `lib/searchTool/views/pe-searchtool-init.js`
  - **Scope:** Front-office.
  - **Description:** Initializes the expert search tool, binding event listeners to the search input and integrating the autocomplete functionality.
- `views/js/admin-element-editor.js`
  - **Scope:** Back-office.
  - **Description:** Powers the visual editor for individual elements within an expert card layout (e.g., text fields, images, icons). Handles drag-and-drop, resizing, and style property adjustments.
- `views/js/admin-expert-photo.js`
  - **Scope:** Back-office.
  - **Description:** Manages the photo upload and preview functionality for expert profiles in the admin panel.
- `views/js/admin-layout-studio.js`
  - **Scope:** Back-office.
  - **Description:** The main JavaScript for the “Visual Business Card Designer.” It handles the overall layout canvas, element management, saving/loading layouts, and applying styles.
- `views/js/admin-list-layout-studio.js`
  - **Scope:** Back-office.
  - **Description:** Manages the studio for designing how multiple expert cards are displayed (grid, carousel, list), including options for responsiveness and navigation.
- `views/js/front.js`
  - **Scope:** Front-office.
  - **Description:** Contains general front-office JavaScript for the module, including:
    - Event listeners for contact form submission (AJAX calls to `ajax.php`).
    - Logic for displaying and hiding the contact form modal.
    - Initialization of any carousel or slider functionalities for expert lists.
    - General UI enhancements for expert cards.

### 4.5 CSS Stylesheets (`views/css/`)

#### Front-Office CSS

- `lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Front-office.
  - **Description:** Styles for the autocomplete dropdown suggestions in the expert search tool.
- `views/css/front.css`
  - **Scope:** Front-office.
  - **Description:** General front-office styles for the module, including basic layout, typography, and responsiveness for expert cards and lists.
- `views/css/pe-expert-card-front.css`
  - **Scope:** Front-office.
  - **Description:** Specific styling for the individual expert business cards, applying the chosen layout and element styles.
- `views/css/pe-front-contact.css`
  - **Scope:** Front-office.
  - **Description:** Styles for the expert contact form, including modal presentation, input fields, and buttons.
- `views/css/pe-front-experts.css`
  - **Scope:** Front-office.
  - **Description:** Styles for the overall display of multiple experts, such as grid layouts, list layouts, or carousel navigation.

#### Back-Office CSS

- `views/css/admin-config.css`
  - **Scope:** Back-office.
  - **Description:** General styling for the module’s main configuration page in the admin panel.
- `views/css/admin-element-editor.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the visual element editor within the layout studio.
- `views/css/admin-expert-card-studio.css`
  - **Scope:** Back-office.
  - **Description:** Core CSS for the expert card layout studio interface.
- `views/css/admin-expert-photo.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the expert photo upload and preview area in the admin forms.
- `views/css/admin-experts-list.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the list view of experts in `AdminProductExpertController`.
- `views/css/admin-layout-builder.css`
  - **Scope:** Back-office.
  - **Description:** Styles related to the layout building components.
- `views/css/admin-layout-studio.css`
  - **Scope:** Back-office.
  - **Description:** Overarching styles for the layout studio interface.
- `views/css/admin-list-layout-studio.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the list layout studio interface.
- `views/css/admin-pe-overrides.css`
  - **Scope:** Back-office.
  - **Description:** Specific CSS overrides or adjustments for PrestaShop’s default admin styles to ensure module UI consistency.
- `views/css/admin-searchtool.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the search tool within the admin panel (if applicable, e.g., for searching products/categories during assignment).

### 4.6 Smarty Template Structure (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`
  - **Scope:** Front-office.
  - **Description:** Likely includes the necessary JavaScript and CSS for the search tool, often hooked into `displayHeader` or `displayFooter` to load assets.
- `views/templates/admin/configure.tpl`
  - **Scope:** Back-office.
  - **Description:** The main template for the module’s configuration page (`getContent()` method), rendering the general settings form.
- `views/templates/admin/list-layout.tpl`
  - **Scope:** Back-office.
  - **Description:** Template for the list layout studio in the admin, allowing configuration of how multiple expert cards are displayed.
- `views/templates/admin/product-tab.tpl`
  - **Scope:** Back-office.
    **Description:** This template is likely used to inject a custom tab or section into the PrestaShop product editing page, allowing direct assignment of experts to a product from its edit screen.
- `views/templates/hook/product-experts.tpl`
  - **Scope:** Front-office.
  - **Hook:** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (as configured).
  - **Description:** The primary template responsible for rendering the block of expert cards on the front office. It iterates through the resolved experts and includes `_pe-expert-card-element.tpl` for each.
- `views/templates/hook/_pe-expert-card-element.tpl`
  - **Scope:** Front-office.
  - **Hook:** Included by `product-experts.tpl`.
  - **Description:** Renders a single expert business card, applying the chosen layout and displaying the expert’s photo, name, role, bio, and contact links. It likely includes `_pe-expert-card-row.tpl` for structured content.
- `views/templates/hook/_pe-expert-card-row.tpl`
  - **Scope:** Front-office.
  - **Hook:** Included by `_pe-expert-card-element.tpl`.
  - **Description:** Renders a single row or section within an expert card, used to structure the content elements (e.g., a row for contact icons, a row for name and role).

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_productexpert_expert`: Stores core expert profile information (name, role, bio, photo ID, active status, layout preset).
- `ps_productexpert_expert_lang`: Stores multi-language fields for experts (if any, e.g., bio).
- `ps_productexpert_expert_link`: Stores individual contact links for each expert (type, value, icon).
- `ps_productexpert_expert_photo`: Stores metadata for expert profile images.
- `ps_productexpert_expert_product`: Many-to-many relationship table linking experts to products.
- `ps_productexpert_expert_category`: Many-to-many relationship table linking experts to categories.
- `ps_productexpert_expert_manufacturer`: Many-to-many relationship table linking experts to brands (manufacturers).
- `ps_productexpert_expert_supplier`: Many-to-many relationship table linking experts to suppliers.
- `ps_productexpert_layout_preset`: Stores definitions of custom expert card layouts created by the merchant.
- `ps_productexpert_list_layout`: Stores definitions of custom expert list layouts (grid, carousel, etc.).
- `ps_configuration`: Stores module’s global configuration settings (e.g., `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Load module’s CSS and JS assets for front-office. |
| `displayBackOfficeHeader` | In the `<head>` section of every Back Office page. | Load module’s CSS and JS assets for admin screens. |
| `displayModuleConfigureExtraButtons` | On the module manager page, next to the “Configure” button. | Add quick links to “Manage Experts” or “Layout Studio”. |
| `displayAdminProductsExtra` | On the product edit page in the Back Office. | Inject the expert assignment tab/section for products. |
| `displayProductButtons` | Near the “Add to Cart” button on product pages. | Display expert cards in a prominent product-specific area. |
| `displayProductExtraContent` | In a dedicated section/tab on product pages. | Display expert cards as additional product content. |
| `displayLeftColumn` | In the left sidebar of applicable pages. | Display expert cards or the expert search tool in the left column. |
| `displayRightColumn` | In the right sidebar of applicable pages. | Display expert cards or the expert search tool in the right column. |
| `displayFooter` | In the footer section of all pages. | Display expert cards or a link to an experts page in the footer. |
| `displayTop` | In the top section of the store (header). | Display the expert search tool for global access. |
| `displayNav` | In the navigation bar (often above `displayTop`). | Display the expert search tool for global access. |
| `actionFrontControllerSetMedia` | Before front controller renders, for adding assets. | Dynamically add front-office specific JS/CSS based on context. |
| `actionAdminControllerSetMedia` | Before admin controller renders, for adding assets. | Dynamically add back-office specific JS/CSS based on context. |
| `actionObjectProductAddAfter` | After a new product is added. | Potentially trigger expert assignment logic or cache clearing. |
| `actionObjectProductUpdateAfter` | After a product is updated. | Potentially trigger expert assignment logic or cache clearing. |
| `actionObjectProductDeleteAfter` | After a product is deleted. | Clean up any expert assignments related to the deleted product. |
| `actionObjectCategoryUpdateAfter` | After a category is updated. | Clear cache related to category-based expert assignments. |
| `actionObjectManufacturerUpdateAfter` | After a manufacturer (brand) is updated. | Clear cache related to brand-based expert assignments. |
| `actionObjectSupplierUpdateAfter` | After a supplier is updated. | Clear cache related to supplier-based expert assignments. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official technical support, please refer to your customer account at MyPresta.eu. Our team is dedicated to providing comprehensive assistance and ensuring your module operates smoothly.

- **MyPresta.eu Order History & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support:** Access our support portal through your account for direct assistance.
