---
title: "Front office Sticky Notes - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Front office Sticky Notes PrestaShop module by MyPresta.eu."
sidebar:
  label: "Front office Sticky Notes - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Front office Sticky Notes Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/front-office-sticky-notes.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/front-office-sticky-notes/)
>
> ---


# Front office Sticky Notes

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are usually available on any modern hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration screen for the Front office Sticky Notes module. This is where you manage all your sticky notes.

The configuration page will display a list of all sticky notes you have created. From here, you can:

- **Add New Sticky Note:** Click a button (usually “Add new” or a plus icon) to create a new note.
- **Edit Existing Sticky Note:** Click an “Edit” icon next to a note in the list to modify its settings.
- **Delete Sticky Note:** Click a “Delete” icon next to a note to remove it from your store.

When adding or editing a sticky note, you will typically see a form with the following settings:

- **Note Content (Text):**

  - **What this setting does:** This is the actual message or text that will appear inside your sticky note. You can use basic HTML tags (like `<b>` for bold, `<i>` for italic, `<br>` for line breaks, or `<a>` for links) to format your text and include clickable links.
  - **Effect of changing this setting:** The text you enter here will be displayed to your customers.
  - **Recommended value:** Keep it concise and impactful. For example, “Limited Stock!”, “New Arrivals!”, “Free Shipping over $75!”.
  - **Merchant scenario / example:** You want to announce a flash sale. You’d enter: `<b>Flash Sale!</b> 20% off all dresses! <a href="/20-off-dresses">Shop Now!</a>`
- **Note Color (Background Color):**

  - **What this setting does:** This allows you to choose the background color of your sticky note. A color picker tool is usually provided for easy selection.
  - **Effect of changing this setting:** The sticky note will appear with the chosen background color. This is crucial for making it stand out or match your brand.
  - **Recommended value:** Choose a color that contrasts well with your store’s background and the text color, making the note easily readable and noticeable. Bright, warm colors (yellow, orange, light green) often work well for attention.
  - **Merchant scenario / example:** For a warning message, you might choose a bright red or orange. For a general announcement, a classic yellow or light blue.
- **Text Color:**

  - **What this setting does:** This sets the color of the text within your sticky note.
  - **Effect of changing this setting:** The text will be displayed in the selected color.
  - **Recommended value:** Always choose a color that provides high contrast with your chosen background color for optimal readability. Black or dark gray on a light background, or white on a dark background, are usually best.
  - **Merchant scenario / example:** If your note background is yellow, you’d choose black or dark gray for the text. If the background is dark blue, white text would be ideal.
- **Position (X-coordinate / Left offset):**

  - **What this setting does:** This determines the horizontal position of the sticky note on the page, measured from the left edge of the screen or its parent container. It’s usually specified in pixels (px).
  - **Effect of changing this setting:** A higher value moves the note further to the right. A lower value moves it closer to the left.
  - **Recommended value:** Experiment to find a position that doesn’t obstruct important content but is still visible. Start with values like `20px` or `50px` and adjust.
  - **Merchant scenario / example:** You want a note to appear slightly to the right of your main logo in the header. You might set this to `200px`.
- **Position (Y-coordinate / Top offset):**

  - **What this setting does:** This determines the vertical position of the sticky note on the page, measured from the top edge of the screen or its parent container. It’s usually specified in pixels (px).
  - **Effect of changing this setting:** A higher value moves the note further down the page. A lower value moves it closer to the top.
  - **Recommended value:** Consider where the note will be most effective without being intrusive. For header messages, a small value like `10px` or `20px` might work. For product page notes, you might need to scroll down to see the effect.
  - **Merchant scenario / example:** You want a note to appear just below your main navigation bar. You might set this to `100px`.
- **Width:**

  - **What this setting does:** This controls the width of the sticky note container. It’s usually specified in pixels (px).
  - **Effect of changing this setting:** A larger width allows for more text on a single line, while a smaller width will cause text to wrap more frequently.
  - **Recommended value:** Choose a width that comfortably fits your message without being excessively large or too narrow. `200px` to `300px` is a common range.
  - **Merchant scenario / example:** If your message is short, `200px` might be enough. If it’s a slightly longer sentence, `280px` might be better.
