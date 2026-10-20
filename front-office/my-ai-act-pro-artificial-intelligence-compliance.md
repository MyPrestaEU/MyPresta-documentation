---
title: "My AI Act Pro - Artificial Intelligence Compliance - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the My AI Act Pro - Artificial Intelligence Compliance PrestaShop module by MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Artificial Intelligence Compliance - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy My AI Act Pro - Artificial Intelligence Compliance Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Artificial Intelligence Compliance

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.6.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Ensure your server meets PrestaShop’s general requirements for optimal performance.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > My AI Act Pro)

This is the main control panel for your AI Act compliance module. Here you’ll enable features, define global settings, and manage the overall behavior of the AI disclosures.

#### General Settings Tab

- **Enable AI Act Compliance:**

  - **What this setting does:** This is the master switch for the entire module.
  - **Effect of changing this setting:**
    - *When enabled:* All features of the module (badges, banners, logs, etc.) will become active on your store according to their individual settings.
    - *When disabled:* The module will cease to display any AI Act related content on your front office, and its background processes will be paused.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this once you’re ready to go live with your AI Act compliance. If you need to temporarily disable all disclosures for maintenance, turn this off.
- **Display AI Disclosure Badge on Product Pages:**

  - **What this setting does:** Controls whether the AI disclosure badge appears on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The AI badge will be visible on product pages for products marked as AI-generated.
    - *When disabled:* The badge will not show on product pages, even if products are flagged.
  - **Recommended value:** YES
  - **Merchant scenario / example:** This is crucial for direct product transparency. Keep it enabled to inform customers directly on the product they are viewing.
- **Display AI Disclosure Badge on Product Listings:**

  - **What this setting does:** Controls whether the AI disclosure badge appears on category pages, search results, or other product listing views.
  - **Effect of changing this setting:**
    - *When enabled:* A smaller AI badge will appear on product thumbnails in lists.
    - *When disabled:* No badge will appear in product listings.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enabling this provides immediate transparency as customers browse, helping them identify AI-generated content before clicking into a product page.
- **AI Disclosure Badge Position (Product Page):**

  - **What this setting does:** Determines where the AI badge is placed on the product page. Options typically include “Above product image,” “Below product image,” “Near product name,” “In product description,” etc.
  - **Effect of changing this setting:** The badge will move to the selected location on the product page.
  - **Recommended value:** Experiment to find the best fit for your theme, often “Above product image” or “Near product name” for visibility.
  - **Merchant scenario / example:** If your product images are very large, placing the badge “Below product image” might be less intrusive. If you want it immediately noticeable, “Above product image” is better.
- **AI Disclosure Badge Layout:**

  - **What this setting does:** Allows you to choose a pre-defined visual style for the AI badge from the “Layout Studio.”
  - **Effect of changing this setting:** The appearance of the AI badge (icon, text, colors, shape) will change according to the selected layout.
  - **Recommended value:** Select a layout that matches your store’s branding and is clearly visible.
  - **Merchant scenario / example:** You might create a custom layout with your brand colors and a specific icon to ensure the badge looks professional and integrates well.
- **AI Policy Page Link:**

  - **What this setting does:** Allows you to link to a dedicated CMS page or external URL explaining your store’s AI policy.
  - **Effect of changing this setting:** The module will use this URL when linking to your AI policy from badges, banners, or other disclosure elements.
  - **Recommended value:** Create a detailed CMS page (e.g., “Our AI Transparency Policy”) and link it here.
  - **Merchant scenario / example:** This link is crucial for providing comprehensive information to customers who want to learn more about your AI usage.
- **Enable AI Disclosure Banner:**

  - **What this setting does:** Activates a site-wide banner to inform customers about your AI usage.
  - **Effect of changing this setting:**
    - *When enabled:* A banner will appear in the selected hook (e.g., header or footer).
    - *When disabled:* No banner will be displayed.
  - **Recommended value:** YES, especially for initial rollout or if your store uses AI extensively.
  - **Merchant scenario / example:** Use this banner to make a general statement about your store’s AI policy, perhaps linking to your dedicated policy page.
