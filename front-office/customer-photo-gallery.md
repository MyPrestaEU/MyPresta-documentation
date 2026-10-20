---
title: "Customer Photo Gallery - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Customer Photo Gallery PrestaShop module by MyPresta.eu."
sidebar:
  label: "Customer Photo Gallery - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Customer Photo Gallery Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/customer-photo-gallery/)
>
> ---


# Customer Photo Gallery

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically required for PrestaShop itself and any module interactions. Ensure your server has sufficient disk space to store uploaded photos and videos.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

This is the main configuration screen for the Customer Photo Gallery module, where you control all its features and how it appears in your store.

| Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- |
| **Allow JPEG Uploads** | YES | **What this setting does:** Controls whether customers can upload images in JPEG format.   **Effect of changing this setting:**   *When enabled:* Customers can upload .jpg and .jpeg files.   *When disabled:* JPEG files will be rejected during upload.   **Recommended value:** YES (JPEG is a very common image format).   **Merchant scenario:** If you want to restrict image types for specific quality or branding reasons, you might disable some formats. |
| **Allow GIF Uploads** | YES | **What this setting does:** Controls whether customers can upload images in GIF format.   **Effect of changing this setting:**   *When enabled:* Customers can upload .gif files.   *When disabled:* GIF files will be rejected.   **Recommended value:** YES (GIFs can be useful for simple animations or transparent backgrounds). |
| **Allow PNG Uploads** | YES | **What this setting does:** Controls whether customers can upload images in PNG format.   **Effect of changing this setting:**   *When enabled:* Customers can upload .png files.   *When disabled:* PNG files will be rejected.   **Recommended value:** YES (PNG is excellent for images with transparency and high quality). |
| **Allow BMP Uploads** | NO | **What this setting does:** Controls whether customers can upload images in BMP format.   **Effect of changing this setting:**   *When enabled:* Customers can upload .bmp files.   *When disabled:* BMP files will be rejected.   **Recommended value:** NO (BMP files are typically very large and uncompressed, not ideal for web use).   **Merchant scenario:** Only enable if you have a specific need for uncompressed images, but be aware of the impact on server storage and page load times. |
| **Enable Pagination** | YES | **What this setting does:** Determines if the gallery pages will use pagination (e.g., “Page 1 of 5”).   **Effect of changing this setting:**   *When enabled:* Gallery content is split into multiple pages, improving load times for large galleries.   *When disabled:* All gallery content loads on a single page, which can be slow for many photos.   **Recommended value:** YES.   **Merchant scenario:** Essential for managing large galleries and providing a smooth user experience. |
| **Allow Unlogged Users to Upload** | NO | **What this setting does:** Allows visitors who are not logged into a customer account to upload photos.   **Effect of changing this setting:**   *When enabled:* Guests can upload photos. This can increase contributions but might also lead to more spam or irrelevant content.   *When disabled:* Only logged-in customers can upload photos, ensuring some level of accountability.   **Recommended value:** NO (unless you have strong moderation in place).   **Merchant scenario:** If you want to maximize contributions and are prepared to moderate, enable this. Otherwise, keep it disabled to maintain quality control. |
| **Maximum File Size (MB)** | 5 | **What this setting does:** Sets the maximum size (in megabytes) for a single image file upload.   **Effect of changing this setting:**   *When set to a higher value:* Customers can upload larger, potentially higher-quality images, but this consumes more server space and bandwidth.   *When set to a lower value:* Restricts file size, saving server resources but potentially limiting image quality.   **Recommended value:** 5-10 MB is usually sufficient for web-optimized images.   **Merchant scenario:** Balance image quality with server resources. Too low, and customers might get frustrated; too high, and your hosting costs could increase. |
| **Enable Product Tab** | NO | **What this setting does:** Displays a dedicated “Customer Photos” tab on product pages.   **Effect of changing this setting:**   *When enabled:* A new tab appears on product pages, showcasing photos specifically related to that product.   *When disabled:* No dedicated tab for customer photos on product pages.   **Recommended value:** YES (if you want to show product-specific UGC).   **Merchant scenario:** Great for products where visual testimonials are highly impactful, like fashion or home decor. |
| **Product Tab Position (Module Hook)** | displayProductExtraContent | **What this setting does:** Determines where the product tab is hooked on the product page.   **Effect of changing this setting:** Changes the visual placement of the “Customer Photos” tab on the product page.   **Recommended value:** `displayProductExtraContent` or `displayProductTab`.   **Merchant scenario:** Test different hooks to find the best visual integration with your theme. |
| **Display in Product Footer** | NO | **What this setting does:** Shows a block of customer photos in the footer area of product pages.   **Effect of changing this setting:**   *When enabled:* A small gallery block appears at the bottom of product pages.   *When disabled:* No customer photos in the product page footer.   **Recommended value:** NO (unless you have a specific design need).   **Merchant scenario:** Can be used to encourage browsing or cross-selling by showing related customer photos. |
| **Display in Customer Account** | YES | **What this setting does:** Adds a link to “My Photos” in the customer’s account dashboard.   **Effect of changing this setting:**   *When enabled:* Logged-in customers see a link to manage their uploaded photos.   *When disabled:* Customers cannot easily access their photo management area from their account.   **Recommended value:** YES.   **Merchant scenario:** Essential for customers to manage their contributions. |
| **Display in My Account Block** | YES | **What this setting does:** Adds a link to “My Photos” in the “My Account” block (usually in the left/right column or footer).   **Effect of changing this setting:**   *When enabled:* A link appears in the quick access “My Account” block.   *When disabled:* No link in the “My Account” block.   **Recommended value:** YES.   **Merchant scenario:** Provides another convenient access point for customers to manage their photos. |
| **Thumbnail Height (px)** | 100 | **What this setting does:** Sets the height of the generated thumbnails for gallery images.   **Effect of changing this setting:**   *When set to a higher value:* Larger thumbnails, potentially clearer but take up more space.   *When set to a lower value:* Smaller thumbnails, saving space but less detail.   **Recommended value:** 100-150px.   **Merchant scenario:** Adjust to fit your theme’s design and ensure a visually appealing gallery layout. |
| **Thumbnail Width (px)** | 100 | **What this setting does:** Sets the width of the generated thumbnails for gallery images.   **Effect of changing this setting:**   *When set to a higher value:* Larger thumbnails.   *When set to a lower value:* Smaller thumbnails.   **Recommended value:** 100-150px.   **Merchant scenario:** Adjust to fit your theme’s design and ensure a visually appealing gallery layout. |
| **Enable Photo Upload Form** | YES | **What this setting does:** Controls the visibility of the photo upload form on the gallery page.   **Effect of changing this setting:**   *When enabled:* Customers can see and use the upload form.   *When disabled:* The upload form is hidden, preventing new submissions.   **Recommended value:** YES (unless you temporarily want to stop new uploads).   **Merchant scenario:** Disable if you’re running a contest with a submission deadline or need to pause uploads for maintenance. |
| **Display Gallery Link** | YES | **What this setting does:** Adds a link to the main photo gallery page in your store’s navigation.   **Effect of changing this setting:**   *When enabled:* A link (e.g., “Customer Gallery”) appears in the chosen hook.   *When disabled:* The link to the main gallery page is hidden.   **Recommended value:** YES.   **Merchant scenario:** Essential for customers to find and browse the gallery. |
| **Display in Right Column** | NO | **What this setting does:** Shows a block with recent customer photos in the right column of your store.   **Effect of changing this setting:**   *When enabled:* A block appears in the right column.   *When disabled:* No block in the right column.   **Recommended value:** NO (can clutter the layout, but depends on your theme).   **Merchant scenario:** Useful if your theme has ample space in the right column and you want to highlight recent contributions. |
| **Display in Left Column** | NO | **What this setting does:** Shows a block with recent customer photos in the left column of your store.   **Effect of changing this setting:**   *When enabled:* A block appears in the left column.   *When disabled:* No block in the left column.   **Recommended value:** NO (can clutter the layout, but depends on your theme).   **Merchant scenario:** Similar to the right column, use if your theme supports it well. |
| **Enable Notifications** | YES | **What this setting does:** Sends email notifications to the store administrator when new photos are uploaded.   **Effect of changing this setting:**   *When enabled:* You receive an email for each new upload, allowing for quick moderation.   *When disabled:* No email notifications.   **Recommended value:** YES.   **Merchant scenario:** Crucial for timely moderation and ensuring only appropriate content is displayed. |
| **Number of Photos on Homepage** | 8 | **What this setting does:** Sets how many customer photos are displayed in the homepage block.   **Effect of changing this setting:** Changes the quantity of photos shown on the homepage.   **Recommended value:** 6-12, depending on your homepage layout.   **Merchant scenario:** Adjust to fit your homepage design without overwhelming the page. |
| **Homepage Photo Order** | Newest First | **What this setting does:** Determines the sorting order of photos displayed on the homepage.   **Effect of changing this setting:** Photos can be ordered by newest, oldest, most popular, etc.   **Recommended value:** Newest First or Most Popular.   **Merchant scenario:** “Newest First” keeps content fresh; “Most Popular” highlights engaging content. |
| **Enable Photo Contest Mode** | NO | **What this setting does:** Activates features for running a photo contest, potentially including voting and prize mechanisms.   **Effect of changing this setting:**   *When enabled:* Additional contest-related options might appear, and the gallery might emphasize voting.   *When disabled:* Standard gallery mode.   **Recommended value:** NO (unless actively running a contest).   **Merchant scenario:** Use this when you want to run a specific campaign to collect photos and engage users with voting. |
| **Exclude Products from Gallery** | (Product IDs) | **What this setting does:** Allows you to specify product IDs that should NOT have customer photos displayed on their product pages.   **Effect of changing this setting:** Photos for these specific products will not appear in the product tab/footer, even if the main product tab setting is enabled.   **Recommended value:** Leave empty unless necessary.   **Merchant scenario:** If you have sensitive products, or products where customer photos are irrelevant or inappropriate, you can exclude them. |
| **Customer Account Link Visibility** | YES | **What this setting does:** Controls the visibility of the “My Photos” link within the customer’s account dashboard.   **Effect of changing this setting:**   *When enabled:* Link is visible.   *When disabled:* Link is hidden.   **Recommended value:** YES.   **Merchant scenario:** Keep enabled for customer convenience. |
| **My Account Block Link Visibility** | YES | **What this setting does:** Controls the visibility of the “My Photos” link within the “My Account” block (e.g., in columns).   **Effect of changing this setting:**   *When enabled:* Link is visible.   *When disabled:* Link is hidden.   **Recommended value:** YES.   **Merchant scenario:** Keep enabled for customer convenience. |
| **Enable Voting for Photos** | YES | **What this setting does:** Allows customers (and optionally guests) to vote on uploaded photos.   **Effect of changing this setting:**   *When enabled:* Voting buttons/stars appear next to photos.   *When disabled:* No voting functionality.   **Recommended value:** YES (increases engagement).   **Merchant scenario:** Use to identify popular photos, run contests, or simply encourage interaction. |
| **Voting System Type** | Stars | **What this setting does:** Chooses the visual style of the voting system (e.g., stars, thumbs up/down).   **Effect of changing this setting:** Changes how the voting mechanism looks.   **Recommended value:** Stars (generally more intuitive).   **Merchant scenario:** Select the style that best fits your store’s aesthetic. |
| **Allow Unlogged Users to Vote** | NO | **What this setting does:** Allows visitors who are not logged in to vote on photos.   **Effect of changing this setting:**   *When enabled:* Guests can vote. This can increase participation but might be susceptible to abuse.   *When disabled:* Only logged-in customers can vote.   **Recommended value:** NO (to prevent vote manipulation).   **Merchant scenario:** Enable only if you prioritize maximum participation over strict vote integrity. |

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration | CG\_ALLOW\_JPEG | YES | Allow JPEG image uploads. |
| Module Configuration | CG\_ALLOW\_GIF | YES | Allow GIF image uploads. |
| Module Configuration | CG\_ALLOW\_PNG | YES | Allow PNG image uploads. |
| Module Configuration | CG\_ALLOW\_BMP | NO | Allow BMP image uploads (large files). |
| Module Configuration | CG\_PAGINATION | YES | Enable pagination for gallery pages. |
| Module Configuration | CG\_ALLOW\_UNLOGGED | NO | Allow guests to upload photos. |
| Module Configuration | CG\_MAX\_FILE\_SIZE | 5 MB | Max file size for uploads. |
| Module Configuration | CG\_PRODUCTTAB | NO | Display customer photos in a product tab. |
| Module Configuration | cg\_productTabM | displayProductExtraContent | Hook for product tab placement. |
| Module Configuration | CG\_PRODUCTFOOTER | NO | Display photos in product footer. |
| Module Configuration | CG\_CUSTOMERACCOUNT | YES | Show “My Photos” link in customer account. |
| Module Configuration | CG\_MYACCOUNTBLOCK | YES | Show “My Photos” link in My Account block. |
| Module Configuration | CG\_THUMBHEIGHT | 100 | Height of generated thumbnails. |
| Module Configuration | CG\_THUMBWIDTH | 100 | Width of generated thumbnails. |
| Module Configuration | CG\_FUPLOADON | YES | Enable the photo upload form. |
| Module Configuration | CG\_GALLERY | YES | Display link to main gallery page. |
| Module Configuration | CG\_RIGHTCOL | NO | Display photos in right column. |
| Module Configuration | CG\_LEFTCOL | NO | Display photos in left column. |
| Module Configuration | CG\_NTF | YES | Send admin email notifications for new uploads. |
| Module Configuration | cg\_hpg\_nb | 8 | Number of photos on homepage. |
| Module Configuration | cg\_hpg\_o | Newest First | Order of photos on homepage. |
| Module Configuration | cg\_contest | NO | Enable photo contest mode. |
| Module Configuration | cg\_excludeproduct | (empty) | Product IDs to exclude from gallery. |
| Module Configuration | CG\_CUSTOMERACCOUNTV | YES | Visibility of “My Photos” link in customer account. |
| Module Configuration | CG\_MYACCOUNTBLOCKV | YES | Visibility of “My Photos” link in My Account block. |
| Module Configuration | CG\_voting | YES | Enable voting for photos. |
| Module Configuration | CG\_VOTE\_STAR | Stars | Visual style of the voting system. |
| Module Configuration | cg\_unl\_voting | NO | Allow unlogged users to vote. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My uploaded photos aren’t appearing in the gallery.**
**A:**

