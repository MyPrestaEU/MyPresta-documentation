---
title: "Order images uploader - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Order images uploader PrestaShop module by MyPresta.eu."
sidebar:
  label: "Order images uploader - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Order images uploader Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/order-images-uploader/)
>
> ---


# Order images uploader

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. Ensure your server has adequate file upload limits configured in `php.ini` (e.g., `upload_max_filesize`, `post_max_size`) to accommodate the size of files your customers might upload.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Order images uploader)

This is the main configuration screen where you control the general behavior and appearance of the module.

#### General Settings

- **Enable module:**

  - **What this setting does:** This is the master switch to turn the entire module’s functionality on or off.
  - **Effect of changing this setting:**
    - *When enabled:* The module’s features (upload forms, file management) will be active on your front office and back office.
    - *When disabled:* All module functionality will be hidden from customers and administrators, effectively pausing its operation.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you’re setting up the module for the first time, enable it to test. If you need to temporarily disable file uploads for maintenance, set it to NO.
- **Allow customers to upload files:**

  - **What this setting does:** Determines if customers are allowed to upload files at all.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see upload forms and be able to submit files.
    - *When disabled:* Customers will not see any upload options, even if the module is enabled.
  - **Recommended value:** YES
  - **Merchant scenario / example:** If you only want to use the module for internal file management (e.g., administrators uploading files to orders), you might disable this. For most use cases, customers need to upload files, so keep it enabled.
- **Allow guest customers to upload files:**

  - **What this setting does:** Controls whether non-logged-in customers (guests) can upload files.
  - **Effect of changing this setting:**
    - *When enabled:* Guests can upload files, typically associated with their cart or order during checkout.
    - *When disabled:* Only registered and logged-in customers can upload files.
  - **Recommended value:** YES (if you allow guest checkout and need files from guests)
  - **Merchant scenario / example:** If your store allows guest checkout and requires file uploads for guest orders (e.g., a quick print job), enable this. If you want to force customers to register to upload files, disable it.
- **Allow customers to delete files:**

  - **What this setting does:** Gives customers the ability to remove files they have previously uploaded.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will see a “Delete” option next to their uploaded files in their account.
    - *When disabled:* Customers can upload but cannot remove files. Only administrators can delete them.
  - **Recommended value:** NO (unless you trust customers to manage their files perfectly)
  - **Merchant scenario / example:** For custom print orders, you might want to disable this to prevent customers from accidentally deleting a file that’s already in production. If files are temporary or easily replaceable, you might enable it for customer convenience.
- **Allow customers to download files:**

  - **What this setting does:** Determines if customers can download files they (or you) have uploaded to their orders.
  - **Effect of changing this setting:**
    - *When enabled:* Customers can click to download their files from their order history.
    - *When disabled:* Customers cannot download files.
  - **Recommended value:** YES (for transparency and customer access)
  - **Merchant scenario / example:** If you upload a proof or a final design for the customer to review, enabling this allows them to download it.
- **Allow customers to upload files to orders:**

  - **What this setting does:** Specifically controls whether customers can upload files *after* an order has been placed, from their order history page.
  - **Effect of changing this setting:**
    - *When enabled:* An upload option will appear on the customer’s individual order detail page in “My Account”.
    - *When disabled:* Customers can only upload files during the cart/checkout process or on product pages, not to existing orders.
  - **Recommended value:** YES (highly recommended for flexibility)
  - **Merchant scenario / example:** A customer forgot to upload a specific logo after placing an order for custom t-shirts. With this enabled, they can easily add it later.
- **Allow customers to upload files to carts:**

  - **What this setting does:** Controls whether customers can upload files while their items are still in the shopping cart.
  - **Effect of changing this setting:**
    - *When enabled:* An upload option will appear on the shopping cart page.
    - *When disabled:* Customers cannot upload files to their cart.
  - **Recommended value:** YES (convenient for customers)
  - **Merchant scenario / example:** A customer is building a custom photo album. They can upload photos directly to the cart before proceeding to checkout.
- **Allow customers to upload files to products:**

  - **What this setting does:** Controls whether customers can upload files directly on individual product pages.
  - **Effect of changing this setting:**
    - *When enabled:* An upload option will appear on product pages.
    - *When disabled:* Customers cannot upload files on product pages.
  - **Recommended value:** YES (for highly customizable products)
  - **Merchant scenario / example:** For a personalized mug, the customer can upload their desired photo directly on the mug’s product page before adding it to the cart.
- **Allow customers to upload files to customer account:**

  - **What this setting does:** Enables a dedicated “My Files” section in the customer’s account, allowing them to upload and manage files not necessarily tied to a specific order or cart.
  - **Effect of changing this setting:**
    - *When enabled:* A new menu item “My Files” appears in the customer’s “My Account” dashboard.
    - *When disabled:* This section is hidden.
  - **Recommended value:** NO (unless you have a specific need for general file storage)
  - **Merchant scenario / example:** If you want customers to pre-upload common assets (e.g., their company logo) that they might use across multiple future orders, this could be useful. Otherwise, it might add unnecessary complexity.
- **Force customers to upload files to orders:**

  - **What this setting does:** Makes file upload mandatory for an order to be completed. If no files are uploaded, the customer cannot proceed.
  - **Effect of changing this setting:**
    - *When enabled:* Customers will be blocked from completing checkout until they upload at least one file.
    - *When disabled:* File upload is optional.
  - **Recommended value:** NO (only enable if absolutely critical for every order)
  - **Merchant scenario / example:** For a print shop where *every* order requires a design file, enabling this ensures no order goes through without the necessary assets. Be cautious, as this can impact conversion rates if not every product requires a file.
- **Force customers to upload files to products:**

  - **What this setting does:** Makes file upload mandatory for a product to be added to the cart.
  - **Effect of changing this setting:**
    - *When enabled:* Customers cannot add a product to the cart until they upload at least one file for that product.
    - *When disabled:* File upload is optional on the product page.
  - **Recommended value:** NO (only enable for products that are *always* personalized)
  - **Merchant scenario / example:** For a “Design Your Own T-Shirt” product, this ensures the customer provides their design before adding it to the cart.
