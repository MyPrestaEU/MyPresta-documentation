---
title: "Homepage news - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Homepage news PrestaShop module by MyPresta.eu."
sidebar:
  label: "Homepage news - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Homepage news Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/homepage-news/)
>
> ---


# Homepage news

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and are sufficient for this module.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Homepage news” module, where you control how your news articles are displayed on the homepage.

#### **Select Category of CMS pages**

- **What this setting does:** This dropdown allows you to choose which specific CMS category will be used as the source for your homepage news. Only CMS pages belonging to this selected category will be considered for display by the module.
- **Effect of changing this setting:**
  - *When a category is selected:* The module will fetch and display news articles only from CMS pages within that category.
  - *When no category is selected (or an inappropriate one):* The module might not display any news, or it might display pages you didn’t intend to be news articles.
- **Recommended value:** Select the CMS category you have specifically created or designated for your news articles (e.g., “News,” “Blog,” “Updates”).
- **Merchant scenario / example:** You’ve created a CMS category called “Company News” and added several CMS pages to it, such as “New Product Launch,” “Summer Sale Announced,” and “Holiday Opening Hours.” By selecting “Company News” here, only these pages will appear as news on your homepage.

#### **Show full contents of latest CMS page**

- **What this setting does:** This switch determines whether the very latest news article (CMS page) from your selected category will be displayed with its complete content directly on the homepage.
- **Effect of changing this setting:**
  - *When enabled (YES):* The most recent news article’s full content will be visible on your homepage, providing immediate information without requiring a click.
  - *When disabled (NO):* Only the title, miniature, and a short description (if configured) of the latest news article will be shown, similar to other miniatures. Customers will need to click to read the full content.
- **Recommended value:** “YES” if you want to highlight your most important news immediately; “NO” if you prefer a more compact news section where all articles require a click.
- **Merchant scenario / example:** You have a major announcement, like a new store opening. Enabling this ensures customers see the full details right away. If you prefer a cleaner homepage, you might disable it and only show excerpts.

#### **Show CMS pages miniatures**

- **What this setting does:** This switch controls whether smaller, summarized versions (miniatures) of your news articles are displayed on the homepage. These miniatures typically include a title, a small image, and a short description.
- **Effect of changing this setting:**
  - *When enabled (YES):* The module will display a series of miniature news blocks, each representing a recent CMS page from your selected category.
  - *When disabled (NO):* No miniatures will be shown. If “Show full contents of latest CMS page” is also disabled, no news will appear at all.
- **Recommended value:** “YES” to provide an overview of multiple news articles and encourage exploration.
- **Merchant scenario / example:** You want to show the latest 3-5 news articles to give customers a quick glance at recent updates. Enabling miniatures achieves this.

#### **Number of miniatures to display**

- **What this setting does:** If “Show CMS pages miniatures” is enabled, this input field determines how many of the most recent news article miniatures will be shown on your homepage.
- **Effect of changing this setting:**
  - *When set to a higher number (e.g., 5):* More news article miniatures will be visible, providing a broader overview.
  - *When set to a lower number (e.g., 2):* Fewer miniatures will be displayed, making the news section more concise.
- **Recommended value:** 3 to 5, depending on your homepage layout and how much space you want to dedicate to news.
- **Merchant scenario / example:** You have a lot of news but want to keep your homepage clean. Setting this to “3” ensures only the three most recent articles are highlighted.

#### **Number of characters used in description for miniatures**

- **What this setting does:** This input field controls the length of the short description (excerpt) displayed within each news miniature.
- **Effect of changing this setting:**
  - *When set to a higher number (e.g., 200):* The descriptions in the miniatures will be longer, providing more context.
  - *When set to a lower number (e.g., 50):* The descriptions will be shorter, making the miniatures more compact.
- **Recommended value:** 100 to 150 characters, enough to give a good summary without overwhelming the miniature.
- **Merchant scenario / example:** You want to give customers just enough information in the miniature to pique their interest. Setting this to “120” ensures a concise yet informative snippet.

#### **Style of miniatures**

- **What this setting does:** This option (likely a dropdown or radio buttons) allows you to choose the visual layout or style for how the news miniatures are presented on your homepage. The available styles might include options like a grid, a list, or a carousel.
- **Effect of changing this setting:**
  - *When set to “Grid”:* Miniatures might appear in rows and columns, suitable for displaying several items compactly.
  - *When set to “List”:* Miniatures might appear one below the other, good for more detailed descriptions.
  - *When set to “Carousel”:* Miniatures might slide horizontally, saving space and allowing users to browse more items.
- **Recommended value:** Experiment with the available styles to see which best fits your theme’s design and your desired homepage aesthetic.
- **Merchant scenario / example:** Your homepage has limited horizontal space. Choosing a “Carousel” style allows you to display many news items without making the page too long. If you have ample space, a “Grid” might look more appealing.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Select Category of CMS pages | Your designated “News” CMS category | Defines which CMS pages are sourced as news. |
| Module Configuration | Show full contents of latest CMS page | YES | Displays the full content of the newest article directly on the homepage. |
| Module Configuration | Show CMS pages miniatures | YES | Enables the display of summarized news blocks. |
| Module Configuration | Number of miniatures to display | 3-5 | Controls how many recent news miniatures are shown. |
| Module Configuration | Number of characters used in description for miniatures | 100-150 | Sets the length of the text excerpt in miniatures. |
| Module Configuration | Style of miniatures | Varies (e.g., Grid, List, Carousel) | Determines the visual layout of news miniatures. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My news section isn’t showing up on the homepage. What should I check?**
A:

1. **Module Enabled:** Go to **Modules > Module Manager** and ensure “Homepage news” is installed and enabled.
2. **CMS Category Selected:** In the module’s configuration, verify that you have selected a valid CMS category under “Select Category of CMS pages.”
3. **CMS Pages Exist:** Make sure there are actual CMS pages published within the selected category.
4. **Visibility Settings:** Check if “Show CMS pages miniatures” and/or “Show full contents of latest CMS page” are enabled in the module configuration. If both are disabled, nothing will show.
5. **Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).

**Q: The images for my news miniatures aren’t appearing.**
A: The module typically tries to extract the first image from the content of your CMS page.

1. **Image in CMS Page:** Ensure your CMS page content actually includes an image.
2. **Image Path:** Verify the image path in your CMS page is correct and the image file exists on your server.
3. **Theme Compatibility:** Some custom themes might interfere with image rendering. If all else fails, consult your theme developer or MyPresta.eu support.

**Q: How do I translate the news titles and descriptions?**
A: The news titles and content come directly from your CMS pages.

1. **CMS Page Translations:** Go to **Design > Pages** (or **CMS** in older versions), edit your news CMS page.
2. **Edit in All Languages:** For each language you support, ensure you’ve provided the translated title and content for that specific CMS page. The module will automatically display the correct language based on the customer’s selected store language.

**Q: The news section looks strange or misaligned on my homepage.**
A: This is often a CSS conflict with your store’s theme.

1. **Clear Cache:** Always start by clearing your PrestaShop cache (**Advanced Parameters > Performance > Clear cache**).
2. **Module Configuration:** Check if changing the “Style of miniatures” setting helps.
3. **Theme Customization:** Your theme’s CSS might be overriding the module’s styles. You may need to consult a web developer to add custom CSS to your theme to adjust the appearance. MyPresta.eu support can offer guidance but cannot provide custom theme development.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Homepage news” module (`hnews`) is a straightforward PrestaShop module primarily designed to display content from existing CMS pages on the front-office homepage. It leverages PrestaShop’s `Module` class and standard hooks. The module’s logic resides mainly within its main PHP file, `hnews.php`, which handles configuration, hook registration, and data retrieval. It does not introduce custom controllers or complex ObjectModels, relying instead on PrestaShop’s native `CMSCategory` and `CMS` classes for data.

### 4.2 Controllers (`controllers/`)

- **Front-Office Controllers**: None. The module’s front-office display logic is entirely handled by its `hookDisplayHome` method within `hnews.php` and rendered via a Smarty template.
- **Back-Office Admin Controllers**: None. All configuration is managed through the `getContent()` method of the main module class.

### 4.3 Core Classes & Models (`classes/`)

- No custom classes or ObjectModels are introduced by this module. It directly queries the database or uses PrestaShop’s core `CMSCategory` and `CMS` classes to retrieve data.

### 4.4 JavaScript Assets (`views/js/`)

- No custom JavaScript files are included in this module.

### 4.5 CSS Stylesheets (`views/css/`)

- `hnews/views/admin/css/hnews.css`:
  - **Scope:** Back-office admin form styling.
  - **Main UI components:** Likely contains styles specific to the module’s configuration page, ensuring a consistent and readable layout within the PrestaShop back office.
  - **Key CSS class selectors:** May include styles for form elements, labels, and specific containers used in `getContent()`.
- `hnews/views/css/hnews.css`:
  - **Scope:** Front-office customer styling.
  - **Main UI components:** Styles the news section displayed on the homepage, including the main news article (if full content is shown) and the individual news miniatures.
  - **Key CSS class selectors:** Will contain selectors for the main news container, individual miniature blocks, titles, descriptions, and images. Developers can override these classes in their theme’s `custom.css` or `theme.css` to match the store’s design.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - `hnews/views/hnews.tpl`: This is the primary front-office template.
    - **Hook:** Rendered in `displayHome`.
    - **Visual block:** Outputs the entire news section on the homepage, including the full content of the latest news article (if enabled) and the list of news miniatures. It iterates through the news articles passed from the module’s PHP logic.
- **Admin templates (`views/templates/admin/`)**:
  - `hnews/views/admin/elements.tpl`:
    - **Hook:** Not directly hooked, but included/rendered by `getContent()` method in `hnews.php`.
    - **Visual block:** Renders the configuration form elements for the module in the PrestaShop back office. This typically includes the dropdown for CMS categories, switches for display options, and input fields for counts and character limits.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - The module does not create any custom SQL tables.
  - It stores its configuration settings in the `ps_configuration` table using keys like `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHome` | Renders content in the main homepage area. | Displays the news section with the latest CMS pages. |
| `displayHeader` | Executed in the `<head>` section of the front-office page. | Potentially used to load front-office CSS or JS assets (though no JS is present, CSS is loaded). |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media (CSS/JS). | Used to load back-office CSS for the module’s configuration page. |
| `header` | Similar to `displayHeader`, often used for asset loading. | Potentially used to load front-office CSS or JS assets. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Homepage news” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any module-related inquiries or issues.
