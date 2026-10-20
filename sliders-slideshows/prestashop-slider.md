---
title: "Prestashop Slider - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Prestashop Slider PrestaShop module by MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Prestashop Slider Module on MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most web hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main control panel for your Prestashop Slider. Here you’ll define the look, feel, and content of your sliders.

#### **General Settings**

- **What this setting does:** These settings control the overall behavior and appearance of your slider.
- **Effect of changing this setting:**
  - *Slider Width:* Defines how wide the slider will be. Can be a fixed pixel value or a percentage for responsiveness.
  - *Slider Height:* Defines the height of the slider.
  - *Animation Type:* Selects one of the 40 available transition effects between slides.
  - *Animation Speed:* Controls how fast the transition between slides occurs.
  - *Slide Interval:* Sets the duration each slide is displayed before automatically transitioning to the next.
  - *Navigation Arrows:* Enables/disables the left/right arrows for manual slide navigation.
  - *Navigation Dots/Bullets:* Enables/disables the small dots usually found at the bottom of the slider for direct slide selection.
  - *Thumbnails:* Enables/disables small preview images of each slide, often displayed below the main slider.
  - *Thumbnail Preview:* If thumbnails are enabled, this setting controls whether a larger preview appears when hovering over a thumbnail.
  - *Caption Display:* Controls if and how text captions associated with each slide are shown.
- **Recommended value:**
  - *Slider Width:* `100%` for a full-width, responsive slider, or a specific pixel value like `1140px` to match your theme’s main content area.
  - *Slider Height:* Start with `400px` and adjust based on your image aspect ratio and design.
  - *Animation Type:* Experiment! `fade` or `slice` are good starting points for a clean look.
  - *Animation Speed:* `800` (milliseconds) for a smooth transition.
  - *Slide Interval:* `5000` (5 seconds) is a good balance for users to read content without feeling rushed.
  - *Navigation Arrows:* `YES` for better user control.
  - *Navigation Dots/Bullets:* `YES` for easy overview and navigation.
  - *Thumbnails:* `NO` initially, enable if you have many slides and want a visual index.
  - *Thumbnail Preview:* `YES` if thumbnails are enabled.
  - *Caption Display:* `YES` if you plan to add text to your slides.
- **Merchant scenario / example:** You want a full-width banner on your homepage that rotates through three new product lines. You’d set width to `100%`, choose a `fade` animation, and set a `5-second` interval. You’d enable navigation arrows and dots so customers can browse manually if they wish.

#### **Slide Management Section**

- **What this setting does:** This section allows you to add, edit, and remove individual slides from your slider. Each slide consists of an image and associated settings.
- **Effect of changing this setting:**
  - *Adding a new slide:* A new image will be added to your slider rotation. You’ll upload an image, define its link, caption, and potentially a unique animation.
  - *Editing an existing slide:* You can change the image, its destination link, the caption text, or the individual animation type for that specific slide.
  - *Deleting a slide:* The selected slide will be removed from your slider.
  - *Reordering slides:* You can drag and drop slides to change the order in which they appear in the rotation.
- **Recommended value:** Always use high-quality, optimized images that are consistent in size and aspect ratio for a professional look.
- **Merchant scenario / example:** You’re launching a new summer collection. You’d add three slides: one for dresses, one for swimwear, and one for accessories. Each slide would feature a hero image, a caption like “Shop Summer Dresses Now!”, and a link directly to the respective category page. You might give the swimwear slide a “cube” animation for a playful feel, while the others use “fade”.

#### **Hook Selection**

- **What this setting does:** This allows you to choose where in your PrestaShop store the slider will be displayed.
- **Effect of changing this setting:** By selecting a hook (e.g., `displayHeader`, `displayLeftColumn`), the module will inject the slider’s code into that specific area of your theme.
- **Recommended value:**
  - For a prominent, full-width banner: `displayHeader` or a custom hook provided by your theme for top banners.
  - For a smaller, contextual slider: `displayLeftColumn` or `displayRightColumn`.
  - For product-specific sliders: `displayProductExtraContent` or `displayProductButtons`.