- **Force customers to upload files to carts:**

  - **What this setting does:** Makes file upload mandatory for the entire cart to be processed.
  - **Effect of changing this setting:**
    - *When enabled:* Customers cannot proceed from the cart to checkout until they upload at least one file for the cart.
    - *When disabled:* File upload is optional on the cart page.
  - **Recommended value:** NO (use with extreme caution, can severely impact conversion)
  - **Merchant scenario / example:** This is rarely recommended unless *every single order* in your store requires a general file upload. It’s usually better to force uploads at the product or order level if needed.
- **Allowed file extensions (separated by comma):**

  - **What this setting does:** Defines which file types customers are permitted to upload.
  - **Effect of changing this setting:**
    - *When changed:* Only files with the specified extensions (e.g., `jpg,png,gif,pdf`) will be accepted. Any other file type will be rejected.
  - **Recommended value:** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (adjust based on your needs)
  - **Merchant scenario / example:** A print shop might allow `jpg,png,pdf,ai,eps`. A custom jewelry store might only need `jpg,png`. Limiting extensions improves security and ensures you receive usable files.
- **Maximum file size (in MB):**

  - **What this setting does:** Sets the upper limit for the size of a single file a customer can upload.
  - **Effect of changing this setting:**
    - *When changed:* Files larger than this limit will be rejected.
  - **Recommended value:** `10` (or higher if you expect large design files)
  - **Merchant scenario / example:** If customers upload high-resolution images or large design files, you might set this to `50` or `100`. Be aware that very large files can slow down uploads and consume server space. Ensure your server’s `php.ini` `upload_max_filesize` and `post_max_size` are also configured to support this value.
- **Maximum number of files per order:**

  - **What this setting does:** Limits how many individual files a customer can upload for a single order.
  - **Effect of changing this setting:**
    - *When changed:* Customers will be prevented from uploading more files once they reach this limit for a given order.
  - **Recommended value:** `5` (or higher if many files are expected)
  - **Merchant scenario / example:** If a customer is ordering 10 different personalized items, and each needs a file, you might set this to `10` or `20`. If only one or two files are usually needed, a lower number prevents clutter.
- **Maximum number of files per product:**

  - **What this setting does:** Limits how many individual files a customer can upload for a single product.
  - **Effect of changing this setting:**
    - *When changed:* Customers will be prevented from uploading more files once they reach this limit for a given product.
  - **Recommended value:** `1` (if each product needs one design) or `5` (if multiple angles/versions are needed)
  - **Merchant scenario / example:** For a custom portrait, you might allow `3` files (front, side, back reference photos). For a simple logo print, `1` file is sufficient.
- **Maximum number of files per cart:**

  - **What this setting does:** Limits how many individual files a customer can upload for the entire shopping cart.
  - **Effect of changing this setting:**
    - *When changed:* Customers will be prevented from uploading more files once they reach this limit for the cart.
  - **Recommended value:** `5` (or higher if many general files are expected)
  - **Merchant scenario / example:** If a customer is uploading a general instruction document that applies to the whole cart, you might set this to `1`.
- **Display upload form on product page:**

  - **What this setting does:** Controls where the upload form appears on the product page.
  - **Effect of changing this setting:**
    - *When set to ‘In product tab’:* The upload form will appear within a new tab on the product page (e.g., next to “Description” or “Data Sheet”).
    - *When set to ‘Under product description’:* The upload form will appear directly below the main product description.
    - *When set to ‘Under product price’:* The upload form will appear near the product price, usually above the “Add to Cart” button.
  - **Recommended value:** ‘In product tab’ (for less intrusive display) or ‘Under product price’ (for high visibility)
  - **Merchant scenario / example:** For a product where file upload is critical, placing it “Under product price” makes it highly visible. For less critical uploads, a “product tab” keeps the main product information clean.
- **Display upload form on cart page:**

  - **What this setting does:** Controls where the upload form appears on the shopping cart page.
  - **Effect of changing this setting:**
    - *When set to ‘In summary block’:* The upload form will appear within the main cart summary area.
    - *When set to ‘Under cart summary’:* The upload form will appear below the entire cart summary.
  - **Recommended value:** ‘Under cart summary’ (often provides more space)
  - **Merchant scenario / example:** If customers need to upload a general file for the entire order, placing it clearly on the cart page ensures they don’t miss it before checkout.
- **Display upload form on order history page:**

  - **What this setting does:** Controls where the upload form appears on the customer’s individual order detail page.
  - **Effect of changing this setting:**
    - *When set to ‘In order details block’:* The upload form will appear within the main order details section.
    - *When set to ‘Under order details’:* The upload form will appear below the order details.
  - **Recommended value:** ‘In order details block’ (for closer association with the order)
  - **Merchant scenario / example:** After a customer places an order, they can easily find the upload option on their order history page to add missing files.
- **Display upload form on my account page:**

  - **What this setting does:** Controls whether a dedicated “My Files” link appears in the customer’s “My Account” dashboard.
  - **Effect of changing this setting:**
    - *When enabled:* A link will appear, leading to a page where customers can manage general files.
    - *When disabled:* The link will not appear.
  - **Recommended value:** NO (unless you enabled “Allow customers to upload files to customer account” and need this feature)
  - **Merchant scenario / example:** If you want customers to have a central place for all their uploaded files, independent of specific orders, enable this.
- **Display upload form on footer:**

  - **What this setting does:** Adds a link to the file upload manager in your store’s footer.
  - **Effect of changing this setting:**
    - *When enabled:* A link will appear in the footer, providing another access point to the file manager.
    - *When disabled:* No link in the footer.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** If file uploads are a core part of your business, a footer link can make it easily accessible from any page.
- **Display upload form on left column:**

  - **What this setting does:** Adds a link to the file upload manager in your store’s left column.
  - **Effect of changing this setting:**
    - *When enabled:* A link will appear in the left column.
    - *When disabled:* No link in the left column.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** Similar to the footer, this provides another prominent access point.