- **AI Disclosure Banner Position (Hook):**

  - **What this setting does:** Selects where the banner will appear (e.g., `displayHeader`, `displayFooter`).
  - **Effect of changing this setting:** The banner will be rendered in the chosen location.
  - **Recommended value:** `displayHeader` for maximum visibility, or `displayFooter` for a less intrusive approach.
  - **Merchant scenario / example:** Placing it in `displayHeader` ensures every visitor sees it immediately upon landing on your site.
- **AI Disclosure Banner Content:**

  - **What this setting does:** Allows you to customize the text and HTML content of the banner.
  - **Effect of changing this setting:** The banner will display your custom message.
  - **Recommended value:** A concise message like “We use AI to enhance your shopping experience. [Learn more]” with a link to your policy page.
  - **Merchant scenario / example:** You can use this to briefly explain your AI usage and direct customers to your full policy.
- **Enable Human Fallback Information:**

  - **What this setting does:** Displays a message indicating human oversight or offering human assistance for AI-generated content.
  - **Effect of changing this setting:**
    - *When enabled:* A configurable message will appear on relevant pages.
    - *When disabled:* No human fallback message will be shown.
  - **Recommended value:** YES, if you want to reassure customers that human review is involved or provide a contact point.
  - **Merchant scenario / example:** If your AI-generated product descriptions are always reviewed by a human editor, you can use this to state “All AI-generated content is reviewed by our team. Contact us if you have questions.”
- **Human Fallback Message:**

  - **What this setting does:** Customizes the text for the human fallback information.
  - **Effect of changing this setting:** The message will be displayed as entered.
  - **Recommended value:** A clear, reassuring message.
  - **Merchant scenario / example:** “Our AI tools are supervised by human experts. For any concerns, please reach out to our customer service.”
- **Enable Audit Log:**

  - **What this setting does:** Records all AI Act related actions and disclosures in a log for compliance purposes.
  - **Effect of changing this setting:**
    - *When enabled:* Every time an AI disclosure is made or a product is flagged, an entry is saved in the module’s audit log.
    - *When disabled:* No audit trail will be kept.
  - **Recommended value:** YES, this is crucial for demonstrating compliance and troubleshooting.
  - **Merchant scenario / example:** If a regulatory body asks for proof of your AI disclosures, the audit log provides a historical record.

#### API & Integrations Tab

- **Enable REST API:**

  - **What this setting does:** Activates a REST API endpoint for external systems to interact with the module (e.g., flagging products as AI-generated).
  - **Effect of changing this setting:**
    - *When enabled:* The API becomes active, allowing programmatic interaction.
    - *When disabled:* The API is inactive.
  - **Recommended value:** NO, unless you have a specific technical need to integrate with external AI tools or systems.
  - **Merchant scenario / example:** If you use an external AI image generation service, you might use the API to automatically flag images as AI-generated in PrestaShop.
- **API Key Management:**

  - **What this setting does:** Allows you to generate and manage API keys for secure access to the module’s REST API.
  - **Effect of changing this setting:** New keys can be created, existing ones revoked, controlling who can access the API.
  - **Recommended value:** Generate a strong, unique key for each integration.
  - **Merchant scenario / example:** Create a specific API key for your AI image generator and another for your AI content writer, revoking them if an integration is no longer needed.
- **Enable Watermark CRON:**

  - **What this setting does:** Activates a scheduled task (CRON job) to automatically apply watermarks to AI-generated images.
  - **Effect of changing this setting:**
    - *When enabled:* The CRON job will run periodically, applying a configurable watermark to flagged images.
    - *When disabled:* No automatic watermarking will occur.
  - **Recommended value:** NO, unless you specifically require watermarking for AI images.
  - **Merchant scenario / example:** If you want a visual indicator directly on the image itself (e.g., a small “AI” logo) for all AI-generated product images, enable this.
