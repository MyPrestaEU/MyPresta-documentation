---
title: "Tooltip Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Tooltip Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Tooltip Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Tooltip Pro)

This is the main configuration screen for the Tooltip Pro module, where you control its overall behavior and appearance.

- **Menu Location:** Back Office > Modules > Module Manager > Search for “Tooltip Pro” > Click “Configure”

#### Settings & Options:

1. **Enable Tooltips:**

   - **What this setting does:** This is the master switch to activate or deactivate the entire tooltip functionality on your front office.
   - **Effect of changing this setting:**
     - *When enabled (YES):* Tooltips will be active on your store according to your other settings.
     - *When disabled (NO):* No tooltips will appear on your store, regardless of any individual tooltip entries you’ve created.
   - **Recommended value:** YES (once you’ve configured your tooltips).
   - **Merchant scenario / example:** If you’re performing maintenance or want to temporarily disable all tooltips without deleting them, set this to NO.
2. **Highlight Tooltip Keywords:**

   - **What this setting does:** Determines if the text that triggers a tooltip should be visually highlighted on your website.
   - **Effect of changing this setting:**
     - *When enabled (YES):* The keywords you’ve defined for tooltips will have a visual style applied (e.g., a dotted underline, bolding, or a specific color, depending on your theme’s CSS or the module’s default styling). This helps customers identify interactive elements.
     - *When disabled (NO):* The keywords will appear as normal text, but hovering over them will still trigger the tooltip. This can make tooltips less discoverable.
   - **Recommended value:** YES.
   - **Merchant scenario / example:** Enabling this makes it clear to your customers which words are interactive, encouraging them to discover the helpful information. If you prefer a very minimalist design and expect users to discover tooltips naturally, you might disable it.
3. **Tooltip Placement:**

   - **What this setting does:** Controls where the tooltip popup appears relative to the keyword text.
   - **Effect of changing this setting:**
     - *Options (e.g., Top, Bottom, Left, Right, Auto):* Choosing “Top” will make the tooltip appear above the text, “Bottom” below, etc. “Auto” attempts to intelligently place the tooltip to avoid going off-screen.
   - **Recommended value:** Auto.
   - **Merchant scenario / example:** “Auto” is generally the best choice as it adapts to different screen sizes and content layouts. If you find tooltips consistently obscuring important content in a specific area, you might experiment with a fixed placement like “Bottom.”
4. **Tooltip Animation:**

   - **What this setting does:** Selects the animation effect when a tooltip appears and disappears.
   - **Effect of changing this setting:**
     - *Options (e.g., Fade, Grow, Swing, Slide, Fall):* Each option provides a different visual transition. “Fade” is a simple dissolve, “Grow” expands, etc.
   - **Recommended value:** Fade or Grow.
   - **Merchant scenario / example:** A subtle animation like “Fade” or “Grow” adds a polished feel without being distracting. Avoid overly complex animations that might slow down the user experience or feel out of place with your brand.
5. **Tooltip Theme:**

   - **What this setting does:** Allows you to choose a predefined visual theme for your tooltips. This affects colors, borders, and general styling.
   - **Effect of changing this setting:**
     - *Options (e.g., Default, Light, Dark, Bordered, Punk):* Each theme applies a different set of CSS styles.
   - **Recommended value:** Default or Light.
   - **Merchant scenario / example:** Choose a theme that best matches your store’s overall design and branding. “Light” or “Default” are often good starting points. If you have a dark-themed website, “Dark” might be more appropriate.
6. **Tooltip Max Width (pixels):**

   - **What this setting does:** Sets the maximum width for the tooltip popup box in pixels.
   - **Effect of changing this setting:**
     - *Entering a value (e.g., 300):* The tooltip will not exceed this width, wrapping text if necessary.
     - *Leaving empty or 0:* The tooltip will automatically size itself to fit its content, which can sometimes lead to very wide tooltips.
   - **Recommended value:** 250-350 pixels.
   - **Merchant scenario / example:** Setting a reasonable max-width ensures that tooltips don’t become too wide and stretch across the screen, especially on smaller devices or in narrow column layouts.