- **Merchant scenario / example:** You want your main promotional slider to appear right below your website’s main menu. You would select the `displayHeader` hook (or a similar theme-specific hook if available). If you wanted a smaller slider showing “related products” on the side, you’d choose `displayLeftColumn`.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Slider Width | `100%` / `1140px` | Sets the horizontal size of the slider. |
| Module Configuration | Slider Height | `400px` | Sets the vertical size of the slider. |
| Module Configuration | Animation Type | `fade` / `slice` | Defines the visual transition between slides (40 options). |
| Module Configuration | Animation Speed | `800` (ms) | How fast the animation transition occurs. |
| Module Configuration | Slide Interval | `5000` (ms) | How long each slide is visible before changing. |
| Module Configuration | Navigation Arrows | `YES` | Displays left/right arrows for manual navigation. |
| Module Configuration | Navigation Dots/Bullets | `YES` | Displays dots/bullets for direct slide selection. |
| Module Configuration | Thumbnails | `NO` | Displays small preview images of each slide. |
| Module Configuration | Thumbnail Preview | `YES` | Shows a larger preview on thumbnail hover (if enabled). |
| Module Configuration | Caption Display | `YES` | Controls visibility of text captions on slides. |
| Module Configuration | Add/Edit Slide | N/A | Upload image, set link, caption, and individual animation. |
| Module Configuration | Hook Selection | `displayHeader` | Determines where the slider appears in your store. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My slider isn’t showing up after configuration. What should I do?**
A:

1. **Check Hook Selection:** Go back to the module configuration and ensure you’ve selected at least one hook (e.g., `displayHeader`).
2. **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance**, and click “Clear cache” (or “Clear Smarty cache” in older versions).
3. **Check for Conflicts:** Temporarily disable other modules that might be using the same hook or modifying the same page areas (especially other slider modules).
4. **Theme Compatibility:** Some highly customized themes might require minor adjustments. If the issue persists, contact MyPresta.eu support with your theme details.

**Q: My images look blurry or stretched in the slider.**
A: This usually means your images are not the correct dimensions or resolution for your slider settings.

1. **Consistent Dimensions:** Ensure all images uploaded for your slides have the same width and height.
2. **High Resolution:** Upload images with sufficient resolution. If your slider is `1140px` wide, your images should be at least `1140px` wide.
3. **Aspect Ratio:** Match the aspect ratio of your images to the slider’s configured width and height. If your slider is `1140x400px`, try to use images with a similar 114:40 aspect ratio.

**Q: How do I translate the captions for my slides into different languages?**
A: The module should support PrestaShop’s standard translation system.

1. Go to **International > Translations**.
2. Select “Installed modules translations”, your theme, and the language you want to translate.
3. Find the “Prestashop Slider” module in the list. You should be able to edit the captions for each slide directly there. If not, the module might store captions directly in the database, requiring you to edit each slide for each language in the module’s configuration.

**Q: The slider looks fine on desktop but is broken on mobile.**
A:

1. **Check Responsiveness:** The module is designed to be responsive. Ensure your theme itself is responsive.
2. **CSS Conflicts:** Another module or your theme’s CSS might be overriding the slider’s responsive styles. Use your browser’s developer tools to inspect the slider on mobile and look for conflicting CSS rules.
3. **Image Size:** Very large images can sometimes cause issues on mobile. Ensure images are optimized.

**Q: Can I have multiple sliders on different pages?**
A: The current module configuration typically manages one main slider instance with its set of slides. If you need multiple *distinct* sliders with different content and settings on different pages, you might need to duplicate the module (if your theme allows it) or use a more advanced slider solution. For this module, you’d configure one slider and choose its placement via hooks.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the Prestashop Slider module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The `Prestashop Slider` module (`pslider`) is a standard PrestaShop module primarily leveraging the `Module` class. It manages its configuration and slide data directly within the `ps_configuration` table. The front-office display is handled by Smarty templates rendered via PrestaShop’s hook system, injecting JavaScript and CSS assets for the slider functionality. The module uses the `Skitter` jQuery plugin for its animation capabilities.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled directly within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom classes extending `ObjectModel`. All configuration and slide data are stored as serialized arrays within the `ps_configuration` table, managed directly by the `Configuration` class.

