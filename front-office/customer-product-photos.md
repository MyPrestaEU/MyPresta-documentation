---
title: "Customer product photos - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer product photos PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer product photos - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer product photos Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/customer-product-photos/)
>
> ---


# Customer product photos

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the “Customer product photos” module. You’ll find a variety of settings here to control how the module behaves and appears on your storefront.

#### General Settings

- **Allow JPEG files?**
  - **What this setting does:** Determines if customers can upload images in the JPEG format.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can upload `.jpg` or `.jpeg` files.
    - *When disabled:* JPEG files will be rejected during upload.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Most photos are taken in JPEG. Keeping this enabled ensures maximum compatibility for customer uploads.
- **Allow GIF files?**
  - **What this setting does:** Determines if customers can upload images in the GIF format.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can upload `.gif` files.
    - *When disabled:* GIF files will be rejected during upload.
  - **Recommended value:** YES (unless you have a specific reason to disallow animated images)
  - **Merchant scenario / example:** GIFs can be useful for showing short animations of a product, but can also be larger files. Enable if you want to support them.
- **Allow PNG files?**
  - **What this setting does:** Determines if customers can upload images in the PNG format.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can upload `.png` files.
    - *When disabled:* PNG files will be rejected during upload.
  - **Recommended value:** YES
  - **Merchant scenario / example:** PNGs are great for images with transparency or sharp graphics. It’s a common format, so enabling it is generally a good idea.
- **Allow BMP files?**
  - **What this setting does:** Determines if customers can upload images in the BMP format.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can upload `.bmp` files.
    - *When disabled:* BMP files will be rejected during upload.
  - **Recommended value:** NO (unless specifically required)
  - **Merchant scenario / example:** BMP files are typically very large and uncompressed, making them unsuitable for web use. Disabling this helps keep your gallery efficient.
- **Allow unlogged customers to upload photos?**
  - **What this setting does:** Controls whether visitors who are not logged into a customer account can upload photos.
  - **Effect of changing this setting:**
    - *When enabled:* Guests can upload photos. They might be prompted for an email address or name.
    - *When disabled:* Only registered and logged-in customers can upload photos.
  - **Recommended value:** YES (if you want maximum content generation), NO (if you want to tie content to specific customer accounts)
  - **Merchant scenario / example:** If you want to maximize user-generated content, allowing guests is beneficial. If you want to track who uploads what and potentially reward them, require login.
- **Maximum file size (in MB)**
  - **What this setting does:** Sets the upper limit for the size of an image file a customer can upload.
  - **Effect of changing this setting:**
    - *When set to 5:* Customers cannot upload files larger than 5MB.
    - *When set to 0:* No limit (though PHP server limits will still apply).
  - **Recommended value:** 2-5 MB
  - **Merchant scenario / example:** A reasonable limit prevents customers from uploading excessively large files that could slow down your site or consume too much server space. 2-5MB is usually sufficient for high-quality web images.
- **Thumbnail Height (px)**
  - **What this setting does:** Defines the height of the thumbnail images generated for the gallery.
  - **Effect of changing this setting:**
    - *When set to 100:* All thumbnails will be 100 pixels tall.
    - *When set to 200:* All thumbnails will be 200 pixels tall.
  - **Recommended value:** 150-250px (adjust based on your theme’s design)
  - **Merchant scenario / example:** Consistent thumbnail sizes ensure a clean and organized gallery layout. Adjust this to fit your theme’s aesthetic.
- **Thumbnail Width (px)**
  - **What this setting does:** Defines the width of the thumbnail images generated for the gallery.
  - **Effect of changing this setting:**
    - *When set to 100:* All thumbnails will be 100 pixels wide.
    - *When set to 200:* All thumbnails will be 200 pixels wide.
  - **Recommended value:** 150-250px (adjust based on your theme’s design)
  - **Merchant scenario / example:** Similar to height, consistent width helps maintain a visually appealing gallery.
