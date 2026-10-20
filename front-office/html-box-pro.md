---
title: "HTML Box Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the HTML Box Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy HTML Box Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required by PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > HTML Box Pro)

This is the main screen where you manage all your HTML Boxes. The module presents a list of existing boxes and options to add new ones or modify global settings.

#### Global Settings Section

At the top of the configuration page, you’ll find a few global settings that affect how the module operates.

- **Use internal module**

  - **What this setting does:** This is a legacy setting that typically refers to the module’s internal update mechanism.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The module might use its own internal methods for checking updates.
    - *When disabled (“Off”):* The module will rely on standard PrestaShop update mechanisms or manual updates.
  - **Recommended value:** “On” (unless you experience issues, then try “Off”).
  - **Merchant scenario / example:** Generally, leave this on. If you encounter issues with module updates or notifications, your webmaster might suggest toggling this.
- **Prevent removing URLs from images**

  - **What this setting does:** When you use the built-in TinyMCE editor (the rich text editor) to add images, sometimes it can automatically strip out the full URL path, especially if you copy-paste content. This setting prevents that behavior.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* Image URLs you insert into the HTML box content will be preserved exactly as you enter them, preventing broken image links.
    - *When disabled (“Don’t”):* The editor might modify or remove parts of image URLs, potentially leading to images not displaying correctly.
  - **Recommended value:** “On”
  - **Merchant scenario / example:** If you’re adding images from external sources (e.g., a CDN or another website) or even internal images with absolute paths, enabling this ensures your images always show up.
- **Do not load tinyMCE libraries**

  - **What this setting does:** TinyMCE is the rich text editor that allows you to easily format text, add images, and create tables without writing HTML code directly. This setting controls whether the module loads its own version of the TinyMCE editor.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The module will NOT load its TinyMCE editor. This can be useful if your theme or another module already loads TinyMCE, preventing conflicts or duplicate loading. However, you will lose the visual editor for your HTML boxes and will need to write raw HTML.
    - *When disabled (“Off”):* The module will load its TinyMCE editor, providing you with a user-friendly interface to create and edit your HTML box content.
  - **Recommended value:** “Off” (unless you are a developer and prefer to write raw HTML, or if you experience conflicts with other TinyMCE instances).
  - **Merchant scenario / example:** If you want to use the visual editor to easily add text, bold, italics, images, and links without knowing HTML, keep this “Off”. If you’re seeing strange behavior with the editor or console errors, a developer might suggest turning this “On” to troubleshoot.

#### HTML Boxes Management Section

Below the global settings, you’ll find a table listing all your created HTML boxes. From here, you can add new boxes, edit existing ones, or delete them.

- **Add new HTML Box** (Button)

  - **What this does:** Clicking this button takes you to a new form where you can define a brand new HTML box.
  - **Effect:** Opens the “Add New HTML Box” form.
- **Edit** (Icon next to each box)

  - **What this does:** Allows you to modify the settings and content of an existing HTML box.
  - **Effect:** Opens the “Edit HTML Box” form, pre-filled with the box’s current settings.
- **Delete** (Icon next to each box)

  - **What this does:** Permanently removes an HTML box from your store.
  - **Effect:** The HTML box will no longer appear on your front office. This action is irreversible.
  - **Recommended value:** Only delete boxes you no longer need.

#### Add/Edit HTML Box Form

When you click “Add new HTML Box” or “Edit” an existing one, you’ll see a form with the following fields:

- **Name**

  - **What this setting does:** This is an internal name for your HTML box, visible only in the Back Office. It helps you identify different boxes.
  - **Effect of changing this setting:** Changes the label for this box in your module configuration list. No front-office effect.
  - **Recommended value:** A descriptive name (e.g., “Homepage Banner - Summer Sale”, “Product Page Trust Badges”, “Footer Contact Info”).
  - **Merchant scenario / example:** Naming your boxes clearly helps you quickly find and manage them, especially as your store grows and you add more custom content.
- **Shop** (Only visible in multi-store environments)

  - **What this setting does:** If you run multiple stores from a single PrestaShop installation, this allows you to specify which shop(s) this HTML box should appear on.
  - **Effect of changing this setting:** The HTML box will only be displayed on the selected shops.
  - **Recommended value:** Select the specific shops where the content is relevant.
  - **Merchant scenario / example:** You might have a different promotional banner for your French store than for your German store.
- **Position**

  - **What this setting does:** This is the most crucial setting, determining *where* on your store the HTML box will appear. It’s a dropdown list of all available PrestaShop hooks.
  - **Effect of changing this setting:** The content of your HTML box will be rendered in the selected hook’s location.
  - **Recommended value:** Choose the hook that best fits the content’s purpose (e.g., `displayHeader` for a top banner, `displayLeftColumn` for a sidebar block).
  - **Merchant scenario / example:** If you want to add a “Free Shipping” message above your product descriptions, you’d select `displayProductAdditionalInfo`.