### 4.4 JavaScript Assets (`views/js/`)

The module relies on the Skitter jQuery plugin for its slider functionality.

- `pslider/js/jquery.easing.1.3.js`:
  - **Scope:** Front-office.
  - **Purpose:** Provides advanced easing functions for jQuery animations, enhancing the visual smoothness of transitions used by the Skitter plugin.
- `pslider/js/jquery.skitter.js`:
  - **Scope:** Front-office.
  - **Purpose:** This is the core Skitter slider plugin. It initializes the slider, handles slide transitions, navigation, and responsiveness. It reads configuration options (animation type, speed, interval, etc.) from the module’s settings and applies them to the slider instance.
- `pslider/js/noconflict.js`:
  - **Scope:** Front-office.
  - **Purpose:** Ensures jQuery operates in `noConflict()` mode, preventing conflicts with other JavaScript libraries (like Prototype.js, which PrestaShop 1.6 and earlier sometimes used) that might also use the `$` alias. This is crucial for compatibility.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes a single CSS file for styling the Skitter slider.

- `pslider/css/skitter.styles.css`:
  - **Scope:** Front-office customer styling.
  - **Purpose:** Contains all the default visual styles for the Skitter slider, including:
    - Layout of the slider container (`.box_skitter`).
    - Styling for navigation elements (arrows, dots, thumbnails).
    - Default appearance of captions.
    - Responsive adjustments.
  - **Key CSS class selectors developers can override:**
    - `.box_skitter`: Main slider container.
    - `.box_skitter ul`: List of slides.
    - `.box_skitter .info_slide`: Caption container.
    - `.box_skitter .nav_cont`: Navigation container.
    - `.box_skitter .prev_button`, `.box_skitter .next_button`: Navigation arrows.
    - `.box_skitter .info_slide_dots`: Navigation dots.
    - `.box_skitter .box_thumbs`: Thumbnail container.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses Smarty templates to render its front-office content and parts of its back-office configuration.

- **Hook templates (`views/templates/hook/`)**:

  - `pslider/header.tpl`: This template is likely intended to be hooked into `displayHeader` or a similar top-of-page hook. It contains the main HTML structure for the slider and often includes the necessary JavaScript initialization code for the Skitter plugin.
  - `pslider/top.tpl`: Similar to `header.tpl`, this might be used for a different top-level hook, potentially `displayTop` or another theme-specific banner hook. It would also contain the slider’s HTML and JS initialization.
  - `pslider/views/templates/hook/left-column.tpl`: This template is specifically designed for placement in the `displayLeftColumn` hook. It would contain a smaller, potentially different instance of the slider or a modified layout suitable for a sidebar.
- **Admin templates (`views/templates/admin/`)**:

  - `pslider/views/templates/front/form.tpl`: Despite being in `views/templates/front/`, this file is actually used for the module’s configuration form in the Back Office. It defines the HTML structure for the settings fields (width, height, animation, slide management, etc.) that the merchant interacts with. This is rendered by the `getContent()` method in `ajax_pslider.php`.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables.
  - All configuration settings and slide data (image paths, links, captions, individual animation types) are stored as serialized arrays within the `ps_configuration` table. Key names would typically follow a pattern like `PSLIDER_WIDTH`, `PSLIDER_SLIDES`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of the front-office page, or at the very top of the `<body>`. | Injects CSS and JavaScript assets, and potentially the main slider HTML structure. |
| `displayTop` | Renders at the top of the page content, typically above the main content area but below the header. | Displays the main slider banner. |
| `displayLeftColumn` | Renders in the left sidebar of the front-office page. | Displays a sidebar-specific slider. |
| `displayRightColumn` | Renders in the right sidebar of the front-office page. | Displays a sidebar-specific slider. |
| `displayFooter` | Renders in the footer section of the front-office page. | Displays a footer-specific slider. |
| `displayProductExtraContent` | Renders on the product page, typically below the main product information. | Displays product-related sliders (e.g., alternative views, features). |
| `displayProductButtons` | Renders near the “Add to Cart” button on the product page. | Could be used for small, contextual product-related sliders. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media assets. | Allows the module to register its JS and CSS files conditionally. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Prestashop Slider module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have.