- **Check Module Configuration:** Ensure “Enable Photo Upload Form” (`CG_FUPLOADON`) is set to YES.
- **File Type & Size:** Verify that the uploaded file type (JPEG, PNG, GIF, BMP) is allowed in the module settings and that the file size is within the “Maximum File Size” (`CG_MAX_FILE_SIZE`) limit.
- **Moderation:** The module might have an internal moderation queue (though not explicitly listed as a setting, many gallery modules do). Check if there’s an admin section to approve/reject photos.
- **Permissions:** Ensure the `img/customersgallery/` directory (or similar path where images are stored) on your server has write permissions (usually 755 or 777, though 777 is less secure).
- **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop Back Office and clear the Smarty cache, browser cache, and module cache.

**Q2: The gallery link or block isn’t showing up in my store.**
**A:**

- **Module Hooks:** Check the module’s configuration page. Ensure that “Display Gallery Link” (`CG_GALLERY`), “Display in Right Column” (`CG_RIGHTCOL`), “Display in Left Column” (`CG_LEFTCOL`), etc., are enabled for the locations you expect.
- **Hook Management:** Go to **Design > Positions** (or **Modules > Positions** in older versions) in your PrestaShop Back Office. Search for the module (“Customer Photo Gallery”) and ensure it’s hooked to the correct `display` positions (e.g., `displayHeader`, `displayHome`, `displayRightColumn`). If it’s not, “Transplant a module” to the desired hook.
- **Theme Compatibility:** Some custom themes might override standard hook positions. If the module isn’t appearing despite being hooked correctly, it might require minor theme adjustments. Contact your theme developer or MyPresta.eu support.
- **Clear Cache:** Always clear your PrestaShop cache after making changes to module positions or settings.

