---
title: "Custom contents carousel - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Custom contents carousel PrestaShop module by MyPresta.eu."
sidebar:
  label: "Custom contents carousel - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Custom contents carousel Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/custom-contents-carousel/)
>
> ---


# Custom contents carousel

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Custom contents carousel” module organizes its settings across several screens in your PrestaShop Back Office. You’ll first configure global settings, then create “Groups” (which are your carousels), and finally add “Items” (the individual slides) to each group.

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Custom contents carousel)

This is the main configuration screen for the module, accessible immediately after installation or by clicking “Configure” from the Module Manager.

- **What this setting does:** This screen primarily handles general module settings and update checks.
- **Effect of changing this setting:**
  - `mypresta_updates`, `update_`, `updatev_`: These are internal settings used by MyPresta.eu modules to manage updates and version checks. They do not directly affect the front-office display but ensure your module stays up-to-date.
  - `CCAROUSEL_LIGHTSLIDER`: This setting likely controls the activation of the LightSlider JavaScript library, which powers the carousel functionality.
    - *When enabled (YES)*: The LightSlider library will be loaded on your front office, allowing carousels to function correctly.
    - *When disabled (NO)*: The LightSlider library might not load, potentially breaking the carousel display and functionality.
- **Recommended value:**
  - `CCAROUSEL_LIGHTSLIDER`: **YES** (Enabled). This is crucial for the carousel to work.
  - Other settings: Leave as default.
- **Merchant scenario / example:** You’ve just installed the module and want to ensure all necessary scripts are loaded. You’d check that `CCAROUSEL_LIGHTSLIDER` is enabled. If you ever experience issues with the carousel not sliding, this would be one of the first places to check.

### 2.2 Dedicated Admin Screen: Custom Contents Groups (Back Office > Modules > Custom contents carousel > Custom Contents Groups)

This screen allows you to create and manage your individual carousels. Each “group” represents a distinct carousel that you can then populate with slides.

- **Screen Name & Menu Location:** You’ll find this under **Modules > Custom contents carousel > Custom Contents Groups** in your PrestaShop Back Office menu.
- **Available Actions & Settings:**
  - **Grid View**: Displays a list of all your existing carousel groups. You can see their names, status (active/inactive), and actions.
  - **Add New Group**: Click the “Add new” button to create a brand new carousel.
  - **Edit/Delete Group**: For each group, you’ll have options to edit its settings (e.g., name, display options) or delete it entirely.
  - **Status Toggle**: Quickly activate or deactivate a carousel group without deleting it. An inactive group will not appear on your front office.
- **Effect of changes:**
  - **Adding a new group**: Creates a new, empty carousel container. You’ll then need to add items (slides) to it.
  - **Editing a group**: Allows you to change the name of the carousel, its display settings (e.g., auto-play, speed, number of visible slides), and its position.
  - **Activating/Deactivating**: Controls whether the carousel is visible to your customers on the front office.
  - **Deleting a group**: Permanently removes the carousel and all its associated items (slides).
- **Recommended workflow for daily store management:**
  1. Start by creating a new group for each carousel you want to display (e.g., “Homepage Banner Carousel,” “New Arrivals Slider”).
  2. Give each group a clear, descriptive name.
  3. Configure the group’s display settings (e.g., auto-play, loop, pause on hover) to match your desired user experience.
  4. Once the group is created, proceed to the “Custom Contents Items” screen to add slides to it.

### 2.3 Dedicated Admin Screen: Custom Contents Items (Back Office > Modules > Custom contents carousel > Custom Contents Items)

This screen is where you manage the individual slides (items) within your carousels. Each item can be an image, video, text, or embedded content.

- **Screen Name & Menu Location:** You’ll find this under **Modules > Custom contents carousel > Custom Contents Items** in your PrestaShop Back Office menu.
- **Available Actions & Settings:**
  - **Grid View**: Lists all individual slides, showing which group they belong to, their content type, and status.
  - **Add New Item**: Click “Add new” to create a new slide. You’ll then choose the group it belongs to and define its content.
  - **Edit/Delete Item**: Modify the content, link, or display order of an existing slide, or remove it.
  - **Status Toggle**: Activate or deactivate individual slides. An inactive slide will not appear in its carousel.
  - **Drag-and-Drop Reordering**: Easily change the display order of slides within a group.
- **Effect of changes:**
  - **Adding a new item**: Creates a new slide. You’ll specify its content (image upload, video URL, text, HTML), a link, and assign it to one of your existing carousel groups.
  - **Editing an item**: Allows you to update the content, change the link, modify the image, or adjust its position within the carousel.
  - **Activating/Deactivating**: Controls whether a specific slide is visible within its carousel.
  - **Deleting an item**: Permanently removes the slide from its carousel.
