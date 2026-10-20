---
title: "Sell CDKeys / License keys - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Sell CDKeys / License keys PrestaShop module by MyPresta.eu."
sidebar:
  label: "Sell CDKeys / License keys - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Sell CDKeys / License keys Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# Sell CDKeys / License keys

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 5.6 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are typically sufficient. No special server configurations are usually needed beyond a standard PrestaShop hosting environment.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

### 2.1 Module Configuration Page (Back Office > Modules > Configure > Sell CDKeys / License keys)

This is the main configuration area where you define how the module behaves, when to send keys, and general settings.

#### General Settings Tab

- **Enabled:**

  - **What this setting does:** This is the master switch to activate or deactivate the module’s core functionality.
  - **Effect of changing this setting:**
    - *When enabled:* The module will process orders, send CD keys, and display customer keys in the front office according to your other settings.
    - *When disabled:* The module will stop all its operations. No keys will be sent automatically, and the customer’s “My Keys” section might disappear or become inactive.
  - **Recommended value:** YES
  - **Merchant scenario / example:** Enable this once you’ve configured everything to start selling keys. Disable it temporarily if you need to perform maintenance or stop selling digital keys.
- **Select order states:**

  - **What this setting does:** Determines which order statuses will trigger the automatic sending of CD keys to customers. You can select multiple states.
  - **Effect of changing this setting:**
    - *When a selected state is reached:* The module will check the order for CD key products and send the keys.
    - *When an unselected state is reached:* No keys will be sent, even if the order contains CD key products.
  - **Recommended value:** “Payment accepted” and potentially “Delivered” if you want to ensure physical products are also delivered first.
  - **Merchant scenario / example:** If you want keys sent immediately after payment, select “Payment accepted”. If you use a manual payment method like bank wire, you might select “Payment accepted” after you’ve manually confirmed the payment.
- **Groups of customers permitted to receive cdkey:**

  - **What this setting does:** Allows you to restrict CD key delivery to specific customer groups (e.g., “Customers”, “Visitors”, “Guests”).
  - **Effect of changing this setting:**
    - *When a customer is in a selected group:* They will receive CD keys if all other conditions are met.
    - *When a customer is NOT in a selected group:* They will not receive CD keys, even if they purchase a CD key product.
  - **Recommended value:** “Customer” (and “Guest” if you allow guest checkouts for digital products).
  - **Merchant scenario / example:** You might restrict this to “Customers” if you want to encourage account creation or if you have special B2B groups that receive different types of keys.
- **Maximum order value:**

  - **What this setting does:** Sets an upper limit on the total value of an order for which CD keys will be automatically sent. Orders exceeding this value will not trigger automatic key delivery.
  - **Effect of changing this setting:**
    - *Order total below or equal to maximum:* Keys are sent automatically.
    - *Order total above maximum:* Keys are NOT sent automatically. You would need to manually send them.
  - **Recommended value:** Leave empty or set to a very high value (e.g., 999999) if you don’t want any value restriction.
  - **Merchant scenario / example:** Use this as a fraud prevention measure. If you notice a lot of high-value fraudulent orders, you might set a limit to manually review them before releasing expensive keys.
- **Send many codes in one mail:**

  - **What this setting does:** Controls whether multiple CD keys for the same product in a single order are sent in one email or in separate emails.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer buys 3 units of “Game X”, they will receive one email containing all 3 keys for “Game X”.
    - *When disabled:* If a customer buys 3 units of “Game X”, they will receive 3 separate emails, each with one key for “Game X”.
  - **Recommended value:** YES (generally better for customer experience and reduces email clutter).
  - **Merchant scenario / example:** If a customer buys a “4-pack” of a game, sending all 4 keys in one email is much clearer than 4 separate emails.
- **Title of email:**

  - **What this setting does:** Allows you to customize the subject line of the email sent to customers containing their CD keys.
  - **Effect of changing this setting:** The email subject line will reflect your custom title, making it easier for customers to identify the email.
  - **Recommended value:** Something clear and professional, e.g., “Your CD Keys / Licenses from [Your Shop Name] - Order #[Order ID]”.
  - **Merchant scenario / example:** A clear subject line like “Your Game Keys for Order #12345” helps customers quickly find their keys.