**Q3: Photos on product pages are not showing up in a tab.**
**A:**

- **Enable Product Tab:** Ensure `CG_PRODUCTTAB` is set to YES in the module configuration.
- **Product Tab Hook:** Verify that `cg_productTabM` is set to an appropriate hook like `displayProductExtraContent` or `displayProductTab`.
- **Product Exclusion:** Check `cg_excludeproduct` to make sure the product you’re viewing isn’t listed there.
- **Associated Photos:** Ensure there are actually photos uploaded and associated with that specific product.
- **Clear Cache:** Clear all caches.

**Q4: The voting system isn’t working or visible.**
**A:**

- **Enable Voting:** Make sure “Enable Voting for Photos” (`CG_voting`) is set to YES.
- **Unlogged Users:** If guests can’t vote, check “Allow Unlogged Users to Vote” (`cg_unl_voting`).
- **CSS Conflicts:** Sometimes, theme CSS can hide or distort module elements. Use your browser’s developer tools (F12) to inspect the area and check for conflicting styles.
- **JavaScript Errors:** Check your browser’s console (F12 > Console tab) for any JavaScript errors that might be preventing the voting functionality from working.

**Q5: How do I translate the module’s text into other languages?**
**A:**

- Go to **International > Translations** in your PrestaShop Back Office.
- Select “Installed modules translations”.
- Choose your theme, the language you want to translate, and then select “Customer Photo Gallery” from the module list.
- You can then translate all the module’s front-office and back-office strings.
- Remember to save your changes and clear the cache.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The Customer Photo Gallery module follows a standard PrestaShop module architecture, primarily leveraging Front Controllers for user interaction and Smarty templates for rendering. It integrates with various display hooks to embed gallery features across the store. While it doesn’t explicitly define custom `ObjectModel` classes in the provided inventory, it likely uses `Configuration` for settings and directly interacts with the database for photo/video storage and management. AJAX is used for dynamic content loading and interactions like voting.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle all customer-facing interactions and data processing for the gallery.