- **Display upload form on right column:**

  - **What this setting does:** Adds a link to the file upload manager in your store’s right column.
  - **Effect of changing this setting:**
    - *When enabled:* A link will appear in the right column.
    - *When disabled:* No link in the right column.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** Similar to the footer and left column, this provides another prominent access point.
- **Send email to customer about new file:**

  - **What this setting does:** Controls whether an email notification is sent to the customer when a new file is uploaded to their order by an administrator.
  - **Effect of changing this setting:**
    - *When enabled:* Customers receive an email notification.
    - *When disabled:* No email notification is sent.
  - **Recommended value:** YES (for good customer communication)
  - **Merchant scenario / example:** If you upload a design proof for the customer to review, they will be notified by email.
- **Send email to shop owner about new file:**

  - **What this setting does:** Controls whether an email notification is sent to the shop owner (or configured shop email) when a customer uploads a new file.
  - **Effect of changing this setting:**
    - *When enabled:* You (the shop owner) receive an email notification.
    - *When disabled:* No email notification is sent.
  - **Recommended value:** YES (highly recommended for timely processing)
  - **Merchant scenario / example:** A customer uploads a critical design file. You receive an email immediately, allowing you to start processing the order without delay.
- **Attach files to order confirmation email:**

  - **What this setting does:** Determines if customer-uploaded files are attached to the standard PrestaShop order confirmation email.
  - **Effect of changing this setting:**
    - *When enabled:* The files will be included as attachments in the order confirmation email sent to the customer.
    - *When disabled:* Files are not attached to the email.
  - **Recommended value:** NO (unless files are small and few, as large attachments can cause email delivery issues)
  - **Merchant scenario / example:** If customers upload very small, non-critical files, you might enable this. For larger or numerous files, it’s better to let customers download them from their account to avoid email server issues.
- **Attach files to customer service email:**

  - **What this setting does:** Determines if customer-uploaded files are attached to the email sent to the customer when an administrator uploads a new file.
  - **Effect of changing this setting:**
    - *When enabled:* The files will be included as attachments in the email.
    - *When disabled:* Files are not attached to the email.
  - **Recommended value:** NO (similar to order confirmation, avoid large attachments)
  - **Merchant scenario / example:** If you upload a small proof for the customer, you might enable this. For larger files, direct them to download from their account.
- **Attach files to shop owner email:**

  - **What this setting does:** Determines if customer-uploaded files are attached to the email sent to the shop owner when a new file is uploaded by a customer.
  - **Effect of changing this setting:**
    - *When enabled:* The files will be included as attachments in the email notification you receive.
    - *When disabled:* Files are not attached to the email.
  - **Recommended value:** NO (unless files are small and few, as large attachments can clog your inbox)
  - **Merchant scenario / example:** If you prefer to download files directly from the back office, disable this. If you only expect very small files and want them immediately in your inbox, enable it.
- **Enable comments for files:**

  - **What this setting does:** Allows customers and administrators to add comments to each uploaded file.
  - **Effect of changing this setting:**
    - *When enabled:* A text field will appear next to each file for adding notes or instructions.
    - *When disabled:* No comment fields will be available.
  - **Recommended value:** YES (for better communication and context)
  - **Merchant scenario / example:** A customer uploads a logo and adds a comment: “Use this logo, but please change the color to blue.” This provides crucial context.
- **Enable comments for carts:**

  - **What this setting does:** Allows customers to add a general comment to their shopping cart.
  - **Effect of changing this setting:**
    - *When enabled:* A text field will appear on the cart page for general cart comments.
    - *When disabled:* No general cart comment field.
  - **Recommended value:** YES (useful for general instructions)
  - **Merchant scenario / example:** A customer might add a comment like: “Please ensure all items are gift-wrapped together.”
- **Enable comments for orders:**

  - **What this setting does:** Allows customers to add a general comment to their order.
  - **Effect of changing this setting:**
    - *When enabled:* A text field will appear on the order detail page for general order comments.
    - *When disabled:* No general order comment field.
  - **Recommended value:** YES (useful for post-order instructions)
  - **Merchant scenario / example:** A customer might add a comment after placing an order: “I need this delivered by Friday, please.”
- **Enable comments for products:**

  - **What this setting does:** Allows customers to add a comment specific to a product.
  - **Effect of changing this setting:**
    - *When enabled:* A text field will appear on the product page for product-specific comments.
    - *When disabled:* No product-specific comment field.
  - **Recommended value:** YES (useful for product personalization instructions)
  - **Merchant scenario / example:** A customer ordering a custom engraving might add a comment: “Engrave ‘Happy Birthday John’ in script font.”
- **Enable “My Files” tab in customer account:**

  - **What this setting does:** Adds a dedicated “My Files” tab to the customer’s account dashboard.
  - **Effect of changing this setting:**
    - *When enabled:* A new tab appears, allowing customers to view and manage all their uploaded files in one place.
    - *When disabled:* The tab is hidden.
  - **Recommended value:** YES (improves customer experience by centralizing files)
  - **Merchant scenario / example:** Customers can easily find all their uploaded designs, proofs, or documents in one convenient location.
- **Enable “My Files” tab in order history page:**

  - **What this setting does:** Adds a dedicated “My Files” section within the order history page for each specific order.
  - **Effect of changing this setting:**
    - *When enabled:* A section appears within each order’s detail page, showing files related to that specific order.
    - *When disabled:* This section is hidden.
  - **Recommended value:** YES (crucial for order-specific file management)
  - **Merchant scenario / example:** When a customer reviews a past order, they can immediately see all the files they uploaded for that order.
- **Enable “My Files” tab in product page:**

  - **What this setting does:** Adds a dedicated “My Files” section within the product page.
  - **Effect of changing this setting:**
    - *When enabled:* A section appears on the product page, showing files related to that specific product.
      *When disabled:* This section is hidden.
  - **Recommended value:** NO (unless you have a very specific use case, as this can clutter product pages)
  - **Merchant scenario / example:** This might be useful if customers frequently re-order the same personalized product and need to refer to previously uploaded files for that product.