- **Change order status:**

  - **What this setting does:** After CD keys are successfully sent, this option allows you to automatically change the order status to a new, specified state.
  - **Effect of changing this setting:**
    - *When enabled and a state is selected:* The order status will automatically update (e.g., from “Payment accepted” to “CD Keys Sent”).
    - *When disabled:* The order status will remain as it was after the initial trigger (e.g., “Payment accepted”).
  - **Recommended value:** YES, and select a distinct status like “CD Keys Sent” (you might need to create this status in PrestaShop > Order Statuses).
  - **Merchant scenario / example:** This helps you quickly identify orders for which keys have already been delivered, improving your order management workflow.
- **Select order state (for status change):**

  - **What this setting does:** If “Change order status” is enabled, this dropdown lets you choose the specific order status to apply after keys are sent.
  - **Effect of changing this setting:** The chosen status will be applied to the order.
  - **Recommended value:** A custom status like “CD Keys Sent” or “Digital Product Delivered”.
  - **Merchant scenario / example:** Creating a specific status like “CD Keys Sent” allows you to filter orders and see exactly which ones have had their digital products fulfilled.
- **Include keys to invoice:**

  - **What this setting does:** Determines whether the delivered CD keys should also be printed on the customer’s invoice.
  - **Effect of changing this setting:**
    - *When enabled:* The keys will appear on the PDF invoice generated for the order.
    - *When disabled:* Keys will only be sent via email and/or appear in the “My Keys” section, but not on the invoice.
  - **Recommended value:** YES (provides an additional record for the customer).
  - **Merchant scenario / example:** Some customers prefer to have all purchase details, including keys, on their invoice for record-keeping or tax purposes.
- **Turn on pagination:**

  - **What this setting does:** Enables pagination for the list of CD keys displayed in the customer’s “My Keys” section in the front office.
  - **Effect of changing this setting:**
    - *When enabled:* If a customer has many keys, they will be displayed across multiple pages, improving load times and readability.
    - *When disabled:* All keys will be listed on a single page.
  - **Recommended value:** YES (especially if customers might accumulate many keys).
  - **Merchant scenario / example:** A customer who regularly buys game keys will appreciate pagination to quickly find specific keys without scrolling through a very long list.
- **Pagination number of items:**

  - **What this setting does:** If pagination is enabled, this sets how many CD keys are displayed per page in the customer’s “My Keys” section.
  - **Effect of changing this setting:** Controls the density of the key list on each page.
  - **Recommended value:** 10-20 (a good balance for readability).
  - **Merchant scenario / example:** Setting this to 15 means a customer with 30 keys will see 2 pages of keys.

#### CSV Import Settings Tab

- **CSV file row delimiter:**

  - **What this setting does:** Specifies the character used to separate individual rows (lines) in your CSV file when importing CD keys.
  - **Effect of changing this setting:** The module uses this character to correctly parse your CSV file into individual key entries. Incorrect delimiter will lead to import errors.
  - **Recommended value:** `\n` (newline character, standard for most CSV files).
  - **Merchant scenario / example:** If your key list is `key1\nkey2\nkey3`, the module needs to know `\n` separates each key.
- **CSV file column delimiter:**

  - **What this setting does:** Specifies the character used to separate columns (fields) within each row of your CSV file when importing CD keys.
  - **Effect of changing this setting:** The module uses this character to correctly identify different data points (e.g., key, group ID) within each row. Incorrect delimiter will lead to import errors.
  - **Recommended value:** `;` (semicolon) or `,` (comma), depending on how your CSV files are generated.
  - **Merchant scenario / example:** If your CSV is `key1;product_id_1;group_id_1`, the module needs to know `;` separates the fields.

#### Analytics & Fraud Tab