- **`customersgallery/controllers/front/ajax.php`**

  - **Class Name:** `CustomersGalleryAjaxModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller is the backbone for dynamic interactions without full page reloads. It handles AJAX requests for actions such as:
    - Submitting new photos/videos.
    - Processing votes (e.g., star ratings).
    - Loading more gallery items (pagination/infinite scroll).
    - Potentially moderation actions if an unlogged user uploads and requires approval.
    - Returns JSON responses to the client-side JavaScript.
- **`customersgallery/controllers/front/gallery.php`**

  - **Class Name:** `CustomersGalleryGalleryModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller is responsible for displaying the main customer photo and video gallery page.
    - Fetches all approved photos/videos from the database.
    - Applies pagination logic based on module settings (`CG_PAGINATION`).
    - Prepares data for the `gallery.tpl` template, including image paths, titles, descriptions, and voting data.
    - Handles sorting (e.g., by newest, most popular).
- **`customersgallery/controllers/front/index.php`**

  - **Class Name:** `CustomersGalleryIndexModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller might serve as a default entry point or a redirector for the module’s front-office section. It could also be used for a simple landing page or to redirect to the main gallery. In many modules, `index.php` in a front controller directory is a fallback or a simple redirect to the main feature.
- **`customersgallery/controllers/front/myphotos.php`**

  - **Class Name:** `CustomersGalleryMyPhotosModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** This controller manages the “My Photos” section within a customer’s account.
    - Authenticates the logged-in customer.
    - Retrieves all photos uploaded by the current customer.
    - Allows customers to view, edit (e.g., title, description), or delete their own submissions.
    - Prepares data for the `my-photos.tpl` template.
