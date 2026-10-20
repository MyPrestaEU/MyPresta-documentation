---
title: "Manufacturers (brands) images block - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Manufacturers (brands) images block PrestaShop module by MyPresta.eu."
sidebar:
  label: "Manufacturers (brands) images block - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Manufacturers (brands) images block Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/manufacturers-brands-images-block/)
>
> ---


# Manufacturers (brands) images block

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, clicking “Configure” will take you to the main settings page for the “Manufacturers (brands) images block” module. Here you can customize how the brand block appears and behaves on your store.

#### **Position of manufacturers block**

- **What this setting does:** This crucial setting determines where the block of brand images will appear on your website. You can choose from various predefined locations (hooks) within your PrestaShop theme.
- **Effect of changing this setting:**
  - *When set to `displayRightColumn` (or `displayLeftColumn`):* The brand block will appear in the right (or left) sidebar of your store, typically alongside other blocks like categories or bestsellers. This is great for constant visibility.
  - *When set to `displayFooter`:* The block will appear at the very bottom of your website, often used for supplementary navigation.
  - *When set to `displayTop` (or `displayTopColumn`):* The block will be visible near the top of your page, often in the header area, making brands immediately noticeable.
  - *When set to `displayHome`:* The block will only appear on your store’s homepage, making it a central feature for brand discovery.
- **Recommended value:** `displayHome` for a prominent homepage feature, or `displayRightColumn` (or `displayLeftColumn`) for consistent visibility across product and category pages.
- **Merchant scenario / example:** If you want customers to easily browse brands while shopping for products, choose `displayRightColumn`. If you want to make a strong brand statement on your homepage, choose `displayHome`.

#### **Enable carousel**

- **What this setting does:** This setting transforms the static grid of brand logos into an animated, scrolling carousel.
- **Effect of changing this setting:**
  - *When enabled (YES):* Brand logos will scroll horizontally, allowing you to display many brands in a compact space. This is visually dynamic and saves screen real estate.
  - *When disabled (NO):* Brand logos will be displayed as a static grid, showing all available logos at once (or as many as fit the block’s dimensions). This offers immediate overview without interaction.
- **Recommended value:** `YES` if you have many brands or want a more modern, dynamic look. `NO` if you have only a few brands and prefer a static display.
- **Merchant scenario / example:** If you carry 50+ brands, enabling the carousel is essential to avoid a very long, cluttered block. If you only have 5-10 brands, a static display might be sufficient.

#### **Activate categories filter**

- **What this setting does:** This allows the module to display only those manufacturers that are associated with products within the *currently viewed category*.
- **Effect of changing this setting:**
  - *When enabled (YES):* On a category page (e.g., “T-Shirts”), the brand block will only show logos of manufacturers who produce T-shirts. This makes the block highly relevant to the customer’s current browsing context.
  - *When disabled (NO):* The brand block will always show *all* active manufacturers in your store, regardless of the current page or category.
- **Recommended value:** `YES` for better user experience and relevance, especially in stores with diverse product categories.
- **Merchant scenario / example:** A customer browsing “Smartphones” will only see brands like Apple, Samsung, and Xiaomi if this is enabled, rather than also seeing clothing brands. This helps them narrow down their search.

#### **Enable auto-scroll for carousel**

- **What this setting does:** If the carousel is enabled, this setting controls whether the brand logos automatically scroll without customer interaction.
- **Effect of changing this setting:**
  - *When enabled (YES):* The carousel will automatically slide through brand logos at a set speed, creating a dynamic visual effect.
  - *When disabled (NO):* The carousel will only scroll when the customer manually clicks navigation arrows or drags the carousel.
- **Recommended value:** `YES` for a more engaging and dynamic display, but ensure the speed is not too fast.
- **Merchant scenario / example:** You want to ensure all your brands get some visibility even if customers don’t interact with the carousel. Enabling auto-scroll achieves this.

#### **Speed of auto-scroll**

- **What this setting does:** This setting defines how quickly the carousel automatically scrolls from one set of brands to the next, measured in milliseconds. (Only applicable if “Enable auto-scroll for carousel” is YES).
- **Effect of changing this setting:**
  - *Higher value (e.g., 5000ms = 5 seconds):* Slower scroll speed, giving customers more time to view each set of logos.
  - *Lower value (e.g., 2000ms = 2 seconds):* Faster scroll speed, making the carousel more dynamic but potentially harder to read.
- **Recommended value:** 3000-5000 milliseconds (3-5 seconds) for a comfortable viewing experience.
- **Merchant scenario / example:** If you have many brands and want customers to see them all without feeling rushed, set a slower speed like 4000ms.

#### **Pause carousel on mouseover**

- **What this setting does:** If auto-scroll is enabled, this setting controls whether the carousel temporarily stops scrolling when a customer moves their mouse cursor over the brand block.
- **Effect of changing this setting:**
  - *When enabled (YES):* The carousel will pause, allowing the customer to comfortably examine a brand logo or click on it without the carousel moving away. This improves user experience.
  - *When disabled (NO):* The carousel will continue to auto-scroll even if the mouse is over it, which can be frustrating for customers trying to interact.
