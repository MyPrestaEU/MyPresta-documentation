---
title: "Custom contents slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Custom contents slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Custom contents slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Custom contents slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/custom-contents-slider/)
>
> ---


# Custom contents slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for the “Custom contents slider” module. This is where you define the content, appearance, and behavior of your sliders.

The configuration page is powered by the `SmartyTemplatesManager` library, which allows you to create and manage multiple custom content blocks.

#### **Main Form (mainForm.tpl)**

This section provides an overview of your existing sliders and allows you to add new ones.

- **What this section does:** Displays a list of all custom content sliders you have created. Each entry shows basic information like the slider’s name, position, and status.
- **Effect of changing this section:** From here, you can quickly see which sliders are active and where they are displayed. You can also click to edit existing sliders or add new ones.
- **Recommended action:** Review your existing sliders. If you’re setting up for the first time, you’ll want to click the “Add New Template” button.

#### **Create/Edit Template Form (createTemplateForm.tpl / editTemplateForm.tpl)**

When you click “Add New Template” or “Edit” an existing slider, you’ll be taken to a form where you define all the details for that specific slider.

- **Template Name:**

  - **What this setting does:** This is an internal name for your slider, visible only in the back office. It helps you identify different sliders.
  - **Effect of changing this setting:** Changing this only affects how you see it in the admin panel; it has no front-office impact.
  - **Recommended value:** A descriptive name, e.g., “Summer Sale Left Slider”, “Newsletter Signup Bottom”.
  - **Merchant scenario / example:** If you have multiple promotions, naming them clearly helps you manage them.
- **Template Content:**

  - **What this setting does:** This is the core of your slider. You can enter any HTML, text, or even Smarty code here. This content will be displayed inside the sliding panel.
  - **Effect of changing this setting:** This directly changes what your customers see when the slider expands. You can include images, links, paragraphs, forms, etc.
  - **Recommended value:** Use standard HTML. Keep it concise and visually appealing. For images, use absolute URLs or PrestaShop’s image helper.
  - **Merchant scenario / example:**

    ```
    <h3>Limited Time Offer!</h3><p>Get <strong>15% OFF</strong> all summer collection items!</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">Shop Now!</a>
    ```

    (Note: Smarty variables like `{$link->getPageLink(...)` require Smarty processing to be enabled for the content, which this module supports.)
- **Position:**

  - **What this setting does:** Determines where the slider will appear on the customer’s screen.
  - **Effect of changing this setting:**
    - *Left:* Slider appears from the left edge.
    - *Right:* Slider appears from the right edge.
    - *Bottom:* Slider appears from the bottom edge.
  - **Recommended value:** Choose based on your design and other elements on your page. Right and Bottom are often less intrusive than Left.
  - **Merchant scenario / example:** Use “Right” for a quick contact form, “Bottom” for a cookie consent banner, or “Left” for a special discount code.
- **Open on:**

  - **What this setting does:** Defines how the slider expands to show its content.
  - **Effect of changing this setting:**
    - *Click:* The slider expands only when the customer clicks on its trigger tab.
    - *Hover:* The slider expands when the customer moves their mouse cursor over its trigger tab.
  - **Recommended value:** “Click” is generally less intrusive and prevents accidental openings. “Hover” can be good for very subtle, quick-peek content.
  - **Merchant scenario / example:** For important announcements or forms, “Click” is better. For a quick “Hello, how can I help?” chat button, “Hover” might work.
- **Active:**

  - **What this setting does:** Toggles whether this specific slider is visible and active on your front office.
  - **Effect of changing this setting:**
    - *Enabled (Yes):* The slider will appear on your store according to its settings.
    - *Disabled (No):* The slider will be hidden from your store, but its configuration will be saved.
  - **Recommended value:** “Yes” for active sliders, “No” for sliders you want to temporarily hide or are still working on.
  - **Merchant scenario / example:** You might disable a Christmas promotion slider after the holidays, then re-enable it next year.

#### **Button Manager (buttonManager.tpl)**

This section is part of the `SmartyTemplatesManager` and allows you to manage the buttons or triggers for your sliders. While the module primarily uses the “Open on” setting, this section might offer additional customization for the visual trigger itself.

- **What this section does:** Provides options to customize the appearance of the tab or button that customers interact with to open the slider. This might include text, icons, or basic styling.
- **Effect of changing this section:** Modifies the visual look of the slider’s trigger on the front office.
- **Recommended value:** Keep the trigger clear and inviting. Use concise text or a relevant icon.
- **Merchant scenario / example:** You could set the button text to “Sale!”, “Contact Us”, or use a small chat icon.

#### **Select Input (selectInput.tpl)**

This is a generic template for dropdown selections within the `SmartyTemplatesManager`. It’s used for settings like “Position” and “Open on”.

