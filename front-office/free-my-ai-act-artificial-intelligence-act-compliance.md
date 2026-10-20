---
title: "Free My AI Act - Artificial Intelligence Act compliance - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free My AI Act - Artificial Intelligence Act compliance PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free My AI Act - Artificial Intelligence Act compliance"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free My AI Act - Artificial Intelligence Act compliance Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Artificial Intelligence Act compliance

## 1. Requirements & Compatibility
-   **Supported PrestaShop Versions**: PrestaShop 9.x
-   **PHP Compatibility**: PHP 7.4 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for a PrestaShop installation and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
To access the module's configuration, navigate to **Modules > Module Manager**, search for "Free My AI Act", and click the "Configure" button.

This screen provides all the essential settings to control how AI content is disclosed on your store.

#### **General Settings**

-   **Enable AI Act Compliance:**
    -   **What this setting does:** This is the master switch to activate or deactivate the module's features across your store.
    -   **Effect of changing this setting:**
        -   *When enabled:* All configured AI disclosure features (badges, banners, notices) will become active on your front office.
        -   *When disabled:* All AI disclosure features will be hidden, and the module will not display any AI-related information to customers.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You've completed your setup and are ready to go live with AI Act compliance. Enable this setting. If you need to temporarily disable all disclosures for maintenance, switch it to NO.

#### **AI Content Disclosure Options**

-   **Show AI Badge on Product Images:**
    -   **What this setting does:** Controls whether a small badge (e.g., "AI Generated" or an icon) appears directly on product images in category listings and on the product page.
    -   **Effect of changing this setting:**
        -   *When enabled:* A visual indicator will be overlaid on product images that you have marked as AI-generated.
        -   *When disabled:* No badge will appear on product images, even if they are marked as AI-generated.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You use AI to generate or enhance many of your product photos. Enabling this provides immediate visual disclosure to customers as they browse.

-   **Show Additional Info Notice on Product Page:**
    -   **What this setting does:** Determines if a dedicated text notice is displayed on individual product pages to inform customers about AI-generated content (text or images) for that specific product.
    -   **Effect of changing this setting:**
        -   *When enabled:* A customizable text block will appear on product pages, typically below the description or in a new tab, detailing the use of AI for that product's content.
        -   *When disabled:* No specific AI disclosure notice will be shown on product pages.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You want to provide a more detailed explanation about the AI content for each product. This notice allows you to elaborate beyond just a badge.

-   **Show Store-wide AI Policy Banner:**
    -   **What this setting does:** Activates a banner that appears consistently across your entire store (e.g., at the top or bottom of every page) to inform visitors about your general AI content policy.
    -   **Effect of changing this setting:**
        -   *When enabled:* A customizable banner will be visible on all pages, often with a link to a more comprehensive AI policy page.
        -   *When disabled:* No store-wide banner will be displayed.
    -   **Recommended value:** YES
    -   **Merchant scenario / example:** You want to make a general statement about your store's use of AI and direct customers to a dedicated policy page for full transparency.

-   **Link to AI Policy Page (URL):**
    -   **What this setting does:** Allows you to specify the URL of a CMS page or external link where customers can find your detailed AI content policy. This link will typically be included in the store-wide banner or additional info notices.
    -   **Effect of changing this setting:**
        -   *When a URL is entered:* The banner and notices will include a clickable link to this page.
        -   *When left empty:* No link will be provided, or the banner/notice might not appear if it relies on this link.
    -   **Recommended value:** `[Your CMS page URL, e.g., /content/10-ai-policy]`
    -   **Merchant scenario / example:** You've created a dedicated CMS page explaining your AI usage, data practices, and commitment to transparency. Enter its URL here so customers can easily access it.

#### **Content Customization**

-   **AI Badge Text (e.g., "AI"):**
    -   **What this setting does:** Defines the short text that appears on the AI badge overlaid on product images.
    -   **Effect of changing this setting:**
        -   *When changed:* The text on the badge will update accordingly.
    -   **Recommended value:** AI
    -   **Merchant scenario / example:** You prefer a shorter label like "AI" instead of "AI Generated" to keep the badge concise.