- **Watermark Image/Text:**

  - **What this setting does:** Defines the watermark to be applied (e.g., an image file or text string).
  - **Effect of changing this setting:** The CRON job will use this watermark.
  - **Recommended value:** A subtle, clear indicator if used.
  - **Merchant scenario / example:** Upload a small, semi-transparent “AI Generated” image or enter “AI” as text.

#### Shortcodes Tab

- **Shortcode List & Usage:**
  - **What this setting does:** Provides a list of available shortcodes that can be inserted into product descriptions, CMS pages, or other text areas.
  - **Effect of changing this setting:** No direct change, but using these shortcodes in your content will display the corresponding AI disclosure elements.
  - **Recommended value:** Use these shortcodes to embed specific disclosures where global settings might not be enough.
  - **Merchant scenario / example:** You might have a product where only a specific paragraph of the description was AI-generated. You can wrap that paragraph with a shortcode to display a small badge next to it.

### 2.2 Dedicated Admin Screens & Controller Views

#### 2.2.1 AI Act > Bulk Product Management (AdminMyAiActBulkController)

- **Screen Name & Menu Location:** In your PrestaShop Back Office, navigate to **AI Act > Bulk Product Management**.
- **Available Actions & Settings:** This screen provides a powerful grid view to manage the AI Act status of multiple products at once.
  - **Product Listing:** Displays a list of all your products with columns for product name, ID, and most importantly, their AI Act status.
  - **Filters & Search:** Allows you to filter products by various criteria (e.g., category, supplier, AI Act status) to quickly find specific items.
  - **Bulk Actions:**
    - **Mark as AI-Generated:** Select multiple products and apply the “AI-generated” flag to them simultaneously.
    - **Unmark as AI-Generated:** Remove the “AI-generated” flag from selected products.
    - **Apply Specific AI Act Tags:** Assign custom tags or rules (if configured) to multiple products.
- **Effect of changes:**
  - When you mark products as AI-generated, the front-office badges and disclosures will appear for these products according to your module’s general settings.
  - Unmarking products removes these disclosures.
  - Applying tags allows for more granular control over specific disclosure types or messages.
- **Recommended workflow for daily store management:**
  1. After importing new products or generating content with AI, use the filters to quickly locate these products.
  2. Select all relevant products using the checkboxes.
  3. Use the “Mark as AI-Generated” bulk action to apply the flag.
  4. Periodically review products to ensure their AI Act status is accurate.

#### 2.2.2 AI Act > Audit Logs (AdminMyAiActLogsController)

- **Screen Name & Menu Location:** In your PrestaShop Back Office, navigate to **AI Act > Audit Logs**.
- **Available Actions & Settings:** This screen displays a detailed log of all AI Act-related events and disclosures, provided the “Enable Audit Log” setting is active.
  - **Log Entries:** Each entry typically includes:
    - **Timestamp:** When the event occurred.
    - **Action/Event:** What happened (e.g., “Product X flagged as AI,” “AI badge displayed for Product Y”).
    - **User/System:** Who initiated the action (e.g., “Admin User Z,” “CRON Job,” “Front Office Visitor”).
    - **Product ID/Context:** Which product or entity was affected.
    - **Details:** Any additional relevant information.
  - **Filters & Search:** Allows you to filter log entries by date range, event type, or product to investigate specific incidents.
- **Effect of changes:** This screen is for viewing only; you cannot directly make changes here. It serves as a historical record.
- **Recommended workflow for daily store management:**
  1. Regularly review the audit logs, especially after making significant changes to AI Act settings or product data, to ensure everything is working as expected.
  2. In case of a compliance audit or customer inquiry, use this log to retrieve specific disclosure events.

#### 2.2.3 AI Act > Layout Studio (AdminMyAiActLayoutsController - *Inferred from templates and description*)