- **Enable “My Files” tab in cart page:**

  - **What this setting does:** Adds a dedicated “My Files” section within the cart page.
  - **Effect of changing this setting:**
    - *When enabled:* A section appears on the cart page, showing files related to the items in the cart.
      *When disabled:* This section is hidden.
  - **Recommended value:** NO (unless you have a very specific use case, as this can clutter cart pages)
  - **Merchant scenario / example:** If customers are building a complex order with many files, this could provide an overview of all files currently associated with the cart.
- **Show file upload button on product page:**

  - **What this setting does:** Controls the visibility of the “Upload File” button on product pages.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
    - *When disabled:* The button will be hidden.
  - **Recommended value:** YES (if you allow product file uploads)
  - **Merchant scenario / example:** If you want customers to upload files for product personalization, this button needs to be visible.
- **Show file upload button on cart page:**

  - **What this setting does:** Controls the visibility of the “Upload File” button on the cart page.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
    - *When disabled:* The button will be hidden.
  - **Recommended value:** YES (if you allow cart file uploads)
  - **Merchant scenario / example:** If customers need to upload a general file for their entire order, this button needs to be visible on the cart page.
- **Show file upload button on order history page:**

  - **What this setting does:** Controls the visibility of the “Upload File” button on the customer’s order detail page.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
    - *When disabled:* The button will be hidden.
  - **Recommended value:** YES (if you allow post-order file uploads)
  - **Merchant scenario / example:** If customers might need to add files after placing an order, this button needs to be visible on their order history page.
- **Show file upload button on my account page:**

  - **What this setting does:** Controls the visibility of the “Upload File” button on the customer’s “My Account” page.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
      *When disabled:* The button will be hidden.
  - **Recommended value:** NO (unless you enabled “Allow customers to upload files to customer account” and need this feature)
  - **Merchant scenario / example:** If you want customers to upload general files to their account, this button needs to be visible.
- **Show file upload button on footer:**

  - **What this setting does:** Controls the visibility of the “Upload File” button in the footer.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
      *When disabled:* The button will be hidden.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** If file uploads are a core part of your business, a footer button can make it easily accessible from any page.
- **Show file upload button on left column:**

  - **What this setting does:** Controls the visibility of the “Upload File” button in the left column.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
      *When disabled:* The button will be hidden.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** Similar to the footer, this provides another prominent access point.
- **Show file upload button on right column:**

  - **What this setting does:** Controls the visibility of the “Upload File” button in the right column.
  - **Effect of changing this setting:**
    - *When enabled:* The button will be visible.
      *When disabled:* The button will be hidden.
  - **Recommended value:** NO (unless you want high visibility for the file manager)
  - **Merchant scenario / example:** Similar to the footer and left column, this provides another prominent access point.

#### Advanced Settings

- **Enable debug mode:**

  - **What this setting does:** Activates a special mode that displays additional information and error messages, primarily for troubleshooting.
  - **Effect of changing this setting:**
    - *When enabled:* More detailed error messages and debugging information might appear on the screen or in logs.
    - *When disabled:* Normal operation, errors are suppressed or logged silently.
  - **Recommended value:** NO (only enable when troubleshooting with support)
  - **Merchant scenario / example:** If you encounter an issue and need to provide more information to MyPresta.eu support, they might ask you to enable debug mode.
- **Delete files when order is deleted:**

  - **What this setting does:** Automatically removes all associated uploaded files when an order is deleted from the PrestaShop back office.
  - **Effect of changing this setting:**
    - *When enabled:* Files are permanently removed from your server when an order is deleted.
    - *When disabled:* Files remain on the server even if the associated order is deleted.
  - **Recommended value:** YES (to keep your server clean and avoid orphaned files)
  - **Merchant scenario / example:** If you frequently delete test orders, enabling this prevents your server from accumulating unnecessary files.
- **Delete files when product is deleted:**

  - **What this setting does:** Automatically removes all associated uploaded files when a product is deleted from the PrestaShop back office.
  - **Effect of changing this setting:**
    - *When enabled:* Files are permanently removed from your server when a product is deleted.
      *When disabled:* Files remain on the server even if the associated product is deleted.
  - **Recommended value:** YES (to keep your server clean and avoid orphaned files)
  - **Merchant scenario / example:** If you remove old or discontinued products, this ensures their associated files are also cleaned up.
- **Delete files when cart is deleted:**

  - **What this setting does:** Automatically removes all associated uploaded files when a cart is deleted from the PrestaShop back office.
  - **Effect of changing this setting:**
    - *When enabled:* Files are permanently removed from your server when a cart is deleted.
      *When disabled:* Files remain on the server even if the associated cart is deleted.
  - **Recommended value:** YES (to keep your server clean and avoid orphaned files)
  - **Merchant scenario / example:** Carts are often temporary. Enabling this prevents your server from accumulating files from abandoned carts.
- **Delete files when customer is deleted:**

  - **What this setting does:** Automatically removes all associated uploaded files when a customer account is deleted from the PrestaShop back office.
  - **Effect of changing this setting:**
    - *When enabled:* Files are permanently removed from your server when a customer is deleted.
      *When disabled:* Files remain on the server even if the associated customer is deleted.
  - **Recommended value:** YES (for data privacy and server hygiene)
  - **Merchant scenario / example:** If a customer requests their data to be removed (GDPR compliance), this ensures their uploaded files are also deleted.
- **Delete files when customer file is deleted:**

  - **What this setting does:** When an administrator or customer deletes a specific file, this setting controls whether the actual file is removed from the server.
  - **Effect of changing this setting:**
    - *When enabled:* The file is permanently removed from the server.
      *When disabled:* The file record is removed from the database, but the actual file remains on the server (orphaned).
  - **Recommended value:** YES (always, to prevent orphaned files and save disk space)
  - **Merchant scenario / example:** When a customer decides they no longer need a file, deleting it also frees up server space.