- **What this section does:** Presents a dropdown list of predefined options for a particular setting.
- **Effect of changing this section:** Allows you to choose from a limited set of options for a given configuration.
- **Recommended value:** Select the option that best fits your desired slider behavior.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Main Form | (List of Sliders) | N/A | Overview of all created sliders; allows adding/editing. |
| Create/Edit Template | **Template Name** | Descriptive Name | Internal identifier for the slider in the back office. |
| Create/Edit Template | **Template Content** | Custom HTML/Text | The actual content displayed inside the slider. |
| Create/Edit Template | **Position** | Right / Bottom | Where the slider appears on the screen (Left, Right, Bottom). |
| Create/Edit Template | **Open on** | Click | How the slider expands (Click or Hover). |
| Create/Edit Template | **Active** | Yes | Toggles the visibility of the slider on the front office. |
| Button Manager | (Button options) | N/A | Customizes the visual trigger for the slider (text, icon, style). |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My slider isn’t showing up on the front office. What should I check?**
A:

1. **Is the slider “Active”?** Go to the module configuration, edit your slider, and ensure the “Active” setting is set to “Yes”.
2. **Is the content valid?** Ensure there are no unclosed HTML tags or JavaScript errors in your “Template Content” that could break the display.
3. **Clear your cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and clear the Smarty cache (and optionally the entire cache).
4. **Check for conflicts:** Temporarily disable other modules that might be adding floating elements or modifying the page layout to see if there’s a conflict.

**Q: The slider appears, but the styling looks off or doesn’t match my theme.**
A:

1. **Module’s default CSS:** The module comes with its own CSS. Your theme’s CSS might be overriding it, or vice-versa.
2. **Custom theme styling:** You might need to add custom CSS rules to your theme’s stylesheet to adjust the slider’s appearance. Use your browser’s developer tools (F12) to inspect the slider elements and identify the CSS classes to target.
3. **Content styling:** If you’re putting raw HTML into the “Template Content”, ensure you’re using appropriate classes or inline styles that work with your theme.

**Q: Can I have multiple sliders active at once?**
A: Yes, the module supports multiple sliders. However, be mindful of user experience. Having too many sliders (e.g., one on the left, one on the right, and one on the bottom) can clutter the interface and overwhelm customers. It’s generally best to use one or two strategically.

**Q: How do I add images or links to my slider content?**
A: You can use standard HTML tags within the “Template Content” field:

- **Images:** `<img src="your_image_url.jpg" alt="Description" style="width:100px;">` (Use absolute URLs for images).
- **Links:** `<a href="your_page_url.html">Click Here</a>` (You can also use Smarty variables for PrestaShop links, e.g., `<a href="{$link->getPageLink('contact')}">Contact Us</a>`).

**Q: Does it work with multi-language and multi-store?**
A: Yes, the module is designed to work correctly in multi-language and multi-store environments. You can create different sliders or different content for the same slider for each language and store, allowing for highly targeted messaging.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Custom contents slider” module (`saslider`) is built as a standard PrestaShop module, primarily leveraging the `Module` class for its lifecycle and `SmartyTemplatesManager` for dynamic content creation and management. It integrates with PrestaShop’s hook system to inject its front-office assets and content. The module’s core logic resides within its main `index.php` file, handling configuration, installation, and front-office rendering. It does not utilize dedicated front or admin controllers but rather relies on the `getContent()` method for its back-office configuration and direct hook registration for front-office display.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office rendering is handled directly via registered hooks within the main module file.
- **Back-Office Admin Controllers**: None. All back-office configuration is managed through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

The module does not define custom classes extending `ObjectModel`. Its primary data storage for slider configurations is likely handled via `Configuration::updateValue()` for module-level settings and potentially serialized data stored in `ps_configuration` for individual slider content and properties, managed by the `SmartyTemplatesManager` library.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily responsible for the sliding animation and interaction (click/hover) logic for different slider positions.

- `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

  - **Scope**: Back-office.
  - **Responsibility**: This script is part of the `SmartyTemplatesManager` library. It likely handles the dynamic creation, editing, and management of templates (sliders) within the module’s configuration interface. It might manage form submissions, AJAX calls for saving/loading content, and UI interactions for the template management system.
- `saslider/views/js/saslider-click-bottom.js`

  - **Scope**: Front-office.
  - **Responsibility**: Implements the JavaScript logic for a bottom-positioned slider that expands/collapses on a click event. It will bind click listeners to the slider’s trigger element, toggle CSS classes or directly manipulate `style` properties to animate the slider’s expansion and contraction.
- `saslider/views/js/saslider-click-left.js`

  - **Scope**: Front-office.
  - **Responsibility**: Similar to `saslider-click-bottom.js`, but specifically for a left-positioned slider, handling its click-based expansion/contraction.
- `saslider/views/js/saslider-click-right.js`

  - **Scope**: Front-office.
  - **Responsibility**: Similar to `saslider-click-bottom.js`, but specifically for a right-positioned slider, handling its click-based expansion/contraction.
- `saslider/views/js/saslider-hover-bottom.js`

  - **Scope**: Front-office.
  - **Responsibility**: Implements the JavaScript logic for a bottom-positioned slider that expands/collapses on a hover event. It will bind `mouseenter` and `mouseleave` listeners to the slider’s trigger element, toggling its visibility and position.
- `saslider/views/js/saslider-hover-left.js`

  - **Scope**: Front-office.
  - **Responsibility**: Similar to `saslider-hover-bottom.js`, but specifically for a left-positioned slider, handling its hover-based expansion/contraction.
- `saslider/views/js/saslider-hover-right.js`

  - **Scope**: Front-office.
  - **Responsibility**: Similar to `saslider-hover-bottom.js`, but specifically for a right-positioned slider, handling its hover-based expansion/contraction.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes several CSS files for both back-office configuration styling and front-office slider appearance.

- `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

  - **Scope**: Back-office admin form styling.
  - **Main UI components**: Styles the elements of the `SmartyTemplatesManager` interface, including forms, buttons, input fields, and potentially list tables for managing templates.
  - **Key CSS class selectors**: Likely includes classes for form layouts, input groups, and general administrative UI components.