- **Screen Name & Menu Location:** In your PrestaShop Back Office, navigate to **AI Act > Layout Studio** (or similar, based on module menu structure).
- **Available Actions & Settings:** This screen is where you design and manage the visual appearance of your AI disclosure badges and other elements.
  - **Layout List:** A table showing all existing badge layouts.
  - **Add New Layout / Edit Layout:**
    - **Layout Name:** A descriptive name for your layout.
    - **Badge Type:** Choose between icon-only, text-only, or icon + text.
    - **Icon Picker:** Select from a catalog of icons or upload your own.
    - **Text Content:** Enter the text to display on the badge (e.g., “AI Generated”).
    - **Styling Options:**
      - **Colors:** Background color, text color, icon color.
      - **Borders:** Border style, width, color.
      - **Shadows:** Drop shadow effects.
      - **Gradients:** Background gradient options.
      - **Padding & Margins:** Spacing around the badge.
      - **Font Settings:** Font size, weight.
    - **Preview:** A live preview of your badge as you design it.
- **Effect of changes:**
  - Creating new layouts gives you more options for how your AI disclosures look.
  - Editing an existing layout will immediately update the appearance of all badges using that layout across your store.
- **Recommended workflow for daily store management:**
  1. Start with a default layout and customize it to match your brand’s aesthetic.
  2. Create different layouts for different types of AI disclosures if needed (e.g., one for AI images, another for AI text).
  3. Test layouts on various devices to ensure they are visible and look good.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable AI Act Compliance | YES | Master switch for all module features. |
|  | Display AI Disclosure Badge on Product Pages | YES | Shows badge on product detail pages. |
|  | Display AI Disclosure Badge on Product Listings | YES | Shows badge on category/search pages. |
|  | AI Disclosure Badge Position (Product Page) | *Theme-dependent* | Controls badge placement on product pages. |
|  | AI Disclosure Badge Layout | *Customizable* | Visual style of the AI badge. |
|  | AI Policy Page Link | *Your CMS page URL* | Link to your store’s AI policy. |
|  | Enable AI Disclosure Banner | YES | Activates a site-wide informational banner. |
|  | AI Disclosure Banner Position (Hook) | `displayHeader` | Placement of the banner (e.g., top/bottom of page). |
|  | AI Disclosure Banner Content | *Customizable text/HTML* | Message displayed in the banner. |
|  | Enable Human Fallback Information | YES | Displays message about human oversight. |
|  | Human Fallback Message | *Customizable text* | Content of the human fallback message. |
|  | Enable Audit Log | YES | Records all AI Act related actions for compliance. |
|  | Enable REST API | NO | Activates API for external integrations. |
|  | API Key Management | *N/A* | Generate/manage API keys for secure access. |
|  | Enable Watermark CRON | NO | Automatically watermarks AI-generated images. |
|  | Watermark Image/Text | *N/A* | Defines the watermark content. |
|  | Shortcode List & Usage | *N/A* | Provides shortcodes for granular content disclosure. |
| **AI Act > Bulk Product Management** | Mark as AI-Generated (Bulk Action) | N/A | Flags multiple products as AI-generated. |
|  | Unmark as AI-Generated (Bulk Action) | N/A | Removes AI-generated flag from products. |
|  | Apply Specific AI Act Tags (Bulk Action) | N/A | Assigns custom disclosure tags to products. |
| **AI Act > Audit Logs** | View Log Entries | N/A | Provides a historical record of AI Act events. |
| **AI Act > Layout Studio** | Create/Edit Layouts | N/A | Design custom visual styles for AI badges. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I’ve configured the module, but I don’t see any AI badges or banners on my store. What’s wrong?**
A1:

- **Check Master Switch:** First, ensure “Enable AI Act Compliance” is set to YES in the module’s main configuration.
- **Individual Feature Switches:** Verify that “Display AI Disclosure Badge on Product Pages,” “Display AI Disclosure Badge on Product Listings,” and “Enable AI Disclosure Banner” are also set to YES if you want those features active.
- **Product Status:** For badges to appear, products must be explicitly marked as “AI-generated.” Check this in the product editing page (under a dedicated tab) or via “AI Act > Bulk Product Management.”
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache. Sometimes, old content is displayed.
- **Theme Compatibility:** While the module is designed to be compatible, some highly customized themes might require minor adjustments. Check your browser’s developer console for JavaScript errors.