-   **AI Badge Color:**
    -   **What this setting does:** Sets the background color of the AI badge.
    -   **Effect of changing this setting:**
        -   *When changed:* The badge's background color will update, allowing you to match your store's branding.
    -   **Recommended value:** #FF0000 (Red) or a color that contrasts well with your product images.
    -   **Merchant scenario / example:** Your brand uses a specific color palette. You can set the badge color to a contrasting shade that is still visually appealing.

-   **AI Badge Text Color:**
    -   **What this setting does:** Sets the color of the text within the AI badge.
    -   **Effect of changing this setting:**
        -   *When changed:* The text color on the badge will update.
    -   **Recommended value:** #FFFFFF (White) or a color that contrasts well with your chosen badge background.
    -   **Merchant scenario / example:** If your badge background is dark, you'll want white or light-colored text for readability.

-   **Additional Info Notice Text:**
    -   **What this setting does:** Allows you to customize the full text displayed in the "Additional Info Notice" on product pages.
    -   **Effect of changing this setting:**
        -   *When changed:* The content of the notice on product pages will reflect your custom text.
    -   **Recommended value:** "Please note: Parts of this product description and/or images may have been generated or enhanced using Artificial Intelligence to provide you with comprehensive information."
    -   **Merchant scenario / example:** You want to clearly state that both text and images might be AI-generated and explain why (e.g., for comprehensive information).

-   **Store-wide Banner Text:**
    -   **What this setting does:** Customizes the message displayed in the store-wide AI policy banner.
    -   **Effect of changing this setting:**
        -   *When changed:* The text in the banner across all pages will update.
    -   **Recommended value:** "Our store uses AI to enhance content. Learn more about our AI policy."
    -   **Merchant scenario / example:** You want a concise message in the banner that encourages customers to click the link for more details.

#### **Product-Specific AI Flagging**

This module also integrates directly into your product editing page. When you edit a product in the Back Office (**Catalog > Products > Edit Product**), you will find a new tab or section related to "AI Act Compliance".

-   **Mark Product Content as AI-Generated:**
    -   **What this setting does:** A checkbox or toggle on the product editing page that allows you to individually mark a specific product's text content (description, short description, features) as AI-generated.
    -   **Effect of changing this setting:**
        -   *When enabled for a product:* The "Additional Info Notice" (if enabled in module config) will appear on that product's page, and any other text-based AI disclosures will activate.
        -   *When disabled for a product:* No text-based AI disclosures will appear for that specific product.
    -   **Recommended value:** Enable for any product where AI was used for text.
    -   **Merchant scenario / example:** You used an AI writing assistant to create the long description for a new product. You would enable this setting for that specific product.

-   **Mark Product Images as AI-Generated:**
    -   **What this setting does:** A checkbox or toggle on the product editing page that allows you to individually mark a specific product's images as AI-generated or AI-enhanced.
    -   **Effect of changing this setting:**
        -   *When enabled for a product:* The "AI Badge" (if enabled in module config) will appear on that product's images, and the "Additional Info Notice" will also activate.
        -   *When disabled for a product:* No AI badge will appear on images for that specific product.
    -   **Recommended value:** Enable for any product where AI was used for images.
    -   **Merchant scenario / example:** You used an AI image generator or enhancer for the main product image. You would enable this setting for that specific product.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Enable AI Act Compliance | YES | Master switch for all module features. |