- **Recommended value:** `YES` for a better user experience.
- **Merchant scenario / example:** A customer sees a brand they like and moves their mouse to click it. If the carousel pauses, they can easily click. If it doesn’t, the brand might scroll away before they can react.

#### **Size of brand image**

- **What this setting does:** This setting allows you to define the maximum width of the brand images displayed in the block. The height will scale proportionally.
- **Effect of changing this setting:**
  - *Larger value (e.g., 150px):* Brand logos will appear larger, making them more prominent and easier to see. This might take up more space in the block.
  - *Smaller value (e.g., 80px):* Brand logos will appear smaller, allowing more logos to fit in a given space but potentially making them less noticeable.
- **Recommended value:** 100-120 pixels for a good balance of visibility and space efficiency. Adjust based on your theme’s layout.
- **Merchant scenario / example:** If your sidebar is narrow, you might need to set a smaller image size (e.g., 80px) to prevent logos from overflowing. On a wide homepage block, you might use 150px for greater impact.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Position of manufacturers block | `displayHome` or `displayRightColumn` | Determines where the brand block appears (e.g., homepage, sidebar, footer). |
| Module Configuration | Enable carousel | `YES` | Transforms static grid into a scrolling carousel for dynamic display. |
| Module Configuration | Activate categories filter | `YES` | Shows only brands relevant to the current category being viewed. |
| Module Configuration | Enable auto-scroll for carousel | `YES` | Makes the carousel automatically scroll through brands. |
| Module Configuration | Speed of auto-scroll | 3000-5000ms | Controls how fast the carousel scrolls (in milliseconds). |
| Module Configuration | Pause carousel on mouseover | `YES` | Stops auto-scroll when a customer hovers over the block. |
| Module Configuration | Size of brand image | 100-120px | Sets the maximum width for brand logos in the block. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My brand block isn’t showing up after installation, or it’s in the wrong place.**

- **A:** First, check the module’s configuration page in your Back Office. Ensure the “Position of manufacturers block” setting is correctly chosen. If it’s set to `displayHome`, it will only appear on the homepage. If it’s set to a column, ensure your theme actually displays that column on the pages you’re viewing.
- **A:** Clear your PrestaShop cache. Go to **Advanced Parameters > Performance**, then click “Clear cache” in the top right. Sometimes, theme changes or new module installations require a cache refresh.
- **A:** Check your theme’s “Positions” (Design > Positions in PS 1.7/8). Ensure the module is hooked to the desired position. If it’s not listed, try re-saving the module’s configuration.

**Q2: My brand images look distorted or are not the right size.**

- **A:** Go to the module’s configuration and adjust the “Size of brand image” setting. This controls the maximum width.
- **A:** Ensure the original manufacturer images uploaded to PrestaShop (Catalog > Manufacturers) are of good quality and ideally have a consistent aspect ratio. While the module scales them, heavily distorted source images will still look bad.
- **A:** After changing image sizes, it’s often a good idea to regenerate thumbnails. Go to **Design > Image Settings** (or **Preferences > Images** in older PS versions) and click “Regenerate thumbnails.” Select “manufacturers” as the image type.

**Q3: The carousel isn’t scrolling, or the auto-scroll isn’t working.**

- **A:** Check if “Enable carousel” is set to `YES`. If not, it will be a static block.
- **A:** If the carousel is enabled, check if “Enable auto-scroll for carousel” is also set to `YES`. If this is `NO`, the carousel will only move manually.
- **A:** If both are enabled, check your browser’s developer console (F12) for any JavaScript errors. Conflicts with other modules or theme scripts can sometimes prevent carousels from functioning. Try temporarily disabling other modules to isolate the issue.

**Q4: The “Activate categories filter” isn’t working; I still see all brands on category pages.**

- **A:** Ensure this setting is set to `YES` in the module configuration.
- **A:** Verify that your products are correctly associated with both a category and a manufacturer in your PrestaShop catalog. If a product isn’t linked to a manufacturer, or the manufacturer isn’t linked to any products in that category, it won’t appear when filtered.
- **A:** Clear your PrestaShop cache after making any changes to product/manufacturer associations.

**Q5: How do I translate the module’s title or text?**

- **A:** Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations,” choose your theme, and select the language you want to translate.
- Find the “Manufacturers (brands) images block” module in the list and you can edit any translatable strings it provides (e.g., the block title).

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Manufacturers (brands) images block” module (`mib`) is a standard PrestaShop module following an MVC-like pattern. It primarily leverages PrestaShop’s hook system to inject its content into various front-office positions. The core logic resides in the main `mib.php` file, which handles installation, uninstallation, configuration, and content rendering for the hooks. It uses a third-party JavaScript library (`lightslider.js`) for the carousel functionality and custom CSS for styling. Configuration settings are stored in `ps_configuration`.

