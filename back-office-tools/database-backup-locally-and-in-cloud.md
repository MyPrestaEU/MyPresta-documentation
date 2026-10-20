---
title: "Database backup locally and in cloud - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Database backup locally and in cloud PrestaShop module by MyPresta.eu."
sidebar:
  label: "Database backup locally and in cloud - Merchant Manual & Configuration Guide"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Database backup locally and in cloud Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Database backup locally and in cloud

## 1. Requirements & Compatibility

- **Supported PrestaShop Versions**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP Compatibility**: PHP 7.1 - 8.5
- **Hosting Requirements**: Standard PHP extensions (cURL, JSON, OpenSSL). Sufficient server resources (CPU, memory) for database export, especially for very large databases, though the module is designed to mitigate these issues with chunking. Write permissions for the backup directory on your server.

## 2. Complete Configuration Walkthrough (Every Setting Grouped by Screen)

The “Database backup locally and in cloud” module provides a comprehensive interface for managing your backups. You’ll primarily interact with two main areas: the module’s main configuration page and its dedicated “My Backups” admin screen.

### 2.1 Module Main Configuration Page (Back Office > Modules > Module Manager > Configure “Database backup locally and in cloud”)

This initial configuration page (`mybackups/index.php` via `getContent()`) handles the basic setup and integration of the module.

#### General Settings

- **What this setting does:** These settings control fundamental aspects of how the module operates and integrates with your PrestaShop environment.
- **Effect of changing this setting:** Adjusting these can impact performance, security, and the overall reliability of your backups.
- **Recommended value:** Generally, stick to the defaults unless you have a specific reason or are advised by support.

#### Cloud Storage Integrations

- **What this setting does:** This section allows you to connect your PrestaShop store to various cloud storage providers where your backups will be stored. Each provider (Google Drive, Dropbox, FTP/FTPS, Amazon S3) will have its own set of connection details.
- **Effect of changing this setting:** Successfully connecting to a cloud service enables that service as a backup destination. Incorrect credentials will prevent backups from being uploaded to that specific cloud.
- **Recommended value:** Connect to at least one cloud storage provider for off-site backups. Google Drive and Dropbox are often the easiest to set up for most merchants.
- **Merchant scenario / example:** You want to store your backups on Google Drive. You would click the “Connect to Google Drive” button, follow the authentication steps, and grant the module permission to access a specific folder in your Google Drive. This ensures that even if your server crashes, your backups are safe in the cloud.

### 2.2 Dedicated Admin Screen: My Backups (Back Office > My Backups)

This is the central hub for managing all your database backups. You’ll find this screen under a new menu item, typically named “My Backups” or similar, added to your PrestaShop Back Office navigation. This screen is powered by `mybackups/controllers/admin/AdminMyBackupsController.php`.

#### Dashboard & Backup List

- **Screen Name & Menu Location:** You’ll find “My Backups” under the main PrestaShop menu, usually grouped with “Administration” or “Advanced Parameters.”
- **Available Actions & Settings:**
  - **Backup List:** This table displays all your existing database backups, whether stored locally or in the cloud. Each entry typically shows:
    - **Date/Time:** When the backup was created.
    - **Size:** The size of the compressed backup file.
    - **Location:** Where the backup is stored (Local, Google Drive, Dropbox, FTP, S3).
    - **Actions:**
      - **Download:** Download the backup file to your computer.
      - **Restore:** Initiate a database restore process using this backup. (Be extremely careful with this action, as it will overwrite your current database!)
      - **Delete:** Remove the backup file from its storage location.
  - **Create New Backup Button:** A prominent button to manually initiate a new database backup.
  - **Cloud Storage Status:** Visual indicators showing which cloud services are currently connected and available.
  - **Scheduled Backups:** A section to view and manage your automated backup tasks (cron jobs).
- **Effect of changes:**
  - **Creating a new backup:** Generates a new compressed SQL dump of your database and stores it in the configured locations (local and/or cloud).
  - **Restoring a backup:** Replaces your current live database with the data from the selected backup file. This is a powerful and potentially destructive action; always ensure you have a fresh backup before attempting a restore.
  - **Deleting a backup:** Permanently removes the backup file from its storage.
