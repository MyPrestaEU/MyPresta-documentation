---
title: "Return Button Pro - documentation and user manual"
description: "Configure the EU withdrawal form, manage cases in the back office, and fix common problems for shop owners who already use Return Button Pro."
sidebar:
  label: "Return Button Pro - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy EU Return Button – Online Withdrawal Form Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Screenshots in this manual show the English back office. Use the same menu names and labels as written here.

## 1. Requirements

Return Button Pro works on PrestaShop 1.6, 1.7, 8, and 9. Use the module package that matches your shop: the dedicated PrestaShop 1.6 build for 1.6 shops, and the PrestaShop 1.7–9 build for newer shops. Download the correct ZIP from your MyPresta.eu order history when both packages are available.

- PrestaShop: 1.6.x, 1.7.x, 8.x, and 9.x
- PHP: versions your PrestaShop already runs on, including older stacks with PrestaShop 1.6 (PHP 5.6 and PHP 7.x) and the PHP versions required by PrestaShop 1.7–9 (PHP 7.1+ / PHP 8.x as your host and shop require). The module is maintained for PHP 7.x environments as well as current shop PHP.
- PHP extensions used by the module: JSON, curl (update checks), fileinfo (attachment MIME checks), hash (tokens and guest security)
- Other modules: not required. If the free Return Button module is installed and enabled, disable it before you configure or use Return Button Pro. Both cannot run at the same time.
- External accounts: none. Optional MyPresta.eu update checks use the internet from the Updates tab.

## 2. Installation

1. Upload the module ZIP in **Modules** → **Module Manager**, then install and enable **Return Button Pro**.
2. After install, a **Withdrawals** item appears under **Customers**. Open configuration from **Module Manager** → **Return Button Pro** → **Configure** (tabs: **Dashboard**, **Settings**, **Updates**).
3. Installation does not clear the PrestaShop cache. Clear cache yourself after theme or hook changes if the storefront still looks wrong.

Uninstall: the **Withdrawals** menu entry is removed and configuration values are deleted. Withdrawal tables and case records stay in the database for legal evidence. Reinstalling does not wipe those records; the module can use them again when tables already exist. Uploaded staff attachments under the module folder are not removed by uninstall.

If you upgrade from the free Return Button module, Pro can copy compatible settings and migrate empty Pro tables from free-module data when Pro has no rows yet. Disable the free module first.

## 3. Configuration and back-office work

### 3.1 Full withdrawal process

End-to-end flow from the storefront to staff handling:

1. The customer finds the withdrawal entry: footer button, My Account link, order detail button, or the form URL when guest access is on.
2. **Step 1 – order:** logged-in customers see their orders with eligibility hints (days left, unavailable reasons). Guests enter order reference and email. The customer selects an eligible order, chooses **Full order** or **Partial** (with quantities on allowed lines), optionally adds a message and IBAN, then continues.
3. **Step 2 – confirm:** the customer reviews the statement summary. When **Require legal confirmation checkbox** is on, they must tick the legal text, then submit.
4. The module saves the case, moves it to **Registered**, and sends the customer confirmation (durable medium) plus a shop notification (and **Notification email** when set). The success page shows the withdrawal reference.
5. Staff open **Customers** → **Withdrawals** (or the order side panel), open **View**, set status (**In progress**, **Refunded**, **Rejected**, and so on), and enter a customer message when required.
6. The customer follows status via **Track withdrawal status**, the status page, and **Print / save PDF**. Staff messages from status changes appear in the customer withdrawal history.

Statuses used by the module:

| Field | At the start | What it does |
|---|---|---|
| **Pending** | Brief state when the statement is first saved | Open case before the customer’s legal confirmation finishes, or when staff set this status later. Counts toward duplicate blocking with other open statuses. |
| **Registered** | After the customer confirms on step 2 | Statement recorded; confirmation emails attempted. Default post-submit status. |
| **In progress** | Staff action | Shop is handling the case (returns, checks, refund prep). Still blocks a second active request when duplicate blocking is on. |
| **Refunded** | Staff action | Case closed with refund outcome. Visible on the customer status page. |
| **Rejected** | Staff action | Case closed without refund. Use a clear customer message when the setting requires it. |