- **Enable custom CSS:**

  - **What this setting does:** Provides a text area where you can add your own CSS rules to customize the appearance of the module’s elements.
  - **Effect of changing this setting:**
    - *When enabled and CSS added:* Your custom styles will override or supplement the module’s default styling.
      *When disabled or empty:* The module uses its default styling.
  - **Recommended value:** NO (unless you have specific design needs and CSS knowledge)
  - **Merchant scenario / example:** You want to change the color of the upload button to match your brand’s primary color. You would add CSS rules here.
- **Custom CSS:**

  - **What this setting does:** This is the text area where you type or paste your custom CSS code.
  - **Effect of changing this setting:** The visual appearance of the module elements will change according to your CSS rules.
  - **Recommended value:** Leave empty unless you know CSS.
  - **Merchant scenario / example:** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Dedicated Admin Screens & Controller Views

The module adds new sections to your PrestaShop back office for managing uploaded files.

#### 2.2.1 Customer Files Manager (Back Office > Orders > Customer Files)

This screen provides a centralized place for you to view and manage all files uploaded by your customers.

- **Screen Name & Menu Location:** **Customer Files** (found under the **Orders** menu in PrestaShop 1.7/8/9. In older versions, it might be directly under the main Modules menu or a custom tab).
- **Available Actions & Settings:**
  - **File Listing Table:** You’ll see a table listing all uploaded files. Each row typically shows:
    - **File Name:** The name of the uploaded file.
    - **Customer:** The name of the customer who uploaded the file (or “Guest” if applicable).
    - **Order ID:** The ID of the order the file is associated with.
    - **Product:** The product name if the file is linked to a specific product.
    - **Cart ID:** The ID of the cart the file is associated with.
    - **Date Uploaded:** When the file was uploaded.
    - **Size:** The size of the file.
    - **Actions:** Buttons to **Download** the file, **View Details** (including comments), or **Delete** the file.
  - **Filtering & Searching:** You can typically filter the list by customer, order ID, or search by file name to quickly find specific files.
  - **Bulk Actions:** Options to select multiple files and perform actions like bulk deletion.
- **Effect of changes:**
  - **Downloading a file:** Saves the file to your computer for review or processing.
  - **Deleting a file:** Removes the file from the list and, if configured, from your server.
  - **Viewing details:** Opens a pop-up or new page with more information about the file, including any associated comments.
- **Recommended workflow for daily store management:**
  1. Regularly check this section, especially if you receive email notifications for new uploads.
  2. Use the filters to quickly find files for specific orders you are processing.
  3. Download necessary files for production, design, or review.
  4. Add comments to files if you need to communicate with the customer or your team about them.
  5. Delete old or unnecessary files to keep your server clean.

#### 2.2.2 Order Detail Page Integration (Back Office > Orders > Orders > View Order)

The module also integrates directly into the standard PrestaShop order detail page.

- **Screen Name & Menu Location:** When you view any specific order in **Back Office > Orders > Orders**, you will find a new section or tab related to “Customer Files” or “Uploaded Files”.
- **Available Actions & Settings:**
  - **Files for this Order:** A list of all files specifically uploaded for the current order by the customer or by an administrator.
  - **Upload New File:** An option to upload a file yourself as an administrator, associating it directly with this order. This is useful for uploading proofs, final designs, or internal documents.
  - **Add Comments:** You can add comments to individual files or a general comment for the order.
  - **Download/Delete:** Options to download or delete individual files associated with this order.
- **Effect of changes:**
  - **Uploading a file as admin:** The file becomes part of the order’s attachments, visible to the customer in their order history (if configured).
  - **Adding comments:** Provides context for the file or order, visible to the customer and other administrators.
- **Recommended workflow for daily store management:**
  1. When processing an order that requires customer files, navigate to the order detail page.
  2. Review the uploaded files in the dedicated section.
  3. Download files as needed for production.
  4. If you create a proof or a final design, upload it here so the customer can access it.
  5. Use the comment fields to communicate with the customer or leave internal notes.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enable module | YES | Master switch for module functionality. |