- **Height:**

  - **What this setting does:** This controls the height of the sticky note container. It’s usually specified in pixels (px).
  - **Effect of changing this setting:** A larger height allows for more lines of text. If the text exceeds the height, it might be cut off or overflow, depending on your theme’s CSS.
  - **Recommended value:** Often, you can leave this empty or set it to `auto` if the module supports it, allowing the height to adjust to the content. If you need a fixed size, `100px` to `150px` is a common range.
  - **Merchant scenario / example:** If you have a multi-line message, you might need to increase the height to ensure all text is visible.
- **Rotation (Angle):**

  - **What this setting does:** This allows you to rotate the sticky note by a certain degree, giving it a more natural “stuck on” appearance.
  - **Effect of changing this setting:** The note will appear tilted by the specified angle. Positive values rotate clockwise, negative values counter-clockwise.
  - **Recommended value:** Small rotations like `3deg`, `-5deg`, or `7deg` often look best, providing a subtle, realistic effect without making the text difficult to read.
  - **Merchant scenario / example:** To make a note look like it’s casually stuck to the page, you might set this to `5deg`.
- **Z-Index:**

  - **What this setting does:** This CSS property determines the stacking order of elements. An element with a higher z-index value is placed in front of elements with lower values.
  - **Effect of changing this setting:** If your sticky note is appearing behind other elements (like pop-ups, menus, or banners), increasing its z-index will bring it to the front.
  - **Recommended value:** Start with a relatively high value like `999` or `9999`. If it’s still hidden, increase it further.
  - **Merchant scenario / example:** Your sticky note is hidden behind a cookie consent banner. You would increase its Z-Index to `9999` to ensure it’s always on top.
- **Active / Enabled:**

  - **What this setting does:** This is a simple toggle (Yes/No switch) to enable or disable the sticky note without deleting it.
  - **Effect of changing this setting:**
    - *When enabled:* The sticky note will be visible on your front office according to its other settings.
    - *When disabled:* The sticky note will be hidden from your front office, but its configuration will be saved, allowing you to reactivate it later.
  - **Recommended value:** “Yes” when you want the note to be visible; “No” when you want to temporarily hide it.
  - **Merchant scenario / example:** You have a seasonal promotion note. You can disable it after the season ends and re-enable it next year without recreating it.

#### 2.1.1 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Note Content (Text) | Varies | The message displayed on the sticky note. Supports basic HTML. |
| Module Configuration | Note Color (Background) | Varies (e.g., Yellow) | Sets the background color of the note. Choose for contrast. |
| Module Configuration | Text Color | Varies (e.g., Black) | Sets the color of the text. Ensure high contrast with background. |
| Module Configuration | Position (X-coordinate) | Varies (e.g., 50px) | Horizontal position from the left. Adjust for placement. |
| Module Configuration | Position (Y-coordinate) | Varies (e.g., 50px) | Vertical position from the top. Adjust for placement. |
| Module Configuration | Width | Varies (e.g., 250px) | Width of the sticky note. Affects text wrapping. |
| Module Configuration | Height | Varies (e.g., auto or 120px) | Height of the sticky note. Affects content visibility. |
| Module Configuration | Rotation (Angle) | Varies (e.g., 5deg) | Tilts the note for a realistic “stuck” effect. |
| Module Configuration | Z-Index | Varies (e.g., 9999) | Stacking order. Higher values appear on top of other elements. |
| Module Configuration | Active / Enabled | Yes | Toggles the visibility of the sticky note on the front office. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My sticky note isn’t showing up on the front office.**
A:

1. **Check “Active” status:** Go to the module configuration and ensure the “Active” switch for that specific note is set to “Yes”.
2. **Clear Cache:** PrestaShop often caches content. Go to **Advanced Parameters > Performance** and click “Clear cache”.
3. **Z-Index:** If the note’s Z-Index is too low, it might be hidden behind other elements. Try increasing the Z-Index value (e.g., to `9999`).
4. **Positioning:** Double-check the X and Y coordinates. If they are very high, the note might be off-screen. Try setting small values like `10px` for both to see if it appears.
5. **Module Installation:** Ensure the module is correctly installed and enabled in **Modules > Module Manager**.

