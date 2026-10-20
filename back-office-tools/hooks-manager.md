---
title: "Hooks Manager - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Hooks Manager PrestaShop module by MyPresta.eu."
sidebar:
  label: "Hooks Manager - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Hooks Manager Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the Hooks Manager module. You will see a list of all custom hooks you have created, along with options to add new ones.

#### Adding a New Custom Hook:

At the top of the configuration page, you’ll find the fields to create a new hook.

- **Hook Name:**

  - **What this setting does:** This is the unique, technical name for your new hook. It must start with `display` (e.g., `displayMyCustomHook`, `displayProductExtraInfo`). This name is what you will later use in your theme’s `.tpl` files to “call” the hook.
  - **Effect of changing this setting:** This name is crucial for developers to place the hook in your theme. Changing it after creation would require updating your theme files.
  - **Recommended value:** Use descriptive, camelCase names starting with `display`. Example: `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Merchant scenario / example:** You want to add a banner below the “Add to Cart” button on product pages. You might name the hook `displayProductBelowAddToCart`.
- **Hook Title:**

  - **What this setting does:** This is a friendly, human-readable title for your hook that will appear in your PrestaShop Back Office (e.g., when you go to **Design > Positions** to assign modules to hooks).
  - **Effect of changing this setting:** Makes it easier to identify your custom hook among the many standard hooks in the Back Office.
  - **Recommended value:** A clear, descriptive title. Example: “Product Page - Below Add to Cart”, “Homepage - Top Promo Banner”.
  - **Merchant scenario / example:** For the `displayProductBelowAddToCart` hook, you’d set the title to “Product Page - Below Add to Cart”.
- **Hook Description:**

  - **What this setting does:** An optional, longer description to provide more context about the hook’s intended purpose or placement. This is also for internal use in the Back Office.
  - **Effect of changing this setting:** Helps you and your team remember the specific use case for each custom hook.
  - **Recommended value:** Briefly explain where the hook is intended to be placed and what kind of content it should hold. Example: “Intended for trust badges or small promotional messages directly under the add to cart button.”
  - **Merchant scenario / example:** For the `displayProductBelowAddToCart` hook, you might add “Use for small trust badges or a free shipping message.”
- **Visibility:**

  - **What this setting does:** This determines if the hook is visible in the list of available hooks when you go to **Design > Positions** in your PrestaShop Back Office.
  - **Effect of changing this setting:**
    - *When enabled:* The hook will appear in the list, allowing you to easily assign modules to it.
    - *When disabled:* The hook will still exist and function if called in your theme, but it won’t appear in the “Design > Positions” list, making it harder to manage modules for it.
  - **Recommended value:** **Enabled (Yes)**, unless you have a very specific reason to hide it.
  - **Merchant scenario / example:** You’ve created a new hook and want to immediately start assigning modules to it. Keep it enabled.

#### Managing Existing Custom Hooks:

Below the “Add New Hook” section, you’ll see a table listing all the custom hooks you’ve created.

- **Enabled / Disabled Switch (for each hook):**

  - **What this setting does:** This switch allows you to activate or deactivate an individual custom hook.
  - **Effect of changing this setting:**
    - *When enabled:* The hook is active, and any modules assigned to it will render their content when the hook is called in your theme.
    - *When disabled:* The hook is inactive. Even if called in your theme, it will not render any content from modules assigned to it. This is a soft way to temporarily hide content without unhooking modules.
  - **Recommended value:** **Enabled** for hooks you want to use, **Disabled** for hooks you want to temporarily hide.
  - **Merchant scenario / example:** You have a seasonal promotion banner placed via a custom hook. When the promotion ends, you can disable the hook to hide the banner without removing the module.
- **Live Edit (for each hook):**

  - **What this setting does:** This is a quick link to the “Design > Positions” page, filtered to show only the selected custom hook.
  - **Effect of changing this setting:** Clicking this button takes you directly to the page where you can “hook” (assign) other modules to this specific custom hook.
  - **Recommended value:** Use this button whenever you want to assign a module to your newly created custom hook.
  - **Merchant scenario / example:** You’ve just created `displayProductBelowAddToCart` and now want to assign your “Trust Badges” module to it. Click “Live Edit” next to `displayProductBelowAddToCart`.

#### Other Configuration Keys (Internal):

You might see `mypresta_updates`, `update_`, `updatev_` in the module’s internal configuration. These are typically related to module updates and licensing checks by MyPresta.eu and do not require merchant interaction.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Hook Name | Descriptive, `display` prefix | Unique technical identifier for the hook. Used in theme files. |
| Module Configuration | Hook Title | Clear, human-readable | Appears in Design > Positions for easy identification. |
| Module Configuration | Hook Description | Optional, informative | Provides context for the hook’s purpose. |
| Module Configuration | Visibility | Enabled (Yes) | Makes the hook visible in Design > Positions for module assignment. |
| Module Configuration | Enabled / Disabled (per hook) | Enabled | Activates/deactivates the custom hook’s ability to render content. |
| Module Configuration | Live Edit (per hook) | N/A (Action button) | Direct link to Design > Positions to assign modules to the hook. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve created a hook and assigned a module, but nothing is showing up on my store. What’s wrong?**
A: This is the most common issue. The Hooks Manager module *creates* the hook, but you (or your webmaster) still need to *place* that hook into your theme’s `.tpl` files.
- **Solution:** You need to edit your theme files (e.g., `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) and insert the following code snippet where you want the hook to appear: `{$hook_name}`. Replace `hook_name` with the actual name of your hook (e.g., `{$hook_displayProductBelowAddToCart}`).
- **Also check:**
1. Is the hook “Enabled” in the Hooks Manager configuration?
2. Is the module you’re trying to display actually “hooked” to your custom hook under **Design > Positions**?
3. Have you cleared your PrestaShop cache (**Advanced Parameters > Performance**)?