- **Recommended workflow for daily store management:**
  1. Select the carousel group you want to add slides to (if you have multiple).
  2. Click “Add new item” and choose the content type (image, video, text, HTML).
  3. Upload your image, paste your video URL, or enter your text/HTML.
  4. Add a relevant link if the slide should direct customers to a product, category, or external page.
  5. Set the display order.
  6. Repeat for all slides in your carousel.
  7. Use the drag-and-drop feature to fine-tune the order of your slides.

### 2.4 Dedicated Admin Screen: index.php (ccarousel/controllers/admin/index.php)

This file is a standard PrestaShop practice for securing admin directories. It typically contains a simple `die('No direct script access allowed');` statement and doesn’t present a configurable screen or managed entity itself. It’s a security measure, not a configuration interface.

### 2.5 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | `CCAROUSEL_LIGHTSLIDER` | YES | Enables/disables the core JavaScript library for carousel functionality. **Must be YES for carousels to work.** |
| Custom Contents Groups | Group Name | User-defined | Identifies your carousel (e.g., “Homepage Banners”). |
| Custom Contents Groups | Status | Enabled | Controls visibility of the entire carousel on the front office. |
| Custom Contents Groups | Carousel Settings | User-defined | Controls auto-play, speed, loop, navigation, etc., for each carousel. |
| Custom Contents Items | Item Content | User-defined | The actual content of the slide (image, video, text, HTML). |
| Custom Contents Items | Item Link | Optional URL | Where the slide directs customers when clicked. |
| Custom Contents Items | Status | Enabled | Controls visibility of individual slides within a carousel. |
| Custom Contents Items | Position | User-defined | Determines the order of slides within a carousel. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My carousel isn’t showing up on the homepage.**

- **A:** First, check if the “Custom contents carousel” module is enabled in **Modules > Module Manager**. Then, navigate to **Modules > Custom contents carousel > Custom Contents Groups** and ensure your carousel group is active (green checkmark). Finally, make sure you have at least one active “Custom Contents Item” assigned to that group. Also, verify that the `CCAROUSEL_LIGHTSLIDER` setting on the main module configuration page is enabled.

**Q2: My carousel images are blurry or distorted.**

- **A:** Ensure the images you upload are of high quality and appropriate dimensions for the space where the carousel is displayed. If your theme has specific image size recommendations for banners or sliders, try to match those. The module will scale images, but starting with a good source image is key.

**Q3: The carousel isn’t sliding or auto-playing.**

- **A:** This is often a JavaScript issue.
  1. Go to **Modules > Configure > Custom contents carousel** and ensure `CCAROUSEL_LIGHTSLIDER` is set to “YES”.
  2. Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).
  3. Clear your browser’s cache.
  4. If the issue persists, there might be a JavaScript conflict with another module or your theme. Check your browser’s developer console (F12) for any JavaScript errors.

**Q4: How do I change the order of slides in my carousel?**

- **A:** Go to **Modules > Custom contents carousel > Custom Contents Items**. You should see a list of your slides. Look for a column with arrows or a drag-and-drop icon. You can usually drag and drop the rows to reorder them, or there might be a “Position” field you can edit. Remember to save your changes.

**Q5: Can I have multiple carousels on different pages?**

- **A:** The module primarily uses the `displayHome` hook, meaning it’s designed for the homepage. While you can create multiple *groups* (carousels), they will all typically render in the same hooked position. To display carousels on different pages or in different positions, custom theme integration or additional hook registration would be required (see Developer Guide).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview for developers and webmasters maintaining or extending the “Custom contents carousel” module.

### 4.1 Architecture Overview

The “Custom contents carousel” module follows a standard PrestaShop MVC (Model-View-Controller) pattern for its Back Office components. It leverages PrestaShop’s `Module` class for core functionality and `AdminController` for managing content groups and items. The front-office display is primarily handled via a Smarty template hooked into `displayHome`, with JavaScript (LightSlider) and CSS assets loaded via `displayHeader`. Data persistence is managed through custom `ObjectModel` classes.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**:
  The module does not contain any dedicated front-office controllers. All front-office rendering is handled directly through the main module class (`ccarousel.php`) by registering hooks and rendering templates.
