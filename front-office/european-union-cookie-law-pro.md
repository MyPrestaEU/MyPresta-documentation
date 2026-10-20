---
title: "European Union Cookie Law Pro - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the European Union Cookie Law Pro PrestaShop module by MyPresta.eu."
sidebar:
  label: "European Union Cookie Law Pro - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy European Union Cookie Law Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/european-union-cookie-law-pro/)
>
> ---


# European Union Cookie Law Pro

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > European Union Cookie Law Pro)

This is the main configuration screen where you’ll define the appearance, content, and behavior of your cookie notice. The module offers a live preview feature, allowing you to see your changes in real-time within the back office before saving.

#### **General Settings**

- **Enable Cookie Law Module:**

  - **What this setting does:** This is the master switch to turn the cookie notice on or off across your entire store.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The cookie notice will be displayed to visitors according to your other settings.
    - *When disabled (NO):* The cookie notice will not appear on your store, and no cookie consent will be collected by this module.
  - **Recommended value:** YES (to ensure legal compliance).
  - **Merchant scenario / example:** You would disable this temporarily during maintenance or if you’re testing a different cookie solution.
- **Cookie Expiration Time (in days):**

  - **What this setting does:** Determines how long a user’s cookie consent is remembered by your store. After this period, the user will be prompted for consent again.
  - **Effect of changing this setting:**
    - *When set to 365:* A user’s consent will be valid for one year.
    - *When set to 30:* Consent will be valid for one month.
  - **Recommended value:** 365 (one year) is a common and reasonable period for most regulations. Check local laws for specific requirements.
  - **Merchant scenario / example:** If your local regulations require re-consent every 6 months, you would set this to 180.
- **Display on Mobile Devices:**

  - **What this setting does:** Controls whether the cookie notice is shown to users browsing on smartphones and tablets.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The cookie notice will appear on mobile devices, adapting its layout for smaller screens.
    - *When disabled (NO):* Mobile users will not see the cookie notice.
  - **Recommended value:** YES (for full compliance across all devices).
  - **Merchant scenario / example:** You should always enable this, as mobile users are subject to the same privacy laws.
- **Display to Visitors from EU Countries Only:**

  - **What this setting does:** If enabled, the cookie notice will only be shown to visitors whose IP address indicates they are browsing from an EU member state.
  - **Effect of changing this setting:**
    - *When enabled (YES):* Non-EU visitors will not see the banner.
    - *When disabled (NO):* All visitors, regardless of their location, will see the banner.
  - **Recommended value:** Depends on your target audience and legal advice. If you only serve EU customers, YES might be appropriate. If you serve a global audience and want to be safe, NO is better.
  - **Merchant scenario / example:** An Australian store primarily serving Australian customers might enable this to avoid showing the banner to their main audience, while still complying for the few EU visitors. A global store might disable it to be universally compliant.

#### **Content & Links**

- **Cookie Law Message:**

  - **What this setting does:** This is the main text displayed within the cookie notice, informing users about cookie usage. You can use a rich text editor to format it.
  - **Effect of changing this setting:** The text you enter here will be the primary message your customers read.
  - **Recommended value:** A clear, concise message like “This website uses cookies to ensure you get the best experience on our website. [Learn More]”
  - **Merchant scenario / example:** You might include information about the types of cookies used (e.g., “We use cookies for analytics and to improve your shopping experience.”).
- **“Accept” Button Text:**

  - **What this setting does:** Defines the text displayed on the button that users click to accept cookies.
  - **Effect of changing this setting:** Changes the label of the acceptance button.
  - **Recommended value:** “Accept”, “Got it”, “OK”, “I understand”.
  - **Merchant scenario / example:** You might use “Accept & Continue” to encourage users to proceed.
- **“More Info” Button Text:**

  - **What this setting does:** Defines the text displayed on the button that users click to learn more about your cookie policy.
  - **Effect of changing this setting:** Changes the label of the information button.
  - **Recommended value:** “Learn More”, “More Info”, “Privacy Policy”.
  - **Merchant scenario / example:** You might use “Cookie Settings” if you have a detailed preference management system.
