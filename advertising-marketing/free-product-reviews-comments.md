---
title: "Free product reviews (comments) - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Free product reviews (comments) PrestaShop module by MyPresta.eu."
sidebar:
  label: "Free product reviews (comments)"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free product reviews (comments) Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Free product reviews (comments)

## 1. Requirements & Compatibility
This module is designed for broad compatibility with modern PrestaShop versions and standard hosting environments.

-   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP Compatibility**: PHP 7.1 - 8.5
-   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required, which are typically available on any modern PrestaShop-compatible hosting environment. No unusual or specialized server configurations are needed.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure)
After installation, clicking "Configure" will take you to the main configuration screen for the "Free product reviews (comments)" module. This is where you control how reviews behave and appear on your store.

#### General Settings

-   **Enable reviews:**
    *   **What this setting does:** This is the master switch for the entire review system.
    *   **Effect of changing this setting:**
        *   *When enabled:* The review section will appear on product pages, and customers will be able to read and submit reviews.
        *   *When disabled:* The review section will be hidden from product pages, and no new reviews can be submitted or viewed.
    *   **Recommended value:** YES
    *   **Merchant scenario / example:** Enable this to start collecting and displaying customer feedback immediately after installation.

-   **Reviews must be approved by an employee:**
    *   **What this setting does:** Determines whether reviews are published automatically or require manual approval by a store administrator.
    *   **Effect of changing this setting:**
        *   *When enabled:* All submitted reviews will enter a "pending" state and will not be visible on the front office until an administrator manually approves them in the module's review management section. This allows you to filter out spam, inappropriate content, or reviews that don't meet your guidelines.
        *   *When disabled:* Reviews are published instantly upon submission, without any human intervention.
    *   **Recommended value:** YES (especially for new stores or to maintain quality control)
    *   **Merchant scenario / example:** If you want to ensure all reviews are appropriate and constructive before they go live, enable this. This is crucial for maintaining your brand image and preventing spam.

-   **Allow guest reviews:**
    *   **What this setting does:** Controls whether non-logged-in visitors (guests) can submit reviews.
    *   **Effect of changing this setting:**
        *   *When enabled:* Any visitor to your product page can submit a review, even if they don't have an account or aren't logged in. They will typically be asked for a name and email address.
        *   *When disabled:* Only customers who are logged into their PrestaShop account can submit reviews.
    *   **Recommended value:** YES (to encourage more reviews) or NO (to ensure reviews come from actual customers).
    *   **Merchant scenario / example:** If you want to maximize the number of reviews, even from casual browsers, enable guest reviews. If you prefer to only collect reviews from verified customers who have purchased from you, disable this.

-   **Minimum time between 2 reviews from the same user (in seconds):**
    *   **What this setting does:** Sets a cooldown period to prevent a single user from submitting multiple reviews in quick succession for the same product.
    *   **Effect of changing this setting:**
        *   *When set to a value (e.g., 3600 for 1 hour):* A user must wait at least this many seconds after submitting a review before they can submit another review for the same product.
        *   *When set to 0:* There is no time limit, and users can submit reviews as frequently as they wish.
    *   **Recommended value:** 3600 (1 hour) or 86400 (24 hours) to prevent spamming.
    *   **Merchant scenario / example:** To prevent a single customer from flooding a product with multiple reviews, set this to a reasonable duration like 3600 seconds (1 hour).

-   **Display reviews on product page:**
    *   **What this setting does:** Determines if the review list and submission form are shown directly on the product page.
    *   **Effect of changing this setting:**
        *   *When enabled:* The review section will be visible on the product page, allowing customers to read and write reviews.
        *   *When disabled:* The review section will be hidden from the product page. This might be used if you prefer to link to a separate reviews page or manage reviews differently.
    *   **Recommended value:** YES
    *   **Merchant scenario / example:** To make reviews easily accessible to shoppers browsing your products, keep this enabled.