- **Recommended workflow for daily store management:**
  1. **Initial Setup:** Connect to your preferred cloud storage providers on the module’s configuration page.
  2. **Schedule Backups:** Set up a cron job (see “Practical Use Cases” below) to automatically create backups daily or weekly, depending on your store’s activity. Ensure these scheduled backups are sent to at least one cloud location.
  3. **Regular Monitoring:** Periodically check the “My Backups” dashboard to ensure backups are being created successfully and that your cloud connections are active.
  4. **Manual Backup (Optional):** Create a manual backup before any major store changes (e.g., module installations, theme updates, product imports).
  5. **Test Restore (CRITICAL):** Occasionally, perform a test restore on a *development or staging environment* (NEVER on your live store without extreme caution) to ensure your backups are valid and the restore process works as expected.

#### Backup Creation Form

When you click “Create New Backup,” you’ll typically be presented with options:

- **Backup Name:**
  - **What this setting does:** Allows you to give a custom name to your backup file for easy identification.
  - **Effect of changing this setting:** The backup file will be saved with this name (e.g., `my-store-backup-2023-10-27.sql.zip`).
  - **Recommended value:** Use a descriptive name, perhaps including the date or a brief note about the reason for the backup (e.g., “Pre-update backup”).
- **Storage Locations:**
  - **What this setting does:** Select where the backup file should be saved. Options typically include “Local Server” and any connected cloud services (Google Drive, Dropbox, FTP, S3).
  - **Effect of changing this setting:** The backup will be stored only in the selected locations.
  - **Recommended value:** Always select “Local Server” and at least one cloud storage option for redundancy.
- **Exclude Tables:**
  - **What this setting does:** Allows you to select specific database tables that should *not* be included in the backup. This can be useful for very large tables that contain non-critical or easily regeneratable data (e.g., cache tables, log tables).
  - **Effect of changing this setting:** The selected tables will be skipped, resulting in a smaller backup file.
  - **Recommended value:** For most merchants, leave this empty to back up the entire database. Only exclude tables if you understand the implications and are trying to reduce backup size due to severe hosting constraints.
- **Start Backup Button:** Initiates the backup process. You’ll typically see a progress bar or status updates as the backup is created and uploaded.

### 2.3 Configuration Quick Reference Table

| Screen / View | Setting / Option | Default / Recommended | Purpose & Impact |
| --- | --- | --- | --- |
| **Module Configuration Page** | General Settings | Default | Controls fundamental module operations, performance, and security. |
|  | Google Drive Integration | Connect | Enables Google Drive as a backup destination. |
|  | Dropbox Integration | Connect | Enables Dropbox as a backup destination. |
|  | FTP/FTPS Integration | Configure | Enables FTP/FTPS as a backup destination. |
|  | Amazon S3 Integration | Configure | Enables Amazon S3 as a backup destination. |
| **My Backups Dashboard** | Create New Backup | N/A | Manually initiates a new database backup. |
|  | Backup List (Download) | N/A | Downloads a backup file to your local computer. |
|  | Backup List (Restore) | N/A | **CRITICAL:** Overwrites current database with selected backup. Use with extreme caution, preferably on staging. |
|  | Backup List (Delete) | N/A | Permanently removes a backup file from its storage location. |
| **Backup Creation Form** | Backup Name | Auto-generated | Custom name for the backup file. |
|  | Storage Locations | Local + Cloud | Selects where the backup will be saved (local server, cloud services). |
|  | Exclude Tables | None | Skips specified tables from the backup to reduce file size. |

## 3. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q: My backups are failing or taking too long. What should I do?**
A:

- **Check Server Resources:** Large databases require significant server memory and execution time. While the module chunks exports, very constrained hosting environments can still struggle. Contact your host to check PHP memory limits (`memory_limit`) and max execution time (`max_execution_time`).
- **Clear Cache:** Sometimes, PrestaShop’s cache can interfere. Go to **Advanced Parameters > Performance** and click “Clear cache.”
- **Exclude Tables:** Consider excluding non-critical tables (like cache or statistics tables) from the backup if they are very large. This can significantly reduce backup size and time.
- **Check Error Logs:** Look in your PrestaShop error logs (usually `var/logs/` or `app/logs/` depending on PS version) or your server’s PHP error logs for specific error messages.

**Q: I connected to Google Drive/Dropbox, but I don’t see my backups there.**
A:

- **Check Connection Status:** Go to the module’s configuration page and verify that your cloud service shows as “Connected.” If not, try reconnecting.
- **Folder Permissions:** Ensure the module has the necessary permissions to write to the specified folder in your cloud storage. For Google Drive/Dropbox, the module usually creates its own folder.
- **Manual Upload Test:** Try creating a small manual backup and explicitly selecting the cloud service as a destination to see if it uploads successfully.
- **Check Cloud Storage Directly:** Log into your Google Drive or Dropbox account via their website and manually browse the folders to see if the backups are there, perhaps in an unexpected location.

**Q: How do I restore my database from a backup?**
A:

- **WARNING:** Restoring a database will overwrite your current live database. This is a highly destructive action. **Always have a fresh backup of your current database before attempting a restore.**
- Go to **Back Office > My Backups**.
- Locate the backup file you wish to restore in the list.
- Click the “Restore” button next to that backup.
- Follow the on-screen prompts. The module will guide you through the process.
- If your store is completely down, you might need to manually upload the backup file via FTP and then use the module’s interface or a tool like phpMyAdmin to import it. In such critical situations, it’s best to consult with a developer or your hosting provider.

**Q: What happens if my server runs out of disk space during a local backup?**
A: The backup process will likely fail, and you’ll see an error message related to disk space. Ensure you have sufficient free disk space on your server, especially if you’re storing multiple local backups or have a very large database. Regularly delete old local backups that have already been safely uploaded to the cloud.

**Q: My custom theme doesn’t display correctly after a restore.**
A: Database backups primarily restore your data. Theme files, module files, and images are typically stored on your server’s file system, not directly in the database.

- **Clear Cache:** Go to **Advanced Parameters > Performance** and clear all caches (Smarty, filesystem, etc.).
- **Check File System:** Ensure all your theme files, module files, and image folders are present and have correct permissions on the server. A database restore won’t affect these files. If you’ve restored from a very old backup, some module configurations might need to be re-saved in the Back Office.

## 4. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section provides a deep dive into the technical architecture and codebase of the “Database backup locally and in cloud” module for developers and webmasters.

### 4.1 Architecture Overview

The MyBackups module is designed with a strong emphasis on robustness, scalability, and fault tolerance, particularly for handling large database operations and external cloud integrations. It follows a modular, object-oriented approach, leveraging PrestaShop’s MVC pattern where appropriate but also implementing its own internal service-oriented architecture for core backup/restore logic.

Key architectural patterns include:

- **Chunked Processing:** Database export and import are broken into smaller, manageable chunks to circumvent PHP execution time and memory limits.
- **State Management:** A robust state management system (`MyBackupsStateManager`) tracks the progress of long-running backup/restore jobs, allowing for web-cron execution and recovery from interruptions.
- **Storage Abstraction:** An interface-based design (`MyBackupsStorageInterface`) allows for easy integration of new cloud storage providers without altering core backup logic.
- **OAuth Integration:** Secure OAuth 2.0 flows for Google Drive and Dropbox, handling token storage and refresh.
- **Cron/Job Runner:** Dedicated front controllers and classes for triggering and managing background jobs via cron or web-cron.

### 4.2 Controllers (`controllers/`)

#### Front-Office Controllers

These controllers are primarily used for background tasks and OAuth callbacks, not for rendering customer-facing content.