- **Link to Privacy Policy Page:**

  - **What this setting does:** Specifies the URL where users can find your full privacy or cookie policy. This link will be attached to the “More Info” button or a specific part of your message.
  - **Effect of changing this setting:** When users click the “More Info” button, they will be redirected to this URL.
  - **Recommended value:** The full URL of your CMS page (e.g., `https://yourstore.com/content/3-terms-and-conditions`).
  - **Merchant scenario / example:** You create a dedicated CMS page in PrestaShop (Design > Pages) for your “Cookie Policy” and link to it here.

#### **Display Options & Styling**

- **Cookie Notice Position:**

  - **What this setting does:** Determines where the cookie notice appears on your website.
  - **Effect of changing this setting:**
    - *Top Bar:* Banner appears at the top of the browser window.
    - *Bottom Bar:* Banner appears at the bottom of the browser window.
    - *Center Modal:* A pop-up in the middle of the screen.
    - *Floating Box (Top-Left, Top-Right, Bottom-Left, Bottom-Right):* A smaller, fixed box in one of the corners.
  - **Recommended value:** Bottom Bar or Floating Box are generally less intrusive. Center Modal is highly visible but can be disruptive.
  - **Merchant scenario / example:** A fashion store might prefer a subtle “Bottom Bar” to keep the focus on products, while a service-based business might use a “Center Modal” for maximum visibility.
- **Background Color:**

  - **What this setting does:** Sets the main background color of the cookie notice banner.
  - **Effect of changing this setting:** Changes the visual background of the notice.
  - **Recommended value:** A color that contrasts well with your text and matches your brand.
  - **Merchant scenario / example:** Use your brand’s primary color or a neutral grey.
- **Text Color:**

  - **What this setting does:** Sets the color of the main message text within the notice.
  - **Effect of changing this setting:** Changes the color of the message text.
  - **Recommended value:** A color that provides good readability against your chosen background.
  - **Merchant scenario / example:** White text on a dark background, or dark grey text on a light background.
- **Link Color:**

  - **What this setting does:** Sets the color for any links within your cookie message (e.g., the “Learn More” link if it’s part of the message).
  - **Effect of changing this setting:** Changes the color of clickable text within the message.
  - **Recommended value:** Your brand’s accent color or a standard blue for links.
  - **Merchant scenario / example:** Use a bright color to make the “Learn More” link stand out.
- **Button Background Color:**

  - **What this setting does:** Sets the background color for the “Accept” and “More Info” buttons.
  - **Effect of changing this setting:** Changes the visual background of the buttons.
  - **Recommended value:** A color that makes the buttons clearly visible and clickable.
  - **Merchant scenario / example:** Use your brand’s call-to-action color.
- **Button Text Color:**

  - **What this setting does:** Sets the color of the text on the “Accept” and “More Info” buttons.
  - **Effect of changing this setting:** Changes the color of the button labels.
  - **Recommended value:** A color that provides good contrast with the button background.
  - **Merchant scenario / example:** White text on a colored button, or black text on a light button.
- **Button Hover Background Color:**

  - **What this setting does:** Sets the background color of the buttons when a user hovers their mouse over them.
  - **Effect of changing this setting:** Provides visual feedback to the user that the button is interactive.
  - **Recommended value:** A slightly darker or lighter shade of the normal button background color.
  - **Merchant scenario / example:** A subtle change in color to indicate interactivity.
- **Button Hover Text Color:**

  - **What this setting does:** Sets the text color of the buttons when a user hovers their mouse over them.
  - **Effect of changing this setting:** Provides visual feedback.
  - **Recommended value:** Often the same as the normal button text color, or a contrasting color if the background changes significantly.
  - **Merchant scenario / example:** If your button background turns dark on hover, you might change the text to white.
- **Border Radius (px):**

  - **What this setting does:** Controls the roundness of the corners of the cookie notice and its buttons. A value of 0 means sharp corners, higher values mean rounder corners.
  - **Effect of changing this setting:**
    - *0px:* Sharp, square corners.
    - *5px:* Slightly rounded corners.
    - *20px:* Very rounded, pill-shaped corners.
  - **Recommended value:** 0-5px for a modern, clean look; higher for a softer, friendlier feel.
  - **Merchant scenario / example:** Match this to the border-radius used in your theme for consistency.