-   **Number of reviews per page:**
    *   **What this setting does:** Controls how many reviews are displayed on a single page within the review list before pagination is applied.
    *   **Effect of changing this setting:**
        *   *When set to a value (e.g., 5):* Only 5 reviews will be shown at a time, with "Next" and "Previous" buttons or page numbers to navigate through the rest.
        *   *When set to a very high number:* All reviews might load on one page, which can impact page load speed if there are many reviews.
    *   **Recommended value:** 5-10
    *   **Merchant scenario / example:** If a product has many reviews, setting this to 5 or 10 will keep the product page tidy and load quickly, while still allowing customers to browse all feedback.

#### Review Criteria Management

This section allows you to define specific criteria (e.g., "Quality," "Price," "Features") that customers can rate in addition to the overall product rating.

-   **Add new criterion:**
    *   **What this does:** Allows you to create a new, specific aspect of a product that customers can rate (e.g., "Value for Money," "Ease of Use," "Durability").
    *   **Effect of changing this setting:** When you add a criterion, it will appear as an additional rating option in the review submission form on the product page. Customers will be able to give a star rating for each criterion you define.
    *   **Recommended value:** Add criteria relevant to your products.
    *   **Merchant scenario / example:** For an electronics store, you might add criteria like "Performance," "Battery Life," and "Design." For a clothing store, "Fit," "Material Quality," and "Style."

-   **List of existing criteria:**
    *   **What this does:** Displays a table of all criteria you have previously added, along with options to edit or delete them.
    *   **Effect of changing this setting:** You can modify the name of a criterion (e.g., change "Quality" to "Product Quality") or remove a criterion if it's no longer relevant. Deleting a criterion will remove it from future review submissions, but existing reviews that used that criterion might still display their ratings for it (depending on module implementation).
    *   **Recommended value:** Keep your criteria list updated and relevant.
    *   **Merchant scenario / example:** If you introduce a new product line with unique characteristics, you might add a new criterion. If a criterion becomes redundant, you can delete it.

#### Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
|---|---|---|---|
| Module Configuration | Enable reviews | YES | Master switch for the review system. |
| Module Configuration | Reviews must be approved by an employee | YES | Controls manual approval of reviews to prevent spam/inappropriate content. |
| Module Configuration | Allow guest reviews | YES | Allows non-logged-in users to submit reviews. |
| Module Configuration | Minimum time between 2 reviews from the same user (in seconds) | 3600 (1 hour) | Prevents review spamming from a single user. |
| Module Configuration | Display reviews on product page | YES | Shows or hides the review section on product pages. |
| Module Configuration | Number of reviews per page | 5-10 | Controls pagination for the review list on product pages. |
| Module Configuration | Add new criterion | N/A | Creates specific rating aspects (e.g., "Quality", "Price"). |
| Module Configuration | List of existing criteria | N/A | Manages (edit/delete) the custom review criteria. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My reviews are not showing up on the product page after submission.**
A: Check if "Reviews must be approved by an employee" is enabled in the module configuration. If so, you need to manually approve them in the module's administration interface (usually found under the module's configuration page, where you'll see a list of reviews). Once approved, they will appear on the front office.

**Q2: The review section looks strange or doesn't fit my theme's design.**
A: This is often a CSS conflict with your custom PrestaShop theme.
    *   **Clear Cache:** First, try clearing your PrestaShop cache under **Advanced Parameters > Performance**.
    *   **Theme Overrides:** Your theme might have its own styling for review elements or might be missing specific styling for this module. You may need a webmaster to inspect the CSS and apply custom styles to make it blend seamlessly. The module provides its own CSS files (`myprestacomments.css`, etc.), but your theme's styles might override them.

**Q3: Customers are complaining they can't submit reviews, or the form isn't appearing.**
A:
    *   **Check "Enable reviews":** Ensure the main switch in the module configuration is set to YES.
    *   **Check "Display reviews on product page":** Make sure this is also enabled.
    *   **Guest Reviews:** If non-logged-in users can't submit, check "Allow guest reviews." If it's disabled, only logged-in customers can submit.
    *   **Minimum Time Between Reviews:** If a specific user can't submit, they might be hitting the "Minimum time between 2 reviews" limit.

**Q4: How do I translate the module's text into other languages?**
A: You can translate the module's text directly within PrestaShop:
    1.  Go to **International > Translations**.
    2.  Select "Installed modules translations" for the "Type of translation".
    3.  Choose your theme.
    4.  Select the language you want to translate.
    5.  Find "Free product reviews (comments)" in the list of modules and click "Modify." You can then edit all translatable strings.