|  | Allow customers to upload files | YES | Allow customers to submit files. |
|  | Allow guest customers to upload files | YES | Allow non-logged-in users to upload. |
|  | Allow customers to delete files | NO | Prevent customers from removing files. |
|  | Allow customers to download files | YES | Allow customers to retrieve their files. |
|  | Allow customers to upload files to orders | YES | Enable post-order uploads via order history. |
|  | Allow customers to upload files to carts | YES | Enable uploads on the shopping cart page. |
|  | Allow customers to upload files to products | YES | Enable uploads on individual product pages. |
|  | Allow customers to upload files to customer account | NO | Enable general file storage in “My Account”. |
|  | Force customers to upload files to orders | NO | Make file upload mandatory for order completion. |
|  | Force customers to upload files to products | NO | Make file upload mandatory to add product to cart. |
|  | Force customers to upload files to carts | NO | Make file upload mandatory to proceed from cart. |
|  | Allowed file extensions | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Restrict file types for security and usability. |
|  | Maximum file size (MB) | `10` | Limit individual file size. |
|  | Maximum number of files per order | `5` | Limit files per order. |
|  | Maximum number of files per product | `1` | Limit files per product. |
|  | Maximum number of files per cart | `5` | Limit files per cart. |
|  | Display upload form on product page | ‘In product tab’ or ‘Under product price’ | Position of upload form on product page. |
|  | Display upload form on cart page | ‘Under cart summary’ | Position of upload form on cart page. |
|  | Display upload form on order history page | ‘In order details block’ | Position of upload form on order history page. |
|  | Display upload form on my account page | NO | Show/hide “My Files” link in customer account. |
|  | Display upload form on footer | NO | Show/hide “My Files” link in footer. |
|  | Display upload form on left column | NO | Show/hide “My Files” link in left column. |
|  | Display upload form on right column | NO | Show/hide “My Files” link in right column. |
|  | Send email to customer about new file | YES | Notify customer when admin uploads a file. |
|  | Send email to shop owner about new file | YES | Notify shop owner when customer uploads a file. |
|  | Attach files to order confirmation email | NO | Attach uploaded files to order confirmation. |
|  | Attach files to customer service email | NO | Attach uploaded files to customer service email. |
|  | Attach files to shop owner email | NO | Attach uploaded files to shop owner notification. |
|  | Enable comments for files | YES | Allow comments on individual files. |
|  | Enable comments for carts | YES | Allow general comments on carts. |
|  | Enable comments for orders | YES | Allow general comments on orders. |
|  | Enable comments for products | YES | Allow comments on individual products. |
|  | Enable “My Files” tab in customer account | YES | Show dedicated “My Files” tab in customer account. |
|  | Enable “My Files” tab in order history page | YES | Show files section on order history page. |
|  | Enable “My Files” tab in product page | NO | Show files section on product page. |
|  | Enable “My Files” tab in cart page | NO | Show files section on cart page. |
|  | Show file upload button on product page | YES | Control visibility of upload button on product page. |
|  | Show file upload button on cart page | YES | Control visibility of upload button on cart page. |
|  | Show file upload button on order history page | YES | Control visibility of upload button on order history page. |
|  | Show file upload button on my account page | NO | Control visibility of upload button on my account page. |
|  | Show file upload button on footer | NO | Control visibility of upload button in footer. |
|  | Show file upload button on left column | NO | Control visibility of upload button in left column. |
|  | Show file upload button on right column | NO | Control visibility of upload button in right column. |
| **Advanced Settings** | Enable debug mode | NO | Display detailed error messages. |
|  | Delete files when order is deleted | YES | Remove files when associated order is deleted. |
|  | Delete files when product is deleted | YES | Remove files when associated product is deleted. |
|  | Delete files when cart is deleted | YES | Remove files when associated cart is deleted. |
|  | Delete files when customer is deleted | YES | Remove files when associated customer is deleted. |
|  | Delete files when customer file is deleted | YES | Remove actual file from server when deleted. |
|  | Enable custom CSS | NO | Activate custom CSS input. |
|  | Custom CSS | Leave empty | Text area for custom CSS rules. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers can’t upload files, or they get an error message.**
A1:

- **Check Module Status:** Ensure “Enable module” and “Allow customers to upload files” are both set to YES in the module configuration.
- **File Type & Size:** Verify that the file type (extension) and size are within the “Allowed file extensions” and “Maximum file size” limits you’ve set.
- **Server Limits:** Your hosting provider might have lower PHP upload limits (`upload_max_filesize`, `post_max_size` in `php.ini`) than your module settings. Contact your host or webmaster to increase these if necessary.
- **Permissions:** Ensure the module’s upload directory (usually `modules/orderfiles/uploads/`) has write permissions (e.g., 755 or 777, though 777 is generally not recommended for security).
- **Debug Mode:** Temporarily enable “Debug mode” in the module’s advanced settings and check for any specific error messages.

**Q2: The upload form isn’t showing up on my product/cart/order page.**
A2:

- **Module Configuration:** Double-check the “Display upload form on…” settings for the specific page (product, cart, order history) in the module’s configuration.
- **Hook Conflicts:** Another module might be interfering with the display hooks. Try temporarily disabling other modules that modify product, cart, or order pages to see if the form appears.
- **Theme Compatibility:** Custom themes might not correctly render standard PrestaShop hooks. If you’re using a custom theme, you might need a webmaster to manually integrate the module’s hooks into your theme files.
- **Cache:** Clear your PrestaShop cache (Advanced Parameters > Performance > Clear cache) and your browser cache.

**Q3: I’m not receiving email notifications when customers upload files.**
A3:

- **Module Configuration:** Ensure “Send email to shop owner about new file” is set to YES.
- **Shop Email:** Verify that your shop’s email address (PS\_SHOP\_EMAIL in Advanced Parameters > E-mail) is correctly configured and working.
- **Email Settings:** Check your PrestaShop email settings (Advanced Parameters > E-mail) and ensure emails are being sent successfully (e.g., try sending a test email).
- **Spam Folder:** Check your spam or junk folder for the notifications.
- **Server Mailer:** Your server’s mail function might be misconfigured. Consult your hosting provider.

**Q4: How do I translate the module’s text into other languages?**
A4:

- In your PrestaShop back office, navigate to **International > Translations**.
- Select “Installed modules translations”.
- Choose your theme, the language you want to translate, and then select “Order images uploader” from the module list.
- You can then translate all the module’s visible text strings.

**Q5: My uploaded files are not being deleted when I delete an order/product/customer.**
A5:

- **Module Configuration:** Ensure the corresponding “Delete files when…” settings (e.g., “Delete files when order is deleted”) are set to YES in the module’s advanced settings.
- **Manual Deletion:** If these settings were disabled, files might have accumulated. You may need to manually clean up the `modules/orderfiles/uploads/` directory on your server for old, orphaned files.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

### 4.1 Architecture Overview

The “Order images uploader” module follows a standard PrestaShop module architecture, leveraging MVC principles. It extends the `Module` class for its core functionality and uses `ModuleFrontController` and `AdminController` for handling front-office and back-office requests, respectively. File uploads are managed through dedicated controllers and JavaScript, ensuring a smooth user experience. Configuration is stored in `ps_configuration`, and custom data (file records) are managed through direct database interaction or potentially a custom `ObjectModel` (though none were explicitly listed in the inventory, the module likely uses direct SQL for file records).

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers handle customer interactions and file management on the storefront.

- `controllers/front/customerfiles.php`
  - **Class name & parent class:** `OrderFilesCustomerfilesModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** Manages the customer’s “My Files” section, displaying a list of their uploaded files, allowing them to view, download, and potentially delete them. It likely handles AJAX requests for file operations within this context.
- `controllers/front/download.php`
  - **Class name & parent class:** `OrderFilesDownloadModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** Handles secure file downloads. It verifies user permissions (e.g., if the file belongs to the logged-in customer or if the user is an admin) before serving the file, preventing unauthorized access.