Scope on the form: **Full order** or **Partial**. Type: **Contract withdrawal** (paid) or **Contract cancellation (unpaid order)** when the order was never paid.

### 3.2 Dashboard

Open **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filter with **From** / **To** and **Apply**, or reset with **Last 30 days**. The panel shows all-time totals, pending backlog, detected theme profile, active footer hook, KPIs (withdrawals in period, rate vs orders, email confirmation share, average days from order to withdrawal, partial/full share, cancellations, refunded share of closed cases, rejection rate), a daily submissions chart, status breakdown, most withdrawn products, and oldest pending cases with **Open**.

Use **Manage all withdrawals** for the list under Customers, or **Export CSV** for a download of cases in the current shop.

### 3.3 Settings

Open the **Settings** tab and click **Save** after changes.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Theme integration

Match the module to Classic, Hummingbird, or a custom theme. Adjust these if buttons or forms look unstyled after a theme update.

| Field | At the start | What it does |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Chooses which front-office templates and CSS the module loads (Classic vs Hummingbird). Correct button styling, form layout, and My Account link appearance. Leave Auto-detect unless the button looks wrong after a theme change; then force Classic-type or Hummingbird-type to match your active theme. After changing, clear PrestaShop cache and refresh the storefront. |
| **Footer button hook** | Auto (by theme profile) | Defines where in the page footer the withdrawal button is injected. Auto follows the theme profile (Hummingbird → displayFooterBefore, Classic → displayFooter). If the button is missing or misaligned, try displayFooterBefore or displayFooter manually, save, clear cache, and check the shop footer. For manual placement, put the custom hook in a theme template and select displayRbproButton here; keep **Footer button** enabled so the button shows only in that template. |

#### General & access

| Field | At the start | What it does |
|---|---|---|
| **Module enabled** | Yes | Master switch for the entire module. When disabled, withdrawal buttons, the form, guest access, and tracking are hidden on the storefront; existing withdrawal records in the back office remain. Use this for maintenance or legal review without uninstalling. |
| **Public status tracking page** | Yes | Enables a public page where customers check withdrawal status using withdrawal reference + email (no login). Reduces “where is my return?” tickets. Enable if you want a **Track withdrawal status** link next to the footer button; communicate the reference from the confirmation email. Disable if you handle status only by account email or phone. |
| **Guest access (order ref + email)** | Yes | Allows non-logged-in customers to open the form by entering order reference and email on step 1. Recommended for B2C EU distance sales. Turn off if only logged-in customers may withdraw. Guest sessions use a signed cookie. |
| **Block duplicate active requests** | Yes | Prevents a second open withdrawal for the same order while one is already Pending, Registered, or In progress. Avoids duplicate cases and conflicting refunds. Keep enabled in production. Disable only for testing or unusual partial-claim processes. |
| **Require legal confirmation checkbox (step 2)** | Yes | Forces the customer to tick a legally worded checkbox before submitting. Explicit consent record aligned with EU withdrawal rules. Edit the checkbox text per language under Texts & SEO. If disabled, submission is still logged without a mandatory tick box. |
| **Require message to customer when changing status** | Yes | Staff must enter a message to the customer before a withdrawal status can be updated. The message is stored in the audit trail and shown on the customer status page. Turn off only if you need fast status changes without writing each time. |
| **Show deadline countdown to customer** | Yes | Shows how many days remain in the statutory withdrawal period (order list and form). Needs a correct **Order state = delivered** mapping and withdrawal period. If dates look wrong, check order history and the delivered state. |
| **Optional IBAN field** | No | Adds an optional IBAN field on the form for refund payouts. Enable only if you refund by bank transfer and your privacy policy covers it. Leave off if you refund to the original payment method only. |
| **Notification email** | Empty | Extra address that receives new withdrawal notifications (in addition to the shop contact). Example: returns@yourshop.com. Leave empty to use only PrestaShop’s default mail flow without this recipient. |

#### Withdrawal rules