**Q: My sticky note text is cut off or overflowing.**
A:

1. **Adjust Width/Height:** Increase the “Width” and/or “Height” settings for that specific sticky note in the module configuration.
2. **Check HTML:** If you’re using HTML, ensure all tags are correctly closed (e.g., `<b>` has a corresponding `</b>`). Incorrect HTML can sometimes break rendering.

**Q: The sticky note looks different on mobile than on desktop.**
A: The module aims for responsiveness, but exact placement can vary due to different screen sizes and your theme’s CSS.

1. **Test on Device:** Always test the note’s appearance on actual mobile devices or use your browser’s developer tools (F12) to simulate mobile views.
2. **Adjust Positioning:** You might need to adjust the X and Y coordinates for mobile-specific placement, though the module might not offer separate mobile settings. If it’s a major issue, consider if the note is truly essential on mobile or if a different approach is needed.
3. **Theme Conflicts:** Occasionally, your theme’s CSS might conflict. If you suspect this, contact MyPresta.eu support with details of your theme.

**Q: How do I make the text a link?**
A: You can use standard HTML anchor tags within the “Note Content” field.
Example: `<a href="https://yourstore.com/new-products">Click here for New Arrivals!</a>`
Remember to include the full URL, including `https://`.

**Q: Can I have different sticky notes for different languages?**
A: Yes, the module supports PrestaShop’s multi-language features. When editing a sticky note, you should see language tabs next to the “Note Content” field (and potentially other text-based fields). Select the desired language tab and enter the translated content for that note.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, customize, or debug the “Front office Sticky Notes” module.

### 4.1 Architecture Overview

The “Front office Sticky Notes” module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `ModuleFrontController` for AJAX interactions. It stores configuration data directly in `ps_configuration` and renders its content via a Smarty template hooked into the front office. The module uses client-side JavaScript for dynamic behavior and a dedicated CSS file for styling.

### 4.2 Controllers (`controllers/`)

The module utilizes front controllers to handle AJAX requests related to sticky note management (add, edit, delete). These are not full-page controllers but endpoints for dynamic interactions.