- **Active**

  - **What this setting does:** Controls whether the HTML box is currently visible on your store.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The HTML box will be displayed on your front office.
    - *When disabled (“Off”):* The HTML box will be hidden, but its content and settings are saved, allowing you to reactivate it later.
  - **Recommended value:** “On” for active content, “Off” for content you want to temporarily hide or prepare for future use.
  - **Merchant scenario / example:** You can prepare a Christmas promotion box in advance, keep it “Off”, and then switch it to “On” when the time comes, without having to recreate it.
- **Only on secured (SSL) pages**

  - **What this setting does:** Restricts the display of the HTML box to pages that are loaded over HTTPS (secure connection).
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The box will only appear on pages with `https://` in the URL.
    - *When disabled (“Off”):* The box will appear on both secure (HTTPS) and non-secure (HTTP) pages (if your store still uses HTTP, which is not recommended).
  - **Recommended value:** “On” if the content contains sensitive information or if you want to ensure it only loads on secure pages. Generally, all modern stores should be fully HTTPS, so this might not be strictly necessary, but it adds an extra layer of control.
  - **Merchant scenario / example:** If your HTML box contains a payment badge or a security seal, you might want to ensure it only appears on secure pages to reinforce trust.
- **Only on homepage**

  - **What this setting does:** Restricts the display of the HTML box to only your store’s homepage.
  - **Effect of changing this setting:**
    - *When enabled (“On”):* The box will only appear when customers visit your main homepage.
    - *When disabled (“Off”):* The box will appear on all pages where its selected “Position” (hook) is available.
  - **Recommended value:** “Off” unless the content is specifically designed for the homepage.
  - **Merchant scenario / example:** A large promotional banner for a site-wide sale would typically be set to “On” for this option if you only want it on the homepage, or “Off” if you want it to appear in the header on every page.
- **Contents** (This is the main content editor)

  - **What this setting does:** This is where you enter the actual HTML, JavaScript, or CSS code that will be displayed. It uses the TinyMCE rich text editor (if not disabled globally) for easy content creation.
  - **Effect of changing this setting:** The content you enter here will be rendered on your front office in the selected hook.
  - **Recommended value:** Enter your desired content. You can use:
    - Plain text
    - HTML (e.g., `<p>Hello World!</p>`, `<img>` tags, `<a>` links)
    - CSS (wrap in `<style>` tags, e.g., `<style>.my-class { color: red; }</style>`)
    - JavaScript (wrap in `<script>` tags, e.g., `<script>alert('Welcome!');</script>`)
  - **Merchant scenario / example:**
    - *HTML:* Adding a custom banner image: `<img src="https://yourstore.com/img/cms/banner.jpg" alt="Summer Sale" style="width:100%;">`
    - *JavaScript:* Embedding a Google Analytics tracking code: `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
    - *CSS:* Changing the color of a specific element: `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Config Page | Use internal module | On | Controls internal update mechanism. |
| Main Config Page | Prevent removing URLs from images | On | Ensures image URLs are preserved in the editor. |
| Main Config Page | Do not load tinyMCE libraries | Off | Enables the visual editor for easy content creation. |
| Add/Edit Form | Name | Descriptive Name | Internal label for the HTML box. |
| Add/Edit Form | Shop | All Shops | Selects which shops display the content (multi-store). |
| Add/Edit Form | Position | (Choose Hook) | Determines where the content appears on the front office. |
| Add/Edit Form | Active | On | Toggles visibility of the HTML box on the front office. |
| Add/Edit Form | Only on secured (SSL) pages | Off (or On if critical) | Restricts display to HTTPS pages. |
| Add/Edit Form | Only on homepage | Off | Restricts display to the homepage only. |
| Add/Edit Form | Contents | (Your HTML/JS/CSS) | The actual content to be displayed. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My HTML box isn’t showing up on the front office. What should I check?**
A1:

- **Is it Active?** Go to the module configuration and ensure the “Active” switch for your box is set to “On”.
- **Correct Position (Hook)?** Double-check that you’ve selected the correct “Position” (hook) where you expect the content to appear. Some hooks are specific to certain pages (e.g., `displayProductAdditionalInfo` only on product pages).
- **Homepage Only?** If you set “Only on homepage” to “On”, it will only appear on your main homepage.
- **SSL Only?** If “Only on secured (SSL) pages” is “On”, ensure you are viewing an HTTPS page.
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.
- **Content Errors:** If your HTML/JS/CSS content has errors, it might prevent the box from rendering. Try a simple “Hello World” text to test.