**Q2: The AI badge appears, but it doesn’t look good with my theme’s design. How can I change its appearance?**
A2:

- **Layout Studio:** Navigate to **AI Act > Layout Studio** in your Back Office. Here you can create and edit badge layouts. You have extensive options for colors, icons, text, shadows, and gradients.
- **Select Layout:** After creating or editing a layout, go back to the module’s main configuration and select your desired layout under “AI Disclosure Badge Layout.”
- **CSS Overrides (Advanced):** If the Layout Studio doesn’t offer enough customization, a webmaster can use custom CSS in your theme to override the module’s default styles (see Section 7.5 for CSS file locations).

**Q3: How do I mark products as AI-generated efficiently, especially if I have many?**
A3:

- **Bulk Product Management:** Go to **AI Act > Bulk Product Management**. This screen allows you to filter your products and select multiple items to mark or unmark them as AI-generated in one go. This is the most efficient method for large catalogs.
- **Individual Product Page:** For single products, you will find a dedicated tab (e.g., “AI Act Compliance”) when editing a product in the Back Office, where you can toggle its AI status.

**Q4: I want to provide a detailed explanation of my AI policy. Where should I put it?**
A4:

- **Dedicated CMS Page:** Create a new CMS page (Design > Pages) titled something like “Our AI Transparency Policy” or “How We Use AI.” Write your comprehensive policy here.
- **Link in Module:** In the module’s main configuration, set the “AI Policy Page Link” to the URL of your newly created CMS page. This link will then be used by banners and badges to direct customers to your policy.

**Q5: The CRON job for watermarking isn’t working. What should I check?**
A5:

- **Enable Watermark CRON:** Ensure “Enable Watermark CRON” is set to YES in the module’s configuration.
- **CRON Job Setup:** Verify that the CRON job itself is correctly set up on your server. The module usually provides the exact command line to add to your hosting panel’s CRON manager. If you’re unsure, contact your hosting provider or a webmaster.
- **Permissions:** Ensure the module and image folders have correct write permissions.
- **Error Logs:** Check your server’s PHP error logs and PrestaShop’s debug mode for any related errors.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “My AI Act Pro” module follows PrestaShop’s standard MVC (Model-View-Controller) architecture. It leverages `ObjectModel` for database interactions, registers various hooks for front-office display, and includes dedicated admin controllers for configuration and data management. The module introduces several custom classes to encapsulate specific business logic related to AI Act compliance, such as API handling, badge layout management, and audit logging. It also includes front controllers for API and CRON job execution, allowing for external integrations and scheduled tasks.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/api.php`
  - **Class name & parent class:** `MyaiactproApiModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller handles the module’s REST API endpoints. It processes incoming requests (e.g., to flag products as AI-generated, retrieve AI status) and returns JSON responses. It’s responsible for API key validation and dispatching requests to the appropriate `AiActApi` class methods.
- `controllers/front/cron.php`
  - **Class name & parent class:** `MyaiactproCronModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller serves as the endpoint for the module’s CRON jobs, specifically for the watermark application. When accessed via a scheduled task, it triggers the watermarking process for AI-generated images.
- `controllers/front/index.php`
  - **Class name & parent class:** `MyaiactproIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** A placeholder or default front controller. In many modules, this might handle a default route or redirect. For this module, it might be a fallback or used for specific, simple front-office interactions not covered by `api.php` or `cron.php`.

#### Back-Office Admin Controllers

- `controllers/admin/AdminMyAiActBulkController.php`
  - **Class name & parent class:** `AdminMyAiActBulkController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Accessible via **AI Act > Bulk Product Management**. Manages the `product` entity indirectly by allowing bulk updates to their AI Act status.
  - **Responsibility:** Provides a grid interface for listing products and applying bulk actions related to AI Act compliance (e.g., marking products as AI-generated, applying tags). It handles form submissions for bulk updates.
- `controllers/admin/AdminMyAiActLogsController.php`
  - **Class name & parent class:** `AdminMyAiActLogsController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Accessible via **AI Act > Audit Logs**. Manages the `aiact_audit_log` entity.
  - **Responsibility:** Displays a paginated list of audit log entries, providing a historical record of AI Act related events. It handles filtering and viewing log details.