- **Photos per page in gallery** (CG\_PAGINATION)
  - **What this setting does:** Controls how many customer photos are displayed on a single page in the main gallery view before pagination kicks in.
  - **Effect of changing this setting:**
    - *When set to 12:* The gallery will show 12 photos per page.
    - *When set to 24:* The gallery will show 24 photos per page.
  - **Recommended value:** 12-24
  - **Merchant scenario / example:** A moderate number prevents overwhelming the user and keeps page load times reasonable. Too few means more clicks, too many can slow down the page.
- **Enable Voting for Photos?** (CG\_voting)
  - **What this setting does:** Allows customers to vote on uploaded photos, typically with a simple “like” or star rating.
  - **Effect of changing this setting:**
    - *When enabled:* Voting controls (e.g., stars, thumbs up) will appear next to each photo.
    - *When disabled:* No voting options will be displayed.
  - **Recommended value:** YES (encourages interaction)
  - **Merchant scenario / example:** Enabling voting can highlight popular photos and encourage more engagement from your community.
- **Allow unlogged customers to vote?** (cg\_unl\_voting)
  - **What this setting does:** Determines if visitors who are not logged in can cast votes on photos.
  - **Effect of changing this setting:**
    - *When enabled:* Guests can vote on photos.
    - *When disabled:* Only logged-in customers can vote.
  - **Recommended value:** NO (to prevent spam/bot voting and ensure more meaningful engagement)
  - **Merchant scenario / example:** Restricting voting to logged-in users helps ensure that votes come from actual customers and reduces the risk of manipulation.
- **Voting Style** (CG\_VOTE\_STAR, CGV\_voting)
  - **What this setting does:** Selects the visual style for the voting mechanism (e.g., different star colors).
  - **Effect of changing this setting:**
    - *When set to ‘Black Stars’:* Voting will use black star icons.
    - *When set to ‘Gold Stars’:* Voting will use gold star icons.
  - **Recommended value:** Gold Stars (often associated with quality and reviews)
  - **Merchant scenario / example:** Choose a style that best matches your store’s branding and aesthetic.
- **Enable Contest Mode?** (cg\_contest)
  - **What this setting does:** Activates features that support running a photo contest, such as displaying winners or specific contest rules.
  - **Effect of changing this setting:**
    - *When enabled:* Additional contest-related options or displays might appear.
    - *When disabled:* Standard gallery behavior.
  - **Recommended value:** NO (unless you are actively running a contest)
  - **Merchant scenario / example:** If you plan to run a “best photo” contest, enable this to leverage the module’s contest features.

#### Front-Office Display Locations

These settings control where the customer photo gallery and upload options appear on your storefront.

- **Show upload form on product page?** (CG\_FUPLOADON)
  - **What this setting does:** Determines if the photo upload form is directly visible on the product page.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a form to upload photos directly on the product page.
    - *When disabled:* The upload form will not appear on the product page; customers might need to go to their account or a dedicated gallery page to upload.
  - **Recommended value:** YES (for maximum convenience and content generation)
  - **Merchant scenario / example:** Making the upload form easily accessible on the product page encourages more customers to share their photos right after viewing the product.
- **Show gallery on product page as a tab?** (CG\_PRODUCTTAB, cg\_productTabM)
  - **What this setting does:** Integrates the customer photo gallery as a new tab on the product page (e.g., next to “Description” or “Data Sheet”).
  - **Effect of changing this setting:**
    - *When enabled:* A new tab will appear on product pages, displaying customer photos for that specific product.
    - *When disabled:* The gallery will not appear as a tab.
  - **Recommended value:** YES
  - **Merchant scenario / example:** This is a very prominent and effective way to display user-generated content, making it easily discoverable for shoppers.
- **Show gallery on product page in footer?** (CG\_PRODUCTFOOTER)
  - **What this setting does:** Displays a section of customer photos in the footer area of the product page.
  - **Effect of changing this setting:**
    - *When enabled:* A block of customer photos will appear below the main product content.
    - *When disabled:* No photos will appear in the product page footer.
  - **Recommended value:** YES (as an additional display point)
  - **Merchant scenario / example:** This provides another opportunity to showcase customer photos without cluttering the main product information area.