- **Back-Office Admin Controllers**:

  - `controllers/admin/AdminCustomContentsGroupsController.php`
    - Class name: `AdminCustomContentsGroupsController`
    - Parent class: `ModuleAdminController`
    - Responsibility: Manages the `gcarousel` entity (carousel groups). This controller handles the listing, adding, editing, and deleting of carousel groups. It defines the form fields for group configuration (e.g., name, status, carousel settings like auto-play, speed).
  - `controllers/admin/AdminCustomContentsItemsController.php`
    - Class name: `AdminCustomContentsItemsController`
    - Parent class: `ModuleAdminController`
    - Responsibility: Manages the `gcitem` entity (individual carousel slides/items). This controller handles the listing, adding, editing, and deleting of slides. It defines the form fields for slide content (image upload, video URL, text/HTML, link, position, associated group). It also manages the drag-and-drop reordering functionality for slides.
  - `controllers/admin/index.php`
    - Class name: N/A (simple PHP file)
    - Parent class: N/A
    - Responsibility: A security measure to prevent direct directory listing or access. Contains `die('No direct script access allowed');`.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the `ObjectModel` definitions for `gcarousel` and `gcitem` are likely embedded directly within the main module file (`ccarousel.php`) or within the respective `AdminController` files.

- **`gcarousel` (Carousel Group Model)**:

  - Likely extends `ObjectModel`.
  - Interacts with a custom database table (e.g., `ps_gcarousel`).
  - `$definition` fields would include: `id_gcarousel`, `name`, `active`, `settings` (possibly a serialized array or JSON string for carousel display options).
  - Key methods: `add()`, `update()`, `delete()`, `getGroups()`.
- **`gcitem` (Carousel Item/Slide Model)**:

  - Likely extends `ObjectModel`.
  - Interacts with a custom database table (e.g., `ps_gcitem`).
  - `$definition` fields would include: `id_gcitem`, `id_gcarousel` (foreign key), `position`, `active`, `type` (image, video, text, html), `content` (path to image, video URL, text), `link`, `title`, `description` (for multi-language support).
  - Key methods: `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 JavaScript Assets (`views/js/`)

- `ccarousel/lib/src/js/lightslider.js`
  - Scope: Front-office.
  - Responsibility: This is the core LightSlider library. It initializes and manages the carousel functionality. It binds event listeners for navigation (arrows, dots), handles touch/swipe gestures, auto-play, looping, and responsive adjustments. The module’s `hookDisplayHeader` or `hookDisplayHome` method would typically enqueue this script, and then an inline script or a separate module JS file would call `$('#your-carousel-selector').lightSlider({...});` to initialize specific carousels.

### 4.5 CSS Stylesheets (`views/css/`)

- `ccarousel/css.css`
  - Scope: Front-office.
  - Responsibility: Likely contains custom styling specific to the “Custom contents carousel” module, overriding or extending the base LightSlider styles to match PrestaShop’s default theme or provide module-specific visual adjustments.
- `ccarousel/lib/src/css/ccarousel.css`
  - Scope: Front-office.
  - Responsibility: Could be a base stylesheet for the module’s structure or a placeholder. Given the name, it’s likely module-specific styling.
- `ccarousel/lib/src/css/lightslider.css`
  - Scope: Front-office.
  - Responsibility: The default stylesheet for the LightSlider library. It provides the essential styling for the carousel container, slides, navigation arrows, and pagination dots. Developers can override these styles in their theme’s `custom.css` or by modifying `ccarousel/css.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `ccarousel/views/templates/hook/ccarousel.tpl`
    - Rendered in: `displayHome` (and potentially other hooks if configured in the module).
    - Outputs: The HTML structure for one or more carousels. This template iterates through the carousel groups and their associated items, generating the necessary `<ul>` and `<li>` elements that LightSlider expects. It includes image tags, video embeds, or raw HTML content based on the item’s type, along with links. It also likely contains the JavaScript initialization call for LightSlider, passing configuration options retrieved from the `gcarousel` settings.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - `ps_gcarousel`: Stores information about each carousel group.
    - `id_gcarousel` (PK, INT)
    - `name` (VARCHAR)
    - `active` (TINYINT)
    - `settings` (TEXT or JSON, for serialized LightSlider options)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_gcitem`: Stores information about each individual slide/item.
    - `id_gcitem` (PK, INT)
    - `id_gcarousel` (FK to `ps_gcarousel`, INT)
    - `position` (INT)
    - `active` (TINYINT)
    - `type` (VARCHAR, e.g., ‘image’, ‘video’, ‘text’, ‘html’)
    - `content` (TEXT, stores image path, video URL, or raw text/HTML)
    - `link` (VARCHAR)
    - `title` (VARCHAR, for multi-language)
    - `description` (TEXT, for multi-language)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Stores module-specific configuration values, such as `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES`, etc.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Enqueues necessary CSS (`lightslider.css`, `ccarousel.css`) and JavaScript (`lightslider.js`) files for the carousel to function and be styled correctly. |
| `displayHome` | In the main content area of the homepage. | Renders the `ccarousel.tpl` template, which generates the HTML structure for the active carousel groups and their items, along with the LightSlider initialization script. |

## 5. Official Support & Updates

For official updates, technical support, and to ensure you are running the latest, most secure version of the “Custom contents carousel” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions regarding module functionality and compatibility.