- **`customersgallery/controllers/front/myvideos.php`**

  - **Class Name:** `CustomersGalleryMyVideosModuleFrontController` (likely extends `ModuleFrontController`)
  - **Responsibility:** Similar to `myphotos.php`, but specifically for managing videos uploaded by the current customer.
    - Authenticates the logged-in customer.
    - Retrieves all videos uploaded by the current customer.
    - Allows customers to view, edit, or delete their own video submissions.
    - Prepares data for the `my-videos-16.tpl` template.

#### Back-Office Admin Controllers

The module dossier indicates no dedicated Admin Controllers. All back-office configuration is handled via the main module file’s `getContent()` method.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no custom classes in the `classes/` directory. This suggests that the module likely manages its data directly within the `customersgallery.php` file or uses generic PrestaShop database interaction methods.

- **Data Storage:** Photo and video metadata (paths, titles, user IDs, product IDs, approval status, votes) are likely stored in custom database tables created during the module’s installation. The module’s main PHP file (`customersgallery.php`) would contain the SQL queries for these tables.

### 4.4 JavaScript Assets (`views/js/`)

- **`customersgallery/js/customersgallery.js`**

  - **Scope:** Front-office.
  - **Detail:** This is likely the main custom JavaScript file for the gallery. It would contain:
    - Event listeners for photo/video uploads (e.g., form submission, file input changes).
    - AJAX calls to `ajax.php` for uploads, voting, and loading more content.
    - Client-side validation for file types and sizes.
    - Dynamic updates to the gallery display (e.g., adding new photos without page refresh).
    - Interaction with the Fancybox library for image lightboxes.
