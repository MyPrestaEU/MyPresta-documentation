---
title: "Back office Sticky Notes - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Back office Sticky Notes PrestaShop module by MyPresta.eu."
sidebar:
  label: "Back office Sticky Notes - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Back office Sticky Notes Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/back-office-sticky-notes/)
>
> ---


# Back office Sticky Notes

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient and usually pre-installed on most hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main configuration screen for the “Back office Sticky Notes” module. This is where you manage your sticky notes.

The configuration page itself doesn’t have many “settings” in the traditional sense (like on/off switches). Instead, it’s your central hub for creating, editing, and managing all your sticky notes.

#### **Adding a New Sticky Note**

At the top of the configuration page, you will typically find a form or section to add a new note.

- **Note Content (Text Area):**

  - **What this setting does:** This is where you type the actual message or reminder for your sticky note.
  - **Effect of changing this setting:** Whatever you type here will be displayed on the sticky note in your back office.
  - **Recommended value:** Be concise and clear. Use bullet points or short sentences for readability.
  - **Merchant scenario / example:** “Remember to follow up with customer #1234 about their order status.” or “New product images for ‘Summer Collection’ due by Friday.”
- **Note Color (Color Picker):**

  - **What this setting does:** Allows you to choose the background color of your sticky note.
  - **Effect of changing this setting:** The sticky note will appear with the chosen color in the back office. Different colors can help categorize notes or highlight urgency.
  - **Recommended value:** Choose colors that stand out but are not too distracting. You might use red for urgent notes, yellow for general reminders, and green for completed tasks.
  - **Merchant scenario / example:** Set a note about a critical bug to red, and a note about a new marketing idea to yellow.
- **Save / Add Note Button:**

  - **What this setting does:** Submits the content and color you’ve chosen to create a new sticky note.
  - **Effect of changing this setting:** A new sticky note will be created and will appear on your back office pages. It will also be listed in the “Existing Notes” section below.
  - **Recommended value:** Click this after you’ve finalized your note content and color.
  - **Merchant scenario / example:** After typing your reminder and selecting a color, click “Save” to make the note active.

#### **Managing Existing Sticky Notes**

Below the “Add New Note” section, you will see a list or table of all the sticky notes you have already created.

- **Note List (Table/Display):**

  - **What this setting does:** Shows all active sticky notes, their content, and their assigned color.
  - **Effect of changing this setting:** This is a display of your current notes. You can visually review them here.
  - **Recommended value:** Regularly review this list to ensure notes are still relevant.
  - **Merchant scenario / example:** Quickly scan the list to see all pending tasks or reminders.
- **Edit Button (for each note):**

  - **What this setting does:** Allows you to modify the content or color of an existing sticky note.
  - **Effect of changing this setting:** Clicking this will typically load the note’s content back into the “Add New Note” form (which might change to “Edit Note” mode), allowing you to make changes. Once saved, the note will update across your back office.
  - **Recommended value:** Use this to update task statuses, add more details, or change urgency.
  - **Merchant scenario / example:** A note says “Check new product images.” Once checked, you can edit it to “New product images approved.”
- **Delete Button (for each note):**

  - **What this setting does:** Permanently removes a sticky note.
  - **Effect of changing this setting:** The note will disappear from your back office and will no longer be listed in the configuration. This action is usually irreversible.
  - **Recommended value:** Delete notes only when the task is completed or the information is no longer relevant.
  - **Merchant scenario / example:** Once an order issue is resolved, delete the sticky note related to it.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | **Note Content (Text Area)** | Clear, concise text | The actual message displayed on the sticky note. |
| Module Configuration Page | **Note Color (Color Picker)** | User-selected | Sets the background color of the note for categorization/urgency. |
| Module Configuration Page | **Save / Add Note Button** | Click after content/color set | Creates a new sticky note visible in the back office. |
| Module Configuration Page | **Edit Button (per note)** | Click to modify | Allows updating content or color of an existing note. |
| Module Configuration Page | **Delete Button (per note)** | Click to remove | Permanently removes a sticky note from the back office. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My sticky notes are not appearing in the back office after I save them.**
A1:

- **Clear Cache:** The most common reason for display issues is caching. Go to **Advanced Parameters > Performance** in your PrestaShop back office. Click “Clear cache” (or “Clear Smarty cache” in older versions).
- **Check Module Status:** Ensure the module is still installed and enabled in **Modules > Module Manager**.
- **Browser Cache:** Try clearing your browser’s cache or opening your back office in an incognito/private browsing window to rule out browser-specific issues.

**Q2: Can I move the sticky notes around on the screen?**
A2: Yes, once a sticky note is displayed in your back office, you should be able to click and drag it to any position on the page. The module is designed to remember its position for you.

**Q3: Can different administrators see each other’s sticky notes?**
A3: Yes, by default, all sticky notes created through this module are visible to all administrators who have access to the back office. This is a key feature for team collaboration.

**Q4: The colors of my sticky notes look strange or are not applying correctly.**
A4:

- **Check Color Picker:** Ensure you are using the color picker tool correctly on the module’s configuration page.
- **Custom Theme Conflicts:** If you are using a heavily customized back office theme, there might be CSS conflicts. Try temporarily switching to the default PrestaShop back office theme to see if the issue persists. If it resolves, your theme’s CSS is likely overriding the module’s styles.
- **Browser Compatibility:** Ensure your browser is up-to-date.

**Q5: How do I translate the module’s interface into another language?**
A5:

- Go to **International > Translations** in your PrestaShop back office.
- Select “Installed modules translations,” choose your theme, and then select the language you want to translate.
- Find “Back office Sticky Notes” in the list and translate the available text strings.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The “Back office Sticky Notes” module is a classic PrestaShop module primarily designed for the Back Office. It leverages PrestaShop’s module architecture, utilizing the `Module` class for installation, uninstallation, and configuration. The core functionality revolves around displaying and managing user-created “sticky notes” within the admin panel. It relies heavily on JavaScript for front-end interaction (dragging, positioning) and AJAX for saving note data. Data persistence is handled via `ps_configuration` for module settings and likely custom database tables or `ps_configuration` for the notes themselves.

### 4.2 Controllers (`controllers/`)

This module does not appear to use dedicated Front-Office or Back-Office Admin Controllers in the traditional PrestaShop MVC sense (i.e., files in `controllers/front/` or `controllers/admin/`). All configuration and AJAX handling seem to be managed directly within the main module file (`addstickynote.php`) using the `getContent()` method for configuration and potentially `ajaxProcess` methods or direct AJAX calls for dynamic note management.

### 4.3 Core Classes & Models (`classes/`)

Based on the provided inventory, there are no custom classes or `ObjectModel` definitions within a `classes/` directory. This suggests that sticky note data is likely stored directly in the `ps_configuration` table, where each note’s content, color, and position might be serialized or stored as individual configuration keys.

### 4.4 JavaScript Assets (`views/js/`)

The module relies heavily on JavaScript for its interactive features in the back office.

- `stickynotes/js/advajax.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Likely a custom AJAX utility script, possibly a wrapper for jQuery’s AJAX functions or a standalone implementation to handle asynchronous communication with the module’s PHP backend for saving/loading notes.
- `stickynotes/js/joverlay.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Suggests functionality related to overlays or modal popups, potentially used for editing note content in a more user-friendly interface, or for displaying confirmation messages.
- `stickynotes/js/jscolor/jscolor.js`:
  - **Scope:** Back-office (specifically on the module configuration page).
  - **Responsibility:** A third-party JavaScript library for providing a color picker interface. This is used to allow administrators to select the background color for their sticky notes.
- `stickynotes/js/script.js`:
  - **Scope:** Back-office.
  - **Responsibility:** This is likely the main script for the module’s front-end logic. It would handle:
    - Initialization of sticky notes on page load.
    - Drag-and-drop functionality for repositioning notes.
    - Saving note positions via AJAX.
    - Event listeners for editing/deleting notes.
    - Interaction with `advajax.js` for data persistence.
    - Potentially rendering new notes dynamically.
- `stickynotes/js/script17.js`:
  - **Scope:** Back-office (PrestaShop 1.7.x and 8.x specific).
  - **Responsibility:** This script likely contains adaptations or specific code for PrestaShop 1.7+ environments, addressing differences in DOM structure, jQuery versions, or back office theme changes compared to older PrestaShop versions (1.5/1.6). It would ensure compatibility and proper functioning on newer platforms.

### 4.5 CSS Stylesheets (`views/css/`)

The module includes CSS files to style the appearance of the sticky notes.

- `stickynotes/css/stickynotes-twig-shit.css`:
  - **Scope:** Back-office admin styling.
  - **Responsibility:** The name suggests this file contains specific styling adjustments or overrides for PrestaShop 1.7+ back offices, which utilize Twig templating. It likely targets elements within the new back office theme to ensure notes are displayed correctly and consistently.
  - **Key CSS selectors:** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (hypothetical, based on common naming conventions).
- `stickynotes/css/stickynotes.css`:
  - **Scope:** Back-office admin styling.
  - **Responsibility:** This is the primary stylesheet for the sticky notes, defining their default appearance, positioning, and interactive states (e.g., when being dragged). It would contain general styles applicable across different PrestaShop versions.
  - **Key CSS selectors:** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (hypothetical). Developers can override these classes in their custom back office themes if needed.

### 4.6 Smarty Template Structure (`views/templates/`)

The module uses a single Smarty template for rendering the sticky notes in the back office.

- **Hook templates (`views/templates/hook/`)**:
  - `stickynotes/sticky-notes-back-office.tpl`:
    - **Rendered in hook:** This template is likely hooked into a global back office hook, such as `displayBackOfficeHeader` or `displayAdminAfterHeader`, to inject the necessary HTML structure and JavaScript initialization for the sticky notes across all admin pages.
    - **Visual block output:** It outputs the HTML containers for the sticky notes, potentially including a hidden template for new notes, and the JavaScript calls to initialize the note display and drag functionality. It would also contain the logic to iterate through existing notes and render them.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - This module does not appear to create custom SQL tables. It is highly probable that all sticky note data (content, color, position, ID) is stored in the `ps_configuration` table. Each note might correspond to a unique `PS_STICKY_NOTE_X` configuration key, where `X` is an identifier, and the value is a serialized array or JSON string containing the note’s properties.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Executed in the `<head>` section of every back office page. | Injects CSS and JavaScript files required for sticky note functionality and styling. |
| `displayAdminAfterHeader` (or similar) | Executed after the main header of every back office page. | Renders the HTML structure for the sticky notes and initializes their display and interactive behavior. |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media (JS/CSS). | Potentially used to conditionally load JS/CSS assets based on the current admin page, though `displayBackOfficeHeader` is more common for global assets. |
| `actionModuleInstall` | Executed when the module is installed. | Creates initial configuration entries in `ps_configuration` (if any) and registers necessary hooks. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | Cleans up configuration entries and unregisters hooks. |

## 5. Official Support & Updates

For official updates, technical support, and to download the latest versions of the “Back office Sticky Notes” module, please visit your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and compatibility.