- `controllers/front/filesmanager.php`
  - **Class name & parent class:** `OrderFilesFilesmanagerModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** This is likely a central controller for the main file management interface, potentially used for general file uploads not tied to a specific order/product, or as a hub for all customer files.
- `controllers/front/index.php`
  - **Class name & parent class:** `OrderFilesIndexModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** A placeholder or default front controller. In PrestaShop, `index.php` in a controller directory often serves as a fallback or a simple redirect.
- `controllers/front/myfiles.php`
  - **Class name & parent class:** `OrderFilesMyfilesModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** Similar to `customerfiles.php`, this controller likely handles the “My Files” section in the customer account, providing the interface for viewing and managing personal files.
- `controllers/front/thumb.php`
  - **Class name & parent class:** `OrderFilesThumbModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** Generates and serves thumbnails for uploaded image files, improving performance and display in file listings.
- `controllers/front/upload.php`
  - **Class name & parent class:** `OrderFilesUploadModuleFrontController` extending `ModuleFrontController`
  - **Responsibility:** The core controller for handling all file upload requests from the front office (product page, cart page, order history, “My Files”). It processes the uploaded file, validates its type and size, stores it on the server, and records its details in the database. It likely handles AJAX responses for upload progress and status.

#### Back-Office Admin Controllers

These controllers provide the administrative interface for managing uploaded files.

- `controllers/admin/customerFiles.php`
  - **Class name & parent class:** `AdminCustomerFilesController` extending `ModuleAdminController`
  - **Tab name and managed entity:** “Customer Files” (under Orders menu). Manages the listing, viewing, downloading, and deletion of all customer-uploaded files across the entire store. It provides a comprehensive grid view with filtering options.
- `controllers/admin/index.php`
  - **Class name & parent class:** `AdminOrderFilesIndexController` extending `ModuleAdminController`
  - **Tab name and managed entity:** Similar to the front-office `index.php`, this might be a placeholder or a simple redirect for the admin section. The primary file management is handled by `AdminCustomerFilesController`.

### 4.3 Core Classes & Models (`classes/`)

The provided inventory indicates no custom classes in the `classes/` directory. This suggests the module might be using direct database queries for file management or storing file information directly in `ps_configuration` or a custom table without a dedicated `ObjectModel`. Given the complexity of file management, it’s more likely that file records are stored in a custom database table and managed via direct SQL or a simple helper class within the main module file.

### 4.4 JavaScript Assets (`views/js/`)

These scripts enhance the user experience for file uploads and management.

- `orderfiles/js/jquery.form.js`
  - **Scope:** Front-office and Back-office (wherever forms are submitted via AJAX).
  - **Description:** A jQuery plugin for easily submitting HTML forms via AJAX, including file uploads. It handles progress tracking and simplifies asynchronous form submissions.
- `orderfiles/js/orders.js`
  - **Scope:** Back-office (specifically within order detail pages).
  - **Description:** Likely handles the AJAX functionality for uploading files directly from the admin order detail page, displaying files associated with an order, and managing comments within the order context.
- `orderfiles/js/script-customers.js`
  - **Scope:** Front-office (customer account pages, “My Files” section).
  - **Description:** Manages the interactive elements within the customer’s “My Files” section, including displaying file lists, handling download/delete actions, and potentially AJAX updates for file status or comments.
- `orderfiles/js/script.js`
  - **Scope:** Front-office (product pages, cart pages, general upload forms).
  - **Description:** The main front-office JavaScript for handling file uploads. It likely initializes the upload forms, handles drag-and-drop functionality, displays upload progress, validates file types/sizes client-side, and sends AJAX requests to `upload.php`.

### 4.5 CSS Stylesheets (`views/css/`)

These stylesheets control the visual presentation of the module’s elements.

- `orderfiles/css/ajaxuploader.css`
  - **Scope:** Front-office and Back-office (wherever the AJAX uploader interface is used).
  - **Description:** Styles for the file upload widget itself, including progress bars, drag-and-drop areas, and file preview elements.
  - **Key CSS class selectors:** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
- `orderfiles/css/backoffice.css`
  - **Scope:** Back-office (admin controllers).
  - **Description:** Specific styling for the module’s administrative interfaces, such as the “Customer Files” listing and the integration within the order detail page.
  - **Key CSS class selectors:** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
- `orderfiles/css/orderfiles.css`
  - **Scope:** Front-office (general module elements).
  - **Description:** General styling for the module’s front-office components, including buttons, file listings, and comment sections on product, cart, and order history pages.
  - **Key CSS class selectors:** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
- `orderfiles/css.css`
  - **Scope:** Potentially global or fallback styling.
  - **Description:** This might be an older or generic stylesheet. Developers should check its contents to understand its specific impact, as `orderfiles.css` is more descriptive.
  - **Key CSS class selectors:** (Requires inspection)

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

These templates are rendered via PrestaShop hooks to inject module content into various parts of the store.

- `displayProductPageUploadFormSmall.tpl`: Renders a compact upload form on the product page.
- `filesmanager-orderhistory.tpl`: Displays the file manager interface within the customer’s order history page.
- `force-redirect.tpl`: A utility template, possibly used for redirects after certain actions or to enforce file uploads.
- `header.tpl`: Injects CSS/JS assets or other necessary code into the `<head>` section of the front office.
- `my-account-17.tpl`: Renders the “My Files” link/tab for PrestaShop 1.7.x and newer customer account dashboards.
- `my-account.tpl`: Renders the “My Files” link/tab for older PrestaShop versions (e.g., 1.6.x) customer account dashboards.
- `orderConfirmation.tpl`: Displays file upload options or a summary on the order confirmation page.
- `product-files-button.tpl`: Renders the “Upload File” button on the product page.
- `product-files.tpl`: Displays a list of files associated with a product, potentially with upload options.
- `shopping-cart-force-files-alert.tpl`: Displays an alert message if file upload is mandatory on the cart page and no files are uploaded.
- `shopping-cart-qty-infos-alert.tpl`: Likely displays an alert related to quantity information in the cart, possibly tied to file uploads.
- `shopping-cart.tpl`: Integrates file upload functionality or file listings into the shopping cart page.
- `tab.tpl`: A generic tab template, possibly used for creating new tabs on product pages or in the customer account.