**Q5: I want to remove a review that is inappropriate or spam.**
A: Navigate to the module's configuration page in the Back Office. You should see a list of all submitted reviews. From there, you can typically "Delete" or "Disapprove" reviews. If you have "Reviews must be approved by an employee" enabled, you can simply choose not to approve it.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)
This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 4.1 Architecture Overview
The "Free product reviews (comments)" module (`myprestacomments`) follows a standard PrestaShop module architecture, leveraging `ModuleFrontController` for front-office interactions and `Module` for its main configuration and hook management. It uses a custom database table for storing review data and relies on Smarty templates for rendering both front-office review displays and back-office configuration forms. The module integrates with PrestaShop's hook system to inject its content into product pages.

### 4.2 Controllers (`controllers/`)

-   **Front-Office Controllers**:
    *   `controllers/front/default.php`
        *   **Class Name & Parent Class**: `MyPrestaCommentsDefaultModuleFrontController` extending `ModuleFrontController`
        *   **Responsibility**: This controller likely handles the initial display of reviews on the product page or serves as a fallback for general review-related actions. It would typically fetch reviews for a given product and pass them to the Smarty template.
    *   `controllers/front/feedback.php`
        *   **Class Name & Parent Class**: `MyPrestaCommentsFeedbackModuleFrontController` extending `ModuleFrontController`
        *   **Responsibility**: This controller is dedicated to handling the submission of new reviews. It processes POST requests from the review form, validates the input (rating, comment, criteria), checks for guest review permissions and time limits, and then saves the review to the database. It also manages the approval status based on module configuration.
    *   `controllers/front/index.php`
        *   **Class Name & Parent Class**: `MyPrestaCommentsIndexModuleFrontController` extending `ModuleFrontController`
        *   **Responsibility**: This controller might serve as a general entry point or handle AJAX requests related to reviews, such as loading more reviews via pagination or handling "report abuse" functionality.

-   **Back-Office Admin Controllers**:
    *   No dedicated custom Admin Controllers (`controllers/admin/`) are listed. This suggests that the administration of reviews (listing, approving, deleting) is handled directly within the `getContent()` method of the main module file (`index.php`) or through a standard `AdminController` that the module extends or integrates with. The presence of `list_action_approve.tpl` and `list_action_noabuse.tpl` templates strongly indicates that review management is integrated into a standard PrestaShop list view, likely within the module's own configuration page.

### 4.3 Core Classes & Models (`classes/`)
No custom classes are listed in the `classes/` directory. This implies that the module might be using a more direct approach for database interaction within its main module file or controllers, or it might be leveraging existing PrestaShop `ObjectModel`s if applicable (though unlikely for custom review data). It's probable that the review data structure is managed directly within the `install.sql` and the module's `index.php`.

### 4.4 JavaScript Assets (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Scope**: Front-office
    *   **Description**: A jQuery plugin for creating interactive star rating widgets. It handles the visual display of stars and captures the user's rating selection in the review submission form.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Scope**: Front-office
    *   **Description**: A jQuery plugin to count characters or words in a textarea, often used to provide real-time feedback to users about their review length.
-   `js/moderate.js`
    *   **Scope**: Back-office
    *   **Description**: This script likely handles AJAX actions for moderating reviews in the Back Office. It would be responsible for approving, disapproving, or deleting reviews without a full page reload, interacting with the module's `getContent()` or a hidden admin controller.
-   `js/myprestacomments.js`
    *   **Scope**: Front-office
    *   **Description**: The main custom JavaScript for the module. It orchestrates the front-office review functionality, including:
        *   Initializing the `jquery.rating.pack.js` for star ratings.
        *   Handling the submission of the review form (potentially via AJAX).
        *   Displaying success or error messages.
        *   Managing pagination or "load more" functionality for reviews.
        *   Potentially handling "report abuse" clicks.
-   `js/productCriterion.js`
    *   **Scope**: Back-office
    *   **Description**: This script is used in the Back Office for managing review criteria. It likely handles the dynamic addition, editing, and deletion of criteria fields on the module's configuration page, possibly using AJAX to update the database.

### 4.5 CSS Stylesheets (`views/css/`)