7. **Delay Before Showing (milliseconds):**

   - **What this setting does:** The time (in milliseconds) a user needs to hover over a keyword before the tooltip appears.
   - **Effect of changing this setting:**
     - *Higher value (e.g., 500ms):* Tooltips appear after a longer delay, preventing them from popping up too quickly if a user is just moving their mouse across the page.
     - *Lower value (e.g., 0ms):* Tooltips appear instantly.
   - **Recommended value:** 200-300.
   - **Merchant scenario / example:** A slight delay (e.g., 200ms) provides a smoother user experience, as it prevents accidental tooltips from appearing and disappearing rapidly.
8. **Delay Before Hiding (milliseconds):**

   - **What this setting does:** The time (in milliseconds) the tooltip remains visible after the user moves their mouse away from the keyword.
   - **Effect of changing this setting:**
     - *Higher value (e.g., 200ms):* The tooltip stays visible for a short period, allowing users to move their mouse slightly without the tooltip disappearing immediately.
     - *Lower value (e.g., 0ms):* The tooltip disappears instantly when the mouse leaves the keyword.
   - **Recommended value:** 100-200.
   - **Merchant scenario / example:** A small delay here can be helpful if a user accidentally moves their mouse off the keyword but wants to continue reading the tooltip.
9. **Allowed Page Types for Tooltips:**

   - **What this setting does:** Specifies on which types of pages tooltips should be active.
   - **Effect of changing this setting:**
     - *Checkboxes (e.g., Product Pages, Category Pages, CMS Pages, All Pages):* Select the specific page types where you want your tooltips to function.
     - *Selecting “All Pages”:* Tooltips will be active everywhere on your store.
   - **Recommended value:** Select only the page types where you genuinely need tooltips to avoid unnecessary processing on other pages.
   - **Merchant scenario / example:** If you primarily use tooltips for product specifications, you might only check “Product Pages.” If you have a lot of technical terms across your entire site, “All Pages” might be appropriate.

### 2.2 Dedicated Admin Screen: Tooltip List (Back Office > Tooltip Pro > Tooltips)

This screen is where you manage all the individual tooltips you want to create and display on your store. It acts as a central hub for adding, editing, and deleting tooltip entries.

- **Screen Name & Menu Location:** Back Office > Tooltip Pro > Tooltips
- **Available Actions & Settings:**
  - **Tooltip List Table:** Displays a list of all your created tooltips, typically showing the keyword, the content, and its status (enabled/disabled).
  - **Add New Tooltip Button:** Click this to create a new tooltip entry.
  - **Edit/Delete Actions:** Each tooltip in the list will have action buttons (e.g., a pencil icon for “Edit,” a trash can icon for “Delete”) to manage individual entries.
  - **Bulk Actions:** Often, there are options to enable, disable, or delete multiple selected tooltips at once.

#### When Adding/Editing a Tooltip:

1. **Keyword:**

   - **What this setting does:** This is the exact word or phrase that, when found on your website, will trigger the tooltip.
   - **Effect of changing this setting:** The module will search for this specific text on your enabled pages. Case sensitivity might apply depending on the module’s internal logic (assume it’s case-sensitive for best results).
   - **Recommended value:** Be precise. Use the exact spelling and capitalization as it appears on your site.
   - **Merchant scenario / example:** If you want to explain “Organic Cotton,” enter “Organic Cotton.” If you enter “organic cotton,” it might not trigger on “Organic Cotton.”
2. **Tooltip Content:**

   - **What this setting does:** This is the information that will be displayed inside the tooltip popup. It’s typically a rich text editor (WYSIWYG) allowing for various content types.
   - **Effect of changing this setting:** Whatever you enter here will be shown to the customer when they hover over the keyword.
   - **Recommended value:** Keep it concise and informative. Use images, videos, or links sparingly to avoid overwhelming the user.
   - **Merchant scenario / example:** For “Organic Cotton,” you might add: “Organic cotton is grown without harmful chemicals, pesticides, or GMOs, making it better for the environment and your skin. [Link to blog post about sustainability].”
3. **Active:**

   - **What this setting does:** Controls whether this specific tooltip entry is active or inactive.
   - **Effect of changing this setting:**
     - *When enabled (YES):* This individual tooltip will appear on your store.
     - *When disabled (NO):* This tooltip will not appear, even if the main module is enabled.
   - **Recommended value:** YES (for tooltips you want to display).
   - **Merchant scenario / example:** You might disable a tooltip temporarily if the information is outdated or if a product feature it describes is no longer available, without deleting the entire entry.