- **Front-Office Controllers**:

  - `controllers/front/add.php`
    - **Class Name & Parent Class**: `StickynotesfoAddModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: Handles AJAX requests to add a new sticky note. It likely receives POST data containing note content, position, colors, etc., validates it, and saves it to the database (via `Configuration` class or a custom `ObjectModel` if one existed). Returns a JSON response indicating success or failure.
  - `controllers/front/delete.php`
    - **Class Name & Parent Class**: `StickynotesfoDeleteModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: Handles AJAX requests to delete an existing sticky note. It expects an identifier (e.g., `id_note`) in the request, removes the corresponding data from the database, and returns a JSON response.
  - `controllers/front/edit.php`
    - **Class Name & Parent Class**: `StickynotesfoEditModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: Handles AJAX requests to update an existing sticky note. It receives POST data with the note’s ID and updated properties, modifies the database record, and returns a JSON response.
  - `controllers/front/index.php`
    - **Class Name & Parent Class**: `StickynotesfoIndexModuleFrontController` extending `ModuleFrontController`
    - **Responsibility**: This controller might serve as a general entry point for AJAX requests or could be a fallback. Given the specific `add`, `delete`, `edit` controllers, `index.php` might handle listing notes or other general interactions not covered by the specific CRUD operations.
- **Back-Office Admin Controllers**: None detected. All back-office configuration is handled within the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

No custom `classes/` or `ObjectModel` definitions were detected. The module likely stores its configuration directly in PrestaShop’s `ps_configuration` table, using unique keys for each sticky note’s properties. This approach is common for simpler modules managing a limited number of settings.

### 4.4 JavaScript Assets (`views/js/`)

- `js/advajax.js`
  - **Scope**: Likely Front-office.
  - **Description**: This file suggests a custom or third-party AJAX utility script. It probably provides helper functions for making asynchronous requests to the module’s front controllers (`add.php`, `delete.php`, `edit.php`). It might encapsulate common AJAX patterns, error handling, or data serialization. Developers should review this file to understand how AJAX calls are structured and initiated within the module.
- `js/jscolor/jscolor.js`
  - **Scope**: Back-office (for configuration).
  - **Description**: This is a third-party JavaScript library for a color picker. It’s used in the module’s back-office configuration form to provide a user-friendly interface for selecting note and text colors. It binds to input fields of a specific class or ID, transforming them into interactive color selection tools.

### 4.5 CSS Stylesheets (`views/css/`)

- `css/stickynotes.css`
  - **Scope**: Front-office customer styling.
  - **Description**: This is the primary stylesheet for the sticky notes displayed on the front office. It defines the visual appearance of the notes, including:
    - Base styling for the sticky note container (e.g., `position: absolute;`, `background-color`, `border-radius`).
    - Text styling within the note (`font-size`, `color`, `line-height`).
    - The “peeled” or rotated effect (likely using `transform: rotate()`).
    - `z-index` to ensure visibility.
    - Potentially responsive adjustments for different screen sizes using media queries.
  - **Key CSS class selectors developers can override**: Developers should inspect the rendered HTML to identify the main container class (e.g., `.sticky-note`, `.stickynotesfo-item`) and its child elements to apply custom styling in their theme’s `custom.css` or `theme.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/front/`)**:
  - `views/templates/front/sticky-notes-front-office.tpl`
    - **Hook**: This template is likely rendered in a general front-office hook such as `displayHeader`, `displayFooter`, or potentially `displayBeforeBodyClosingTag`. The module’s `hookDisplayHeader` or `hookDisplayFooter` method would typically fetch all active sticky notes from the database and assign them to this template.
    - **Visual Block Output**: This template is responsible for iterating through the list of active sticky notes and rendering the HTML structure for each one. It will dynamically insert the note’s content, colors, positions, width, height, rotation, and z-index as inline styles or data attributes, which are then picked up by `stickynotes.css` and potentially `advajax.js` for dynamic updates. Each note will likely be a `div` element with unique IDs or classes.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables. Instead, it stores its configuration data in PrestaShop’s `ps_configuration` table. Each sticky note’s properties (content, color, position, etc.) are stored as individual configuration keys, likely prefixed with `STICKYNOTESFO_NOTE_` followed by a unique identifier (e.g., `STICKYNOTESFO_NOTE_1_CONTENT`, `STICKYNOTESFO_NOTE_1_COLOR`). Multi-language fields would use `_LANG_ID` suffixes.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Executed at the end of the `<head>` section of every front-office page. | Ideal for injecting CSS, JavaScript, and potentially the initial HTML structure of the sticky notes, ensuring they are available early in the DOM. |
| `displayFooter` | Executed at the end of the `<body>` section of every front-office page. | Can be used to inject the sticky notes’ HTML, especially if they are meant to float or be positioned absolutely relative to the viewport. |
| `displayLeftColumn` | Executed within the left column of pages that have one. | Allows placement of sticky notes specifically within the left sidebar. |
| `displayRightColumn` | Executed within the right column of pages that have one. | Allows placement of sticky notes specifically within the right sidebar. |
| `displayProductAdditionalInfo` (or similar product page hook) | Executed on the product page, typically near the product description or add-to-cart button. | Allows placement of sticky notes specific to individual product pages. |
| `actionFrontControllerSetMedia` | Executed when a front controller is setting its media (CSS/JS). | Used by the module to register its `stickynotes.css` and `advajax.js` files for front-office display. |
| `actionAdminControllerSetMedia` | Executed when an admin controller is setting its media (CSS/JS). | Used by the module to register `jscolor.js` and any other admin-specific CSS/JS for its configuration page. |

## 5. Official Support & Updates

For official updates, technical support, and any further assistance with the “Front office Sticky Notes” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely support and ensuring your module functions optimally.