- `controllers/admin/index.php`
  - **Class name & parent class:** `MyaiactproAdminIndexModuleAdminController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Typically a default or introductory admin controller for the module’s main menu entry.
  - **Responsibility:** May serve as a redirect to the main configuration or a dashboard for the module.

### 4.3 Core Classes & Models (`classes/`)

- `classes/AiActApi.php`
  - **Database table:** No direct table interaction, but interacts with `AiActApiKey` and `AiActAuditLog`.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Handles API request parsing, authentication, and dispatches actions to update product AI status.
- `classes/AiActApiDocumentation.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Generates and provides documentation for the module’s REST API, typically for display in the Back Office.
- `classes/AiActApiKey.php`
  - **Database table:** `ps_myaiactpro_api_key`
  - **Extends `ObjectModel`:** Yes.
  - **`$definition` fields:** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
  - **Key public methods:** Manages the creation, retrieval, validation, and deletion of API keys for secure API access.
- `classes/AiActAuditLog.php`
  - **Database table:** `ps_myaiactpro_audit_log`
  - **Extends `ObjectModel`:** Yes.
  - **`$definition` fields:** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
  - **Key public methods:** Records and retrieves audit log entries for AI Act compliance actions.
- `classes/AiActBadgeLayout.php`
  - **Database table:** `ps_myaiactpro_badge_layout`
  - **Extends `ObjectModel`:** Yes.
  - **`$definition` fields:** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
  - **Key public methods:** Manages the creation, storage, and retrieval of custom visual layouts for AI disclosure badges.
- `classes/AiActConfigureUi.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Helper class for building and rendering the module’s configuration forms in the Back Office, abstracting UI elements.
- `classes/AiActDisplayResolver.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Determines which AI Act disclosures (badges, banners, etc.) should be displayed on the front office based on module settings, product status, and current context.
- `classes/AiActFlag.php`
  - **Database table:** `ps_myaiactpro_product_flag` (or similar, linking products to AI status)
  - **Extends `ObjectModel`:** Yes (likely, or a custom class managing product-AI status relationships).
  - **`$definition` fields:** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
  - **Key public methods:** Manages the AI-generated status of individual products and their associated badge layouts.
- `classes/AiActIconCatalog.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Provides a list or catalog of available icons for use in badge layouts, often integrating with Font Awesome or similar icon libraries.
- `classes/AiActShortcode.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Processes and renders custom shortcodes embedded in content, replacing them with AI disclosure elements.
- `classes/AiActTagRule.php`
  - **Database table:** `ps_myaiactpro_tag_rule` (or similar for custom tags/rules)
  - **Extends `ObjectModel`:** Yes.
  - **`$definition` fields:** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
  - **Key public methods:** Manages custom rules or tags that can be applied to products for more specific AI disclosures beyond a simple “AI-generated” flag.
- `classes/index.php`
  - **Database table:** None.
  - **Extends `ObjectModel`:** No.
  - **Key public methods:** Typically an empty file to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Scope:** Back-office (likely for product search in bulk management).
  - **Description:** Provides autocomplete functionality for input fields, typically used in admin forms for searching products, categories, or other entities.
- `views/js/admin_api.js`
  - **Scope:** Back-office (API & Integrations tab).
  - **Description:** Handles client-side interactions for the API key management interface, including generating new keys, revoking keys, and displaying API documentation modals.
- `views/js/admin_icon_picker.js`
  - **Scope:** Back-office (Layout Studio).
  - **Description:** Manages the icon selection interface within the Layout Studio, allowing administrators to browse and select icons for badges.