- **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE:**

  - **What these settings do:** These are internal configuration keys related to the module’s analytics and fraud detection dashboard. They control how data is displayed, aggregated, and filtered within the module’s back-office analytics section.
  - **Effect of changing these settings:** Adjusts the visual representation and data points shown in the module’s dashboard, helping you monitor key sales and potential fraud patterns.
  - **Recommended value:** Default values are usually fine. Adjust only if you need specific reporting views.
  - **Merchant scenario / example:** You might adjust `CDKEYS_ANALYTICS_PERIOD` to view sales trends over a week instead of a month, or `CDKEYS_ANALYTICS_TOP_LIMIT` to see more top-selling key groups.
- **CDKEYS\_ALERT\_COOLDOWN\_HOURS:**

  - **What this setting does:** Defines a cooldown period in hours for fraud alerts. If an alert is triggered for a customer, another alert for the same customer won’t be triggered within this cooldown period.
  - **Effect of changing this setting:** Prevents alert spam for repeat fraudulent attempts from the same customer within a short timeframe.
  - **Recommended value:** 24-48 hours (to allow time for manual review without constant re-alerting).
  - **Merchant scenario / example:** If a customer attempts multiple fraudulent orders within an hour, this prevents you from receiving an alert for each attempt, consolidating it to one initial alert.
- **CDKEYS\_EXPORT\_MASK\_CODES:**

  - **What this setting does:** When exporting CD key data, this setting determines if the actual key codes should be masked (hidden) for security reasons.
  - **Effect of changing this setting:**
    - *When enabled:* Exported data will show masked codes (e.g., `*****`).
    - *When disabled:* Exported data will show the full, unmasked key codes.
  - **Recommended value:** YES (for security, especially if sharing export files).
  - **Merchant scenario / example:** If you need to share a list of used keys with a supplier but don’t want to expose the actual key values, enable masking.

### 2.2 Dedicated Admin Screens & Controller Views

The module adds several new sections to your PrestaShop Back Office menu, typically under a main “CD Keys” or “Licenses” tab.

#### 2.2.1 CD Keys > Groups (AdminCdKeysGroupsController)

- **Screen Name & Menu Location:** **Back Office > CD Keys > Groups**
- **Purpose:** This screen allows you to create and manage groups of CD keys. A group is essentially a pool of keys that can be assigned to one or more products. This is crucial for managing your key inventory.
- **Available Actions & Settings:**
  - **Add new group:** Create a new group with a name (e.g., “Windows 11 Pro Keys”, “Game X Deluxe Edition”).
  - **Edit group:** Modify the name of an existing group.
  - **Delete group:** Remove a group (ensure no active products are linked to it and no keys are assigned).
  - **View keys in group:** Navigate directly to the list of keys associated with a specific group.
- **Effect of changes:**
  - Creating a group allows you to categorize your keys and link them to products.
  - Deleting a group will remove its association with products and keys, potentially causing issues if keys are still needed.
- **Recommended workflow for daily store management:**
  1. Before importing any keys, create a group for each distinct product or version of a product that requires a key.
  2. Assign the appropriate group to your products (this is done on the product edit page, under the “Modules” tab or a dedicated “CD Keys” tab added by the module).

#### 2.2.2 CD Keys > List (AdminCdKeysListController)

- **Screen Name & Menu Location:** **Back Office > CD Keys > List**
- **Purpose:** This is your central inventory for all individual CD keys. Here you can import, view, and manage the status of each key.
- **Available Actions & Settings:**
  - **Import CSV:** Upload a CSV file containing your keys. You’ll specify the group to which these keys belong during the import process.
  - **Add new key:** Manually add a single key, assign it to a group, and set its status (e.g., “Available”, “Used”).
  - **Edit key:** Modify an existing key’s value, group, or status.
  - **Delete key:** Remove a key from the inventory.
  - **Filter/Search:** Find specific keys by value, group, or status.
  - **Export:** Export your key inventory (with optional masking).
- **Effect of changes:**
  - Importing keys populates your inventory, making them available for sale.
  - Changing a key’s status (e.g., to “Used”) prevents it from being assigned to new orders.
  - Deleting a key removes it permanently.
- **Recommended workflow for daily store management:**
  1. Regularly import new batches of keys from your suppliers into their respective groups.
  2. Monitor the “Used” status to ensure keys are being assigned correctly.
  3. If a customer reports an issue with a key, you can find it here, verify its status, and potentially assign a new one.