- **Show gallery in customer account?** (CG\_CUSTOMERACCOUNT, CG\_CUSTOMERACCOUNTV)
  - **What this setting does:** Creates a dedicated “My Photos” section within the customer’s personal account area.
  - **Effect of changing this setting:**
    - *When enabled:* Logged-in customers will see a new link and page in their account to manage their uploaded photos.
    - *When disabled:* Customers cannot manage their photos from their account.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Essential for customers to view and manage their contributions, fostering a sense of ownership and community.
- **Show link to gallery in “My Account” block?** (CG\_MYACCOUNTBLOCK, CG\_MYACCOUNTBLOCKV)
  - **What this setting does:** Adds a link to the “My Photos” section (or the main gallery) in the “My Account” block, which is often found in the left or right column or footer.
  - **Effect of changing this setting:**
    - *When enabled:* A quick link will appear for logged-in users.
    - *When disabled:* The link will not be present in the block.
  - **Recommended value:** YES (for easy navigation)
  - **Merchant scenario / example:** Makes it very easy for customers to access their photo gallery or upload new photos from almost any page.
- **Show gallery in right column?** (CG\_RIGHTCOL)
  - **What this setting does:** Displays a block of customer photos in your store’s right column.
  - **Effect of changing this setting:**
    - *When enabled:* A dynamic block of photos will appear in the right sidebar.
    - *When disabled:* No photos will appear in the right column.
  - **Recommended value:** NO (can be distracting, consider only if your theme has ample space)
  - **Merchant scenario / example:** Useful if you have a wide layout and want to constantly showcase customer content, but can sometimes clutter the page.
- **Show gallery in left column?** (CG\_LEFTCOL)
  - **What this setting does:** Displays a block of customer photos in your store’s left column.
  - **Effect of changing this setting:**
    - *When enabled:* A dynamic block of photos will appear in the left sidebar.
    - *When disabled:* No photos will appear in the left column.
  - **Recommended value:** NO (similar to right column, use sparingly)
  - **Merchant scenario / example:** Similar to the right column, use if your theme design allows for it without compromising readability.
- **Show gallery on homepage?** (CG\_GALLERY, cg\_hpg\_nb, cg\_hpg\_o)
  - **What this setting does:** Displays a selection of customer photos directly on your store’s homepage. You might also have options to control the number of photos (cg\_hpg\_nb) and their order (cg\_hpg\_o).
  - **Effect of changing this setting:**
    - *When enabled:* A section with customer photos will appear on the homepage.
    - *When disabled:* No customer photos will be shown on the homepage.
  - **Recommended value:** YES (highly recommended for engagement)
  - **Merchant scenario / example:** The homepage is prime real estate. Showcasing customer photos here immediately conveys trust and community to new visitors.
- **Exclude specific products from gallery?** (cg\_excludeproduct)
  - **What this setting does:** Allows you to specify product IDs that should not have customer photos displayed or uploaded.
  - **Effect of changing this setting:**
    - *When product ID 123 is entered:* Product 123 will not show customer photos, and uploads for it will be disabled.
    - *When left empty:* All products are eligible for customer photos.
  - **Recommended value:** Leave empty unless you have sensitive or non-visual products.
  - **Merchant scenario / example:** If you sell digital products or services that don’t have a visual component, or products you don’t want user-generated content for, you can exclude them here.

#### Notifications & Updates

- **Enable email notifications for new uploads?** (CG\_NTF)
  - **What this setting does:** Sends an email notification to the store administrator whenever a new customer photo is uploaded.
  - **Effect of changing this setting:**
    - *When enabled:* You will receive an email for each new upload, allowing you to moderate quickly.
    - *When disabled:* No email notifications will be sent.
  - **Recommended value:** YES (essential for moderation and quality control)
  - **Merchant scenario / example:** Staying on top of new uploads helps you ensure that all content is appropriate and high-quality before it’s widely visible.