- **Glass Effect:**

  - **What this setting does:** Applies a translucent, frosted glass-like effect to the background of the cookie notice.
  - **Effect of changing this setting:** Makes the background slightly transparent and blurred, allowing content behind it to show through subtly.
  - **Recommended value:** Try it and see if it fits your design. It can add a premium feel.
  - **Merchant scenario / example:** Use this if your theme has a modern, minimalist aesthetic.
- **Gradient Background:**

  - **What this setting does:** Allows you to use a smooth transition between two colors for the background of the cookie notice instead of a single solid color.
  - **Effect of changing this setting:** Creates a visually appealing color blend. You’ll typically have options for a start and end color.
  - **Recommended value:** Use colors that complement each other and your brand.
  - **Merchant scenario / example:** A tech store might use a blue-to-purple gradient for a modern look.
- **Overlay Background Color (for Center Modal):**

  - **What this setting does:** When using the “Center Modal” position, this sets the color of the semi-transparent layer that covers the rest of the page behind the modal.
  - **Effect of changing this setting:** Controls the visual focus on the modal. A darker, more opaque overlay makes the modal stand out more.
  - **Recommended value:** A semi-transparent black (`rgba(0,0,0,0.7)`) or a dark shade that matches your theme.
  - **Merchant scenario / example:** Use a dark, slightly transparent overlay to ensure the cookie modal is the primary focus when it appears.
- **Custom CSS:**

  - **What this setting does:** Provides a text area where you can add your own custom CSS rules to further style the cookie notice, overriding the module’s default styles.
  - **Effect of changing this setting:** Allows for advanced customization beyond the provided options.
  - **Recommended value:** Leave empty unless you have specific design requirements and CSS knowledge.
  - **Merchant scenario / example:** You might use this to change the font size of the message, add a shadow, or adjust padding if the built-in options aren’t enough.

#### **Presets & Live Preview**

- **Load Preset:**

  - **What this setting does:** Allows you to quickly apply a predefined set of styling options (colors, positions, effects) from a library of ready-made designs.
  - **Effect of changing this setting:** Instantly transforms the look of your cookie notice to match the chosen preset. All individual styling settings will be updated.
  - **Recommended value:** Browse the presets to find one that closely matches your brand, then fine-tune it.
  - **Merchant scenario / example:** You’re looking for a dark, minimalist banner. You select a “Dark Theme” preset and then just adjust the exact shades of black and grey.
- **Live Preview:**

  - **What this setting does:** This section of the configuration page displays a real-time preview of your cookie notice as you adjust settings.
  - **Effect of changing this setting:** Shows you exactly how your banner will look on the front office, without needing to save and refresh your store.
  - **Recommended value:** Always use the live preview to verify your design choices before saving.
  - **Merchant scenario / example:** You’re experimenting with different button colors; the live preview immediately shows you which combination looks best.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Enable Cookie Law Module | YES | Master switch for the cookie notice. |
|  | Cookie Expiration Time (days) | 365 | How long consent is remembered. |
|  | Display on Mobile Devices | YES | Show banner on phones/tablets. |
|  | Display to EU Visitors Only | NO (for global compliance) | Target EU visitors or all visitors. |
|  | Cookie Law Message | Customizable | Main text of the cookie notice. |
|  | “Accept” Button Text | “Accept” | Label for the consent button. |
|  | “More Info” Button Text | “Learn More” | Label for the info button. |
|  | Link to Privacy Policy Page | Your Policy URL | URL for detailed cookie policy. |
|  | Cookie Notice Position | Bottom Bar / Floating Box | Where the banner appears (Top/Bottom Bar, Center Modal, Floating Box). |
|  | Background Color | Customizable | Main background color of the notice. |
|  | Text Color | Customizable | Color of the message text. |
|  | Link Color | Customizable | Color of links within the message. |
|  | Button Background Color | Customizable | Background color of action buttons. |
|  | Button Text Color | Customizable | Text color on action buttons. |
|  | Button Hover Background Color | Customizable | Background color on button hover. |
|  | Button Hover Text Color | Customizable | Text color on button hover. |
|  | Border Radius (px) | 0-5 | Roundness of corners. |
|  | Glass Effect | NO | Adds a translucent, frosted effect. |
|  | Gradient Background | NO | Uses a color gradient for the background. |
|  | Overlay Background Color | Semi-transparent dark | Color of the background overlay for Center Modal. |
|  | Custom CSS | Empty | For advanced styling overrides. |
|  | Load Preset | Choose one | Apply predefined styling options. |
|  | Live Preview | N/A | Real-time visual feedback of settings. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve configured the module, but the cookie banner isn’t showing up on my store.**
A:

1. **Check “Enable Cookie Law Module”:** Make sure it’s set to YES in the module configuration.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” (or “Clear Smarty cache” in older versions). Browser cache might also need clearing (Ctrl+F5 or Cmd+R).
3. **Check EU Country Setting:** If “Display to Visitors from EU Countries Only” is enabled, ensure you are testing from an EU IP address. Try disabling this setting temporarily for testing.
4. **Theme Compatibility:** While the module is designed to be compatible, some highly customized themes might have conflicts. Check your browser’s developer console (F12) for JavaScript errors.

**Q: The banner looks different on my store than in the live preview.**
A:

1. **Clear Cache:** Always clear your PrestaShop cache (**Advanced Parameters > Performance**) after making changes. Your browser cache might also be showing an older version.
2. **Custom CSS Conflicts:** If you’ve added “Custom CSS” or your theme has conflicting styles, they might override the module’s settings. Temporarily remove your custom CSS to see if that resolves the issue.
3. **Theme Overrides:** Your theme might have specific CSS rules that are more specific than the module’s. A developer can help identify and resolve these.

**Q: How do I translate the cookie message and button texts into other languages?**
A:

1. Go to **International > Translations** in your PrestaShop back office.
2. Select “Installed modules translations” as the Type of translation.
3. Choose your theme.
4. Select the language you want to translate.
5. Find the “European Union Cookie Law Pro” module in the list. You will be able to translate the “Cookie Law Message,” “Accept Button Text,” and “More Info Button Text” there.

**Q: The cookie banner is covering an important part of my website (e.g., a chat widget, menu item).**
A:

1. **Adjust Position:** Experiment with the “Cookie Notice Position” setting. If a bottom bar covers a chat widget, try a top bar or a floating box in a different corner.
2. **Custom CSS (Advanced):** If no position works, a developer can use the “Custom CSS” field to adjust the `z-index` property of the cookie banner or the conflicting element to ensure the correct element is on top.

**Q: Does this module handle different cookie categories (e.g., essential, analytics, marketing)?**
A: This module primarily focuses on displaying a general cookie consent notice and collecting a single “accept” or “decline” (via not accepting) consent. For more advanced, granular cookie category management (where users can select which types of cookies they allow), you would typically need a more complex solution or integrate with a dedicated Consent Management Platform (CMP). This module is designed for straightforward compliance.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a technical overview for developers and webmasters looking to understand, customize, or debug the “European Union Cookie Law Pro” module.

### 4.1 Architecture Overview

The `uecookiepro` module follows a standard PrestaShop module architecture, primarily leveraging the `Module` class for its core functionality and `getContent()` for back-office configuration. It injects its front-office content directly into a chosen hook, dynamically rendering the cookie banner based on configuration settings. Styling is managed through inline styles and potentially custom CSS, with JavaScript handling user interaction and consent storage.

### 4.2 Controllers (`controllers/`)

This module does not contain any custom front-office or back-office controllers. All configuration is handled within the main module file’s `getContent()` method, and front-office display is managed via hooks.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` instances. All configuration is stored directly in the `ps_configuration` table using standard PrestaShop configuration keys.

### 4.4 JavaScript Assets (`views/js/`)

The module includes several JavaScript files, primarily for back-office configuration enhancements and front-office interaction.

- `uecookiepro/jscolor/jscolor.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Provides the color picker functionality used in the module’s configuration form, allowing merchants to visually select colors for the banner.
- `uecookiepro/tinymce-original.js`:
  - **Scope:** Back-office.
  - **Responsibility:** The core TinyMCE rich text editor library. This is used for the “Cookie Law Message” field, enabling merchants to format their message with HTML.