#### 2.2.3 CD Keys > Archive (AdminCdKeysArchiveController)

- **Screen Name & Menu Location:** **Back Office > CD Keys > Archive**
- **Purpose:** This screen provides a historical record of all CD keys that have been assigned to customer orders. It acts as an audit log for key distribution.
- **Available Actions & Settings:**
  - **View assigned keys:** See which key was assigned to which order, for which product, and to which customer.
  - **Filter/Search:** Find specific archived keys by order ID, customer name, product, or key value.
  - **Resend email:** Option to resend the CD key email to the customer (useful if they claim not to have received it).
- **Effect of changes:** This screen is primarily for viewing and auditing. Actions here do not change the status of keys in the “List” section but allow for customer support actions like resending emails.
- **Recommended workflow for daily store management:**
  1. Use this screen to quickly look up a customer’s purchased keys if they contact support.
  2. Verify that keys were sent correctly for specific orders.
  3. Resend keys if a customer’s email was lost or accidentally deleted.

#### 2.2.4 Product Edit Page (Back Office > Catalog > Products > Edit Product)

- **Screen Name & Menu Location:** When editing a product, look for a new tab or section related to “CD Keys” or “Modules”.
- **Purpose:** This is where you link a specific product to a CD key group, marking it as a “CD Key product.”
- **Available Actions & Settings:**
  - **Enable CD Key for this product:** A toggle or checkbox to indicate that this product requires CD key delivery.
  - **Select CD Key Group:** A dropdown to choose which group of keys this product should draw from when an order is placed.
- **Effect of changes:**
  - *When enabled and a group is selected:* Any purchase of this product will automatically trigger the module to assign an available key from the chosen group and send it to the customer.
  - *When disabled:* The product will be treated as a regular PrestaShop product, and no keys will be assigned or sent.
- **Recommended workflow for daily store management:**
  1. For every digital product you sell that requires a unique key, navigate to its edit page.
  2. Enable the CD Key option and select the correct key group you created earlier.
  3. Ensure you have enough keys in the selected group to cover potential sales.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration** | Enabled | YES | Master switch for module functionality. |
|  | Select order states | Payment accepted | Triggers key delivery when order reaches this status. |
|  | Groups of customers permitted to receive cdkey | Customer, Guest | Restricts key delivery to specified customer groups. |
|  | Maximum order value | Empty (no limit) | Sets a value cap for automatic key delivery (fraud prevention). |
|  | Send many codes in one mail | YES | Bundles multiple keys for same product into one email. |
|  | Title of email | Your CD Keys from [Shop Name] | Customizes the subject line of key delivery emails. |
|  | Change order status | YES | Automatically updates order status after key delivery. |
|  | Select order state (for status change) | “CD Keys Sent” (custom) | The specific status to apply after keys are sent. |
|  | Include keys to invoice | YES | Prints delivered keys on the customer’s PDF invoice. |
|  | Turn on pagination | YES | Enables pagination for “My Keys” in customer account. |
|  | Pagination number of items | 10-20 | Number of keys displayed per page in “My Keys”. |
|  | CSV file row delimiter | `\n` | Character separating rows in CSV key import. |
|  | CSV file column delimiter | `;` or `,` | Character separating columns in CSV key import. |
|  | CDKEYS\_EXPORT\_MASK\_CODES | YES | Masks key codes in export files for security. |
| **CD Keys > Groups** | Add/Edit Group Name | N/A | Manages categories/pools of keys. |
| **CD Keys > List** | Import CSV | N/A | Bulk uploads keys into groups. |
|  | Add/Edit Key | N/A | Manually manages individual key values and status. |
| **CD Keys > Archive** | Resend Email | N/A | Resends key delivery email for a specific order. |
| **Product Edit Page** | Enable CD Key for this product | YES | Marks a product as requiring CD key delivery. |
|  | Select CD Key Group | (Specific Group) | Links product to a pool of keys for fulfillment. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving their CD keys. What should I check first?**
A1:

1. **Module Enabled?** Go to `Modules > Module Manager > Sell CDKeys / License keys` and ensure the module is “Enabled”.
2. **Order Status:** Check your module configuration under “Select order states”. Is the current status of the customer’s order (e.g., “Payment accepted”) selected in this list?
3. **Product Linked to Group:** On the product edit page (`Catalog > Products > Edit Product`), ensure the “Enable CD Key for this product” is checked and the correct “CD Key Group” is selected.
4. **Keys in Group:** Go to `CD Keys > List` and check if there are available (unused) keys in the group assigned to the product. If not, import more keys.
5. **Customer Group:** Verify the customer’s group is allowed to receive keys under “Groups of customers permitted to receive cdkey” in the module configuration.
6. **Email Configuration:** Check your PrestaShop email settings (`Advanced Parameters > E-mail`) to ensure emails are being sent correctly from your store. Also, ask the customer to check their spam/junk folder.

**Q2: I imported a CSV file, but the keys aren’t showing up or are incorrect.**
A2:

1. **Delimiter Settings:** Double-check your “CSV file row delimiter” and “CSV file column delimiter” settings in the module configuration. These must exactly match how your CSV file is structured. Common issues are using comma (`,`) instead of semicolon (`;`) or vice-versa.
2. **File Format:** Ensure your CSV file is plain text, not an Excel file saved as CSV with complex formatting.
3. **Target Group:** Did you select the correct CD Key Group during the import process?

**Q3: The “My Keys” section is not appearing in the customer’s account.**
A3:

1. **Module Enabled:** Ensure the module is active.
2. **Theme Compatibility:** While the module uses standard PrestaShop hooks, some heavily customized themes might override the default `displayCustomerAccount` hook. Check if your theme has modified this area. If so, you might need minor theme adjustments (refer to Section 7.6 for hook templates).
3. **Cache:** Clear your PrestaShop cache (`Advanced Parameters > Performance > Clear cache`).

**Q4: How do I create a new order status like “CD Keys Sent”?**
A4:

1. Go to `Shop Parameters > Order Settings > Statuses`.
2. Click “Add new order status”.
3. Give it a clear name (e.g., “CD Keys Sent”).
4. Choose a distinct color (e.g., light blue) to easily identify it in your order list.
5. Ensure “Consider the associated order as validated” is checked if you want it to count as a completed order.
6. Save the new status, then go back to the module configuration to select it for “Select order state (for status change)”.

**Q5: Can I manually assign a key to an order or customer?**
A5: The module primarily automates this. If you need to manually assign a key (e.g., for a replacement), you would typically:

1. Go to `CD Keys > List`, find an available key, and note its value.
2. Go to the customer’s order (`Orders > Orders`), and add a private note with the key.
3. Manually email the key to the customer.
4. Then, go back to `CD Keys > List`, find that key, and manually change its status to “Used” to prevent it from being assigned again.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the “Sell CDKeys / License keys” module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The module follows a standard PrestaShop MVC (Model-View-Controller) pattern. It extends `Module` for its core functionality and `AdminController` for its Back Office interfaces. It leverages PrestaShop’s `ObjectModel` for managing CD key groups, individual keys, and their usage history. Key delivery is primarily event-driven, triggered by `actionOrderStatusPostUpdate` and `actionOrderStatusUpdate` hooks. Front-office interaction is minimal, mainly providing a customer-facing “My Keys” section.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