**Q2: The TinyMCE editor (visual editor) isn’t working or looks strange.**
A2:

- **“Do not load tinyMCE libraries” setting:** Ensure this is set to “Off” in the module’s global settings if you want to use the visual editor.
- **Theme Conflicts:** Sometimes, custom themes or other modules can interfere with TinyMCE. Try temporarily disabling other modules to see if the issue resolves.
- **Browser Issues:** Try a different browser or clear your browser’s cache and cookies.

**Q3: My images or links are broken after saving the HTML box content.**
A3:

- **“Prevent removing URLs from images” setting:** Make sure this is set to “On” in the module’s global settings.
- **Absolute vs. Relative Paths:** Always use absolute URLs (starting with `http://` or `https://`) for images and links, especially if they are external or if you want them to work consistently across your site.
- **Check the HTML:** Inspect the generated HTML code in the editor (usually a “Source code” button) to ensure your `src` and `href` attributes are correct.

**Q4: How do I translate the content of my HTML boxes for different languages?**
A4:

- HTML Box Pro supports multi-language content. When you are editing an HTML box, you will see language tabs (e.g., English, French, Spanish) next to the “Contents” field.
- Click on each language tab and enter the translated content for that specific language. The module will automatically display the correct language version to your customers based on their selected store language.

**Q5: The content looks good on desktop but is distorted on mobile.**
A5:

- **Responsive Design:** Ensure the HTML content you’re adding is designed to be responsive. Use CSS properties like `max-width: 100%; height: auto;` for images, and consider using CSS media queries within your `<style>` tags for more complex layouts.
- **Theme Responsiveness:** While the module itself is responsive, if your custom HTML isn’t, it might break the layout. Test thoroughly on different devices.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The HTML Box Pro module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `getContent()` for its Back Office configuration. It dynamically registers hooks and renders content based on stored configuration. The module uses a custom `SmartyTemplatesManager` library for managing its Back Office forms and templates, providing a consistent UI for adding and editing HTML boxes. Content is stored in the `ps_configuration` table, with each HTML box represented by a unique configuration key.

### 4.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers in the `controllers/front` or `controllers/admin` directories. All Back Office logic is handled within the `htmlboxpro.php` file’s `getContent()` method, which renders forms and processes submissions. Front-office content rendering is handled directly via hook execution within the main module file.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom `ObjectModel` classes or other core classes in a `classes/` directory. All data management and business logic are encapsulated within the `htmlboxpro.php` main module file. HTML box configurations are stored directly in the `ps_configuration` table, with keys like `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X`, etc., where `X` is the box ID and `Y` is the language ID.

### 4.4 JavaScript Assets (`views/js/`)

- `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Scope:** Back-office.
  - **Responsibility:** Provides JavaScript functionality for the `SmartyTemplatesManager` library, which is used to render and manage the module’s configuration forms (e.g., adding/editing HTML boxes). This includes dynamic form elements, AJAX interactions for saving/loading template data, and potentially tab management.
- `htmlboxpro/views/js/script.js`
  - **Scope:** Back-office.
  - **Responsibility:** Contains module-specific JavaScript for the Back Office configuration page. This might include event listeners for form submissions, dynamic updates to the HTML box list, or other UI enhancements specific to HTML Box Pro.
- `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
  - **Scope:** Back-office.
  - **Responsibility:** This script is loaded when the “Prevent removing URLs from images” option is enabled. It contains TinyMCE configuration and plugins specifically designed to prevent the editor from stripping or modifying absolute URLs, particularly for images. It ensures that `src` attributes remain intact.
- `htmlboxpro/views/js/tinymce16.inc.js`
  - **Scope:** Back-office.
  - **Responsibility:** This script contains the core TinyMCE editor initialization and configuration for the module. It defines the editor’s toolbar, plugins, and general behavior when editing HTML box content. It’s loaded when the “Do not load tinyMCE libraries” option is disabled.

### 4.5 CSS Stylesheets (`views/css/`)