- **MyPresta.eu Updates** (mypresta\_updates, update\_, updatev\_)
  - **What this setting does:** This is a standard setting in MyPresta.eu modules to check for available updates.
  - **Effect of changing this setting:**
    - *When enabled:* The module will periodically check MyPresta.eu for new versions.
    - *When disabled:* The module will not check for updates automatically.
  - **Recommended value:** YES (always stay updated for security and features)
  - **Merchant scenario / example:** Keeping this enabled ensures you are notified of new features, bug fixes, and security patches, helping your store stay current and secure.

#### Internal/Advanced Settings (Usually leave as default)

- **CG\_LAST\_TAB**: Internal setting to remember the last active tab in the module configuration.
- **cg\_altered1, cg\_altered2**: Internal flags, usually related to module updates or data migrations.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | Allow JPEG files? | YES | Allows customers to upload JPEG images. |
| Module Configuration | Allow GIF files? | YES | Allows customers to upload GIF images. |
| Module Configuration | Allow PNG files? | YES | Allows customers to upload PNG images. |
| Module Configuration | Allow BMP files? | NO | Disallows large, uncompressed BMP images. |
| Module Configuration | Allow unlogged customers to upload photos? | YES / NO (Merchant choice) | Controls guest uploads. |
| Module Configuration | Maximum file size (in MB) | 2-5 MB | Limits upload size to prevent large files. |
| Module Configuration | Thumbnail Height (px) | 150-250px | Sets consistent height for gallery thumbnails. |
| Module Configuration | Thumbnail Width (px) | 150-250px | Sets consistent width for gallery thumbnails. |
| Module Configuration | Photos per page in gallery | 12-24 | Controls pagination for the main gallery. |
| Module Configuration | Enable Voting for Photos? | YES | Allows customers to vote on photos. |
| Module Configuration | Allow unlogged customers to vote? | NO | Prevents spam/bot voting. |
| Module Configuration | Voting Style | Gold Stars | Sets the visual style for voting icons. |
| Module Configuration | Enable Contest Mode? | NO | Activates contest-specific features. |
| Module Configuration | Show upload form on product page? | YES | Displays upload form directly on product pages. |
| Module Configuration | Show gallery on product page as a tab? | YES | Adds a dedicated tab for photos on product pages. |
| Module Configuration | Show gallery on product page in footer? | YES | Displays photos below product content. |
| Module Configuration | Show gallery in customer account? | YES | Creates a “My Photos” section in customer accounts. |
| Module Configuration | Show link to gallery in “My Account” block? | YES | Adds quick link to gallery in My Account block. |
| Module Configuration | Show gallery in right column? | NO | Displays photos in the right sidebar. |
| Module Configuration | Show gallery in left column? | NO | Displays photos in the left sidebar. |
| Module Configuration | Show gallery on homepage? | YES | Displays photos on the store’s homepage. |
| Module Configuration | Exclude specific products from gallery? | Leave empty | Prevents photos for specified products. |
| Module Configuration | Enable email notifications for new uploads? | YES | Sends admin email on new photo uploads. |
| Module Configuration | MyPresta.eu Updates | YES | Enables automatic update checks. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customer photos aren’t showing up after upload, or the gallery looks empty.**
**A1:**

- **Check Module Configuration:** Ensure that the display options (e.g., “Show gallery on product page as a tab”, “Show gallery on homepage?”) are enabled in the module settings.
- **Clear Cache:** PrestaShop uses caching. Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” and “Clear cache” if separate options). This often resolves display issues.
- **Image Moderation:** Some modules have an approval process. Check if there’s an admin section (though this module doesn’t have a dedicated admin controller, it might have an internal approval status) where photos need to be approved before going live.
- **File Permissions:** Ensure your `img/customersgallery` folder (or similar path where images are stored) has correct write permissions (usually 755 or 775). Your hosting provider can help with this.

**Q2: Customers are having trouble uploading photos, or they get an error message.**
**A2:**