- `controllers/front/index.php`:
  - **Class Name:** `CdkeysIndexModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Likely a placeholder or a redirect controller. In many modules, `index.php` in the front controller directory might handle default routing or simply redirect to a more specific controller.
- `controllers/front/mykeys.php`:
  - **Class Name:** `CdkeysMykeysModuleFrontController` (extends `ModuleFrontController`)
  - **Responsibility:** Handles the display of the customer’s purchased CD keys in their “My Account” section. It fetches `cdkey_used` records associated with the current customer, applies pagination if enabled, and renders `views/templates/front/mykeys.tpl`.

#### Back-Office Admin Controllers

- `controllers/admin/AdminCdKeysArchiveController.php`:
  - **Tab Name:** CD Keys > Archive
  - **Managed Entity:** `cdkey_used` (records of assigned keys)
  - **Responsibility:** Provides a list management interface for all CD keys that have been assigned to orders. It allows viewing, filtering, and potentially resending key emails. It uses `HelperList` for its display.
- `controllers/admin/AdminCdKeysGroupsController.php`:
  - **Tab Name:** CD Keys > Groups
  - **Managed Entity:** `cdkey_group`
  - **Responsibility:** Manages the creation, editing, and deletion of CD key groups. These groups act as categories for your keys and are linked to products. It uses `HelperList` and `HelperForm` for its interfaces.
- `controllers/admin/AdminCdKeysListController.php`:
  - **Tab Name:** CD Keys > List
  - **Managed Entity:** `cdkey`
  - **Responsibility:** Manages the inventory of individual CD keys. This includes importing CSV files, adding/editing/deleting keys, and viewing their status (available, used). It uses `HelperList` and `HelperForm`.
- `controllers/admin/index.php`:
  - **Tab Name:** CD Keys (Main Dashboard)
  - **Managed Entity:** N/A (Dashboard)
  - **Responsibility:** This likely serves as the main dashboard for the module, displaying analytics, key statistics, and potentially fraud alerts. It aggregates data from `cdkey_used` and `cdkey` tables.

### 4.3 Core Classes & Models (`classes/`)

The module dossier indicates no explicit `classes/` directory. This suggests that the primary `ObjectModel` definitions and core business logic are likely encapsulated within the main `cdkeys.php` file itself, or within the respective controller files.

If `ObjectModel` definitions are present in `cdkeys.php`, they would typically look like:

- `CdKeyGroup` (for `ps_cdkey_group` table): Manages key groups.
  - `$definition` would include `id_cdkey_group`, `name`.
- `CdKey` (for `ps_cdkey` table): Manages individual keys.
  - `$definition` would include `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (e.g., ‘available’, ‘used’).
- `CdKeyUsed` (for `ps_cdkey_used` table): Manages assigned keys.
  - `$definition` would include `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add`.

### 4.4 JavaScript Assets (`views/js/`)

- `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Manages the UI for creating, editing, and selecting email templates within the module’s configuration. It likely handles AJAX calls to save template content, preview emails, and switch between different template versions.
- `cdkeys/lib/searchTool/views/js/autocomplete.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Provides autocomplete functionality for search fields within the module’s admin interfaces (e.g., searching for products, customers, or key groups). It binds to input fields and makes AJAX requests to fetch suggestions.
- `cdkeys/views/js/adminCdKeysDashboard.js`:
  - **Scope:** Back-office (AdminCdKeysDashboardController or main module dashboard).
  - **Responsibility:** Powers the interactive elements of the module’s main dashboard. This could include chart rendering (e.g., using Chart.js or similar library), data filtering, and dynamic updates of statistics.