- **`customersgallery/js/fancybox.js`**

  - **Scope:** Front-office.
  - **Detail:** A third-party library (Fancybox) for creating elegant, responsive lightboxes for images and multimedia. This script enables the “click to enlarge” functionality for gallery photos.
- **`customersgallery/js/script.js`**

  - **Scope:** Front-office.
  - **Detail:** This could be a general utility script or a legacy script. It might contain:
    - Helper functions for UI interactions.
    - Additional event handlers not specific to the core gallery logic.
    - Potentially scripts related to the voting mechanism or other interactive elements.
- **`customersgallery/lib/voucherengine/script.js`**

  - **Scope:** Front-office.
  - **Detail:** This suggests integration with a “voucher engine” or a similar reward system. This script would handle:
    - Logic for awarding vouchers or discounts upon successful photo/video submission (if `cg_contest` is enabled or a similar reward system is in place).
    - AJAX calls to trigger voucher generation or application.

### 4.5 CSS Stylesheets (`views/css/`)

- **`customersgallery/css/customersgallery.css`**

  - **Scope:** Front-office (main gallery styling).
  - **Detail:** Contains the core CSS rules for the layout, appearance, and responsiveness of the customer photo gallery, including:
    - Grid layouts for photo display.
    - Styling for thumbnails, captions, and user information.
    - Styles for the upload form and pagination.
    - Responsive adjustments for different screen sizes.
  - **Key Selectors:** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
- **`customersgallery/css/fancybox.css`**

  - **Scope:** Front-office.
  - **Detail:** Stylesheet for the Fancybox lightbox library, controlling the appearance of the enlarged images, navigation arrows, close button, and overlay.
  - **Key Selectors:** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

  - **Scope:** Front-office.
  - **Detail:** These are different color themes for the star-based voting system (`CG_VOTE_STAR`). `star.css` is likely the base styling, and the others provide color overrides.
  - **Key Selectors:** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
- **`customersgallery/lib/voucherengine/ps16.css`**

  - **Scope:** Front-office.
  - **Detail:** This stylesheet is specifically for the “voucher engine” integration, likely providing styling for any elements related to voucher display or notification, potentially with specific overrides for PrestaShop 1.6 themes.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Custom Templates (`views/templates/custom/`)

These are likely specific forms or components.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Purpose:** Renders the HTML form for customers to upload photos.
  - **Variables:** Likely includes fields for file input, title, description, and potentially product association.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Purpose:** Could be an alternative or updated version of the upload form, possibly for video uploads or a different layout.

#### Front-Office Templates (`views/templates/front/`)

These templates render the main gallery pages and user-specific content.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Purpose:** Main template for displaying the customer photo and video gallery.
  - **Variables:** Loops through `$photos` and `$videos` arrays, displaying thumbnails, titles, and voting elements. Includes pagination.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Purpose:** Could be an alternative gallery layout or a specific view for contests.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Purpose:** Another alternative gallery layout.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Purpose:** Renders a navigation menu specific to the gallery, potentially with links to “My Photos,” “My Videos,” “Upload,” etc.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Purpose:** Displays the list of photos uploaded by the currently logged-in customer, with options to edit or delete.
  - **Variables:** `$customer_photos` array.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Purpose:** Displays the list of videos uploaded by the currently logged-in customer, specifically designed for PrestaShop 1.6 compatibility.
  - **Variables:** `$customer_videos` array.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Purpose:** Renders a form specifically for uploading videos, distinct from the photo upload form.

#### Hook Templates (`views/templates/hook/`)

