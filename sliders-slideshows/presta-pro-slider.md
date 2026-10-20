---
title: "Presta Pro Slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Presta Pro Slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Presta Pro Slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Presta Pro Slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No unusual server configurations are required.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Presta Pro Slider)

This is the main configuration screen where you manage the overall settings for your slider and add/edit individual slides.

#### General Slider Settings

- **What this setting does:** These settings control the overall appearance and behavior of your slider, such as its dimensions, animation speed, and where it appears on your site.
- **Effect of changing this setting:** Adjusting these values will directly impact how the slider looks and functions for your customers.

| Setting / Option | What it does | Effect of changing | Recommended Value | Merchant Scenario / Example |
| --- | --- | --- | --- | --- |
| **Slider Width (px)** | Sets the total width of the slider in pixels. | *If set to 1000:* The slider will be 1000 pixels wide. *If set to 500:* The slider will be 500 pixels wide. | `100%` (for full width) or a specific pixel value like `1170` (common for content areas). | You want your slider to span the entire content area of your homepage, which is 1170px wide. You would enter `1170`. If you want it to be responsive and take full available width, use `100%`. |
| **Slider Height (px)** | Sets the total height of the slider in pixels. | *If set to 400:* The slider will be 400 pixels tall. *If set to 250:* The slider will be 250 pixels tall. | `350` - `500` (depending on image content). | You have high-quality banner images that look best at a certain height. You’d set this to `450` to ensure your images are displayed without being too stretched or squashed. |
| **Animation Speed (ms)** | Controls how fast the transition between slides occurs, in milliseconds. | *If set to 500:* Slides transition quickly (0.5 seconds). *If set to 2000:* Slides transition slowly (2 seconds). | `1000` (1 second) | You want a smooth, noticeable transition between your promotional slides, but not so slow that customers get bored. Setting it to `1000` provides a good balance. |
| **Autoplay** | Determines if the slider automatically advances to the next slide. | *When enabled (YES):* Slides will automatically change after a set delay. *When disabled (NO):* Slides will only change when a customer clicks navigation arrows or dots. | `YES` | You want your main promotions to cycle automatically on the homepage without customer interaction. |
| **Autoplay Speed (ms)** | If Autoplay is enabled, this sets the delay before the next slide appears, in milliseconds. | *If set to 5000:* Each slide displays for 5 seconds. *If set to 3000:* Each slide displays for 3 seconds. | `5000` (5 seconds) | You have a lot of text on your slides and want to give customers enough time to read it before the next slide appears. Setting it to `7000` (7 seconds) would be appropriate. |
| **Display on Hook** | Selects the PrestaShop hook where the slider will be displayed. | *If set to `displayHeader`*: The slider appears at the top of every page. *If set to `displayLeftColumn`*: The slider appears in the left sidebar. | `displayHome` (if available, otherwise `displayHeader` or `displayTop`) | You want the slider to be a prominent feature on your homepage. You would select `displayHome` or `displayTop`. If you want it on product pages, you might select `displayProductFooter`. |
| **Background Color** | Sets the background color of the slider container. | *If set to #FFFFFF:* The background will be white. *If set to #000000:* The background will be black. | `Leave empty` (for transparent) or a color matching your theme. | Your theme has a light background, and you want the slider to blend in seamlessly. You would set this to `#FFFFFF`. |
| **Text Color** | Sets the default color for text within the slider (captions, descriptions). | *If set to #000000:* Text will be black. *If set to #FF0000:* Text will be red. | `#333333` (dark grey) | Your slider images are bright, and you need dark text to ensure readability. You’d set this to `#333333`. |

#### Slide Management Section

This section allows you to add, edit, and delete individual slides that make up your slideshow.

- **Add New Slide Button:** Click this to open a form for creating a brand new slide.
- **Existing Slides List:** Displays a table of all your currently active slides, usually with options to edit or delete them.

### 2.2 Dedicated Admin Screens & Controller Views

#### AdminprosliderController (Back Office > Modules > Presta Pro Slider > Configure > “Add New Slide” or “Edit” an existing slide)

This screen appears when you click “Add New Slide” or the “Edit” button next to an existing slide in the main configuration. It allows you to define the content and behavior of each individual slide.

- **Screen Name & Menu Location:** Accessed from the main module configuration page by clicking “Add New Slide” or the edit icon for an existing slide.
- **Available Actions & Settings:** This form allows you to input all the details for a single slide.