| Field | At the start | What it does |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Calendar days customers have to withdraw after the order is considered delivered. Default 14 for EU distance contracts. Change only when law or your terms require another value. Countdown starts from the delivery date derived from order history and **Order state = delivered**. |
| **Order state = delivered** | Auto | Order state that marks goods as delivered (start of the withdrawal period). Choose the state you set when the parcel is delivered (for example Delivered, or Shipped if that is your final state). Auto uses a sensible default from your shop; override if deadlines use the wrong date. |
| **Allowed order statuses** | All order statuses | Controls when customers may submit a withdrawal based on the order’s current status. Choose **All order statuses** to skip the filter, or **Only selected statuses** and move statuses from the left column to **Allowed for withdrawal**. Orders outside the list show as unavailable in the account order list. |
| **Excluded products** | Empty | Specific products that cannot be withdrawn (sealed goods, custom items, and similar). Search by name or keep IDs; excluded lines show the exclusion message on the form. |
| **Excluded product variants** | Empty | Specific variants excluded from withdrawal. Search the product, then select the variant. |
| **Excluded categories** | Empty | All products in these categories are non-withdrawable. |
| **Excluded manufacturers** | Empty | Products from these manufacturers cannot be withdrawn. |
| **Excluded suppliers** | Empty | Products linked to these suppliers cannot be withdrawn. |
| **Excluded customer groups** | Empty | Customers in these groups cannot use withdrawal at all (no form access, buttons hidden). |

#### Footer & appearance

| Field | At the start | What it does |
|---|---|---|
| **Footer button** | Yes | Shows the main withdrawal call-to-action in the shop footer (hook configured above). Disable if you only want My Account and order-detail links. Requires **Module enabled** and a correct footer hook. |
| **Footer theme** | Light footer (dark text) | Color scheme for footer text and links (not the button background). Choose Light on pale footers, Dark on black/dark footers so **Track withdrawal status** stays readable. Clear cache after change. |
| **Footer alignment** | Center | Horizontal alignment of the footer button block: Left, Center, or Right. Affects footer hook output only. |
| **Button color** | #2563eb | Background color of withdrawal buttons (footer, order detail, and similar). Pick a hex color with enough contrast against white text. Does not change the theme primary color globally. |
| **Custom CSS** | Empty | Extra CSS on pages where module buttons appear. Use for margins, fonts, or hiding elements without editing theme files. Test on staging first. |
| **Link in customer account** | Yes | Adds a withdrawal entry in My Account. Recommended on. Disable only if you rely solely on footer or order links. |
| **Link on order detail** | Yes | Shows withdrawal action on the order detail page when the order is eligible. Blocked orders show a short reason instead of the button. |

#### Texts & SEO

Fill every active shop language.

| Field | At the start | What it does |
|---|---|---|
| **Noindex on form page** | Yes | Adds robots noindex,nofollow on the withdrawal form URL so legal/form pages stay out of search results. Turn off only if you intentionally want the form indexed. |
| **Button label** | Withdraw from contract | Text on all withdrawal buttons and links. Short label works best in the footer. Main customer-facing phrase for the module. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Shown next to excluded products on the form. Explain why the item cannot be selected; mention your terms if needed. |
| **SEO title** | Withdraw from contract | HTML page title of the withdrawal form (browser tab). Keep under about 60 characters per language. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta description for the form. Usually unused for ranking when noindex is on. Leave blank to omit. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Label beside the mandatory checkbox on step 2. Use clear, country-appropriate wording. Required when **Require legal confirmation checkbox** is on. |

### 3.4 Updates

Open the **Updates** tab.

| Field | At the start | What it does |
|---|---|---|
| **Manual Check** | — | Checks MyPresta.eu for a newer module version. You see **New version available!** or **Module is up to date!** Needs curl and outbound HTTPS. |
| **Automatic Notifications** | Enabled (module default for update prefs) | When enabled, the back office can show a notice that a new version exists. Save with **Save**. |
| **Product Page** | Link on form | Opens the official product page for release information. Use Support (§7) for paid-module help after login. |

If the free Return Button module is still enabled, settings and update actions are blocked until you disable it.

### 3.5 Withdrawals list

Go to **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

Default sort is newest submission first. Columns:

| Field | At the start | What it does |
|---|---|---|
| **ID** | Auto | Internal case id. |
| **Submitted** | From form | Date and time the customer submitted. |
| **Order** | From order | PrestaShop order reference. |
| **First name** / **Last name** / **Email** | From customer | Contact identity on the case. |
| **Scope** | Full order or Partial | Whether the whole order or selected lines were withdrawn. |
| **Type** | Contract withdrawal or cancellation | Paid withdrawal vs unpaid-order cancellation. |
| **Status** | Registered after confirm | Current case status (Pending, Registered, In progress, Refunded, Rejected). |
| **Email** | Yes/No | Whether the confirmation email was recorded as sent. |

Use search and sort on the list. Open a case with **View**. There is no **Add new** action: requests are created only by customers on the storefront. If someone tries to create a case in the back office, the warning explains that withdrawals cannot be created manually and the list is shown again.

Export CSV from **Dashboard** (**Export CSV**) when you need a spreadsheet of cases for the shop.

### 3.6 Withdrawal case view

Open a row with **View**.

The header shows reference, ID, submitted date, status, type, scope, email-sent flag and time, deadline, IP, user-agent, customer name and email, and a link to the PrestaShop order. The products block lists each withdrawn line with quantity and unit price. IBAN and the customer message appear when the customer provided them.

**Update status**

1. Choose **New status**.
2. Write **Message to customer** (required when that setting is on; optional otherwise). The help text explains that the message appears in the storefront withdrawal history.
3. Click **Update status**.

Success: **Status updated.** Other messages: **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** sends the customer confirmation again, updates the sent flag when successful, and logs the event. Success: **Confirmation email sent.** Failure: **Could not send email.**

**Internal notes** are staff-only. Enter text and click **Add note**. Notes appear under **Internal notes** and in the audit trail; they are not a substitute for the customer-facing status message.

**Attachments** accept staff uploads (PDF and common images, max 10 MB). Download by clicking the file name. Messages: **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** lists date, event, employee, and details (status transitions and messages). Typical events: customer submitted the statement, customer confirmed the legal statement, status updated, confirmation email sent, document added, internal note added.

Use **Back to list** to return to **Withdrawals**.

### 3.7 Order side panel in the back office

On PrestaShop 1.7.7 and newer, open an order in the back office. When that order has withdrawal cases, a **Withdrawal requests** side block lists each reference, status badge, date, and **View** (opens the case). On older 1.7 builds without the side-order hook, use **Customers** → **Withdrawals** and filter by order reference.

Pending cases can also raise a back-office warning with a count of requests pending review and a link to the list.

## 4. Storefront

No storefront screenshots are included here; wire the theme and check the live shop after saving Settings and clearing cache.

### 4.1 Footer

With **Footer button** on and the correct hook, pages show the withdrawal button (label from **Button label**) styled with **Button color**, plus **Track withdrawal status** when public tracking is on. **Footer alignment** and **Footer theme** control layout and text contrast. If the theme never calls the selected footer hook, change the hook or place the custom hook in a template and select that option under **Footer button hook**.

### 4.2 Customer account

With **Link in customer account** on, My Account shows the withdrawal entry (and track link where the account template includes it). Excluded customer groups see no entry points.

### 4.3 Order detail

With **Link on order detail** on, eligible orders show the withdrawal button pre-filled for that order. Existing cases for the order are listed with status. Ineligible orders show a short reason instead of the button, for example period ended, status not allowed, duplicate active request, or no eligible products.

### 4.4 Guest access

When **Guest access** is on, a visitor opens the form, enters order reference and email, then continues like a logged-in customer for that order. When guest access is off, guests see that they must log in (or you must enable guest access in Settings). Invalid security tokens and too many attempts show clear wait / retry messages.

### 4.5 Track status

**Track withdrawal status** asks for withdrawal reference (format like RBP-…) and email, then shows status, submitted date, scope, confirmation email state, and links to details and print. Wrong pair: **No withdrawal found for these details.**

### 4.6 Status page and print