### 4.2 Controllers (`controllers/`)

This module does not utilize custom Front-Office or Back-Office Admin Controllers. All configuration is handled via the `getContent()` method in the main module file, and front-office rendering is done directly through hook methods.

### 4.3 Core Classes & Models (`classes/`)

This module does not define any custom classes or `ObjectModel` entities. It directly interacts with PrestaShop’s core `Manufacturer` and `Category` objects and `Configuration` for settings.

### 4.4 JavaScript Assets (`views/js/`)

- **`mib/lib/js/lightslider.js`**
  - **Scope:** Front-office.
  - **Description:** This is a third-party jQuery plugin responsible for creating the responsive content carousel. It handles the sliding animation, navigation controls, and responsive behavior for the brand logos when the carousel option is enabled.
  - **Key Functionality:** Initializes `lightSlider` on a specified HTML element, manages slide transitions, touch/swipe gestures, and responsive adjustments.
- **`mib/views/js/mib.js`**
  - **Scope:** Front-office.
  - **Description:** This is the module’s custom JavaScript file. It contains the initialization logic for the `lightslider.js` plugin based on the module’s configuration settings.
  - **Key Functionality:**
    - Checks if the carousel is enabled (`MIB_CAROUSEL` configuration).
    - Initializes the `lightSlider` on the `#lightSlider` element within the module’s template.
    - Passes configuration options to `lightSlider` such as `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` based on `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, and `MIB_IMG` settings.
    - Ensures the slider is only initialized if the element exists.

### 4.5 CSS Stylesheets (`views/css/`)

- **`mib/lib/css/lightslider.css`**
  - **Scope:** Front-office customer styling.
  - **Description:** This is the core stylesheet for the `lightslider.js` plugin. It provides the necessary styling for the carousel structure, navigation arrows, and pagination dots.
  - **Key CSS Selectors:** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide`, etc. Developers can override these to customize the carousel’s appearance.
- **`mib/mib.css`**
  - **Scope:** Front-office customer styling.
  - **Description:** This is the module’s custom stylesheet. It provides specific styling for the brand block container, individual brand images, and any hover effects.
  - **Key CSS Selectors:**
    - `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer`: Main container IDs for different hook positions.
    - `.mib_manufacturer_item`: Styles for individual manufacturer links/containers.
    - `.mib_manufacturer_item img`: Styles for the brand images, including `max-width` and `height` adjustments.
    - `.mib_manufacturer_item:hover img`: Defines the hover animation (e.g., `transform: scale(1.1)` for a zoom effect).

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:
  - **`mib/views/templates/hook/mib.tpl`**
    - **Hooked to:** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
    - **Purpose:** This is the main front-office template responsible for rendering the brand block. It dynamically generates the HTML structure for either a static grid of manufacturer logos or the `lightSlider` carousel, based on the module’s configuration.
    - **Key Elements:**
      - Conditional rendering for carousel (`{if $mib_carousel}`).
      - Looping through `$manufacturers` array to display each brand’s image and link.
      - Includes the `mib.js` and `lightslider.js` if the carousel is enabled.
      - Includes `mib.css` and `lightslider.css`.
      - Uses `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` for manufacturer URLs.
      - Uses `{$manufacturer.image}` for brand image paths.
- **Admin templates (`views/templates/admin/`)**:
  - **`mib/views/templates/admin/admin.tpl`**
    - **Purpose:** This template renders the module’s configuration form in the PrestaShop Back Office. It displays all the settings (position, carousel options, image size, etc.) as input fields, select boxes, and switches.
    - **Key Elements:**
      - Standard PrestaShop helper form structure (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
      - Input fields for `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
      - Uses `{$mib_form_action}` for form submission.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:
  - This module does not create any custom database tables.
  - Configuration settings are stored in the `ps_configuration` table using keys such as `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE`.
- **Registered Hooks Table**:

| Hook Name | Execution Timing & Location | Technical Purpose |
| --- | --- | --- |
| `displayRightColumn` | Renders in the right sidebar of the front-office. | Displays the brand block in the right column. |
| `displayFooter` | Renders in the footer section of the front-office. | Displays the brand block in the store’s footer. |
| `displayTop` | Renders in the top section of the front-office (often header). | Displays the brand block in the header area. |
| `actionAdminControllerSetMedia` | Executed when an admin controller sets its media assets. | Used to include the module’s CSS and JS files in the Back Office for configuration. |
| `displayLeftColumn` | Renders in the left sidebar of the front-office. | Displays the brand block in the left column. |
| `displayHome` | Renders on the homepage of the front-office. | Displays the brand block prominently on the homepage. |
| `displayHeader` | Executed in the `<head>` section of every front-office page. | Used to include necessary CSS and JS files for the front-office display. |
| `displayTopColumn` | Renders in the top column section of the front-office (below `displayTop`). | Displays the brand block in the top column area. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Manufacturers (brands) images block” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module’s functionality and integration.