- `mybackups/controllers/front/cron.php`
  - **Class name & parent class:** `MyBackupsCronModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This controller serves as the entry point for scheduled cron jobs. When accessed with the correct token, it triggers the `MyBackupsCronRunner` to process pending backup tasks. It’s designed to be called externally by a server’s cron daemon or a web-cron service.
- `mybackups/controllers/front/index.php`
  - **Class name & parent class:** `MyBackupsIndexModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** A placeholder or default front controller, often used for module routing or simple redirects if no specific action is requested. In this module, it might serve as a base or fallback.
- `mybackups/controllers/front/job.php`
  - **Class name & parent class:** `MyBackupsJobModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Handles AJAX requests related to the progress and status of ongoing backup/restore jobs. It interacts with `MyBackupsJobRunner` and `MyBackupsStateManager` to provide real-time updates to the Back Office UI.
- `mybackups/controllers/front/oauthdropbox.php`
  - **Class name & parent class:** `MyBackupsOauthdropboxModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** This is the callback URI for the Dropbox OAuth 2.0 flow. After a merchant authorizes the module on Dropbox, Dropbox redirects to this controller, which then handles the exchange of the authorization code for an access token and stores it securely.
- `mybackups/controllers/front/oauthgdrive.php`
  - **Class name & parent class:** `MyBackupsOauthgdriveModuleFrontController` extending `ModuleFrontController`.
  - **Responsibility:** Similar to `oauthdropbox.php`, this is the callback URI for the Google Drive OAuth 2.0 flow. It processes the authorization code from Google and obtains/stores the necessary access and refresh tokens.

#### Back-Office Admin Controllers

These controllers manage the module’s interface within the PrestaShop Back Office.

- `mybackups/controllers/admin/AdminMyBackupsController.php`
  - **Class name & parent class:** `AdminMyBackupsController` extending `ModuleAdminController`.
  - **Tab name and managed entity:** This is the primary admin controller for the “My Backups” dashboard. It manages the listing, creation, download, restore, and deletion of backup files. It orchestrates interactions with `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter`, and the various storage classes.
- `mybackups/controllers/admin/index.php`
  - **Class name & parent class:** Standard PrestaShop `index.php` file for admin controller directories.
  - **Responsibility:** Prevents direct directory listing and ensures secure access to the admin controllers.

### 4.3 Core Classes & Models (`classes/`)

- `mybackups/classes/index.php`: Standard empty `index.php` to prevent directory listing.
- `mybackups/classes/MyBackupsAdminAjax.php`: Handles various AJAX requests from the admin interface, such as fetching backup lists, initiating specific actions, or updating UI elements.
- `mybackups/classes/MyBackupsAdminForms.php`: Likely responsible for rendering and processing the module’s configuration forms in the Back Office, including cloud integration settings.
- `mybackups/classes/MyBackupsCatalog.php`: Manages the catalog of backup files, whether local or in the cloud. It provides methods to list, filter, and retrieve information about existing backups.
- `mybackups/classes/MyBackupsCloudUi.php`: Assists in generating the UI elements and logic for cloud storage integration within the Back Office (e.g., connection buttons, status indicators).
- `mybackups/classes/MyBackupsCronRunner.php`: The core logic for executing scheduled backup jobs. It checks for pending tasks and initiates `MyBackupsJobRunner` for each.
- `mybackups/classes/MyBackupsDumpVerifier.php`: Responsible for verifying the integrity and validity of SQL dump files, potentially checking for common errors or incomplete dumps.
- `mybackups/classes/MyBackupsExporter.php`: Handles the actual database export process, including chunking the SQL dump, table filtering, and compression.
- `mybackups/classes/MyBackupsImporter.php`: Manages the database import (restore) process, parsing the SQL dump and executing queries in chunks.
- `mybackups/classes/MyBackupsJobLock.php`: Implements a locking mechanism to prevent multiple concurrent backup/restore jobs from running simultaneously, ensuring data consistency and preventing resource contention.
- `mybackups/classes/MyBackupsJobRunner.php`: Orchestrates the entire backup or restore job, managing the sequence of steps (export, compress, upload/download, import) and interacting with `MyBackupsStateManager`.
- `mybackups/classes/MyBackupsMemoryGuard.php`: A utility class to monitor and manage PHP memory usage during intensive operations, helping to prevent out-of-memory errors.
- `mybackups/classes/MyBackupsOAuthReturn.php`: Handles the final steps of the OAuth callback process, processing the returned authorization code and managing token storage.
- `mybackups/classes/MyBackupsOAuthState.php`: Manages the state parameter during OAuth flows to prevent CSRF attacks.
- `mybackups/classes/MyBackupsPaths.php`: Provides centralized management of file paths and directories used by the module (e.g., backup storage directory).
- `mybackups/classes/MyBackupsStateManager.php`: Crucial for long-running jobs. It stores and retrieves the current state of a backup/restore operation, allowing jobs to be paused and resumed across multiple HTTP requests (e.g., during cron execution or web-based progress updates).
- `mybackups/classes/MyBackupsTableFilter.php`: Implements logic for filtering database tables during export, based on user selections.
- `mybackups/classes/MyBackupsTimeBudget.php`: Helps manage execution time limits for long-running processes, allowing the module to gracefully stop and save state before hitting `max_execution_time`.
- `mybackups/classes/MyBackupsTokenCrypto.php`: Handles the encryption and decryption of sensitive OAuth tokens and API keys for secure storage.
- `mybackups/classes/MyBackupsZip.php`: Manages the compression and decompression of backup files into ZIP archives.