- `cdkeys/views/js/cdkeys-dashboard-demo-console.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Likely a development/debug script or a demo console for the dashboard, possibly logging events or providing test data. Should not be active in production.
- `cdkeys/views/js/cdkeys-fraud-demo-console.js`:
  - **Scope:** Back-office.
  - **Responsibility:** Similar to the dashboard demo console, this is probably a development/debug script for the fraud detection features. Should not be active in production.
- `cdkeys/views/js/cdkeys-pagination.js`:
  - **Scope:** Front-office (`mykeys.tpl`).
  - **Responsibility:** Handles the client-side logic for pagination in the customer’s “My Keys” section. This might involve AJAX calls to load new pages of keys without a full page reload, or simply managing the display of page numbers and navigation.

### 4.5 CSS Stylesheets (`views/css/`)

- `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css`:
  - **Scope:** Back-office.
  - **Main UI components:** Styles the email template management interface, including forms, buttons, and preview areas.
  - **Key CSS class selectors:** `.email-template-manager`, `.template-form`, `.template-preview`.
- `cdkeys/lib/searchTool/views/css/autocomplete.css`:
  - **Scope:** Back-office.
  - **Main UI components:** Styles the autocomplete dropdowns and input fields.
  - **Key CSS class selectors:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `cdkeys/views/css/admin_cdkeys.css`:
  - **Scope:** Back-office.
  - **Main UI components:** General styling for the module’s admin pages, including lists, forms, and dashboard elements.
  - **Key CSS class selectors:** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
- `cdkeys/views/css/cdkeys-admin.css`:
  - **Scope:** Back-office.
  - **Main UI components:** Additional or specific styling for admin interfaces, potentially overriding or extending `admin_cdkeys.css`.
  - **Key CSS class selectors:** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
- `cdkeys/views/css/css.css`:
  - **Scope:** Potentially both Front-office and Back-office, or general utility styles.
  - **Main UI components:** Could contain basic styles for elements used across different parts of the module.
  - **Key CSS class selectors:** Generic classes that might be applied to various module elements.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

- `cdkeys/views/templates/hook/adminOrder.tpl`:
  - **Hook:** `displayAdminOrder`
  - **Output:** Displays CD key information directly within the PrestaShop Back Office order detail page. This allows administrators to quickly see which keys were assigned to an order.
- `cdkeys/views/templates/hook/adminOrderFraud.tpl`:
  - **Hook:** `displayAdminOrderTop` (or similar, potentially `displayAdminOrder`)
  - **Output:** Displays fraud-related information or alerts for an order on the Back Office order detail page.
- `cdkeys/views/templates/hook/my-account-16.tpl`:
  - **Hook:** `displayCustomerAccount` (for PrestaShop 1.6.x)
  - **Output:** Adds a link or block to the customer’s “My Account” page, directing them to their “My Keys” section.
- `cdkeys/views/templates/hook/my-account-17.tpl`:
  - **Hook:** `displayCustomerAccount` (for PrestaShop 1.7.x, 8.x, 9.x)
  - **Output:** Similar to `my-account-16.tpl`, but adapted for the different template structure of newer PrestaShop versions, adding a link to the “My Keys” section.
- `cdkeys/views/templates/hook/orderDetailDisplayed.tpl`:
  - **Hook:** `displayOrderDetailDisplayed`
  - **Output:** Displays CD key information on the customer’s front-office order detail page.

#### Admin templates (`views/templates/admin/`)

- `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl`:
  - **Purpose:** Renders buttons or controls for the email template manager.
- `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl`:
  - **Purpose:** Renders the form for creating new email templates.
- `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl`:
  - **Purpose:** Renders the form for editing existing email templates.
- `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl`:
  - **Purpose:** The main container or form for the email template management interface.
- `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl`:
  - **Purpose:** Renders a select dropdown input, likely for choosing email templates or languages.
- `cdkeys/lib/searchTool/views/scripts.tpl`:
  - **Purpose:** Includes JavaScript scripts for the search tool/autocomplete functionality.
- `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl`:
  - **Purpose:** Renders a specific action button (e.g., “Resend Email”) within a `HelperList` table in the admin controllers (e.g., `AdminCdKeysArchiveController`).
- `cdkeys/views/templates/admin/customerGroups.tpl`:
  - **Purpose:** Renders the customer group selection interface in the module’s configuration.
- `cdkeys/views/templates/admin/getCombinations.tpl`:
  - **Purpose:** Potentially used for displaying or selecting product combinations related to CD keys (e.g., if different combinations require different key groups).
- `cdkeys/views/templates/admin/orderstates.tpl`:
  - **Purpose:** Renders the multi-select dropdown for “Select order states” in the module’s configuration.
- `cdkeys/views/templates/admin/orderstatesRadio.tpl`:
  - **Purpose:** Renders the radio button selection for “Select order state” (for status change) in the module’s configuration.
- `cdkeys/views/templates/admin/script.tpl`:
  - **Purpose:** General script inclusion for admin pages, possibly for module-specific JS.

#### Front-office templates (`views/templates/front/`)

- `cdkeys/views/templates/front/mykeys.tpl`:
  - **Purpose:** The main template for displaying the customer’s list of purchased CD keys in their “My Account” section. It will iterate through `cdkey_used` data and present the keys, order details, and potentially pagination controls.

#### Email templates (`views/templates/email/`)

- `cdkeys/views/templates/email/multikey-instance.tpl`:
  - **Purpose:** This is the core template for the email sent to customers containing their CD keys. It will dynamically populate with the customer’s name, order details, and the actual key(s).

### 4.7 Database Schema & Hooks Map

#### Database Tables

- `ps_cdkey_group`: Stores information about CD key groups.
  - `id_cdkey_group` (PK)
  - `name`
  - `date_add`
  - `date_upd`
- `ps_cdkey`: Stores individual CD keys.
  - `id_cdkey` (PK)
  - `id_cdkey_group` (FK to `ps_cdkey_group`)
  - `key_value` (the actual CD key string)
  - `status` (e.g., ‘available’, ‘used’)
  - `date_add`
  - `date_upd`
- `ps_cdkey_used`: Stores records of CD keys assigned to orders.
  - `id_cdkey_used` (PK)
  - `id_cdkey` (FK to `ps_cdkey`)
  - `id_order` (FK to `ps_orders`)
  - `id_customer` (FK to `ps_customer`)
  - `id_product` (FK to `ps_product`)
  - `date_add`

#### Configuration Records (`ps_configuration`)

- `CDKEYS_ENABLED`: (bool) Master switch.
- `CDKEYS_OSTATES`: (string) Comma-separated list of order states for key delivery.
- `CDKEYS_GROUPS`: (string) Comma-separated list of customer groups for key delivery.
- `CDKEYS_MAX_ORDERTOTAL`: (float) Maximum order value for auto-delivery.
- `CDKEY_HOWDELIVER`: (bool) Send many codes in one mail.
- `CDKEYS_MULTITITLE`: (string) Email subject title.
- `CDKEY_STATUSCHANGE`: (bool) Change order status after delivery.
- `CDKEYS_OSTATES_RADIO`: (int) ID of the order state to change to.
- `CDKEY_INC_INV`: (bool) Include keys on invoice.
- `CDKEY_PAGINATION`: (bool) Enable pagination for My Keys.
- `CDKEY_PAGINATION_NB`: (int) Items per page for My Keys pagination.
- `IV_ROW_DELIMITER`: (string) CSV row delimiter.
- `IV_COL_DELIMITER`: (string) CSV column delimiter.
- `CDKEYS_ANALYTICS_*`: Various settings for dashboard analytics.
- `CDKEYS_ALERT_COOLDOWN_HOURS`: (int) Cooldown for fraud alerts.
- `CDKEYS_EXPORT_MASK_CODES`: (bool) Mask codes on export.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | After an order’s status has been updated (and saved). | Primary trigger for CD key delivery. Checks if the new status matches configured states and sends keys. |
| `displayAdminOrder` | Renders content within the Back Office order detail page. | Displays assigned CD keys for the current order in the admin panel. |
| `ActionAdminControllerSetMedia` | When an admin controller is initialized and media (JS/CSS) is being set. | Injects module-specific JS and CSS files into the Back Office for admin controllers. |
| `displayCustomerAccount` | Renders content in the customer’s “My Account” page. | Adds a link or block for “My Keys” in the customer’s front office account. |
| `DisplayAdminOrderTop` | Renders content at the top of the Back Office order detail page. | Potentially used for displaying fraud alerts or summary information related to CD keys for the order. |
| `actionOrderStatusUpdate` | Before an order’s status is updated (older hook, `actionOrderStatusPostUpdate` is preferred). | Secondary or fallback trigger for CD key delivery, ensuring compatibility with older PrestaShop versions or specific scenarios. |
| `DisplayBackOfficeHeader` | Renders content in the header of all Back Office pages. | Injects global Back Office JS/CSS or menu items for the module. |
| `displayHeader` | Renders content in the `<head>` section of front-office pages. | Injects front-office specific JS/CSS or meta tags. |
| `displayOrderDetailDisplayed` | Renders content within the customer’s front-office order detail page. | Displays assigned CD keys directly on the customer’s order summary page. |
| `actionOrderHistoryAddAfter` | After an order history entry (status change) has been added. | Could be used as an alternative trigger for key delivery or for logging purposes related to status changes. |

## 5. Official Support & Updates

For the latest module updates, bug fixes, and official support, please log in to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). You will find access to your purchased modules and dedicated support channels there.