- `views/js/admin_layouts.js`
  - **Scope:** Back-office (Layout Studio).
  - **Description:** Powers the Layout Studio interface, handling real-time preview updates, style adjustments (colors, shadows, gradients), and form submissions for badge layouts.
- `views/js/front.js`
  - **Scope:** Front-office.
  - **Description:** Contains client-side logic for displaying and interacting with AI disclosure elements on the front office. This might include:
    - Initializing badge tooltips or popovers.
    - Handling click events on badges to reveal more information or navigate to the AI policy page.
    - Ensuring mobile responsiveness of disclosure elements.
- `views/js/tinymce_ai_button.js`
  - **Scope:** Back-office (Product/CMS editor).
  - **Description:** Integrates a custom button into the TinyMCE editor (used for product descriptions and CMS pages) to easily insert AI Act shortcodes.

### 4.5 CSS Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Scope:** Back-office.
  - **Description:** Styles for the autocomplete search input fields and their dropdown results, used in admin forms.
- `views/css/admin.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Contains general styling rules for the module’s Back Office interfaces, including the configuration page, bulk management, audit logs, and layout studio. Developers can override classes like `.myaiactpro-admin-form`, `.myaiactpro-layout-preview`, etc.
- `views/css/front.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Provides the default styling for AI disclosure badges, banners, and other front-office elements. Key CSS class selectors developers can override in their theme include:
    - `.myaiactpro-badge` (for the main badge container)
    - `.myaiactpro-badge-icon` (for the icon within the badge)
    - `.myaiactpro-badge-text` (for the text within the badge)
    - `.myaiactpro-banner` (for the site-wide disclosure banner)
    - `.myaiactpro-additional-info` (for additional info blocks)
    - `.myaiactpro-human-fallback` (for human fallback messages)

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `hook/additional_info.tpl`
  - **Hook:** Potentially `displayProductExtraContent` or custom hook.
  - **Output:** Renders an additional information block on the product page, often used for detailed AI disclosures or policy links.