| Setting / Option | What it does | Effect of changing | Recommended Value | Merchant Scenario / Example |
| --- | --- | --- | --- | --- |
| **Slide Title (Caption)** | The main heading or short text displayed on the slide. | This text will appear prominently on your slide, usually in a larger font. | Keep it concise and impactful. | “Summer Sale!” or “New Arrivals” |
| **Slide Description** | Longer text providing more details about the slide’s content. | This text will appear below the title, offering more information to the customer. | Provide enough detail without being overwhelming. | “Up to 50% off on all swimwear for a limited time!” |
| **Slide Image** | The main background image for this specific slide. | This image will be the visual centerpiece of your slide. | High-quality, relevant image with good resolution. | An attractive picture of a model wearing a new dress for a fashion promotion. |
| **Link URL** | The web address (URL) where customers will be directed when they click on this slide. | *If set:* Clicking the slide takes the customer to this URL. *If empty:* The slide will not be clickable. | A valid URL to a product, category, or informational page. | Link to your “New Arrivals” category page: `https://yourstore.com/new-arrivals` |
| **Open in New Window** | Determines if the link URL opens in a new browser tab/window. | *When enabled (YES):* The link opens in a new tab, keeping your store open in the original tab. *When disabled (NO):* The link opens in the same tab, navigating away from your current page. | `YES` (generally recommended for external links or promotions) | You’re linking to an external blog post or a social media profile. You’d enable this to keep your customers on your PrestaShop store. |
| **Active** | Controls whether this slide is currently visible in the slider. | *When enabled (YES):* The slide will be part of the slideshow. *When disabled (NO):* The slide will be hidden but not deleted, allowing you to reactivate it later. | `YES` for active promotions. | You have a seasonal promotion that’s over, but you might run it again next year. You’d set it to `NO` instead of deleting it. |
| **Order / Position** | Sets the display order of this slide relative to others. | Slides with lower numbers appear earlier in the sequence. | `1`, `2`, `3`, etc., in desired order. | You want your “Summer Sale” slide to appear first, followed by “New Arrivals.” You’d set “Summer Sale” to `1` and “New Arrivals” to `2`. |

- **Recommended workflow for daily store management:**
  1. **Plan your promotions:** Decide what products, categories, or messages you want to highlight.
  2. **Prepare your images:** Ensure you have high-quality images that fit the slider’s dimensions.
  3. **Add new slides:** Use the “Add New Slide” button to create new content. Fill in all details, including title, description, image, and link.
  4. **Order your slides:** Adjust the “Order / Position” to control the sequence.
  5. **Activate/Deactivate:** Use the “Active” toggle to manage visibility without deleting content.
  6. **Review on front-office:** Always check your slider on the live store to ensure it looks and functions as expected.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Slider Width (px) | `100%` or `1170` | Sets the horizontal size of the slider. |
|  | Slider Height (px) | `350` - `500` | Sets the vertical size of the slider. |
|  | Animation Speed (ms) | `1000` | Controls how fast slides transition. |
|  | Autoplay | `YES` | Automatically advances slides. |
|  | Autoplay Speed (ms) | `5000` | Delay between automatic slide changes. |
|  | Display on Hook | `displayHome` / `displayHeader` | Where the slider appears in your store. |
|  | Background Color | `Leave empty` / `#FFFFFF` | Background color of the slider area. |
|  | Text Color | `#333333` | Default text color for captions/descriptions. |
| **Add/Edit Slide** | Slide Title (Caption) | Concise & impactful | Main heading for the slide. |
|  | Slide Description | Informative | Detailed text for the slide. |
|  | Slide Image | High-quality image | Visual background for the slide. |
|  | Link URL | Valid URL | Destination when slide is clicked. |
|  | Open in New Window | `YES` | Opens link in a new browser tab. |
|  | Active | `YES` | Toggles slide visibility. |
|  | Order / Position | `1, 2, 3...` | Determines the sequence of slides. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My slider isn’t showing up on the front office, or it’s showing in the wrong place.**

- **A:** First, check the “Display on Hook” setting in the module configuration. Ensure you’ve selected the correct hook (e.g., `displayHeader`, `displayTop`, `displayHome`). If your theme has custom hook names or doesn’t explicitly support a standard hook in that location, the slider might not appear.
- **A:** Also, verify that individual slides are marked as “Active” in their settings. If no slides are active, nothing will display.
- **A:** Finally, clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, and click “Clear cache” in the top right. Sometimes, changes don’t appear until the cache is refreshed.

**Q2: My slider images look blurry or stretched.**