**Q: Can I use the same custom hook multiple times in different places?**
A: Yes, you can. If you place `{$hook_displayMyCustomHook}` in `product.tpl` and also in `category.tpl`, any module assigned to `displayMyCustomHook` will render in both locations. This is powerful for displaying consistent content across different page types.

**Q: My custom hook is showing up, but the styling is off. What can I do?**
A: The Hooks Manager module only provides the “slot.” The styling of the content within that slot is determined by the module you’ve placed there and your theme’s CSS.
- **Solution:** You might need to add custom CSS to your theme to style the content rendered by the module in your custom hook. Your webmaster can help with this.

**Q: I want to remove a custom hook. How do I do it safely?**
A: In the Hooks Manager configuration, you’ll see a “Delete” button next to each custom hook.
- **Important:** Before deleting, ensure you have removed any calls to that hook (`{$hook_yourCustomHookName}`) from your theme’s `.tpl` files. If you delete the hook but leave the call in your theme, it might cause a minor error or simply render nothing. Also, unhook any modules from it via **Design > Positions**.

**Q: Does this module affect my store’s performance?**
A: The module itself is very lightweight. Adding more hooks and assigning more modules *can* incrementally increase page load time, but this is true for any additional content on your page, regardless of how it’s hooked. The impact is generally negligible unless you’re adding dozens of complex modules to a single page.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview

The Hooks Manager module is a straightforward PrestaShop module designed to extend the core hooking mechanism. It primarily leverages PrestaShop’s `Module` class and `Configuration` table to manage custom hook definitions. It does not introduce complex MVC patterns or custom database tables but rather manipulates the `ps_hook` and `ps_hook_module` tables indirectly through PrestaShop’s API. The module’s core functionality resides within its main PHP file, `hooksmanager.php`, which handles installation, uninstallation, and the Back Office configuration interface.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. All front-office rendering is handled by the standard PrestaShop `Hook::exec()` method when the custom hook is called in a `.tpl` file.
- **Back-Office Admin Controllers**: None. All administration is handled directly within the `hooksmanager.php` file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or `ObjectModel` definitions are present in the `classes/` directory. The module directly interacts with PrestaShop’s core `Hook` and `Module` classes.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are present in the module. The Back Office configuration relies on standard PrestaShop form elements and potentially jQuery if included globally by PrestaShop.

### 4.5 CSS Stylesheets (`views/css/`)

- No custom CSS files are present in the module. The Back Office configuration uses PrestaShop’s default admin theme styling.

### 4.6 Smarty Template Structure (`views/templates/`)

- No custom Smarty template files are present in the module. The entire configuration interface is rendered directly within the `getContent()` method of `hooksmanager.php` using raw HTML and PrestaShop’s helper classes.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create its own custom database tables.
  - It primarily interacts with the following core PrestaShop tables:
    - `ps_hook`: Stores the definitions of all hooks, including those created by this module.
    - `ps_hook_lang`: Stores the translatable titles and descriptions for hooks.
    - `ps_module_hook`: Links modules to hooks, defining which module is displayed in which hook.
    - `ps_configuration`: Stores module-specific configuration values (e.g., `mypresta_updates`, `update_`, `updatev_` for internal module management).
- **Registered Hooks Table**:
  The module itself does not register any hooks to display its own content. Its purpose is to *create* new hooks for other modules to use.

  The module’s core functionality involves:

  - `install()`:
    - Registers the module to `displayAdminProductsExtra` (or similar, though not explicitly stated in dossier, this is common for admin tools to show a link).
    - Creates a new tab in the Back Office (if applicable, though not explicitly stated for this module, it’s common for admin tools).
    - Sets default configuration values in `ps_configuration`.
  - `uninstall()`:
    - Deletes all custom hooks created by the module from `ps_hook` and `ps_hook_lang`.
    - Removes associated `ps_module_hook` entries.
    - Cleans up configuration values from `ps_configuration`.
  - `getContent()`:
    - Handles the Back Office configuration form submission.
    - Processes creation, update, and deletion of custom hooks.
    - Renders the HTML for the configuration page, listing existing hooks and providing the form to add new ones.
    - Uses `Hook::add()` and `Hook::remove()` methods to manage hook entries in the database.

  **Developer Note on Custom Hook Usage:**
  To utilize a custom hook created by this module, a developer must manually insert the Smarty variable `{$hook_YOUR_CUSTOM_HOOK_NAME}` into the desired `.tpl` file within the active PrestaShop theme. For example, if a hook named `displayProductBelowAddToCart` is created, the developer would add `{$hook_displayProductBelowAddToCart}` to `themes/your_theme/templates/catalog/_partials/product-details.tpl` or `product.tpl` at the desired location. PrestaShop’s core `Hook::exec()` method will then handle the rendering of modules assigned to this custom hook.

## 5. Official Support & Updates

For the latest updates, bug fixes, and professional support for the Hooks Manager module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring your module functions optimally and to assisting with any technical queries you may have.