- **Check File Type & Size Limits:** Review the “Allow JPEG/GIF/PNG/BMP files?” and “Maximum file size (in MB)” settings in the module configuration. Ensure the customer’s file matches the allowed types and is within the size limit.
- **Server PHP Limits:** Even if the module allows a large file size, your server’s PHP configuration (e.g., `upload_max_filesize`, `post_max_size` in `php.ini`) might be imposing a stricter limit. Contact your hosting provider to check and potentially increase these limits if necessary.
- **Browser Compatibility:** Ask the customer to try a different browser or clear their browser cache.
- **JavaScript Errors:** Open your browser’s developer console (F12) and check for any JavaScript errors during the upload process. This might indicate a conflict with another module or theme.

**Q3: The customer photos look distorted or incorrectly sized in the gallery.**
**A3:**

- **Thumbnail Dimensions:** Adjust the “Thumbnail Height (px)” and “Thumbnail Width (px)” settings in the module configuration. Experiment with different values to find what looks best with your theme. Remember to clear your PrestaShop cache after making changes.
- **CSS Conflicts:** Your theme’s CSS might be overriding the module’s styling. Use your browser’s developer tools (F12) to inspect the elements and identify any conflicting CSS rules. You might need a webmaster to add custom CSS to your theme to correct this.

**Q4: The “My Photos” link isn’t appearing in the customer account or “My Account” block.**
**A4:**

- **Module Hooking:** Ensure the module is correctly hooked to `displayCustomerAccount` and `displayMyAccountBlock` (or `displayMyAccountBlockFooter` depending on your theme). You can check this in **Design > Positions** (or **Modules > Positions** in older versions) and search for the module. If it’s not hooked, try re-installing the module or manually hooking it.
- **Module Configuration:** Double-check that “Show gallery in customer account?” and “Show link to gallery in ‘My Account’ block?” are enabled in the module settings.
- **Customer Login:** The “My Photos” link is only visible to logged-in customers. Ensure you are logged in when testing.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a detailed technical overview of the “Customer product photos” module, designed for developers and webmasters who need to understand its internal workings, customize its behavior, or troubleshoot advanced issues.

### 4.1 Architecture Overview

The “Customer product photos” module follows a standard PrestaShop module architecture, primarily leveraging Front Controllers for user interaction and Smarty templates for rendering. It uses the main module class (`customersgallery.php`) for configuration management and hook registration. While it doesn’t extend `ObjectModel` for its core data, it interacts with the database directly for storing photo metadata and relies on PrestaShop’s file system for image storage. AJAX is heavily used for dynamic content loading and photo uploads, providing a smooth user experience without full page reloads.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle all customer-facing interactions, including displaying galleries, managing user photos, and processing AJAX requests.

- **`controllers/front/ajax.php`**
  - **Class Name:** `CustomersGalleryAjaxModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This is the primary endpoint for all asynchronous (AJAX) operations. It handles:
    - Photo uploads from the product page or customer account.
    - Voting actions (liking/rating photos).
    - Potentially image deletion or moderation requests from the customer’s “My Photos” section.
    - Returns JSON responses indicating success or failure, along with relevant data.
- **`controllers/front/gallery.php`**
  - **Class Name:** `CustomersGalleryGalleryModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Renders the main, dedicated customer photo gallery page. This page typically displays all approved customer photos, possibly with pagination and filtering options. It fetches photo data from the database and assigns it to the `gallery.tpl` template.
- **`controllers/front/index.php`**
  - **Class Name:** `CustomersGalleryIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** This controller likely serves as a default or fallback entry point for the module’s front-office routes. It might redirect to the main gallery or `myphotos` controller if accessed directly without specific parameters.
- **`controllers/front/myphotos.php`**
  - **Class Name:** `CustomersGalleryMyPhotosModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles the “My Photos” section within the customer’s account. It displays photos uploaded by the currently logged-in customer, allows them to manage (e.g., delete) their own photos, and potentially provides an upload interface. It requires customer authentication.