#### Storage Sub-Classes (`classes/storage/`)

This directory contains classes implementing the `MyBackupsStorageInterface` for various storage backends.

- `mybackups/classes/storage/index.php`: Standard empty `index.php`.
- `mybackups/classes/storage/MyBackupsCloudUploader.php`: A generic class for managing the upload process to cloud storage, potentially handling chunked uploads and progress tracking.
- `mybackups/classes/storage/MyBackupsDropboxStorage.php`: Implements `MyBackupsStorageInterface` for interacting with the Dropbox API.
- `mybackups/classes/storage/MyBackupsFtpStorage.php`: Implements `MyBackupsStorageInterface` for interacting with FTP/FTPS servers.
- `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php`: Implements `MyBackupsStorageInterface` for interacting with the Google Drive API.
- `mybackups/classes/storage/MyBackupsHttp.php`: A utility class for making HTTP requests, likely used by cloud storage classes for API calls.
- `mybackups/classes/storage/MyBackupsLocalStorage.php`: Implements `MyBackupsStorageInterface` for storing and retrieving backups on the local server filesystem.
- `mybackups/classes/storage/MyBackupsS3Storage.php`: Implements `MyBackupsStorageInterface` for interacting with Amazon S3.
- `mybackups/classes/storage/MyBackupsStorageFactory.php`: A factory pattern class responsible for instantiating the correct storage class based on configuration.
- `mybackups/classes/storage/MyBackupsStorageInterface.php`: Defines the contract (methods) that all storage classes must implement (e.g., `upload`, `download`, `delete`, `list_files`).

### 4.4 JavaScript Assets (`views/js/`)

- `mybackups/lib/searchTool/views/js/autocomplete.js`:
  - **Scope:** Likely Back-office.
  - **Details:** Provides autocomplete functionality, possibly for searching through database tables when configuring exclusions or for filtering backup lists.
- `mybackups/views/js/mybackups-cloud.js`:
  - **Scope:** Back-office.
  - **Details:** Handles client-side interactions for cloud storage configuration. This includes AJAX calls to connect/disconnect from services, update UI based on connection status, and potentially handle folder browsing within cloud services.
- `mybackups/views/js/mybackups-job.js`:
  - **Scope:** Back-office.
  - **Details:** Manages the real-time progress display for backup and restore jobs. It uses AJAX to poll the `job.php` front controller for updates on the job’s state, updating progress bars, status messages, and handling job completion or failure notifications.
- `mybackups/views/js/mybackups-table-picker.js`:
  - **Scope:** Back-office.
  - **Details:** Provides the interactive interface for selecting or excluding database tables during backup creation, potentially including search and multi-selection features.