- `saslider/views/css/saslider-bottom.css`

  - **Scope**: Front-office customer styling.
  - **Main UI components**: Defines the specific positioning, initial state (collapsed), and animation properties for the bottom-positioned slider.
  - **Key CSS class selectors**: `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, classes for `open`/`closed` states.
- `saslider/views/css/saslider-left.css`

  - **Scope**: Front-office customer styling.
  - **Main UI components**: Defines the specific positioning, initial state, and animation properties for the left-positioned slider.
  - **Key CSS class selectors**: `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, classes for `open`/`closed` states.
- `saslider/views/css/saslider-right.css`

  - **Scope**: Front-office customer styling.
  - **Main UI components**: Defines the specific positioning, initial state, and animation properties for the right-positioned slider.
  - **Key CSS class selectors**: `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, classes for `open`/`closed` states.
- `saslider/views/css/saslider.css`

  - **Scope**: Front-office customer styling.
  - **Main UI components**: Contains general, common styles applicable to all slider positions, such as base container styles, font sizes, colors, z-index, and transition properties.
  - **Key CSS class selectors**: `.saslider-container`, `.saslider-tab`, `.saslider-content`, and potentially responsive adjustments.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates for both its back-office configuration interface and front-office content rendering.

- **Admin templates (`saslider/lib/smartyTemplatesManager/views/`)**:

  - `buttonManager.tpl`: Likely renders the UI for managing the slider’s trigger button/tab.
  - `createTemplateForm.tpl`: The form template used when creating a new slider.
  - `editTemplateForm.tpl`: The form template used when editing an existing slider.
  - `mainForm.tpl`: The main configuration page template, likely listing all sliders and providing the “Add New” button.
  - `selectInput.tpl`: A reusable template for rendering dropdown `<select>` elements within the admin forms.
- **Hook templates (`saslider/views/`)**:

  - `footer-bottom.tpl`: Renders the HTML structure for a bottom-positioned slider. This template is likely hooked into `displayFooter` or a similar global hook. It contains the wrapper `div`s for the slider, its trigger tab, and the content area.
  - `footer-left.tpl`: Renders the HTML structure for a left-positioned slider. Likely hooked into `displayFooter` or similar.
  - `footer-right.tpl`: Renders the HTML structure for a right-positioned slider. Likely hooked into `displayFooter` or similar.
- **Example/Utility templates (`saslider/lib/smartyTemplatesManager/tpl/`)**:

  - `example.tpl`: An example template, possibly for demonstration or internal testing of the `SmartyTemplatesManager`.
  - `MyShortCode.tpl`: Suggests the `SmartyTemplatesManager` might support some form of shortcode or dynamic content insertion.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not explicitly define custom SQL tables via `install.sql`.
  - Configuration for individual sliders (content, position, active status, open on) is stored in the `ps_configuration` table, likely as serialized data under specific configuration keys managed by the `SmartyTemplatesManager` library. For example, `PS_SASLIDER_TEMPLATES` or similar.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Used to register CSS and JavaScript assets (e.g., `saslider.css`, `saslider-click-right.js`) required for the slider’s front-office display and functionality. |
| `displayFooter` | At the end of the `<body>` section of every page, before the closing `</body>` tag. | Used to render the actual HTML structure of the slider (e.g., `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) into the page, ensuring it floats correctly. |
| `displayLeftColumn` | In the left column of the store. | *Potentially* used to render the slider, though `displayFooter` is more common for floating elements. |
| `displayRightColumn` | In the right column of the store. | *Potentially* used to render the slider, though `displayFooter` is more common for floating elements. |
| `displayProductAdditionalInfo` | On the product page, below the main product information. | *Potentially* used to render a slider specifically on product pages, e.g., for related offers. |
| `actionFrontControllerSetMedia` | After a front controller has set its media, allowing modules to add their own. | Used to conditionally add CSS/JS files based on the current page or other conditions, ensuring optimal loading. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the “Custom contents slider” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely assistance and ensuring your module runs smoothly with your PrestaShop store.