- **`controllers/front/myvideos.php`**
  - **Class Name:** `CustomersGalleryMyVideosModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Although the module name is “Customer product photos,” this controller suggests a potential (or planned) feature for customer video uploads. It would likely function similarly to `myphotos.php` but for video content.

#### Back-Office Admin Controllers

The module does not have any dedicated Admin Controllers. All configuration is handled through the main module’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module does not appear to define custom classes extending `ObjectModel` in a dedicated `classes/` directory. All core logic for database interaction, image processing, and business rules is likely encapsulated within the main `customersgallery.php` file and the front controllers. This means database operations are handled directly via `Db::getInstance()` calls.

### 4.4 JavaScript Assets (`views/js/`)

- **`customersgallery/js/customersgallery.js`**
  - **Scope:** Front-office
  - **Details:** This is the primary custom JavaScript for the module. It likely handles:
    - AJAX calls for photo uploads (e.g., binding to form submissions).
    - AJAX calls for voting mechanisms.
    - Dynamic loading of gallery content.
    - Client-side validation for file types and sizes before upload.
    - Interaction with the Fancybox library for image lightboxes.
    - Event listeners for pagination, filtering, and other gallery interactions.
- **`customersgallery/js/fancybox.js`**
  - **Scope:** Front-office
  - **Details:** This is a third-party library (Fancybox) used for displaying images in a responsive, elegant lightbox overlay when a user clicks on a thumbnail. It handles image zooming, navigation between gallery images, and modal presentation.
- **`customersgallery/js/script.js`**
  - **Scope:** Front-office
  - **Details:** This could be a supplementary script, potentially for general UI enhancements, specific animations, or additional event handling not covered by `customersgallery.js`. It might also contain initialization routines for other JS components.
- **`customersgallery/lib/voucherengine/script.js`**
  - **Scope:** Front-office (potentially)
  - **Details:** The presence of `voucherengine` suggests a potential integration or a separate feature for generating/managing vouchers, possibly as a reward for photo uploads or contest participation. This script would handle the client-side logic for such a system.

### 4.5 CSS Stylesheets (`views/css/`)

- **`customersgallery/css/customersgallery.css`**
  - **Scope:** Front-office customer styling
  - **Details:** This is the main stylesheet for the module’s front-office components. It styles:
    - The layout of the photo gallery (grid, flexbox).
    - Individual photo containers and thumbnails.
    - Upload forms and buttons.
    - Pagination controls.
    - Voting elements (if not handled by specific star CSS).
    - Responsive adjustments for different screen sizes.
  - **Key CSS class selectors:** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
- **`customersgallery/css/fancybox.css`**
  - **Scope:** Front-office customer styling
  - **Details:** Stylesheet for the Fancybox lightbox library, ensuring the image overlay, navigation arrows, close button, and captions are visually consistent and appealing.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
  - **Scope:** Front-office customer styling
  - **Details:** These are specific stylesheets for the star-based voting system. Each file provides a different color scheme or visual style for the star icons, allowing the merchant to choose a design that matches their theme. `star.css` is likely the base styling, with the others providing color overrides.
- **`customersgallery/lib/voucherengine/ps16.css`**
  - **Scope:** Front-office (potentially)
  - **Details:** This stylesheet, found within the `voucherengine` directory, suggests styling specifically for the voucher-related features, potentially optimized for PrestaShop 1.6 themes, but likely compatible or adaptable for newer versions.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

These templates are designed to be rendered when specific PrestaShop hooks are executed, integrating the module’s content into various parts of the store.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook:** `displayLeftColumn`, `displayRightColumn`
  - **Output:** A link or block that directs users to the main customer photo gallery or their “My Photos” section, typically placed in the sidebars.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook:** `displayCustomerAccount`
  - **Output:** A link or block within the customer’s “My Account” page, leading to their dedicated “My Photos” section.
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook:** `displayHome`
  - **Output:** A block or section displaying a selection of customer photos on the store’s homepage, often featuring the latest or most popular uploads.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Output:** A link to the “My Photos” section, integrated into the standard “My Account” block that appears in columns or the footer for logged-in users.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook:** `displayProductFooter`, `displayProductExtraContent`
  - **Output:** A section displaying customer photos for the current product, located below the main product content on the product page.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook:** `displayProductTab`
  - **Output:** The HTML for a new tab header (e.g., “Customer Photos”) that appears on the product page.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook:** `displayProductTabContent`
  - **Output:** The actual content displayed when the “Customer Photos” tab is active on the product page, showing the gallery and potentially the upload form for that specific product.

#### Custom Templates (`views/templates/custom/`)

These templates are likely used for specific forms or parts of the upload process.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Purpose:** Renders the HTML form that customers use to upload their product photos. This might be a simpler version or an older iteration.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Purpose:** Likely an updated or alternative version of the upload form, potentially with different styling, features, or compatibility for newer PrestaShop versions.

#### Front-Office Templates (`views/templates/front/`)

These templates are typically used by the module’s front controllers to render full pages or significant sections of the module’s functionality.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Purpose:** The main template for the dedicated customer photo gallery page, displaying all photos with pagination.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Purpose:** An alternative or updated version of the main gallery template, potentially offering different layouts or features.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Purpose:** Another alternative or updated version of the main gallery template. The module might switch between these based on configuration or PrestaShop version.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Purpose:** Renders a navigation menu specific to the customer photo gallery, potentially for filtering, sorting, or navigating between “My Photos” and the main gallery.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Purpose:** Renders the “My Photos” page within the customer’s account, showing their uploaded images and management options.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Purpose:** Template for the “My Videos” section, specifically designed or optimized for PrestaShop 1.6, if the video upload feature is enabled.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Purpose:** Renders the form for customers to upload videos, if this feature is active.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module does not explicitly define custom SQL files, but based on its functionality, it will interact with the database.

- **Custom Tables (likely created during install()):**
  - `_customersgallery`: Stores metadata for each uploaded photo (e.g., `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
  - `_customersgallery_vote`: Stores records of customer votes (e.g., `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
- **Configuration Records (stored in `ps_configuration`):**
  - `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every page. | Injects CSS and JavaScript assets required by the module (e.g., `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | In the customer’s “My Account” block (often in left/right column or footer). | Adds a link to the customer’s “My Photos” section. |
| `displayLeftColumn` | In the left sidebar of the store. | Displays a block of customer photos or a link to the gallery. |
| `displayRightColumn` | In the right sidebar of the store. | Displays a block of customer photos or a link to the gallery. |
| `displayHome` | On the store’s homepage. | Displays a section of customer photos (latest, most popular). |
| `displayProductTab` | On the product page, for adding new tabs. | Adds the “Customer Photos” tab header. |
| `displayProductTabContent` | On the product page, for the content of a tab. | Displays the customer photo gallery and upload form within the “Customer Photos” tab. |
| `displayProductFooter` | At the bottom of the product page. | Displays a section of customer photos for the current product. |
| `displayProductExtraContent` | Another hook for extra content on the product page. | Can be used as an alternative or additional placement for product-specific photo content. |
| `displayCustomerAccount` | On the customer’s “My Account” page. | Adds a link to the “My Photos” section for the logged-in customer. |
| `displayLeftColumnProduct` | In the left column specifically on product pages. | Displays a block of customer photos or a link to the gallery on product pages. |
| `displayRightColumnProduct` | In the right column specifically on product pages. | Displays a block of customer photos or a link to the gallery on product pages. |
| `displayMyAccountBlockFooter` | In the footer version of the “My Account” block. | Adds a link to the customer’s “My Photos” section in the footer. |
| `actionValidateOrder` | After an order has been successfully validated. | (Potential) Could be used to trigger an email to the customer encouraging photo uploads for purchased products. |

## 5. Official Support & Updates

For official support, module updates, and any further assistance regarding the “Customer product photos” module, please refer to your MyPresta.eu customer account. You can log in at [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) to access the latest versions and submit support tickets.