- **A:** This usually happens if your uploaded images don’t match the “Slider Width” and “Slider Height” settings, or if they are low resolution.
- **A:** **Solution:** Ensure your images are high-resolution and ideally have the same aspect ratio as your configured slider dimensions. For example, if your slider is 1200px wide and 400px high, try to upload images that are at least 1200px by 400px. You might need to resize or crop your images before uploading them.

**Q3: The text on my slides is hard to read.**

- **A:** This is often a contrast issue between your “Slide Image” and the “Text Color” you’ve chosen.
- **A:** **Solution:**
  1. Adjust the “Text Color” in the main module configuration to a color that contrasts well with your images (e.g., white text on dark images, black text on light images).
  2. Consider adding a subtle overlay to your images (you might need a graphic editor for this) to darken or lighten them slightly, making the text pop more.
  3. Keep your “Slide Title” and “Slide Description” concise. Less text is often easier to read quickly.

**Q4: How do I translate the slide titles and descriptions into different languages?**

- **A:** When you are editing a slide, you should see language selection tabs next to the “Slide Title” and “Slide Description” fields (if your PrestaShop store has multiple languages enabled).
- **A:** **Solution:** Click on the flag icon or language tab for each language you want to translate, and then enter the corresponding text for that language. Remember to save your changes.

**Q5: The slider animations are too fast/slow, or autoplay isn’t working.**

- **A:** Check the “Animation Speed (ms)”, “Autoplay”, and “Autoplay Speed (ms)” settings in the main module configuration.
- **A:** **Solution:**
  - Increase “Animation Speed” for slower transitions, decrease for faster.
  - Ensure “Autoplay” is set to `YES` if you want slides to advance automatically.
  - Adjust “Autoplay Speed” to control how long each slide is displayed before moving to the next. Remember these values are in milliseconds (1000ms = 1 second).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Presta Pro Slider module follows a standard PrestaShop module architecture, leveraging the MVC pattern where appropriate. It primarily uses a single main module file (`ajax_proslider.php`) for its core logic and configuration, an administrative controller for managing slides, and front-office templates for rendering the slider. It relies on jQuery and Modernizr for its front-end animations and styling. Slide data is stored directly within PrestaShop’s `ps_configuration` table, rather than a dedicated `ObjectModel` and custom database table.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:

  - `controllers/front/default.php`
    - **Class name & parent class**: `ProsliderDefaultModuleFrontController` extending `ModuleFrontController`.
    - **Responsibility**: This controller is likely intended for a default route or specific front-office action, though its exact purpose might be minimal given the module primarily hooks into existing template areas. It would handle requests to `yourstore.com/module/proslider/default` and could be used for AJAX calls or rendering a standalone page if the module had one. In this module’s context, it might be a placeholder or used for specific data retrieval if the slider content was dynamically loaded.
- **Back-Office Admin Controllers**:

  - `controllers/admin/adminproslider.php`
    - **Class name & parent class**: `AdminprosliderController` extending `ModuleAdminController`.
    - **Tab name and managed entity**: This controller manages the “slides” or “opinions” (as per the dossier, though “opinion” seems like a typo and should likely be “slide” or “proslider\_item” if it were an ObjectModel). It provides the interface for adding, editing, and deleting individual slides. It handles the form submission for slide details (title, description, image, link, etc.) and updates the `ps_configuration` table or a custom table if one were present.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes or models in the `classes/` directory. This suggests that the module stores its data directly in the `ps_configuration` table using serialized arrays or individual configuration keys for each slide, or it might be using a simpler, non-ORM approach within the `AdminprosliderController` to manage data. If it were using `ObjectModel`, there would be a class defined here (e.g., `ProsliderSlide.php`).

### 4.4 JavaScript Assets (`views/js/`)

- `proslider/js/jquery.cslider.js`
  - **Scope**: Front-office.
  - **Description**: This is likely the core jQuery plugin responsible for the animated slider functionality. It handles slide transitions, autoplay logic, navigation controls, and responsiveness. Developers should consult this file for understanding the slider’s animation types and available options.
- `proslider/js/jscolor/jscolor.js`
  - **Scope**: Back-office.
  - **Description**: A JavaScript library for a color picker widget. It’s used in the module’s back-office configuration forms to allow merchants to easily select background and text colors for the slider.
- `proslider/js/modernizr.custom.28468.js`
  - **Scope**: Front-office.
  - **Description**: Modernizr is a JavaScript library that detects HTML5 and CSS3 features in the user’s browser. This specific custom build is likely used by `jquery.cslider.js` to provide feature detection and potentially fallback mechanisms for older browsers, ensuring smooth animations and compatibility.
