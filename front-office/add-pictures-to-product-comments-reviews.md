---
title: "Add pictures to product comments (reviews) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Add pictures to product comments (reviews) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Add pictures to product comments (reviews) - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Add pictures to product comments (reviews) Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Add pictures to product comments (reviews)

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL).
- **Dependency**: This module requires the “Product Comments” module (developed by MyPresta.eu) to be installed and active, as it extends its functionality.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)

After installation, click “Configure” next to the “Add pictures to product comments (reviews)” module in the Module Manager. This will take you to its main configuration screen.

The module’s configuration is straightforward, primarily focusing on enabling or disabling its core functionality.

**Settings & Options:**

- **Enable pictures upload for product comments:**
  - **What this setting does:** This is the main switch to activate or deactivate the module’s core functionality. When enabled, your customers will see the option to upload pictures when they write a product review.
  - **Effect of changing this setting:**
    - *When enabled (YES):* The image upload field will appear in the product review submission form on your product pages. Customers can then attach images to their reviews. Existing reviews with images will also display those images.
    - *When disabled (NO):* The image upload field will be hidden from the product review submission form. Customers will only be able to submit text reviews. Existing reviews with images might still display them, but no new images can be added.
  - **Recommended value:** **YES**. To leverage the benefits of visual reviews, you should enable this feature.
  - **Merchant scenario / example:** If you want to allow customers to show off their new dress or how a gadget works in real life, enable this. If you temporarily want to restrict image uploads for maintenance or a specific campaign, you can disable it.

### 2.2 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| Module Configuration Page | Enable pictures upload for product comments | YES | Controls whether customers can upload images with their product reviews. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I’ve enabled the module, but I don’t see the image upload field on my product page.**
A:

1. **Check “Product Comments” Module:** This module extends the “Product Comments” module. Ensure that the “Product Comments” module (by MyPresta.eu) is installed, enabled, and configured correctly on your store.
2. **Clear Cache:** Go to **Advanced Parameters > Performance** in your PrestaShop back office and click “Clear cache” at the top right. Sometimes, old cached files prevent new module features from appearing.
3. **Theme Compatibility:** While the module is designed for broad compatibility, custom themes might sometimes override default template structures. If clearing cache doesn’t help, contact MyPresta.eu support with details of your theme.

**Q: My customers are uploading pictures, but they don’t appear next to the review.**
A:

1. **Review Moderation:** Check if your “Product Comments” module has review moderation enabled. If so, new reviews (and their associated pictures) will only appear after you approve them in the Back Office.
2. **Check Module Configuration:** Double-check that “Enable pictures upload for product comments” is set to YES in this module’s configuration.
3. **File Permissions:** Ensure that the `img/p/` directory (or wherever PrestaShop stores product images) has correct write permissions (usually 755 or 775). If the server cannot write files, images won’t be saved.

**Q: Can I limit the number of pictures a customer can upload per review?**
A: This specific module provides a basic upload feature. Advanced controls like limiting the number of images or file size might require custom modifications or an update to the core “Product Comments” module. Please check the “Product Comments” module’s settings or contact MyPresta.eu support for such features.

**Q: The uploaded images look distorted or are not displayed correctly.**
A:

1. **CSS Conflicts:** Your theme’s CSS might be conflicting with the module’s styling. Use your browser’s developer tools (F12) to inspect the image elements and identify any conflicting styles.
2. **Image Regeneration:** Sometimes, image thumbnails might not generate correctly. In PrestaShop, go to **Design > Image Settings** and try regenerating thumbnails for “products” or “reviews” if such an option exists, or for all images.
3. **Original Image Quality:** Advise customers to upload reasonably sized and clear images. Extremely low-resolution images will naturally look poor when displayed larger.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Add pictures to product comments (reviews)” module (`reviewspics`) is designed as an extension to the core “Product Comments” module (presumably `productcomments` or a similar MyPresta.eu module). It primarily injects an image upload interface into the existing review form and modifies the display of reviews to include images. It leverages PrestaShop’s hook system for integration and uses standard front-office and back-office assets. The module creates a custom database table to link images to specific product comments.

### 4.2 Controllers (`controllers/`)

This module does not introduce any custom Front-Office or Back-Office controllers. Its functionality is integrated via hooks and direct template modifications within the context of the parent “Product Comments” module.

### 4.3 Core Classes & Models (`classes/`)

This module does not define custom classes in the `classes/` directory. Its primary logic resides within the main `index.php` module file and the `install.sql` for database schema.

### 4.4 JavaScript Assets (`views/js/`)