- **Recommended workflow for daily store management:**
  1. Start by identifying common questions or confusing terms on your product pages, category pages, or important CMS pages.
  2. Go to **Back Office > Tooltip Pro > Tooltips**.
  3. Click “Add New Tooltip.”
  4. Enter the exact **Keyword** you want to explain.
  5. Craft clear, concise, and helpful **Tooltip Content**.
  6. Ensure **Active** is set to YES.
  7. Save your changes.
  8. Test the tooltip on your front office to ensure it appears correctly and provides the desired information.
  9. Regularly review your tooltips to ensure the information remains accurate and relevant.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable Tooltips | YES | Master switch for all tooltip functionality. |
|  | Highlight Tooltip Keywords | YES | Visually marks keywords on front-office. |
|  | Tooltip Placement | Auto | Position of the tooltip popup relative to the keyword. |
|  | Tooltip Animation | Fade / Grow | Visual effect when tooltip appears/disappears. |
|  | Tooltip Theme | Default / Light | Styling (colors, borders) of the tooltip box. |
|  | Tooltip Max Width (pixels) | 250-350 | Prevents tooltips from becoming too wide. |
|  | Delay Before Showing (ms) | 200-300 | Time before tooltip appears on hover. |
|  | Delay Before Hiding (ms) | 100-200 | Time before tooltip disappears after hover. |
|  | Allowed Page Types | Select as needed | Restricts tooltips to specific page types (e.g., Product, Category). |
| **Tooltip List (Add/Edit)** | Keyword | Exact text | The specific word/phrase that triggers the tooltip. |
|  | Tooltip Content | Concise, informative | The information displayed inside the tooltip. |
|  | Active | YES | Enables/disables an individual tooltip entry. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My tooltips aren’t showing up on the front office, even though I’ve created them.**
A:

1. **Check Master Switch:** Go to **Modules > Module Manager > Configure Tooltip Pro**. Ensure “Enable Tooltips” is set to YES.
2. **Check Individual Tooltip Status:** Go to **Tooltip Pro > Tooltips**. Make sure the specific tooltip you’re expecting to see has “Active” set to YES.
3. **Check Page Type:** Verify that the “Allowed Page Types for Tooltips” setting includes the type of page you’re currently viewing (e.g., if you’re on a product page, “Product Pages” must be checked).
4. **Keyword Match:** Ensure the “Keyword” you entered for the tooltip exactly matches the text on your front office, including capitalization and spacing.
5. **Clear Cache:** Sometimes PrestaShop’s cache can prevent new content from appearing. Go to **Advanced Parameters > Performance** and click “Clear cache.”

**Q: The tooltip content looks strange or doesn’t display correctly (e.g., broken images, weird formatting).**
A:

1. **HTML Errors:** If you’ve used the rich text editor, ensure you haven’t introduced any broken HTML tags. Switch to the source code view in the editor to check for unclosed tags or invalid attributes.
2. **Image Paths:** If images aren’t showing, check that the image URL in your tooltip content is correct and accessible. Use absolute URLs (starting with `http://` or `https://`) for images hosted on your server.
3. **CSS Conflicts:** Your theme’s CSS might be overriding the module’s styling. This is more of a developer issue, but you can try changing the “Tooltip Theme” in the module configuration to see if a different theme resolves it.

**Q: Tooltips are appearing on pages where I don’t want them.**
A:

1. **Review “Allowed Page Types”:** Go to **Modules > Module Manager > Configure Tooltip Pro**. Carefully review the “Allowed Page Types for Tooltips” and uncheck any page types where you do not want tooltips to appear.
2. **Keyword Specificity:** If a keyword is very generic (e.g., “product”), it might appear on many pages. Consider making your keywords more specific or restricting them to certain page types.

**Q: How do I translate my tooltips into other languages?**
A:

1. **Edit Tooltip:** Go to **Tooltip Pro > Tooltips** and click “Edit” on the tooltip you want to translate.
2. **Language Selector:** Within the “Tooltip Content” rich text editor, you should see a language selector (usually a flag icon or a dropdown). Select the desired language and enter the translated content for that language. Repeat for all languages.
3. **Keyword Translation:** The “Keyword” itself is usually not translated by the module, as it searches for the exact text on the page. If your keywords change per language (e.g., “Size Guide” vs. “Guide des Tailles”), you would need to create separate tooltip entries for each language’s keyword.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Tooltip Pro module follows a standard PrestaShop module architecture, leveraging MVC principles. It primarily consists of:

- A main module class (`index.php`) for installation, uninstallation, and configuration.
- Dedicated Admin Controllers (`AdminTooltipsListController`) for managing tooltip entities in the Back Office.
- Front Controllers (`ajax.php`) to handle dynamic content requests if needed (though the core tooltip rendering is client-side).
- Client-side JavaScript (using the Tooltipster library) to detect keywords and display tooltips dynamically.
- Custom database table (`ps_tooltips`) to store tooltip definitions.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/ajax.php`
  - **Class name & parent class:** `TooltipsAjaxModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller is designed to handle AJAX requests from the front-office. While the core tooltip content is often rendered directly into the HTML, this controller could be used for dynamic content loading, fetching tooltip data on demand, or other interactive features. It responds to specific routes defined by the module.
- `controllers/front/index.php`
  - **Class name & parent class:** `TooltipsIndexModuleFrontController` extends `ModuleFrontController`.
  - **Responsibility:** This controller might serve as a fallback or a placeholder. In many simple modules, `index.php` in the front controller directory is not directly used for rendering a page but might be present for architectural completeness or to handle default module routing if no other specific front controller matches. For Tooltip Pro, the primary front-office interaction is via JavaScript and hooks.

#### Back-Office Admin Controllers

- `controllers/admin/AdminTooltipsList.php`
  - **Class name & parent class:** `AdminTooltipsListController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** This controller manages the “Tooltips” list in the PrestaShop Back Office. It’s responsible for displaying the grid of existing tooltips, handling add/edit/delete operations for `Tooltip` objects, and rendering the associated forms. It interacts directly with the `Tooltip` `ObjectModel`.
- `controllers/admin/index.php`
  - **Class name & parent class:** `TooltipsAdminIndexModuleFrontController` extends `ModuleAdminController`.
  - **Tab name and managed entity:** Similar to the front-office `index.php`, this might be a placeholder or a default entry point for the module’s admin section. The primary management is handled by `AdminTooltipsList.php`.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no specific `classes/` directory, implying the main `Tooltip` `ObjectModel` and related logic might be defined directly within the main `tooltips/index.php` file or dynamically generated.
Assuming a standard PrestaShop module structure, there would typically be a `Tooltip.php` class.

- **`Tooltip` (hypothetical, likely in `index.php` or a dedicated `classes/Tooltip.php` if present):**
  - **Database table:** `ps_tooltips` (or `_PREFIX_tooltips`)
  - **Extends `ObjectModel`:** Yes.
  - **`$definition` fields:**
    - `id_tooltip`: Primary key (INT)
    - `keyword`: The text string to be highlighted (VARCHAR)
    - `content`: The HTML content of the tooltip (HTML, TEXT)
    - `active`: Boolean for active/inactive status (TINYINT)
    - `date_add`: Creation date (DATETIME)
    - `date_upd`: Last update date (DATETIME)
    - `id_shop`: Shop ID for multi-store (INT)
    - `id_lang`: Language ID for multi-language content (INT)
  - **Key public methods:** Standard `ObjectModel` methods (`add()`, `update()`, `delete()`, `getFields()`). Custom methods might include `getTooltipsByShopAndLang()` or `getKeywordsForPageType()`.

### 4.4 JavaScript Assets (`views/js/`)

The module leverages the `Tooltipster` library for its tooltip functionality.

- `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - **Scope:** Front-office.
  - **Description:** A plugin for the Tooltipster library specifically for handling SVG elements. If your tooltips need to interact with or be placed on SVG graphics, this plugin provides the necessary functionality.