-   `myprestacomments.css`
    *   **Scope**: Front-office & Back-office
    *   **Description**: The primary stylesheet for the module, containing general styles for the review section, star ratings, review forms, and potentially some basic admin panel styling.
    *   **Key Selectors**: `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Scope**: Front-office & Back-office
    *   **Description**: Likely a compatibility stylesheet for PrestaShop 1.6.x, containing specific overrides or adjustments for that version's default theme structure.
-   `myprestacomments24.css`
    *   **Scope**: Front-office & Back-office
    *   **Description**: Likely a compatibility stylesheet for PrestaShop 1.7.x or 8.x, containing specific overrides or adjustments for those versions' default theme structure (e.g., Classic theme).
-   `myprestacomments32.css`
    *   **Scope**: Front-office & Back-office
    *   **Description**: Likely a compatibility stylesheet for PrestaShop 9.x, containing specific overrides or adjustments for the latest default theme structure.

### 4.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook**: Likely `displayProductButtons` or `displayProductExtraContent` (or similar product page hooks).
        *   **Output**: This is the main template for displaying the review summary (average rating, number of reviews) and the "Write a Review" button/link on the product page. It often acts as a wrapper for the full review list and form.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook**: Rendered within `mypresta_myprestacomments.tpl` or directly hooked if the module uses a separate tab.
        *   **Output**: Displays the actual list of individual customer reviews, including their ratings, titles, comments, and reviewer information. It will also handle pagination.

-   **Admin templates (`views/templates/admin/`)**:
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Output**: Likely displays an advertisement or promotional message from MyPresta.eu within the module's configuration page.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Output**: A template fragment for an "Approve" action button or link, used within a list of pending reviews in the Back Office.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Output**: A template fragment for a "Mark as Not Abusive" action button or link, used within a list of reported reviews in the Back Office.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Output**: This is a standard PrestaShop helper template override, used to render the module's configuration form (general settings, criteria management) in the Back Office. It defines the layout and input fields for the `getContent()` method.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Output**: Another standard PrestaShop helper template override, used to render the list of reviews (or criteria) in the Back Office, including columns for review details, status, and action buttons (approve, delete).

-   **Front-office templates (`views/templates/front/`)**:
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Output**: The template for the review submission form itself. This includes the star rating input, text fields for title and comment, and potentially fields for custom criteria ratings. It's rendered when a customer clicks "Write a Review."

### 4.7 Database Schema & Hooks Map

-   **Database Tables**:
    *   `myprestacomments/install.sql`: This file contains the SQL statements executed during module installation. It will define at least one custom table:
        *   `ps_myprestacomments_reviews`: Stores the actual review data (product ID, customer ID, rating, title, comment, date, approval status, abuse status).
        *   `ps_myprestacomments_criteria`: Stores the custom review criteria defined by the merchant (e.g., "Quality", "Price").
        *   `ps_myprestacomments_review_criterion`: A linking table if reviews can rate multiple criteria.

-   **Registered Hooks Table**:

| Hook Name | Execution Timing | Technical Purpose |
|---|---|---|
| `displayHeader` | In the `<head>` section of every page. | To include module's CSS and JS files globally or conditionally. |
| `displayProductExtraContent` | On the product page, typically below the main product description or in a tab. | To display the review summary, list of reviews, and the "Write a Review" form. |
| `displayProductButtons` | On the product page, near the Add to Cart button. | To display a quick link or button to the review section. |
| `displayFooter` | In the footer of every page. | Less common, but could be used for a general link to reviews or module-specific content. |
| `displayLeftColumn` / `displayRightColumn` | In the left or right sidebar. | Could be used to display a block of recent reviews or a review summary. |
| `actionValidateOrder` | After an order has been successfully validated. | Potentially used to trigger an email to the customer asking for a review of purchased products. |
| `actionProductUpdate` | After a product is updated in the Back Office. | To clear cache related to product reviews if necessary. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | After a product is added or updated. | To ensure review data integrity or cache invalidation. |

## 5. Official Support & Updates
For official updates, technical support, and any further assistance with the "Free product reviews (comments)" module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/). Our support team is available to help with module-related issues and ensure your store runs smoothly.