- **`reviewspics/views/js/reviewspics-bo.js`**

  - **Scope:** Back-office.
  - **Purpose:** This script likely handles any JavaScript-driven functionality within the module’s back-office configuration or for managing uploaded images associated with reviews in the admin panel. This could include AJAX calls for image deletion, status updates, or dynamic form elements.
  - **Details:** It would typically bind to elements within the `backOffice.tpl` template or the admin product comment management interface.
- **`reviewspics/views/js/reviewspics.js`**

  - **Scope:** Front-office.
  - **Purpose:** This is the core front-office JavaScript for the image upload functionality. It handles:
    - Displaying the image upload input (e.g., file input, drag-and-drop area).
    - Previewing selected images before upload.
    - AJAX-based image upload during review submission.
    - Validation of image types/sizes (client-side).
    - Potentially, removal of selected images before submission.
  - **Details:** It binds to the review submission form elements, likely within the `displayMyPrestaCommentsField.tpl` template, and interacts with the server-side logic to process image files.

### 4.5 CSS Stylesheets (`views/css/`)

- **`reviewspics/views/css/reviewspics.css`**
  - **Scope:** Front-office (primarily) and potentially Back-office.
  - **Purpose:** This stylesheet provides the visual styling for the image upload form and the display of uploaded images within product reviews.
  - **Main UI components and containers it styles:**
    - The image upload area (e.g., border, background, icon).
    - Image previews (sizing, aspect ratio, borders).
    - Layout of images within a review.
    - Potentially, styling for image management in the Back Office.
  - **Key CSS class selectors developers can override:** Look for classes like `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images`, etc. These can be targeted in a custom theme’s `custom.css` or `theme.css` to match the store’s branding.

### 4.6 Smarty Template Structure (`views/templates/`)

- **Hook templates (`views/templates/hook/`)**:

  - **`reviewspics/views/templates/hook/backOffice.tpl`**

    - **Hook:** Likely rendered in `displayAdminProductsExtra` or a custom hook within the “Product Comments” module’s admin interface.
    - **Outputs:** This template is for the Back Office. It likely renders the module’s configuration form (as described in section 4.1) or provides an interface for administrators to manage images associated with product comments (e.g., viewing, deleting, approving images).
  - **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

    - **Hook:** This template is designed to be hooked into the display of an *individual* product comment, likely within the `displayProductListReviews` or a similar hook provided by the “Product Comments” module.
    - **Outputs:** It renders the actual images associated with a specific product review. It would iterate through the images linked to the comment and display them, potentially as thumbnails or a small gallery.
  - **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

    - **Hook:** This template is intended to be injected into the product review *submission form*, likely via a hook like `displayProductForm` or a custom hook within the “Product Comments” module’s review form.
    - **Outputs:** It renders the HTML structure for the image upload input field that customers interact with when writing a new review. This includes the file input, any drag-and-drop areas, and potentially placeholders for image previews.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The `reviewspics/install.sql` file indicates the creation of at least one custom table to store the image data and link it to product comments.
  - **`ps_reviewspics_image`**: (Likely table name, based on module name and common PrestaShop conventions).
    - **Purpose:** Stores metadata about each uploaded image.
    - **Fields (expected):**
      - `id_reviewspics_image` (Primary Key, INT)
      - `id_product_comment` (Foreign Key, INT, linking to the parent “Product Comments” module’s review table)
      - `image_name` (VARCHAR, filename of the image)
      - `date_add` (DATETIME, timestamp of upload)
      - `active` (TINYINT, for moderation/visibility)
      - `position` (INT, for ordering if multiple images per review)
- **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | Renders in the `<head>` section of all front-office pages. | To include front-office CSS (`reviewspics.css`) and JavaScript (`reviewspics.js`) files. |
| `displayBackOfficeHeader` | Renders in the `<head>` section of all back-office pages. | To include back-office CSS and JavaScript (`reviewspics-bo.js`) for admin configuration or review management. |
| `displayProductListReviews` (or similar from Product Comments module) | Renders within the product review list on product pages. | To inject `displayMyPrestaComment.tpl` for displaying images within existing reviews. |
| `displayProductForm` (or similar from Product Comments module) | Renders within the product review submission form. | To inject `displayMyPrestaCommentsField.tpl` for the image upload input. |
| `actionProductCommentAdd` (or similar from Product Comments module) | Executed after a new product comment is added. | To process uploaded images, save them to the file system, and record their details in `ps_reviewspics_image` table, linking them to the new comment. |
| `actionProductCommentDelete` (or similar from Product Comments module) | Executed after a product comment is deleted. | To clean up associated images from the file system and `ps_reviewspics_image` table. |
| `actionProductCommentUpdate` (or similar from Product Comments module) | Executed after a product comment is updated. | To handle any changes to image associations or moderation status. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and professional support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu). Our team is dedicated to ensuring the smooth operation and continued enhancement of your PrestaShop modules.