| Module Configuration | Show AI Badge on Product Images | YES | Displays "AI" badge on AI-flagged product images. |
| Module Configuration | Show Additional Info Notice on Product Page | YES | Displays a text notice on AI-flagged product pages. |
| Module Configuration | Show Store-wide AI Policy Banner | YES | Displays a banner across all pages for general policy. |
| Module Configuration | Link to AI Policy Page (URL) | `/content/10-ai-policy` | URL for your detailed AI policy page. |
| Module Configuration | AI Badge Text | AI | Text displayed on the product image badge. |
| Module Configuration | AI Badge Color | `#FF0000` (Red) | Background color of the AI badge. |
| Module Configuration | AI Badge Text Color | `#FFFFFF` (White) | Text color of the AI badge. |
| Module Configuration | Additional Info Notice Text | Customizable | Full text for the product page notice. |
| Module Configuration | Store-wide Banner Text | Customizable | Full text for the store-wide banner. |
| Product Edit Page | Mark Product Content as AI-Generated | N/A (per product) | Flags product text content as AI-generated. |
| Product Edit Page | Mark Product Images as AI-Generated | N/A (per product) | Flags product images as AI-generated. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: I've enabled the module and configured settings, but I don't see any AI badges or banners on my store.**
**A1:**
1.  **Check "Enable AI Act Compliance":** Ensure the main switch in the module's configuration is set to YES.
2.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Your browser cache might also need clearing (Ctrl+F5 or Cmd+R).
3.  **Check Individual Product Settings:** For badges and product page notices, ensure you have individually marked the specific products as having AI-generated content/images on their respective product editing pages.
4.  **Theme Compatibility:** While the module is designed for PrestaShop 9.x, custom themes can sometimes interfere. If issues persist, temporarily switch to the default PrestaShop theme to rule out a theme conflict.

**Q2: The AI badge or banner looks strange or is misplaced on my custom theme.**
**A2:** This is often a CSS conflict with your theme.
1.  **Inspect Element:** Use your browser's developer tools (F12) to inspect the AI badge/banner. Look for conflicting CSS rules.
2.  **Custom CSS:** You may need to add custom CSS to your theme's stylesheet (or via a custom CSS module) to adjust the positioning or styling. The module's CSS classes are usually well-defined (e.g., `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Contact Support:** If you're not comfortable with CSS, contact MyPresta.eu support or your web developer for assistance.

**Q3: How do I translate the AI badge text, banner text, or additional info notice into other languages?**
**A3:**
1.  Go to **International > Translations** in your PrestaShop Back Office.
2.  Select "Installed modules translations" for the "Type of translation".
3.  Choose your theme and the language you want to translate.
4.  Find the "Free My AI Act" module in the list. You will be able to translate the text fields you configured (AI Badge Text, Additional Info Notice Text, Store-wide Banner Text) directly there.
5.  Save your changes.

**Q4: What's the difference between this "Free" module and "My AI Act Pro"?**
**A4:** The "Free My AI Act" module provides essential disclosure features for basic compliance. "My AI Act Pro" (a separate, paid module) offers advanced functionalities such as AI Studio integration, API access for automated flagging, audit trails, and advanced watermarking capabilities for images. The Free version is a great starting point, and you can upgrade to Pro if your needs become more complex.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, extend, or troubleshoot the "Free My AI Act" module.

### 4.1 Architecture Overview
The `myaiactfree` module follows a standard PrestaShop module architecture, primarily leveraging hooks for front-office display and `getContent()` for back-office configuration. It integrates directly into the product editing interface by hooking into `displayAdminProductsExtra` to provide product-specific AI flagging options. Configuration is stored in `ps_configuration`, and front-office rendering is achieved through Smarty templates and a dedicated JavaScript file for dynamic interactions.

### 4.2 Controllers (`controllers/`)
This module does not contain any dedicated front-office or back-office controllers. All front-office logic is handled via hooks within the main module file, and back-office configuration is managed by the `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)
This module does not define any custom classes or `ObjectModel` instances. All data is managed directly via `Configuration` for global settings and `Product` properties for product-specific flags.