- `hook/ai_badge.tpl`
  - **Hook:** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock`, or custom hooks.
  - **Output:** Renders the AI disclosure badge on product pages or listings, using the selected layout.
- `hook/banner.tpl`
  - **Hook:** `displayHeader`, `displayFooter`.
  - **Output:** Renders the site-wide AI disclosure banner.
- `hook/human_fallback.tpl`
  - **Hook:** Potentially `displayProductExtraContent` or custom hook.
  - **Output:** Renders the human fallback message on relevant pages.
- `hook/shortcode_badge.tpl`
  - **Hook:** Rendered dynamically by `AiActShortcode` class.
  - **Output:** Renders a specific AI badge when a shortcode is used in content.

#### Admin templates (`views/templates/admin/`)

- `admin/api.tpl`
  - **Purpose:** Renders the API & Integrations configuration panel, including API key management and documentation.
- `admin/bulk_intro.tpl`
  - **Purpose:** Provides an introductory message or instructions for the bulk product management screen.
- `admin/configure.tpl`
  - **Purpose:** The main configuration template for the module, rendered by `getContent()`, containing general settings, feature toggles, and links to other admin screens.
- `admin/configure_shell.tpl`
  - **Purpose:** A wrapper or shell template for the main configuration page, providing a consistent layout.
- `admin/cron_box.tpl`
  - **Purpose:** Displays information related to the CRON job setup, including the CRON command.
- `admin/layouts_form.tpl`
  - **Purpose:** Renders the form for creating or editing an AI badge layout within the Layout Studio.
- `admin/layouts_list.tpl`
  - **Purpose:** Displays the list of existing AI badge layouts in the Layout Studio.
- `admin/mass_settings.tpl`
  - **Purpose:** Renders the interface for applying mass settings or actions to products, used in the bulk management controller.
- `admin/overrides_entity.tpl`
  - **Purpose:** Likely for managing specific overrides or exceptions for AI Act rules on a per-entity basis (e.g., per category, per manufacturer).
- `admin/overrides_fields.tpl`
  - **Purpose:** Renders form fields for defining override rules.
- `admin/overrides_list.tpl`
  - **Purpose:** Displays a list of configured override rules.
- `admin/partials/gradient_editor.tpl`
  - **Purpose:** A partial template for the gradient color picker/editor used in the Layout Studio.
- `admin/partials/icon_picker.tpl`
  - **Purpose:** A partial template for the icon selection interface used in the Layout Studio.
- `admin/partials/shadow_editor.tpl`
  - **Purpose:** A partial template for the shadow effect editor used in the Layout Studio.
- `admin/product_tab.tpl`
  - **Purpose:** Renders the dedicated “AI Act Compliance” tab content within the PrestaShop product editing page.
- `admin/shortcodes.tpl`
  - **Purpose:** Displays the list of available shortcodes and their usage instructions.
- `admin/_api_documentation_modal.tpl`
  - **Purpose:** Renders the content for a modal popup displaying the API documentation.

#### Front-office templates (`views/templates/front/`)

- None explicitly listed as standalone page templates, indicating front-office content is primarily rendered via hooks.

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_myaiactpro_api_key`: Stores API keys for module’s REST API.
  - `id_myaiactpro_api_key` (PK)
  - `key_value` (VARCHAR)
  - `description` (TEXT)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_audit_log`: Records AI Act related events.
  - `id_myaiactpro_audit_log` (PK)
  - `id_employee` (INT)
  - `id_customer` (INT)
  - `id_product` (INT)
  - `action` (VARCHAR)
  - `details` (TEXT)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
- `ps_myaiactpro_badge_layout`: Stores custom visual layouts for AI badges.
  - `id_myaiactpro_badge_layout` (PK)
  - `name` (VARCHAR)
  - `type` (VARCHAR)
  - `icon_class` (VARCHAR)
  - `text_content` (VARCHAR)
  - `styles_json` (TEXT)
  - `active` (TINYINT)
- `ps_myaiactpro_product_flag`: Links products to their AI-generated status and chosen badge layout.
  - `id_product` (PK, INT)
  - `is_ai_generated` (TINYINT)
  - `id_myaiactpro_badge_layout` (INT, FK to `ps_myaiactpro_badge_layout`)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_tag_rule`: Stores custom AI Act tag rules.
  - `id_myaiactpro_tag_rule` (PK)
  - `name` (VARCHAR)
  - `description` (TEXT)
  - `badge_layout_id` (INT, FK to `ps_myaiactpro_badge_layout`)
  - `active` (TINYINT)
- Configuration records in `ps_configuration`: Module settings are stored here (e.g., `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose | Templates Rendered |
| --- | --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS, render top banner. | `hook/banner.tpl` (if configured) |
| `displayFooter` | At the bottom of every page. | Render bottom banner, inject JS. | `hook/banner.tpl` (if configured) |
| `displayProductAdditionalInfo` | On the product page, usually below description. | Display additional AI disclosure info. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | In product listings, near product name/image. | Display AI badge on product thumbnails. | `hook/ai_badge.tpl` |
| `displayProductButtons` | On product page, near add to cart button. | Display AI badge on product page. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | In the Back Office product editing page. | Add a dedicated tab for AI Act settings. | `admin/product_tab.tpl` |
| `actionProductUpdate` | After a product is updated in the Back Office. | Update AI Act flags/status for the product. | N/A |
| `actionProductDelete` | After a product is deleted. | Clean up associated AI Act data. | N/A |
| `actionFrontControllerSetMedia` | Before front controller renders content. | Register front-office CSS/JS. | N/A |
| `actionAdminControllerSetMedia` | Before admin controller renders content. | Register back-office CSS/JS. | N/A |
| `actionRegisterShortcode` | On module installation/update. | Registers custom shortcodes for content parsing. | N/A |
| `displayBackOfficeHeader` | In the `<head>` section of every admin page. | Inject admin CSS/JS. | N/A |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the “My AI Act Pro - Artificial Intelligence Compliance” module.