After submit, **Withdrawal submitted** shows the reference, checklist (statement saved, confirmation email, shop will process), then **View withdrawal details**, **Track status**, and **Print / save PDF**. The status page lists products, quantities, prices, totals, and **Withdrawal history** including staff messages from status updates. Print opens a printable proof page using a secure token from the confirmation flow.

## 5. Problems

### 5.1 Free Return Button still enabled

**Symptom:** configuration is blocked; alert that the other return module is enabled; saves may show that changes were not saved until that module is disabled.

**What to do:** **Modules** → **Module Manager** → find the free Return Button module → **Disable**. Then open Return Button Pro again.

### 5.2 Footer button missing

**Symptom:** no withdrawal button in the footer.

**What to do:** confirm **Module enabled** and **Footer button** are on. On **Settings**, set **Footer button hook** to Auto or try the other footer positions one by one. Clear cache and hard-refresh the shop. For custom themes, place the custom module hook in the template and select that option in **Footer button hook**. Open **Dashboard**: it shows the detected theme profile and the active footer hook name so you can compare with the theme.

### 5.3 “Return not available — the withdrawal period has ended.”

**Symptom:** order detail or form blocks withdrawal with this message.

**What to do:** check **Withdrawal period** and **Order state = delivered**. Fix order history if delivery was never recorded. Extend the period only if your terms allow it.

### 5.4 “An active withdrawal request already exists for this order.”

**Symptom:** customer cannot open a second case.

**What to do:** finish or close the existing case (**Refunded** / **Rejected**), or temporarily turn off **Block duplicate active requests** only if your process truly allows multiple open claims.

### 5.5 “This order status does not allow withdrawal.”

**Symptom:** order is outside the allowed status filter.

**What to do:** on **Settings**, set **Allowed order statuses** to **All order statuses**, or add the current order state to **Allowed for withdrawal**.

### 5.6 “No products in this order are eligible for withdrawal.” / exclusion message on lines

**Symptom:** every line excluded, or selected partial lines invalid.

**What to do:** review excluded products, variants, categories, manufacturers, and suppliers. Adjust **Exclusion message** so customers understand why.

### 5.7 “Withdrawal is not available for your customer account.”

**Symptom:** form or buttons hidden for a logged-in customer.

**What to do:** remove the customer’s group from **Excluded customer groups**, or move the customer to an allowed group.

### 5.8 “Please enter a message for the customer when changing the status.”

**Symptom:** status update fails in the case view.

**What to do:** fill **Message to customer**, or turn off **Require message to customer when changing status** if your process allows empty messages.

### 5.9 Confirmation email not sent

**Symptom:** case shows email not sent; customer has no durable confirmation.

**What to do:** fix PrestaShop mail settings, check spam, use **Resend confirmation email**. Set **Notification email** for staff copies. Confirm the shop contact email works.

### 5.10 Guest cannot find the order

**Symptom:** **No order found for the given details.** or rate-limit wait.

**What to do:** match exact order reference and order email. Wait if too many attempts. Confirm **Guest access** is on.

### 5.11 Updates check fails or stays silent

**Symptom:** manual check does not report a version.

**What to do:** ensure curl works and the server can reach MyPresta.eu. Disable the free module if Pro is blocked. Retry **Manual Check** on the **Updates** tab.

## 6. For developers

### 6.1 Overview

- Technical name: `rbpro`
- Version: current 1.7–9 package (e.g. 1.4.6); PrestaShop 1.6 ships as a separate package (e.g. 1.4.5) with `ps_versions_compliancy` min `1.6.0.0`
- Display name: Return Button Pro
- Author: MyPresta.eu
- Tab: `front_office_features`
- Main class: `Rbpro`
- `ps_versions_compliancy` on the 1.7–9 package: min `1.7.0.0`; on the 1.6 package: min `1.6.0.0`
- Service layer: `RbpWithdrawalService`; security: `RbpSecurity`; theme/hooks: `RbpCompatibility`; analytics: `RbpStatsService`
- Flow: Configuration keys → hooks / front controllers → `rbp_withdrawal*` tables → admin `AdminRbpWithdrawal` → customer status/track/print

### 6.2 Important files