### 4.4 JavaScript Assets (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Scope:** Front-office.
    *   **Responsibility:** This script is likely responsible for any dynamic front-office behavior related to the AI disclosure elements. This could include:
        *   Initializing the AI badge display on product images after the DOM is ready.
        *   Handling click events on the AI policy banner (if it's dismissible or has interactive elements).
        *   Ensuring proper positioning and responsiveness of the AI badge or banner, especially if images are loaded dynamically or resized.
        *   Potentially adding tooltips or popovers when hovering over AI badges.
        *   Binding to `prestashop.on` events for dynamic content updates (e.g., `updateProduct` on product page).

### 4.5 CSS Stylesheets (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Scope:** Back-office admin form styling.
    *   **Responsibility:** Provides styling for the module's configuration page (`configure.tpl`) and potentially the custom tab/section added to the product editing page (`product_tab.tpl`). This ensures a consistent and user-friendly appearance within the PrestaShop Back Office.
    *   **Key CSS class selectors:** Likely targets elements within the module's configuration form, such as specific input fields, labels, or informational blocks.

-   **`myaiactfree/views/css/front.css`**
    *   **Scope:** Front-office customer styling.
    *   **Responsibility:** Defines the visual appearance of all AI disclosure elements visible to customers. This includes:
        *   Styling for the AI badge (e.g., `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`) including its position, background color, text color, padding, and border-radius.
        *   Styling for the additional info notice on product pages (e.g., `.myaiactfree-additional-info`).
        *   Styling for the store-wide AI policy banner (e.g., `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Key CSS class selectors:** Developers can override these classes in their theme's custom CSS to match their brand's design.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`**:
        *   **Hook:** Likely rendered in `displayProductExtraContent` or similar product page hooks.
        *   **Output:** Displays the customizable "Additional Info Notice" text on the product page when a product is flagged as AI-generated.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`**:
        *   **Hook:** Likely rendered in `displayProductListReviews` (for product listings) or `displayProductAdditionalInfo` (for product page image).
        *   **Output:** Generates the HTML structure for the AI badge that overlays product images, including the customizable text and styling.
    *   **`myaiactfree/views/templates/hook/banner.tpl`**:
        *   **Hook:** Likely rendered in `displayHeader`, `displayTop`, `displayWrapperTop`, or `displayFooter`.
        *   **Output:** Renders the store-wide AI policy banner, including the customizable text and a link to the AI policy page.

-   **Admin templates (`views/templates/admin/`)**:
    *   **`myaiactfree/views/templates/admin/configure.tpl`**:
        *   **Purpose:** This is the main template for the module's configuration page accessed via `getContent()`. It renders all the global settings (enable/disable, badge text, banner text, etc.) as described in section 4.1.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`**:
        *   **Purpose:** Likely displays an introductory message or explanation at the top of the module's configuration page, perhaps explaining the AI Act or the module's purpose.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`**:
        *   **Hook:** Rendered via `displayAdminProductsExtra`.
        *   **Purpose:** This template provides the interface within the product editing page (Back Office > Catalog > Products > Edit Product) where merchants can individually mark a product's content and images as AI-generated. It contains the checkboxes or toggles for product-specific AI flags.

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   This module does not create custom SQL tables.
    *   Configuration settings are stored in the `ps_configuration` table using keys typically prefixed with `MYAIACTFREE_`. Examples:
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   Product-specific AI flags (for content and images) are likely stored as `Product` object properties or in a custom field associated with the `Product` entity, possibly through `Configuration::updateValue` with a product ID suffix or directly modifying the `Product` object's data.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | Inject CSS/JS assets (`front.css`, `front.js`) and potentially the store-wide banner (`banner.tpl`). |
| `displayTop` / `displayWrapperTop` | Often at the very top of the page content. | Alternative hook for the store-wide banner (`banner.tpl`). |
| `displayFooter` | At the bottom of every page. | Alternative hook for the store-wide banner (`banner.tpl`). |
| `displayProductListReviews` | On product listing pages, near product images. | Render the AI badge (`ai_badge.tpl`) on product thumbnails. |
| `displayProductAdditionalInfo` | On the product page, near the product image/price block. | Render the AI badge (`ai_badge.tpl`) on the main product image. |
| `displayProductExtraContent` | On the product page, typically below the description or in a new tab. | Render the additional info notice (`additional_info.tpl`). |
| `displayAdminProductsExtra` | On the product editing page in the Back Office. | Inject the custom tab/section for product-specific AI flagging (`product_tab.tpl`). |
| `actionProductUpdate` | After a product is updated in the Back Office. | Save the product-specific AI flags (content/image) to the database. |
| `actionProductAdd` | After a new product is added in the Back Office. | Initialize product-specific AI flags for new products. |

## 5. Official Support & Updates
For official updates, technical support, and to access the latest versions of the "Free My AI Act - Artificial Intelligence Act compliance" module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions you may have regarding the module's functionality or compatibility.