#### Admin templates (`views/templates/admin/`)

These templates are used for the module’s back-office interfaces.

- `admin.tpl`: The main configuration template for the module’s `getContent()` method, rendering the settings form.
- `adminOrderDetailUpload.tpl`: Integrates the file upload and management interface directly into the PrestaShop order detail page in the back office.
- `boscript.tpl`: Contains JavaScript code specifically for the back office, likely included in admin pages.
- `bulk-delete-files.tpl`: Template for a bulk file deletion interface or confirmation.
- `comments_cartfiles.tpl`: Renders the comment section for files associated with a cart.
- `comments_orderfiles.tpl`: Renders the comment section for files associated with an order.
- `comments_productfiles.tpl`: Renders the comment section for files associated with a product.
- `customerfilesmanager.tpl`: The primary template for the `AdminCustomerFilesController`, displaying the grid of all uploaded files.
- `_configure/helpers/list/list_action_details.tpl`: A helper template for displaying a “details” action button in a list.
- `_configure/helpers/list/list_content.tpl`: A helper template for rendering the content rows of a list.
- `_configure/prestashopbug/helpers/list/*.tpl`: These templates appear to be specific overrides or fixes for PrestaShop’s default list helpers, possibly to address compatibility issues or customize the list display for the module’s admin grids. They include `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Front-office templates (`views/templates/front/`)

These are standalone templates for dedicated front-office pages.

- `access-denied.tpl`: Displays a message when a customer tries to access a file or page without proper permissions.
- `customerfilesmanager.tpl`: The main template for the customer’s “My Files” page, displaying their uploaded files.
- `filesmanager.tpl`: A general file manager template, potentially used for a broader file management page.
- `my-files.tpl`: Another template for the “My Files” section, likely similar to `customerfilesmanager.tpl` or a specific view within it.

### 4.7 Database Schema & Hooks Map

#### Database Tables

The module likely creates at least one custom database table to store information about the uploaded files.

- **`ps_orderfiles_files` (or similar):**
  - `id_order_file` (Primary Key)
  - `id_customer` (Link to `ps_customer`)
  - `id_order` (Link to `ps_order`)
  - `id_cart` (Link to `ps_cart`)
  - `id_product` (Link to `ps_product`)
  - `filename` (Original name of the file)
  - `filepath` (Path to the stored file on the server)
  - `file_extension`
  - `file_size`
  - `comment` (User/admin comments)
  - `date_add`
  - `date_upd`
  - `is_admin_upload` (Boolean, to distinguish customer vs. admin uploads)
- **`ps_configuration`:** Stores all the module’s settings (e.g., `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH`, etc.). These keys are prefixed with `OF_` (Order Files).

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayHeader` | In the `<head>` section of every front-office page. | Injects module’s CSS (`orderfiles.css`, `ajaxuploader.css`) and JavaScript (`jquery.form.js`, `script.js`, `script-customers.js`) files. |
| `displayProductAdditionalInfo` (or similar product page hook) | On the product page, typically below the main product details. | Renders `product-files.tpl` or `displayProductPageUploadFormSmall.tpl` for product-specific file uploads. |
| `displayShoppingCartFooter` (or similar cart page hook) | At the bottom of the shopping cart summary. | Renders `shopping-cart.tpl` for cart-wide file uploads and alerts. |
| `displayCustomerAccount` | In the customer’s “My Account” dashboard. | Renders `my-account.tpl` or `my-account-17.tpl` to add the “My Files” link. |
| `displayMyAccountBlock` | In the customer’s “My Account” dashboard (alternative for some themes). | Renders `my-account.tpl` or `my-account-17.tpl` to add the “My Files” link. |
| `displayOrderConfirmation` | On the order confirmation page after a successful purchase. | Renders `orderConfirmation.tpl` to show upload options or file summaries. |
| `displayOrderDetail` | On the customer’s order detail page in “My Account”. | Renders `filesmanager-orderhistory.tpl` to show files related to the specific order. |
| `displayLeftColumn` | In the left column of the front office. | Renders `tab.tpl` (or similar) to display a link to the file manager. |
| `displayRightColumn` | In the right column of the front office. | Renders `tab.tpl` (or similar) to display a link to the file manager. |
| `displayFooter` | In the footer of the front office. | Renders `tab.tpl` (or similar) to display a link to the file manager. |
| `actionObjectOrderAddAfter` | After a new order is successfully added to the database. | Triggers email notifications to the shop owner if a customer uploaded files during checkout. |
| `actionObjectOrderDeleteAfter` | After an order is deleted from the database. | Triggers file deletion from the server if “Delete files when order is deleted” is enabled. |
| `actionObjectProductDeleteAfter` | After a product is deleted from the database. | Triggers file deletion from the server if “Delete files when product is deleted” is enabled. |
| `actionObjectCartDeleteAfter` | After a cart is deleted from the database. | Triggers file deletion from the server if “Delete files when cart is deleted” is enabled. |
| `actionObjectCustomerDeleteAfter` | After a customer is deleted from the database. | Triggers file deletion from the server if “Delete files when customer is deleted” is enabled. |
| `actionAdminOrdersControllerSaveAfter` | After an order is saved/updated in the back office. | Potentially handles admin file uploads or comment updates from the order detail page. |
| `actionAdminControllerSetMedia` | When an admin controller is loaded and its media assets are set. | Injects module’s CSS (`backoffice.css`) and JavaScript (`orders.js`, `jquery.form.js`, `boscript.tpl`) for back-office functionality. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and technical support, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any issues or questions regarding the “Order images uploader” module.