### 4.5 CSS Stylesheets (`views/css/`)

- `mybackups/lib/searchTool/views/css/autocomplete.css`:
  - **Scope:** Back-office admin styling.
  - **Details:** Styles for the autocomplete input fields and suggestion lists used in the Back Office.
- `mybackups/views/css/admin.css`:
  - **Scope:** Back-office admin styling.
  - **Details:** Contains the main styling for the module’s Back Office interface, including the dashboard, backup list, forms, progress bars, and cloud integration sections. Developers can override these styles in their custom admin theme or by adding custom CSS via a hook if needed.

### 4.6 Smarty Template Structure (`views/templates/`)

- `mybackups/lib/searchTool/views/scripts.tpl`:
  - **Scope:** Back-office.
  - **Details:** Likely includes JavaScript and CSS assets for the search/autocomplete tool, potentially hooked into `displayBackOfficeHeader` or similar.
- `mybackups/views/templates/admin/backups.tpl`:
  - **Scope:** Admin template.
  - **Details:** The main template for displaying the list of existing backups, including columns for date, size, location, and action buttons (download, restore, delete). This is the core of the `AdminMyBackupsController`’s display.
- `mybackups/views/templates/admin/configure.tpl`:
  - **Scope:** Admin template.
  - **Details:** Renders the module’s main configuration form, typically accessed via `getContent()` in the main module file. This includes general settings and the initial setup for cloud service integrations.
- `mybackups/views/templates/admin/dashboard.tpl`:
  - **Scope:** Admin template.
  - **Details:** The overarching dashboard template for the “My Backups” section, combining elements like the backup list, “Create New Backup” button, cloud status indicators, and potentially scheduled backup information.
- `mybackups/views/templates/admin/job-progress.tpl`:
  - **Scope:** Admin template.
  - **Details:** Displays the progress bar and status messages for ongoing backup or restore jobs, dynamically updated by `mybackups-job.js`.
- `mybackups/views/templates/admin/table-picker.tpl`:
  - **Scope:** Admin template.
  - **Details:** Renders the interface for selecting or excluding database tables during backup creation.

### 4.7 Database Schema & Hooks Map

- **Database Tables**:

  - The module does not create custom SQL tables for storing backup data itself, as backups are files.
  - It will store configuration values in PrestaShop’s `ps_configuration` table, such as:
    - Cloud API keys/secrets (encrypted).
    - OAuth tokens (encrypted).
    - Module-specific settings (e.g., default backup locations, cron token).
    - Job state information for `MyBackupsStateManager`.
- **Registered Hooks Table**:
  The module primarily uses Back Office hooks and front controllers for its functionality. The listed front-office hooks (Header, Columns, Product, Footer) are likely *not* used by this module, as its functionality is purely administrative and backend-focused. If they were used, it would be for very specific, non-visible purposes, such as loading assets or performing background checks.

| Hook Name | Execution Timing | Technical Purpose |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renders in the `<head>` section of Back Office pages. | Used to inject module-specific CSS (`admin.css`) and JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) into the admin panel. |
| `displayAdminProductsExtra` (or similar) | Potentially for adding a backup option on product edit page, though unlikely for this module. | (If used) To add a specific backup action or information related to product data. |
| `actionModuleInstall` | Executed when the module is installed. | Creates necessary directories, sets default configuration values, registers admin menu tabs, and potentially sets up initial cron job instructions. |
| `actionModuleUninstall` | Executed when the module is uninstalled. | Cleans up configuration values, removes admin menu tabs, and deletes module-specific directories (though often leaves backup files for safety). |
| `actionAdminControllerSetMedia` | Executed before an Admin Controller renders its page. | Used to add specific CSS/JS assets only to the module’s own admin pages (`AdminMyBackupsController`). |

## 5. Official Support & Updates

For the latest updates, bug fixes, and official support for the “Database backup locally and in cloud” module, please refer to your customer account at [MyPresta.eu](https://mypresta.eu/my-account/orders/). Our support team is available to assist you with any technical issues or questions you may have regarding the module’s functionality and configuration.