- `uecookiepro/tinymce16.inc.js`:
  - **Scope:** Back-office.
  - **Responsibility:** An include file likely containing specific TinyMCE initialization and configuration settings tailored for PrestaShop 1.6.x environments, ensuring the editor functions correctly within the module’s configuration.
- `uecookiepro/views/js/patterns.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Likely contains predefined patterns or configurations for the module’s styling presets, used to quickly load different visual themes for the cookie banner.
- `uecookiepro/views/js/presets-community.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Contains additional community-contributed or extended presets for the cookie banner’s visual styling, offering more ready-to-use design options.
- `uecookiepro/views/js/scripts.js`:
  - **Scope:** Front-office and Back-office.
  - **Responsibility:** This is the main custom JavaScript file for the module.
    - **Front-office:** Handles the display logic of the cookie banner, listens for “Accept” button clicks, sets the consent cookie, and hides the banner. It also manages the visibility based on the `Cookie Expiration Time`.
    - **Back-office:** Likely contains logic for the live preview functionality, dynamically updating the preview banner as settings are changed in the configuration form. It might also handle interactions with the “Load Preset” feature.

### 4.5 CSS Stylesheets (`views/css/`)

The module does not explicitly list any `.css` files in the provided inventory. This suggests that styling is primarily handled through:

1. **Inline styles:** Generated dynamically by the module based on the configuration settings (colors, positions, etc.).
2. **`jscolor.js`’s internal CSS:** For the color picker UI.
3. **`tinymce`’s internal CSS:** For the rich text editor UI.
4. **Custom CSS field:** Allowing merchants to inject their own styles.
   Developers looking to override styles should inspect the rendered HTML of the cookie banner and target its elements with more specific CSS rules in their theme’s stylesheet or via the module’s custom CSS field.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `uecookiepro/top.tpl`:
    - **Hook:** This template is designed to be rendered in various front-office hooks such as `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, or even directly within the theme’s `product.tpl` or `index.tpl` depending on the chosen “Cookie Notice Position” and how the module’s `hookDisplay*` methods are implemented.
    - **Output:** It outputs the HTML structure for the cookie consent banner, including the message text, “Accept” button, and “More Info” link. The dynamic styling (colors, position, effects) is injected into this template, either as inline styles or through JavaScript manipulation.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  The module does not create any custom SQL tables. All configuration settings are stored in the standard PrestaShop `ps_configuration` table. Configuration keys typically follow the pattern `UECOOKIEPRO_SETTING_NAME`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of every page. | Potentially used to load CSS/JS assets or to inject the banner at the very top of the page. |
| `displayFooter` | Renders at the bottom of every page, before the closing `</body>` tag. | Common hook for injecting the cookie banner (bottom bar position) or its associated JavaScript. |
| `displayLeftColumn` | Renders in the left sidebar (if enabled by theme). | Less common for cookie banners, but could be used for a floating box in the left column. |
| `displayRightColumn` | Renders in the right sidebar (if enabled by theme). | Less common for cookie banners, but could be used for a floating box in the right column. |
| `displayProductAdditionalInfo` (or similar product page hook) | Renders on the product page, often below the product description or details. | Could be used to place a floating box specifically on product pages. |
| `actionFrontControllerSetMedia` | Executed when a front controller sets its media (CSS/JS). | Ideal for conditionally loading module-specific CSS and JavaScript only when needed, improving performance. |

The module dynamically chooses which hook to use based on the “Cookie Notice Position” setting. For example, if “Bottom Bar” is selected, it likely uses `displayFooter`. If “Top Bar” is selected, it might use `displayHeader`. The “Floating Box” or “Center Modal” positions are typically managed by injecting the HTML into a general hook like `displayFooter` and then using CSS (`position: fixed;`) and JavaScript to control its exact placement and visibility.

## 5. Official Support & Updates

For official support, module updates, and any further assistance, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to providing timely support and ensuring your module functions optimally.