These templates are designed to be rendered within specific PrestaShop hooks.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook:** `displayLeftColumn`, `displayRightColumn`
  - **Purpose:** Renders a block in the left or right column with a link to the main gallery page or a few recent photos.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook:** `displayCustomerAccount`
  - **Purpose:** Adds a link or block within the customer’s account dashboard, typically linking to “My Photos” or “My Videos.”
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook:** `displayHome`
  - **Purpose:** Displays a block of recent or popular customer photos on the store’s homepage.
  - **Variables:** `$homepage_photos` array.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Purpose:** Adds a link to “My Photos” within the “My Account” block, often found in side columns or the footer.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook:** `displayProductFooter`
  - **Purpose:** Renders a block of customer photos related to the current product in the product page footer.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook:** `displayProductTab`, `displayProductExtraContent`
  - **Purpose:** Renders the “Customer Photos” tab header on a product page.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook:** `displayProductTabContent`, `displayProductExtraContent`
  - **Purpose:** Renders the actual content (the gallery of photos) within the “Customer Photos” tab on a product page.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module likely creates custom tables during installation. Based on the functionality, these would include:

- **`ps_customersgallery_photos`**:

  - `id_photo` (PRIMARY KEY, INT)
  - `id_customer` (INT, FK to `ps_customer`)
  - `id_product` (INT, FK to `ps_product`, NULLABLE)
  - `filename` (VARCHAR, path to image file)
  - `title` (VARCHAR)
  - `description` (TEXT)
  - `date_add` (DATETIME)
  - `active` (TINYINT, for moderation status)
  - `votes` (INT, total votes)
  - `rating` (DECIMAL, average rating)
- **`ps_customersgallery_videos`**:

  - `id_video` (PRIMARY KEY, INT)
  - `id_customer` (INT, FK to `ps_customer`)
  - `id_product` (INT, FK to `ps_product`, NULLABLE)
  - `url` (VARCHAR, for external video links like YouTube/Vimeo)
  - `title` (VARCHAR)
  - `description` (TEXT)
  - `date_add` (DATETIME)
  - `active` (TINYINT)
- **`ps_customersgallery_votes`**:

  - `id_vote` (PRIMARY KEY, INT)
  - `id_photo` (INT, FK to `ps_customersgallery_photos`)
  - `id_customer` (INT, FK to `ps_customer`, NULLABLE for unlogged votes)
  - `ip_address` (VARCHAR, for unlogged votes and abuse prevention)
  - `vote_value` (INT, e.g., 1-5 for stars)
  - `date_add` (DATETIME)
- **`ps_configuration`**: Module settings (e.g., `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) are stored here.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayProductExtraContent` | Renders additional content on the product page, often used for tabs. | Displays the “Customer Photos” tab and its content on product pages. |
| `displayRightColumnProduct` | Renders content in the right column of a product page. | Displays a block of product-specific customer photos in the right column. |
| `displayCustomerAccount` | Renders content within the customer’s “My Account” dashboard. | Adds a link or block to “My Photos” and “My Videos” for the logged-in customer. |
| `displayRightColumn` | Renders content in the right column of general store pages. | Displays a block of recent customer photos in the right column. |
| `displayMyAccountBlockFooter` | Renders content in the footer of the “My Account” block. | Adds a link to “My Photos” in the “My Account” block, often in the footer. |
| `displayProductFooter` | Renders content in the footer area of a product page. | Displays a block of product-specific customer photos in the product footer. |
| `displayProductTabContent` | Renders the content of a product tab. | Displays the gallery content within the “Customer Photos” tab on product pages. |
| `displayLeftColumnProduct` | Renders content in the left column of a product page. | Displays a block of product-specific customer photos in the left column. |
| `displayLeftColumn` | Renders content in the left column of general store pages. | Displays a block of recent customer photos in the left column. |
| `displayHome` | Renders content on the store’s homepage. | Displays a block of recent or popular customer photos on the homepage. |
| `displayHeader` | Renders content in the `<head>` section of all pages. | Injects CSS and JavaScript files required by the module across the entire store. |
| `displayMyAccountBlock` | Renders content within the “My Account” block (e.g., in side columns). | Adds a link to “My Photos” in the “My Account” block. |
| `displayProductTab` | Renders the tab header for a product page tab. | Displays the “Customer Photos” tab title on product pages. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our team is dedicated to ensuring the smooth operation and continuous improvement of your PrestaShop modules.
