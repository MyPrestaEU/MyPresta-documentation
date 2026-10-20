---
title: "GPSR Enterprise - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the GPSR Enterprise PrestaShop module by MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy GPSR Enterprise Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Requirements & Compatibility

*   **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
*   **PHP Compatibility**: PHP 7.1 - 8.5
*   **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL) are required and typically available on most modern hosting environments.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The GPSR Enterprise module offers a comprehensive set of configuration options, spread across its main configuration page and several dedicated administration screens.

### 2.1 Module Configuration Page (Back Office > Modules > Module Manager > GPSR Enterprise > Configure)

This is the main configuration screen for the module, where you control its general behavior and front-office display.

*   **Module enabled**
    *   **What this setting does:** This is the master switch for the entire GPSR Enterprise module.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* The module will be active, displaying GPSR information on product pages, allowing you to manage entities, warnings, and mappings, and enabling the API and cron jobs.
        *   *When disabled (No):* The module will be completely inactive. No GPSR information will be shown on the front office, and backend management features will be unavailable or non-functional.
    *   **Recommended value:** **Yes** (to utilize the module's features).
    *   **Merchant scenario / example:** If you are setting up the module for the first time, keep it disabled until all configurations are complete, then enable it to go live.

*   **Storefront theme profile**
    *   **What this setting does:** Allows you to select the visual styling profile for the GPSR information block on your product pages, optimized for different PrestaShop themes.
    *   **Effect of changing this setting:**
        *   *When set to 'Classic':* The module will use styling optimized for the default PrestaShop Classic theme (and many compatible themes).
        *   *When set to 'Hummingbird':* The module will use styling optimized for the newer PrestaShop Hummingbird theme (PrestaShop 8.1+).
    *   **Recommended value:** Select the profile that best matches your current PrestaShop theme. If you're unsure, try 'Classic' first.
    *   **Merchant scenario / example:** If your store uses PrestaShop 8.1+ with the default theme, choose 'Hummingbird' for the best visual integration. If you're on PrestaShop 1.7 or 8.0 with the Classic theme, choose 'Classic'.

*   **Display mode**
    *   **What this setting does:** Controls how the GPSR information block is presented on the product page.
    *   **Effect of changing this setting:**
        *   *Options vary (e.g., 'Tab', 'Accordion', 'Block'):*
            *   **Tab:** The GPSR information will appear as a new tab alongside "Description," "Product Details," etc.
            *   **Accordion:** The information will be presented in an expandable/collapsible accordion section.
            *   **Block:** The information will be displayed as a static block within the product page content flow.
    *   **Recommended value:** **Tab** or **Accordion** for a cleaner product page layout, especially if you have a lot of information.
    *   **Merchant scenario / example:** If your product pages are already very long, using a 'Tab' or 'Accordion' mode keeps the page tidy while still making the information accessible.

*   **Visual style**
    *   **What this setting does:** Defines the overall aesthetic of the GPSR information block.
    *   **Effect of changing this setting:**
        *   *Options vary (e.g., 'Default', 'Minimal', 'Detailed'):* This will change the visual density, use of icons, and general presentation of the information.
    *   **Recommended value:** **Default** or **Minimal** for a clean look. Experiment to see what fits your theme best.
    *   **Merchant scenario / example:** If your theme is very minimalist, choosing a 'Minimal' visual style for the GPSR block will ensure better integration.

*   **Show block title**
    *   **What this setting does:** Determines whether a title is displayed above the GPSR information block on the product page.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* The text specified in "Block title text" will appear as a heading.
        *   *When disabled (No):* No title will be displayed, making the block blend more seamlessly or rely on context.
    *   **Recommended value:** **Yes** for clarity, so customers immediately understand what the block contains.
    *   **Merchant scenario / example:** Enabling this with a title like "Product Safety Information" makes it clear to customers what they are viewing.

*   **Block title text**
    *   **What this setting does:** Allows you to customize the title of the GPSR information block. This setting only applies if "Show block title" is enabled.
    *   **Effect of changing this setting:** The text you enter here will be displayed as the heading for the GPSR information block on the product page.
    *   **Recommended value:** A clear, descriptive title like "Product Safety & Compliance," "EU Safety Information," or "Product Passport Details."
    *   **Merchant scenario / example:** You can set this to "EU Product Safety Information" to clearly communicate the purpose of the block to your European customers.

*   **Hide block when data is incomplete**
    *   **What this setting does:** Controls whether the GPSR information block is displayed on the product page if not all required data (manufacturer, EU responsible person, warnings, documents) has been fully configured for that product.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* If any GPSR data is missing for a product, the entire block will not be shown on the front office. This prevents displaying incomplete or misleading information.
        *   *When disabled (No):* The block will always be displayed, even if some sections are empty. This might show a partially filled block, which could be confusing.
    *   **Recommended value:** **Yes** to maintain a professional appearance and avoid showing half-empty sections.
    *   **Merchant scenario / example:** You're still in the process of adding GPSR data to all your products. Enabling this ensures that only fully compliant product pages display the block, preventing customer confusion on products still being updated.

*   **Show manufacturer entity**
    *   **What this setting does:** Determines if the manufacturer's GPSR entity details are displayed in the front-office block.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* The manufacturer's name, address, and other configured details will be visible.
        *   *When disabled (No):* The manufacturer section will be hidden.
    *   **Recommended value:** **Yes** as this is a core GPSR requirement.
    *   **Merchant scenario / example:** To fully comply with GPSR, you must show the manufacturer's details. Keep this enabled.

*   **Show EU responsible person**
    *   **What this setting does:** Determines if the EU responsible person's GPSR entity details are displayed in the front-office block.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* The EU responsible person's name, address, and other configured details will be visible.
        *   *When disabled (No):* The EU responsible person section will be hidden.
    *   **Recommended value:** **Yes** as this is a core GPSR requirement for products sold in the EU.
    *   **Merchant scenario / example:** If your products require an EU responsible person, enabling this ensures their details are shown.

*   **Show safety warnings**
    *   **What this setting does:** Determines if any associated safety warnings are displayed in the front-office block.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* Configured safety warnings for the product will be visible.
        *   *When disabled (No):* The safety warnings section will be hidden.
    *   **Recommended value:** **Yes** to inform customers of potential hazards.
    *   **Merchant scenario / example:** For products with specific safety instructions (e.g., "Keep out of reach of children"), enabling this ensures these warnings are prominently displayed.

*   **Show linked documents**
    *   **What this setting does:** Determines if links to associated documents (like manuals, declarations) are displayed in the front-office block.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* Links to uploaded documents will be visible.
        *   *When disabled (No):* The linked documents section will be hidden.
    *   **Recommended value:** **Yes** to provide customers with essential product documentation.
    *   **Merchant scenario / example:** If you need to provide a "Declaration of Conformity" or a detailed user manual, enabling this allows customers to easily access these files.

*   **Show product passport button**
    *   **What this setting does:** Controls the visibility of the "Download Product Passport" button on the product page.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* A button will appear, allowing customers to download a PDF containing all GPSR information for the product.
        *   *When disabled (No):* The button will not be shown.
    *   **Recommended value:** **Yes** as the product passport is a key GPSR feature.
    *   **Merchant scenario / example:** To offer customers a comprehensive, downloadable summary of all safety and compliance information, keep this enabled.

*   **Share mappings across all shops**
    *   **What this setting does:** (Only visible in a multi-store setup) Determines if GPSR mappings (how entities, warnings, and documents are assigned to products, categories, or manufacturers) are shared across all your PrestaShop stores.
    *   **Effect of changing this setting:**
        *   *When enabled (Yes):* All GPSR mappings you create will apply to all shops in your multi-store environment. This simplifies management if your product catalog and compliance needs are similar across stores.
        *   *When disabled (No):* Each shop will have its own independent set of GPSR mappings, allowing for shop-specific compliance configurations.
    *   **Recommended value:** **Yes** if your compliance needs are consistent across stores; otherwise, **No**.
    *   **Merchant scenario / example:** If you run multiple country-specific stores but sell the same products with the same compliance requirements, enabling this saves a lot of time by managing mappings once.

*   **Action when enabling share**
    *   **What this setting does:** (Only visible in a multi-store setup, appears when "Share mappings across all shops" is enabled) Defines what happens to existing shop-specific mappings when you switch to shared mappings.
    *   **Effect of changing this setting:**
        *   *Options vary (e.g., 'Merge', 'Overwrite', 'Keep current shop'):*
            *   **Merge:** Attempts to combine existing mappings from all shops into a single shared set.
            *   **Overwrite:** Replaces all existing shop-specific mappings with the mappings from the currently active shop.
            *   **Keep current shop:** Uses the mappings from the currently active shop as the shared mappings, discarding others.
    *   **Recommended value:** Choose carefully based on your data. **Backup your database** before changing this!
    *   **Merchant scenario / example:** If you've been managing GPSR data separately for each shop and now want to centralize, you'll need to decide if you want to combine all data, or if one shop's data should become the master.

*   **Action when disabling share**
    *   **What this setting does:** (Only visible in a multi-store setup, appears when "Share mappings across all shops" is disabled) Defines what happens to the shared mappings when you switch back to shop-specific mappings.
    *   **Effect of changing this setting:**
        *   *Options vary (e.g., 'Duplicate to all shops', 'Keep only for current shop'):*
            *   **Duplicate to all shops:** The current shared mappings are copied to each individual shop, allowing them to be edited independently afterward.
            *   **Keep only for current shop:** The shared mappings are assigned only to the currently active shop, and other shops will start with no GPSR mappings.
    *   **Recommended value:** Choose carefully based on your data. **Backup your database** before changing this!
    *   **Merchant scenario / example:** If you decide to move from shared mappings back to individual shop management, you need to decide if the shared data should be copied to all shops as a starting point, or if only the current shop should retain it.

*   **Custom CSS**
    *   **What this setting does:** Provides a text area where you can add custom CSS rules to further style the GPSR information block on your storefront.
    *   **Effect of changing this setting:** Any valid CSS code entered here will be applied to the GPSR module's front-office elements, allowing you to fine-tune colors, fonts, spacing, etc., to perfectly match your theme.
    *   **Recommended value:** Leave empty unless you have specific styling needs and are comfortable with CSS.
    *   **Merchant scenario / example:** Your theme uses a specific shade of blue for headings. You can add CSS here to ensure the GPSR block title also uses that exact blue, maintaining visual consistency.

### 2.2 Dedicated Admin Screens & Controller Views

The GPSR Enterprise module adds several new menu items under a main "GPSR Enterprise" menu in your PrestaShop Back Office. These screens are where you manage all the detailed compliance data.

#### 2.2.1 GPSR Enterprise Dashboard (Back Office > GPSR Enterprise > Dashboard)

This screen provides an overview of your GPSR compliance status and quick access to key management areas.

*   **Available Actions & Settings:**
    *   **Summary Statistics:** May show counts of configured entities, warnings, mapped products, etc.
    *   **Quick Links:** Buttons or links to jump directly to managing Entities, Warnings, Mappings, Documents, etc.
    *   **Cron Job Status:** Information about the last run and result of the GPSR cron job (for re-indexing or data synchronization).
    *   **API Token:** Displays your unique API token for external integrations.
    *   **Cron Token:** Displays your unique cron job token for secure execution.
*   **Effect of changes:** This screen is primarily for monitoring and navigation. Changes here (e.g., generating new API/Cron tokens) directly impact the security and functionality of external integrations and automated tasks.
*   **Recommended workflow for daily store management:** Check this dashboard periodically to monitor your compliance status and ensure cron jobs are running correctly.

#### 2.2.2 Entities (Back Office > GPSR Enterprise > Entities)

This screen is where you define and manage the "entities" required by GPSR, such as manufacturers and EU responsible persons.

*   **Available Actions & Settings:**
    *   **Entity List:** A table displaying all configured entities, with columns for name, type (Manufacturer, EU Responsible Person), address, contact, etc.
    *   **Add New Entity:** A button to create a new entity.
    *   **Edit/Delete:** Actions for each entity in the list.
    *   **Entity Form:** When adding/editing, you'll find fields for:
        *   **Name:** The official name of the entity.
        *   **Type:** Select whether it's a Manufacturer or an EU Responsible Person.
        *   **Address:** Full postal address.
        *   **Contact Information:** Email, phone, website.
        *   **Multilingual Fields:** Some fields may be translatable for different languages.
*   **Effect of changes:** Creating or updating entities here makes them available for selection when mapping GPSR data to products. Incorrect or incomplete entity data will lead to non-compliance.
*   **Recommended workflow for daily store management:** Before mapping products, ensure all your manufacturers and EU responsible persons are accurately entered here. Update details promptly if they change.

#### 2.2.3 Warnings (Back Office > GPSR Enterprise > Warnings)

This screen allows you to define and manage various safety warnings that can be associated with your products.

*   **Available Actions & Settings:**
    *   **Warning List:** A table displaying all created warnings, with columns for title, icon, and content.
    *   **Add New Warning:** A button to create a new warning.
    *   **Edit/Delete:** Actions for each warning in the list.
    *   **Warning Form:** When adding/editing, you'll find fields for:
        *   **Title:** A short, descriptive title for the warning.
        *   **Icon:** An option to select a visual icon to accompany the warning (e.g., a hazard symbol).
        *   **Content:** The full text of the safety warning (multilingual).
        *   **Severity/Type:** (If available) Categorize the warning.
*   **Effect of changes:** Warnings created here become available for selection when mapping GPSR data to products. They will then appear on the front-office product page.
*   **Recommended workflow for daily store management:** Create all necessary safety warnings here first. Ensure the content is accurate and legally compliant for all languages you support.

#### 2.2.4 Documents (Back Office > GPSR Enterprise > Documents)

This screen is for uploading and managing documents that need to be linked to products, such as declarations of conformity, user manuals, or safety data sheets.

*   **Available Actions & Settings:**
    *   **Document List:** A table displaying uploaded documents, with columns for name, file type, and associated products.
    *   **Upload New Document:** A button to upload a new file.
    *   **Edit/Delete:** Actions for each document.
    *   **Document Form:** When uploading/editing, you'll find fields for:
        *   **Name:** A descriptive name for the document (multilingual).
        *   **File Upload:** The actual file (e.g., PDF).
        *   **Type:** (If available) Categorize the document (e.g., "Manual," "Declaration").
*   **Effect of changes:** Uploaded documents become available for selection when mapping GPSR data to products. Links to these documents will appear on the front-office product page.
*   **Recommended workflow for daily store management:** Upload all relevant product documentation here. Ensure documents are up-to-date and correctly named for easy identification.

#### 2.2.5 Mappings (Back Office > GPSR Enterprise > Mappings)

This is the core of the module's automation, allowing you to define how GPSR data is assigned to products based on various criteria. This section likely contains several sub-sections for different mapping types.

*   **Available Actions & Settings:**
    *   **Global Mappings:** Apply GPSR data to all products by default.
    *   **Category Mappings:** Apply GPSR data to all products within a specific category.
    *   **Manufacturer Mappings:** Apply GPSR data to all products from a specific manufacturer.
    *   **Product/Combination Mappings:** Apply GPSR data to individual products or specific product combinations (variants).
    *   **Mapping Forms:** For each mapping type, you'll configure:
        *   **Assigned Manufacturer Entity:** Select an entity defined in the "Entities" section.
        *   **Assigned EU Responsible Person Entity:** Select an entity defined in the "Entities" section.
        *   **Assigned Warnings:** Select one or more warnings defined in the "Warnings" section.
        *   **Assigned Documents:** Select one or more documents uploaded in the "Documents" section.
        *   **Priority/Override Rules:** (If available) Define how mappings from different levels (global, category, manufacturer, product) interact and override each other.
*   **Effect of changes:** Changes here directly determine what GPSR information is displayed on your product pages. A well-structured mapping strategy significantly reduces manual work.
*   **Recommended workflow for daily store management:** Start with Global Mappings, then refine with Category and Manufacturer Mappings. Use Product/Combination Mappings only for exceptions or unique products. Regularly review your mappings, especially when adding new products or categories.

#### 2.2.6 Mass Actions (Back Office > GPSR Enterprise > Mass Actions)

This screen provides tools for applying GPSR data to multiple products at once, or for performing bulk operations.

*   **Available Actions & Settings:**
    *   **Product Grid:** A filterable and searchable list of products.
    *   **Bulk Assignment:** Select multiple products and then assign a Manufacturer Entity, EU Responsible Person, Warnings, or Documents to all selected products.
    *   **Bulk Removal:** Remove GPSR data from selected products.
    *   **Import/Export:** (If available) Tools to import GPSR data from a CSV file or export existing data.
*   **Effect of changes:** Mass actions can quickly update GPSR data for a large number of products, saving significant time. Use with caution, as changes are applied broadly.
*   **Recommended workflow for daily store management:** Use this after initial setup to quickly apply common GPSR data to large product sets. Also useful for updating data across many products if a regulation changes.

#### 2.2.7 Matcher (Back Office > GPSR Enterprise > Matcher)

This screen helps identify products that might be missing GPSR data or suggests potential mappings.

*   **Managed Table / Entity:** `gpsr_match_suggestion`
*   **Available Actions & Settings:**
    *   **Suggestion List:** Displays products or product groups that the module identifies as potentially needing GPSR data or having incomplete data.
    *   **Matching Rules:** (If available) Configure rules for how the module suggests matches (e.g., based on product name keywords, existing attributes).
    *   **Apply/Dismiss Suggestions:** Actions to either apply the suggested GPSR data or dismiss the suggestion.
*   **Effect of changes:** Applying suggestions will update GPSR data for the identified products. This helps ensure comprehensive compliance.
*   **Recommended workflow for daily store management:** Periodically check this screen to catch any products that might have slipped through your mapping strategy.

#### 2.2.8 Audit Log (Back Office > GPSR Enterprise > Audit Log)

This screen provides a historical record of changes made to GPSR data within the module.

*   **Managed Table / Entity:** `gpsr_audit_log`
*   **Available Actions & Settings:**
    *   **Log Grid:** A table displaying entries with details like:
        *   **Date/Time:** When the change occurred.
        *   **User:** Which administrator made the change.
        *   **Action:** What action was performed (e.g., "Entity created," "Product mapped," "Warning updated").
        *   **Details:** Specifics of the change.
*   **Effect of changes:** This screen is for auditing and monitoring. No direct changes to GPSR data are made here, but it provides a crucial record for accountability and troubleshooting.
*   **Recommended workflow for daily store management:** Use this log to review changes, especially if you have multiple administrators managing GPSR data, or if you need to troubleshoot why certain data is appearing (or not appearing) on the front office.

#### 2.2.9 Ledger (Back Office > GPSR Enterprise > Ledger)

This screen likely provides a more detailed, "silent" record of all GPSR data applied to products, potentially including historical versions or a comprehensive overview for regulatory purposes.

*   **Available Actions & Settings:**
    *   **Product-centric View:** A way to view all GPSR data associated with a specific product, possibly including how it was derived (e.g., from a category mapping, or directly assigned).
    *   **Export Options:** (If available) Export the full ledger for external review or archiving.
*   **Effect of changes:** This screen is primarily for reporting and detailed review. It doesn't directly change front-office data but provides the underlying compliance record.
*   **Recommended workflow for daily store management:** Use this for in-depth compliance checks or when preparing for regulatory audits.

#### 2.2.10 API (Back Office > GPSR Enterprise > API)

This screen provides information and settings related to the module's API for external integrations.

*   **Available Actions & Settings:**
    *   **API Token:** Displays the unique token required to authenticate API requests.
    *   **Generate New Token:** A button to generate a new API token (useful for security if a token is compromised).
    *   **API Documentation Link:** A link to technical documentation for developers on how to use the API.
*   **Effect of changes:** Generating a new token will invalidate the old one, requiring any external systems using the API to be updated with the new token.
*   **Recommended workflow for daily store management:** Only access this if you are integrating the GPSR module with external systems (e.g., ERP, PIM). Keep your API token secure.

#### 2.2.11 Cron (Back Office > GPSR Enterprise > Cron)

This screen manages the module's scheduled tasks, such as re-indexing GPSR data or synchronizing information.

*   **Available Actions & Settings:**
    *   **Cron Job URL:** The URL to trigger the cron job externally (e.g., via your hosting provider's cron service).
    *   **Cron Token:** The unique token for secure cron job execution.
    *   **Enable/Disable Cron:** A switch to activate or deactivate the cron job.
    *   **Last Run/Result:** Information about the last time the cron job ran and its outcome.
    *   **Re-index Settings:** Options for how often and how many products to re-index per run (e.g., `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Effect of changes:** Enabling the cron job ensures that GPSR data is regularly processed and updated in the background, keeping your front-office information current. Incorrect cron settings can lead to outdated data or server load issues.
*   **Recommended workflow for daily store management:** Ensure the cron job is enabled and correctly configured on your hosting server to automate data processing. Monitor its status on the dashboard.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Module Configuration** | Module enabled | Yes | Master switch for module functionality. |
| | Storefront theme profile | Match your theme | Optimizes visual styling for Classic or Hummingbird themes. |
| | Display mode | Tab / Accordion | How GPSR block appears (Tab, Accordion, Block). |
| | Visual style | Default / Minimal | Aesthetic of the GPSR information block. |
| | Show block title | Yes | Displays a title above the GPSR block. |
| | Block title text | "Product Safety & Compliance" | Custom text for the block title. |
| | Hide block when data is incomplete | Yes | Prevents displaying incomplete GPSR information. |
| | Show manufacturer entity | Yes | Displays manufacturer details. |
| | Show EU responsible person | Yes | Displays EU responsible person details. |
| | Show safety warnings | Yes | Displays product safety warnings. |
| | Show linked documents | Yes | Displays links to product documents. |
| | Show product passport button | Yes | Displays button to download PDF product passport. |
| | Share mappings across all shops | Yes (if multi-store) | Centralizes GPSR mappings for multi-store. |
| | Action when enabling share | (Careful choice) | Defines data handling when enabling shared mappings. |
| | Action when disabling share | (Careful choice) | Defines data handling when disabling shared mappings. |
| | Custom CSS | Empty | Add custom CSS for front-office styling. |
| **Entities** | Add/Edit Entity | N/A | Define manufacturers and EU responsible persons. |
| **Warnings** | Add/Edit Warning | N/A | Create and manage safety warnings. |
| **Documents** | Upload/Manage Document | N/A | Upload and link product-related documents. |
| **Mappings** | Global/Category/Manufacturer/Product Mappings | N/A | Assign GPSR data based on product criteria. |
| **Mass Actions** | Bulk Assignment/Removal | N/A | Apply/remove GPSR data for multiple products. |
| **Matcher** | Review Suggestions | N/A | Identifies products needing GPSR data. |
| **Audit Log** | View Log | N/A | Tracks changes made to GPSR data. |
| **Ledger** | View/Export Data | N/A | Comprehensive record of product GPSR data. |
| **API** | API Token, Generate New Token | N/A | Manage API access for external integrations. |
| **Cron** | Cron Job URL, Enable/Disable | Enabled | Automates background GPSR data processing. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: I've configured everything, but the GPSR block isn't showing on my product pages.**
A:
1.  **Check "Module enabled":** Go to **Modules > Module Manager > GPSR Enterprise > Configure** and ensure "Module enabled" is set to "Yes".
2.  **Check "Hide block when data is incomplete":** If this is set to "Yes," the block won't show if any required data (manufacturer, EU responsible person, warnings, documents) is missing for that specific product. Ensure the product has complete GPSR data assigned via mappings or direct product edits.
3.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click "Clear cache" (or "Clear Smarty cache" in older versions). Sometimes, old cached content prevents new module elements from appearing.
4.  **Theme Compatibility:** Ensure your "Storefront theme profile" setting matches your theme (Classic or Hummingbird). If you have a highly customized theme, there might be a CSS conflict. Try adding some custom CSS to force visibility or contact support.

**Q: My GPSR information block looks strange or misaligned on my website.**
A:
1.  **Theme Profile:** Double-check your "Storefront theme profile" setting in the module configuration. Make sure it's set to the correct profile for your PrestaShop theme (Classic or Hummingbird).
2.  **Custom CSS:** If you have custom CSS in your theme or in the module's "Custom CSS" field, it might be conflicting. Try temporarily removing custom CSS to see if the issue resolves.
3.  **Browser Cache:** Clear your browser's cache (Ctrl+F5 or Cmd+R) to ensure you're seeing the latest styling.
4.  **Contact Support:** If the issue persists, your theme might have unique styling that requires specific adjustments. Contact MyPresta.eu support with screenshots and your theme name.

**Q: How do I make sure my GPSR data is translated for international customers?**
A:
1.  **Multilingual Fields:** When creating **Entities** and **Warnings**, ensure you fill in the content for all languages enabled in your store. Look for language flags next to input fields.
2.  **PrestaShop Translations:** For the module's default phrases (like "Download Product Passport" or the block title), go to **International > Translations**, select "Installed modules translations," choose "GPSR Enterprise," and select your target language. Translate any missing phrases there.
3.  **Product Passport:** The generated PDF Product Passport will reflect the language of the product data and warnings you've entered.

**Q: The cron job doesn't seem to be running, or my data isn't updating automatically.**
A:
1.  **Cron Enabled:** In the module's **Cron** screen (Back Office > GPSR Enterprise > Cron), ensure the cron job is enabled.
2.  **Hosting Cron Setup:** Verify that you have correctly set up the cron job on your hosting server using the provided "Cron Job URL" and "Cron Token." This is usually done in your hosting control panel (cPanel, Plesk, etc.). The cron job needs to be triggered periodically (e.g., every hour).
3.  **Last Run Status:** Check the "Last Run" and "Last Result" on the Cron screen. If it shows errors or hasn't run recently, there's an issue with the cron setup or a server-side problem.
4.  **Server Logs:** Check your server's PHP error logs for any messages related to the cron job execution.

**Q: I made a mistake with a mass action and now many products have incorrect GPSR data.**
A:
1.  **Audit Log:** Immediately check the **Audit Log** (Back Office > GPSR Enterprise > Audit Log) to identify exactly what changes were made and by whom.
2.  **Reverse Manually/Via Mass Actions:** Depending on the extent of the error, you might need to use the **Mass Actions** screen again to correct the data, or manually edit individual product mappings if only a few were affected.
3.  **Database Backup:** If the error is severe and widespread, and you have a recent database backup from *before* the mistake, restoring that backup might be the quickest solution. This is why regular backups are crucial.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical structure of the GPSR Enterprise module, intended for developers, webmasters, and technical agencies.

### 4.1 Architecture Overview

The GPSR Enterprise module adheres to PrestaShop's MVC (Model-View-Controller) pattern, extending core functionalities and introducing custom entities. It leverages `ObjectModel` for database interactions, `ModuleFrontController` for front-office data delivery (API, cron, passport generation), and `AdminController` for comprehensive back-office management. The module heavily relies on hooks for integration into product pages and administrative interfaces, ensuring a non-intrusive yet powerful solution. Data mapping is hierarchical, allowing for global, category, manufacturer, and product-specific overrides.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

*   `controllers/front/api.php`
    *   **Class Name:** `GpsrEnterpriseApiModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** Handles API requests for GPSR data. Provides endpoints for external systems to query product safety information, entities, warnings, and documents. Requires authentication via `GPSR_API_TOKEN`. Returns JSON payloads.
*   `controllers/front/cron.php`
    *   **Class Name:** `GpsrEnterpriseCronModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** Serves as the endpoint for scheduled tasks (cron jobs). Triggers background processes like re-indexing GPSR data, synchronizing mappings, or performing data cleanup. Requires authentication via `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Class Name:** `GpsrEnterpriseDataModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** Provides AJAX endpoints for fetching GPSR data dynamically on the front-office product page. This controller likely retrieves the specific manufacturer, EU responsible person, warnings, and documents for a given product ID or combination ID.
*   `controllers/front/index.php`
    *   **Class Name:** `GpsrEnterpriseIndexModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** A placeholder or fallback front controller. Often used for basic module routing or to prevent directory listing.
*   `controllers/front/passport.php`
    *   **Class Name:** `GpsrEnterprisePassportModuleFrontController`
    *   **Parent Class:** `ModuleFrontController`
    *   **Responsibility:** Generates and serves the PDF Product Passport for a specified product. It gathers all relevant GPSR data for the product and renders it into a downloadable PDF document.

#### Back-Office Admin Controllers

All admin controllers extend `GpsrAdminController` (a custom base class within the module) which in turn extends `ModuleAdminController`.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Tab Name:** GPSR Enterprise > Audit Log
    *   **Managed Entity:** `GpsrAuditLogEntry`
    *   **Responsibility:** Manages the display and filtering of the `gpsr_audit_log` table, recording all significant changes made within the GPSR module.
*   `controllers/admin/AdminGpsrController.php`
    *   **Tab Name:** GPSR Enterprise (main entry point)
    *   **Responsibility:** Likely serves as the main dashboard or a redirect to the primary configuration/dashboard screen for the module.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Tab Name:** GPSR Enterprise > Documents
    *   **Managed Entity:** `GpsrDocument` (implied, as no specific class was listed, but it manages documents)
    *   **Responsibility:** Handles the upload, listing, and management of GPSR-related documents (e.g., PDFs).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Tab Name:** GPSR Enterprise > Dashboard (or main configuration)
    *   **Responsibility:** Manages the module's main configuration settings, including API/Cron tokens, global display options, and multi-shop sharing.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Tab Name:** GPSR Enterprise > Entities
    *   **Managed Entity:** `GpsrEntity`
    *   **Responsibility:** Manages the creation, editing, and deletion of GPSR entities (manufacturers, EU responsible persons).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Tab Name:** GPSR Enterprise > Ledger
    *   **Responsibility:** Provides a comprehensive view and management interface for the "silent ledger" of GPSR data associated with products, potentially including historical data.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Tab Name:** GPSR Enterprise > Mappings > Brands
    *   **Managed Entity:** `Manufacturer` (PrestaShop core)
    *   **Responsibility:** Manages GPSR data mappings based on PrestaShop manufacturers.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Tab Name:** GPSR Enterprise > Mappings > Categories
    *   **Managed Entity:** `Category` (PrestaShop core)
    *   **Responsibility:** Manages GPSR data mappings based on PrestaShop categories.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Tab Name:** GPSR Enterprise > Mappings > Combinations
    *   **Managed Entity:** `ProductCombination` (implied)
    *   **Responsibility:** Manages GPSR data mappings for specific product attribute combinations.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Tab Name:** GPSR Enterprise > Mappings > Global
    *   **Responsibility:** Manages global GPSR data mappings that apply as a default across all products.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Tab Name:** GPSR Enterprise > Mass Actions
    *   **Responsibility:** Provides tools for bulk assignment and removal of GPSR data to multiple products.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Tab Name:** GPSR Enterprise > Matcher
    *   **Managed Entity:** `GpsrMatchSuggestion`
    *   **Responsibility:** Manages suggestions for products that might need GPSR data or have incomplete mappings.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Tab Name:** GPSR Enterprise > Warnings
    *   **Managed Entity:** `GpsrWarning`
    *   **Responsibility:** Manages the creation, editing, and deletion of safety warnings.
*   `controllers/admin/index.php`
    *   **Responsibility:** Standard PrestaShop empty `index.php` file to prevent directory listing.

### 4.3 Core Classes & Models (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Responsibility:** A custom base class for all admin controllers within the GPSR module. It likely provides common methods, properties, and template variables used across the module's back-office interfaces, ensuring consistency and reducing code duplication.
*   `classes/GpsrAuditLogEntry.php`
    *   **Extends:** `ObjectModel`
    *   **Database Table:** `ps_gpsr_audit_log`
    *   **`$definition` fields:** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Key public methods:** Methods for logging audit entries, retrieving log data.
    *   **Business Logic:** Records every significant action performed within the GPSR module for auditing and compliance.
*   `classes/GpsrCompatibility.php`
    *   **Responsibility:** Handles compatibility layers for different PrestaShop versions (1.7.x, 8.x, 9.x). This class likely contains static methods to abstract away version-specific differences in API calls, hook names, or template rendering, ensuring the module works seamlessly across supported versions.
*   `classes/GpsrEntity.php`
    *   **Extends:** `ObjectModel`
    *   **Database Table:** `ps_gpsr_entity` (and `ps_gpsr_entity_lang` for multilingual fields)
    *   **`$definition` fields:** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (and multilingual fields like `name_lang`, `address_lang` etc.)
    *   **Key public methods:** Methods for CRUD operations on entities, retrieving entities by type, associating entities with products/mappings.
    *   **Business Logic:** Manages the data for manufacturers and EU responsible persons.
*   `classes/GpsrWarning.php`
    *   **Extends:** `ObjectModel`
    *   **Database Table:** `ps_gpsr_warning` (and `ps_gpsr_warning_lang` for multilingual fields)
    *   **`$definition` fields:** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (and multilingual fields like `title`, `content`)
    *   **Key public methods:** Methods for CRUD operations on warnings, retrieving warnings by ID, associating warnings with products/mappings.
    *   **Business Logic:** Manages the data for safety warnings.
*   `classes/index.php`
    *   **Responsibility:** Standard PrestaShop empty `index.php` file to prevent directory listing.

### 4.4 JavaScript Assets (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Scope:** Likely Back-office.
    *   **Responsibility:** Provides autocomplete functionality for search fields within the admin interface, possibly for selecting products, categories, or entities in mapping screens.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Scope:** Back-office (AdminGpsrEnterpriseController, API tab).
    *   **Responsibility:** Handles AJAX interactions for the API configuration screen, such as generating new API tokens or displaying API documentation modals.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Scope:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsibility:** Manages the UI and AJAX calls for mapping GPSR data to specific product combinations. This likely involves dynamically loading combination lists and handling assignments.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Scope:** Back-office (Product page tab, mapping forms).
    *   **Responsibility:** Provides a UI component for selecting product combinations, often used within mapping forms or the product edit tab.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Scope:** Back-office (Potentially within entity or warning forms).
    *   **Responsibility:** Manages UI logic for applying GPSR rules based on specific countries, if the module supports country-specific compliance.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Scope:** Back-office (Mapping forms, product page tab).
    *   **Responsibility:** Provides a UI component for selecting `GpsrEntity` instances (manufacturers, EU responsible persons) from a dropdown or search interface.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Scope:** Back-office (Warning forms).
    *   **Responsibility:** Contains data (e.g., an array of icon names/paths) used by `admin-icon-picker.js`.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Scope:** Back-office (Warning forms).
    *   **Responsibility:** Implements a UI component for visually selecting an icon to associate with a `GpsrWarning`.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Scope:** Back-office (Text areas in forms, e.g., for product passport templates).
    *   **Responsibility:** Provides functionality to insert predefined "shortcodes" or placeholders into text fields, which will be dynamically replaced with product data when rendered.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Scope:** Back-office (General mapping forms).
    *   **Responsibility:** A generic UI component for selecting various items (products, categories, documents, warnings) from a list or search.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Scope:** Back-office (AdminGpsrMassController).
    *   **Responsibility:** Manages the interactive product grid and bulk action functionality on the "Mass Actions" screen.
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Scope:** Back-office (Product edit page).
    *   **Responsibility:** Injects and manages the custom GPSR tab on the PrestaShop product edit page, allowing direct assignment of GPSR data to individual products.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Scope:** Back-office (AdminGpsrController/AdminGpsrEnterpriseController dashboard).
    *   **Responsibility:** Handles dynamic elements and AJAX updates on the module's dashboard, such as refreshing cron status or displaying statistics.
*   `gpsrenterprise/views/js/front.js`
    *   **Scope:** Front-office.
    *   **Responsibility:** Main JavaScript for the front-office GPSR information block. Handles dynamic loading of data (via `data.php` controller), tab/accordion functionality, and potentially interactions with the Product Passport button.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Scope:** Front-office or Back-office (Product Passport generation).
    *   **Responsibility:** Likely a utility script for generating or displaying barcodes, potentially used within the Product Passport PDF or for product identification.

### 4.5 CSS Stylesheets (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for the autocomplete search fields used in the admin interface.
*   `gpsrenterprise/views/css/admin-api.css`
    *   **Scope:** Back-office (AdminGpsrEnterpriseController, API tab).
    *   **Responsibility:** Styles specific to the API configuration and documentation display.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Scope:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsibility:** Styles for the combination mapping interface.
*   `gpsrenterprise/views/css/admin-combination-picker.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for the product combination selection component.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Scope:** Back-office (Module configuration page).
    *   **Responsibility:** General styles for the main module configuration form.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for country-specific rule configuration interfaces.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Scope:** Back-office (AdminGpsrController/AdminGpsrEnterpriseController dashboard).
    *   **Responsibility:** Styles for the module's administrative dashboard.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for help texts, tooltips, or documentation sections within the admin.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for the generic item selection component.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Enhancements to the default PrestaShop list/grid styling for better readability or functionality.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Scope:** Back-office (AdminGpsrMassController).
    *   **Responsibility:** Styles for the mass actions product grid.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Scope:** Back-office.
    *   **Responsibility:** Styles for the module's custom navigation tabs or menu items within the admin.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Scope:** Back-office (Product edit page).
    *   **Responsibility:** Styles for the GPSR tab added to the PrestaShop product edit page.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Scope:** Front-office (Classic theme).
    *   **Responsibility:** Specific styling for the GPSR block when the "Classic" theme profile is selected.
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Scope:** Front-office (Hummingbird theme).
    *   **Responsibility:** Specific styling for the GPSR block when the "Hummingbird" theme profile is selected.
*   `gpsrenterprise/views/css/front.css`
    *   **Scope:** Front-office.
    *   **Responsibility:** General, base styling for the GPSR information block on the storefront, applied regardless of the theme profile, which is then potentially overridden by `front-classic.css` or `front-hummingbird.css`.

### 4.6 Smarty Template Structure (`views/templates/`)

#### Hook templates (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (depending on configuration)
    *   **Output:** The main GPSR information block for the front-office product page, specifically styled for the Classic theme profile.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (depending on configuration)
    *   **Output:** The main GPSR information block for the front-office product page, specifically styled for the Hummingbird theme profile.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (depending on configuration)
    *   **Output:** A generic or base template for the GPSR information block, which might include logic to load either the classic or hummingbird specific templates based on the module's configuration.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook:** Internal partial template.
    *   **Output:** Renders specific attributes or details within the main GPSR product block, such as individual warnings, entity details, or document links. This is likely included by `product-gpsr.tpl` or its theme-specific variants.

#### Admin templates (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Output:** Contains JavaScript or Smarty logic for the search tool's functionality, likely included in various admin pages.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Output:** Renders the content for the API configuration screen, including token display, generation button, and documentation link.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Output:** A general back-office template, possibly for the main module dashboard or a wrapper for other admin views.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Output:** Displays a list of product combinations, used in mapping or picker interfaces.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Output:** Renders the UI for selecting product combinations.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Output:** Contains JavaScript specific to combination management, likely included in pages dealing with product combinations.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Output:** Renders the main module configuration form (accessed via Modules > Configure).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Output:** Renders a panel for managing country-specific GPSR rules.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Output:** Renders the content for the Cron job configuration and status screen.
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Output:** Renders the module's main dashboard with statistics and quick links.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Output:** Renders the list and management interface for GPSR documents.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Output:** Displays the list of configured GPSR entities.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Output:** Main wrapper template for the Entities management screen.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Output:** Renders the form for adding or editing a `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Output:** Renders the UI for selecting a `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Output:** A template likely used for AJAX responses to dynamically load product combinations.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Output:** Renders a generic UI component for picking items.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Output:** Renders the detailed GPSR ledger view.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Output:** A partial template containing common fields for GPSR mappings (e.g., entity selectors, warning selectors).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Output:** Renders the form for creating/editing category-level GPSR mappings.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Output:** Renders the form for creating/editing product combination-level GPSR mappings.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Output:** Renders the form for creating/editing global GPSR mappings.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Output:** Renders the form for creating/editing manufacturer-level GPSR mappings.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Output:** Main wrapper template for the Mappings section, likely including navigation for different mapping types.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Output:** Renders the product grid and mass action controls for the "Mass Actions" screen.
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Output:** Renders the interface for the GPSR Matcher, displaying suggestions.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Output:** Renders the navigation tabs for the module's back-office sections (Dashboard, Entities, Warnings, Mappings, etc.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Output:** Renders a small preview card for a product, possibly used in picker components or mass action grids.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Output:** Renders the content of the custom GPSR tab on the PrestaShop product edit page.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Output:** Renders the form for adding or editing a `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Output:** Displays the list of configured GPSR warnings.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Output:** Renders the content for a modal window displaying API documentation.

### 4.7 Database Schema & Hooks Map

#### Database Tables

*   `ps_gpsr_audit_log`: Stores audit trail entries for changes made within the module.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK to `ps_employee`)
    *   `action` (e.g., 'add', 'edit', 'delete', 'map')
    *   `object_type` (e.g., 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON or text for more info)
    *   `date_add`
*   `ps_gpsr_entity`: Stores details for manufacturers and EU responsible persons.
    *   `id_gpsr_entity` (PK)
    *   `type` (e.g., 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang`: Multilingual fields for `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning`: Stores safety warning definitions.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang`: Multilingual fields for `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document`: Stores details of uploaded documents.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang`: Multilingual fields for `ps_gpsr_document` (e.g., `name`).
*   `ps_gpsr_product_mapping`: Direct product-level GPSR data assignments.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, for combinations)
    *   `id_gpsr_entity_manufacturer` (FK to `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK to `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning`: Junction table for product-warning relationships.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document`: Junction table for product-document relationships.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping`: Category-level GPSR data assignments.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning`: Junction table for category-warning relationships.
*   `ps_gpsr_category_document`: Junction table for category-document relationships.
*   `ps_gpsr_manufacturer_mapping`: Manufacturer-level GPSR data assignments.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning`: Junction table for manufacturer-warning relationships.
*   `ps_gpsr_manufacturer_document`: Junction table for manufacturer-document relationships.
*   `ps_gpsr_global_mapping`: Stores global default GPSR data.
*   `ps_gpsr_match_suggestion`: Stores suggestions generated by the matcher.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration`: Module settings are stored here with keys like `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN`, etc.

#### Registered Hooks Table

| Hook Name | Execution Timing | Technical Purpose |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | After a product is saved (add or update). | Triggers re-evaluation of GPSR data for the product, updates mappings, or logs changes. |
| `actionAfterUpdateProductFormHandler` | After a product form is updated in the BO. | Refreshes GPSR data displayed in the product tab or triggers related updates. |
| `actionObjectProductDeleteAfter` | After a product object is deleted. | Cleans up associated GPSR data and mappings for the deleted product. |
| `actionAfterCreateProductFormHandler` | After a product form is created in the BO. | Initializes GPSR data for a new product, potentially applying default mappings. |
| `displayAfterProductThumbs` | On the product page, after product images. | Renders the front-office GPSR information block. (Placement depends on theme/config) |
| `actionObjectProductAddAfter` | After a new product object is added. | Triggers initial GPSR data assignment for the new product. |
| `displayProductAdditionalInfo` | On the product page, in the "Additional Info" section. | Renders the front-office GPSR information block, often as a tab. |
| `displayAdminProductsExtra` | On the product edit page in the Back Office. | Injects the custom GPSR tab for product-specific data management. |
| `displayBackOfficeHeader` | In the header of every Back Office page. | Loads module-specific CSS/JS for admin interfaces, adds menu items. |
| `actionAdminControllerSetMedia` | When an admin controller sets its media (CSS/JS). | Loads module-specific CSS/JS for relevant admin pages. |
| `displayProductExtraContent` | On the product page, for extra content blocks. | Renders the front-office GPSR information block, offering flexible placement. |
| `displayFooterProduct` | In the footer section of the product page. | Renders the front-office GPSR information block, often as a block below main content. |
| `displayReassurance` | In the product reassurance block (e.g., free shipping, secure payment). | Renders the front-office GPSR information block, potentially as a small, reassuring badge or link. |
| `actionProductAttributeUpdate` | After a product combination (attribute) is updated. | Triggers re-evaluation of GPSR data for the specific combination. |
| `actionFrontControllerSetMedia` | When a front controller sets its media (CSS/JS). | Loads module-specific CSS/JS for front-office pages where GPSR data is displayed. |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the GPSR Enterprise module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist with any issues or questions you may have regarding the module's functionality or integration.