- `proslider/js/script.js`
  - **Scope**: Front-office.
  - **Description**: This is the module’s main custom JavaScript file. It initializes the `jquery.cslider.js` plugin with the specific settings configured in the back office (width, height, speed, autoplay, etc.). It binds event listeners for slider navigation (if any custom ones are implemented) and ensures the slider functions correctly within the PrestaShop environment.
- `proslider/tinymce16.inc.js`
  - **Scope**: Back-office.
  - **Description**: This file is an include for the TinyMCE rich text editor, specifically configured for PrestaShop 1.6.x. It’s used in the back-office forms for “Slide Description” fields, allowing merchants to format text with HTML. For PrestaShop 1.7.x and 8.x, PrestaShop’s native TinyMCE integration might be used, or this file could still be loaded for compatibility.

### 4.5 CSS Stylesheets (`views/css/`)

- `proslider/css/style2.css`
  - **Scope**: Front-office customer styling.
  - **Description**: This is the primary stylesheet for the front-end slider. It defines the visual appearance of the slider container, individual slides, captions, descriptions, navigation arrows, and pagination dots.
  - **Key CSS class selectors**: Developers can inspect this file for classes like `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots` to override or extend styling in their theme’s custom CSS.
- `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
  - **Scope**: Back-office admin form styling.
  - **Description**: This is a custom build of the jQuery UI CSS framework, specifically for the “UI-lightness” theme. It’s likely used to style elements within the module’s back-office configuration forms, such as date pickers (if any), buttons, or other UI widgets that might be part of the slide management interface.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - `proslider/header.tpl`
    - **Hook**: Likely intended for `displayHeader` or `displayTop`.
    - **Output**: This template would contain the main HTML structure for the slider, including the `div` elements that `jquery.cslider.js` targets, and potentially the loop to render individual slides based on the data passed from the module. It might also include the necessary JS and CSS includes.
  - `proslider/top.tpl`
    - **Hook**: Likely intended for `displayTop` or `displayNav`.
    - **Output**: Similar to `header.tpl`, this would render the slider in the top section of the store, often below the main navigation.
  - `proslider/views/templates/hook/left-column.tpl`
    - **Hook**: `displayLeftColumn` or `displayRightColumn`.
    - **Output**: This template renders a potentially smaller or differently styled version of the slider specifically for the side columns of the store.
- **Admin templates (`views/templates/admin/`)**:

  - `proslider/views/templates/front/form.tpl`
    - **Hook**: This path suggests it’s a front-office template, but the context of `AdminprosliderController` implies it might be used for the *form* to add/edit slides within the admin. This is a common pattern where a module might reuse a “form” template for both front-end (if applicable) and back-end data entry.
    - **Output**: This template would define the HTML form structure for adding or editing a single slide, including input fields for title, description, image upload, URL, active status, and position.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module dossier indicates no custom SQL files. This strongly suggests that the module stores its configuration and slide data directly within PrestaShop’s `ps_configuration` table. Each slide’s data (title, description, image, link, etc.) would likely be serialized into a single configuration key, or multiple keys per slide, e.g., `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE`, etc. This approach is simpler but less scalable than using a dedicated `ObjectModel`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injecting CSS/JS assets and potentially the main slider HTML structure. |
| `displayTop` | Typically below the main navigation, above the content. | Displaying the main slider in a prominent top position. |
| `displayHome` | On the homepage content area. | Displaying the slider as a central feature on the homepage. |
| `displayLeftColumn` | In the left sidebar of pages that have one. | Displaying a smaller, contextual slider in the left column. |
| `displayRightColumn` | In the right sidebar of pages that have one. | Displaying a smaller, contextual slider in the right column. |
| `displayProductFooter` | At the bottom of product pages. | Displaying a slider related to the product (e.g., accessories, related items). |
| `displayFooter` | In the footer section of every page. | Displaying a slider for secondary promotions or brand content. |
| `actionFrontControllerSetMedia` | Before a front controller renders its output, after media is set. | Registering module-specific CSS and JavaScript files for front-office pages. |
| `actionAdminControllerSetMedia` | Before an admin controller renders its output, after media is set. | Registering module-specific CSS and JavaScript files for back-office pages (e.g., for the color picker or TinyMCE). |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing assistance and ensuring the smooth operation of your Presta Pro Slider module.