- `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
  - **Scope:** Front-office.
  - **Description:** The full, bundled version of the Tooltipster library, including its core and potentially other common plugins. This provides the main functionality for creating and managing tooltips.
- `tooltips/lib/tooltipster/js/tooltipster.core.js`
  - **Scope:** Front-office.
  - **Description:** The core functionality of the Tooltipster library. This file contains the essential logic for tooltip creation, positioning, events, and styling.
- `tooltips/views/js/tooltips.js`
  - **Scope:** Front-office.
  - **Description:** This is the module’s custom JavaScript.
    - **Event listeners:** Likely binds to the `ready` event of the document (`$(document).ready()` or similar) to initialize tooltips.
    - **DOM manipulation:** Scans the page content for defined keywords, wraps them in a specific HTML element (e.g., `<span class="tooltip-keyword">`), and then initializes the Tooltipster library on these elements.
    - **Tooltipster initialization:** Configures Tooltipster with settings from the module’s Back Office (placement, animation, theme, delays, max-width).
    - **AJAX calls:** Potentially makes AJAX calls to `controllers/front/ajax.php` to fetch tooltip content dynamically, though the module description suggests content is often pre-rendered.
    - **Mobile interaction:** Handles tap events for mobile devices to trigger tooltips.

### 4.5 CSS Stylesheets (`views/css/`)

- `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
  - **Scope:** Front-office customer styling.
  - **Description:** The main stylesheet for the Tooltipster library, containing default styles for the tooltip box, arrows, and various themes.
- `tooltips/lib/tooltipster/css/tooltipster.core.css`
  - **Scope:** Front-office customer styling.
  - **Description:** Core CSS for the Tooltipster library, defining essential visual properties for tooltips.
- `tooltips/views/css/tooltips-admin.css`
  - **Scope:** Back-office admin form styling.
  - **Description:** Contains specific styles for the module’s configuration pages and the `AdminTooltipsList` controller in the PrestaShop Back Office, ensuring a consistent and user-friendly admin interface.
- `tooltips/views/css/tooltips.css`
  - **Scope:** Front-office customer styling.
  - **Description:** This is the module’s custom front-office CSS.
    - **Main UI components:** Styles the highlighted keywords (e.g., `span.tooltip-keyword`).
    - **Key CSS class selectors:** Developers can override styles for `.tooltip-keyword` or specific Tooltipster theme classes (e.g., `.tooltipster-base`, `.tooltipster-light`) in their theme’s `custom.css` or by creating an override file.

### 4.6 Smarty Template Structure (`views/templates/`)

- `tooltips/views/tooltips.tpl`
  - **Scope:** Front-office hook template.
  - **Description:** This template is likely hooked into `displayHeader` or `displayFooter` to output necessary JavaScript variables and potentially the initialization script for the `tooltips.js` file. It might pass configuration settings from the Back Office (e.g., `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) as Smarty variables to the JavaScript. It does not directly render the tooltip content itself, as that’s handled dynamically by JavaScript.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_tooltips`: Stores the definitions for each tooltip.
    - `id_tooltip` (PK, INT)
    - `keyword` (VARCHAR)
    - `content` (TEXT, HTML allowed)
    - `active` (TINYINT(1))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
    - `id_shop` (INT)
    - `id_lang` (INT)
  - `ps_configuration`: Stores module-wide settings (e.g., `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT`, etc.).
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects CSS and JavaScript files (Tooltipster library, `tooltips.js`, and module-specific styles) into the page. Also outputs configuration variables for JS. |
| `displayBackOfficeHeader` | In the `<head>` section of every Back Office page. | Injects admin-specific CSS (`tooltips-admin.css`) and potentially JS for the module’s configuration and list pages. |
| `actionFrontControllerSetMedia` | After media has been set for a front controller. | Allows the module to conditionally add its CSS/JS based on the current page context (e.g., only on product pages if configured). |
| `moduleRoutes` | During router initialization. | Registers custom front-office routes for `ajax.php` if dynamic content loading is used. |
| `actionObjectTooltipAddAfter` | After a `Tooltip` object is added. | Can be used for cache clearing or logging. |
| `actionObjectTooltipUpdateAfter` | After a `Tooltip` object is updated. | Can be used for cache clearing or logging. |
| `actionObjectTooltipDeleteAfter` | After a `Tooltip` object is deleted. | Can be used for cache clearing or logging. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for your Tooltip Pro module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions perfectly and helps you enhance your PrestaShop store.