| Path | Role |
|---|---|
| `rbpro.php` | Module bootstrap, install/uninstall, configure tabs, hooks, defaults |
| `classes/RbpWithdrawal.php` | Case object model and statuses |
| `classes/RbpWithdrawalService.php` | Eligibility, deadlines, create/confirm, emails, status updates |
| `classes/RbpSecurity.php` | CSRF, guest grant, rate limit, IBAN sanitize |
| `classes/RbpCompatibility.php` | Theme profile, footer hook resolution, admin URLs, required hooks |
| `controllers/admin/AdminRbpWithdrawalController.php` | List and case view |
| `controllers/front/form.php` | Two-step form |
| `controllers/front/confirm.php` | Success page |
| `controllers/front/track.php` | Public track |
| `controllers/front/status.php` | Case details for customer |
| `controllers/front/print.php` | Printable proof |
| `sql/install.sql` | Creates `rbp_*` tables |
| `sql/uninstall.sql` | Comment only — tables kept |
| `lib/updateChecker.php` | MyPresta update UI (`rbproUpdate`) |
| `views/templates/admin/*` | Dashboard, configure shell, case view, order side notice |
| `views/templates/front/*` | Form, confirm, track, status, print, error |
| `views/templates/hook/*` | Footer/account/order buttons (classic / hummingbird) |
| `mails/*` | `rbf_withdrawal_customer` / `rbf_withdrawal_admin` templates |
| `translations/*.php` | Pack translations |

### 6.3 Controllers

| Controller | Parent / entry | Notes |
|---|---|---|
| Configure (`getContent`) | Module Manager | Tabs `rbp_tab`: `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false; view-only create path; export CSV; attachment download |
| Front `form` | Module link | Steps 1–2; guest lookup; draft cookie |
| Front `confirm` | Module link | Success after submit |
| Front `track` | Module link | Reference + email |
| Front `status` | Module link | Timeline + products |
| Front `print` | Module link | HMAC token on reference |

Permissions follow the admin tab. Front controllers require module enabled for the form; tracking respects `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hooks

Registered: `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton`; on PS ≥ 1.7.7 also `displayBackOfficeHeader`, `displayAdminOrderSide`.

Module-executed: `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (and status-related hooks from the service where defined).

Footer output runs only for the hook name resolved by `RbpCompatibility::getFooterHookName()`.

### 6.5 Overrides

No class or controller overrides. Theme integration uses hooks and selectable templates only.

### 6.6 Database

| Table | Content |
|---|---|
| `PREFIX_rbp_withdrawal` | Case header: shop, order, customer, reference, scope, type, status, IBAN, message, IP, UA, lang, email flags, deadline, dates |
| `PREFIX_rbp_withdrawal_product` | Selected lines and quantities |
| `PREFIX_rbp_withdrawal_note` | Internal staff notes |
| `PREFIX_rbp_withdrawal_attachment` | Staff uploads metadata |
| `PREFIX_rbp_withdrawal_history` | Audit events |

Uninstall does **not** drop these tables. `ensureDatabase()` creates missing tables and can migrate from `rbf_*` when Pro tables are empty and free tables have rows.

### 6.7 Configuration keys and translations

Defaults from `Rbpro::CONFIG`:

| Key | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Multilang (not in `CONFIG` array, installed by defaults): `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime: `RBP_ADMIN_FOLDER`. Update prefs use MyPresta update checker keys. Free-module migration maps `RBF_*` → `RBP_*` when Pro keys are empty.

Translations: `translations/{iso}.php`. Field `desc` strings live in `renderConfigurationForm()` via `$this->l()`.

Statuses: `pending`, `confirmed` (label Registered), `processing`, `refunded`, `rejected`.

### 6.8 Extending

Override hook TPL/CSS in the theme for `modules/rbpro/...` without editing the module. Place `{hook h='displayRbproButton'}` for custom button placement. Listen to `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed`. Do not rely on overrides — there are none to cascade.

## 7. Support

Product page: https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

For help with this paid module: log in to your customer account on mypresta.eu, open Contact, and choose **Support for paid modules**. The form requires login for paid modules; after login, select Return Button Pro from your purchase history.