- `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Provides styling for the `SmartyTemplatesManager` library’s UI components, ensuring a consistent look for the module’s configuration forms within the PrestaShop Back Office.
- `htmlboxpro/views/css/styles.css`
  - **Scope:** Back-office admin form styling.
  - **Responsibility:** Contains module-specific CSS rules for the HTML Box Pro configuration page, such as styling for the list of HTML boxes, buttons, or other custom elements within the module’s admin interface.

### 4.6 Smarty Template Structure (`views/templates/`)

The module heavily uses Smarty templates for its Back Office interface.

- **Hook templates (`htmlboxpro/`)**:
  - `htmlboxpro/html.tpl`: This is the primary front-office template. It’s responsible for rendering the actual HTML box content (`{$htmlboxpro_content}`) within the selected hook on the front office.
- **Admin templates (`views/templates/admin/`)**:
  - `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl`: This template is likely an override or specific template used by the module’s configuration form, possibly customizing how the standard PrestaShop `HelperForm` renders its fields, especially for the TinyMCE editor.
- **Admin templates (`views/templates/`)**:
  - `htmlboxpro/views/custom_hook_info.tpl`: Likely displays information or instructions related to custom hooks.
  - `htmlboxpro/views/form-add-new.tpl`: Template for the “Add New HTML Box” form.
  - `htmlboxpro/views/form-edit.tpl`: Template for the “Edit HTML Box” form.
  - `htmlboxpro/views/messages.tpl`: Used to display success, error, or informational messages in the Back Office.
  - `htmlboxpro/views/scripts.tpl`: Likely includes JavaScript and CSS assets for the Back Office configuration page.
- **SmartyTemplatesManager Library Templates (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)**:
  - `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl`: An example template, likely for development or demonstration purposes within the library.
  - `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl`: Renders buttons or action links within the `SmartyTemplatesManager` interface.
  - `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl`: Used for creating new templates/items within the `SmartyTemplatesManager` context.
  - `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl`: Used for editing existing templates/items within the `SmartyTemplatesManager` context.
  - `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl`: The main wrapper or structure for forms managed by the `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl`: A generic template for rendering a select dropdown input.
  - `htmlboxpro/lib/searchTool/views/scripts.tpl`: Likely includes JavaScript and CSS assets for a search tool component within the Back Office.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables. All configuration for HTML boxes is stored in the standard PrestaShop `ps_configuration` table.
  - Configuration keys follow a pattern like:
    - `HBP_NAME_{ID}`: Name of the HTML box.
    - `HBP_CONTENT_{ID}_{LANG_ID}`: The actual HTML/JS/CSS content for a specific box and language.
    - `HBP_HOOK_{ID}`: The name of the hook where the box is displayed.
    - `HBP_ACTIVE_{ID}`: Boolean (0/1) indicating if the box is active.
    - `HBP_SSL_{ID}`: Boolean (0/1) indicating if it’s only on SSL pages.
    - `HBP_HOMEPAGE_{ID}`: Boolean (0/1) indicating if it’s only on the homepage.
    - `HBP_SHOP_{ID}`: Comma-separated list of shop IDs (for multi-store).
    - `HBP_LAST_ID`: Stores the last used ID for an HTML box to generate unique IDs.
    - `HBP_NOTINYJS`: Global setting for “Do not load tinyMCE libraries”.
    - `HBP_FORCEURLS`: Global setting for “Prevent removing URLs from images”.
    - Other keys like `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` for update management.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayAfterCarrier` | After carrier selection in checkout. | Display content related to shipping options or final steps. |
| `displayFooterBefore` | Before the main footer content. | Add content above the standard footer. |
| `displayLeftColumn` | In the left sidebar of applicable pages. | Display sidebar blocks (e.g., categories, filters, custom info). |
| `displayCustomerAccountForm` | Within the customer account creation/edit form. | Add custom fields or information related to customer accounts. |
| `displayRightColumnProduct` | In the right sidebar on product pages. | Display product-specific sidebar content (e.g., related products, trust badges). |
| `displayBanner` | At the top of the page, typically for a site-wide banner. | Display promotional banners or announcements. |
| `actionAdminControllerSetMedia` | When an admin controller sets its media (CSS/JS). | Inject custom CSS/JS into the Back Office (used by the module for its own admin assets). |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Display thank you messages, tracking info, or upsells. |
| `displayHeader` | In the `<head>` section of every page. | Ideal for injecting meta tags, tracking scripts, or global CSS/JS. |
| `displayCartExtraProductActions` | Within the cart summary, near product actions. | Add content related to cart items (e.g., upsells, cross-sells, shipping info). |
| `displayFooter` | In the main footer section of the store. | Add general footer content, links, or copyright info. |
| `displayPaymentByBinaries` | During the payment selection process. | Display payment-related information or trust seals. |
| `displayCustomerLoginFormAfter` | After the customer login form. | Add content below the login form (e.g., “forgot password” links, registration prompts). |
| `displayReassurance` | Within the product reassurance block (often below product image). | Display trust elements like free shipping, secure payment, easy returns. |
| `displayProductAdditionalInfo` | Below the product description or main info block. | Add extra product details, size guides, or custom content. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is ready to assist you with any issues or questions regarding the HTML Box Pro module.
