---
title: "Quote Enterprise - merchant manual"
sidebar:
  label: "Quote Enterprise - merchant manual"
description: "How to configure Quote Enterprise, run the full quote-to-order process, and fix common problems."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Quote Enterprise Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/quote-enterprise/)
>
> ---


## 1. Requirements

The module runs on PrestaShop 1.7, 8 and 9, and on PHP 7.1 through 8.5.

The server needs cURL and JSON. It does not need another module.

You create Google reCAPTCHA keys yourself only if you turn reCAPTCHA on. Slack or Teams webhooks are optional and only for staff digests. Reminder e-mails and digests need a server cron job on the module cron URL.

## 2. Installation

1. Upload the module in **Modules**, **Module Manager**, and enable it.
2. After installation, **Orders** has two entries: **Quotes** and **Audit log**.
3. The module does not clear the cache during installation.
4. Installation creates the quote tables and a hidden virtual product for custom service lines. It also writes the default settings described below.

Uninstall removes the menu entries, the module tables and the configuration keys. The hidden fee product in the catalog is not deleted by uninstall.

## 3. Configuration and back-office work

Open **Modules**, **Module Manager**, **Quote Enterprise**, **Configure**. The module opens on **Dashboard**. The top bar has: **Dashboard**, **Quotes**, **Audit log**, **Settings**, **PDF**, **Emails**, **API**, **Notifications**, **Updates**.

Screenshots in this manual come from an English back office.

Day-to-day quote work also lives under **Orders**, **Quotes** (full list and editor) and **Orders**, **Audit log**.

### 3.1 Full quote process

Use this flow as the map. The sections below explain each screen.

1. A customer requests a quote from a product page, a product list, the cart, or a multi-product quote list. Guests may see buttons if allowed, but saving the request always needs a customer account.
2. The request becomes a quote in **Pending review** (customer request) or staff create a **Draft** from the back office.
3. Staff open the quote under **Orders**, **Quotes**, set prices, discounts, shipping and messages, then **Save** or **Save & send**.
4. **Save & send** e-mails the customer and moves the quote to **Sent** (or keeps negotiation flow when re-sending).
5. The customer opens **My quotes**, views the offer, may download PDF, accept, reject, or ask for changes (**Negotiation**).
6. After **Accepted**, the customer can checkout. Checkout builds a cart from the quote and can become an order (**Converted**). The quote then locks.
7. Past **valid until**, sent or negotiation quotes become **Expired** when opened or when cron runs. Reminder e-mails need cron.

Statuses you will see: **Draft**, **Pending review**, **Sent**, **Negotiation**, **Accepted**, **Converted**, **Expired**, **Rejected**, **Cancelled**.

Only **Sent** and **Negotiation** can be accepted by the customer. Change status manually in the editor when needed.

### 3.2 Dashboard

The dashboard shows the quote pipeline. Open **Analytics parameters** to set the KPI period and chart ranges, then click **Save analytics parameters**. Confirmation: **Tracking parameters updated.**

![Dashboard](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Dashboard tables](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Field | At the start | What it does |
|---|---|---|
| **KPI period** | **Last 90 days** | Time window for KPI cards, funnel table, top customers and staff. Choose 30, 90, 180 or 365 days and save. Counts created, sent, accepted, converted and rejected quotes in that period. |
| **Weekly chart range** | 12 | Number of weeks on the weekly funnel chart (4–52). Weekly tab shows created, sent, accepted and converted per ISO week. |
| **Monthly chart range** | 12 | Number of months on the monthly funnel chart (3–24). |
| **Yearly chart range** | 5 | Number of years on the yearly funnel chart (2–10). |
| **Default chart tab** | **Monthly** | Which chart tab opens first: Weekly, Monthly or Yearly. You can still switch tabs without saving. |
| **Expiring soon window** | 7 | How many days ahead to flag quotes as expiring soon. Typically 7 or 14. Only sent and negotiation quotes with a valid_until date in this window are listed. |

KPI cards: open pipeline value, pending review, expiring soon, converted value, conversion rate, win rate. Below: created, sent, accepted, converted, rejected, average days to convert, average quote value. Charts show the funnel over time. Tables: period funnel, open pipeline aging, expiring soon, recent activity, top customers and staff. Open pipeline means sent, negotiation or accepted quotes.

### 3.3 Quotes tab in module configuration

This tab is a short overview. Full filters, bulk actions and the editor are under **Orders**, **Quotes**.

![Quotes overview](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Purpose of this screen: a quick list of recent quotes from module configuration. Click **View** to open the full quote editor. Use **Manage all quotes** for filters, export and bulk operations. Effect: keeps module settings lightweight while full quote work happens in the dedicated back-office screen.

**Create quote:** select a customer (search), optionally type an **Internal note**, click **Create draft quote**. You are redirected to the full editor. Empty customer shows **Please select a customer.**

**Quote templates** (when templates exist): pick a template and a customer, then **Create from template**.

**Recent quotes** columns: Reference, Customer, Status, Total. Empty: **No quotes yet.** Links: **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Quotes list (Orders menu)

Open **Orders**, **Quotes**. This is the main management screen.

Columns: **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Row actions: edit and duplicate. You cannot add a blank quote from the list toolbar; create from the module overview, from a template, or by duplicating. Error if you try: **Create quotes from module configuration or duplicate an existing quote.**

Bulk actions:

| Action | What it does |
|---|---|
| **Assign to employee** | Sets the assigned employee on the selected quotes. |
| **Extend validity** | Pushes valid until forward for the selection. |
| **Send expiry reminder** | Sends reminder e-mails to selected customers (confirm dialog). |
| **Export CSV** | Downloads CSV for the selection. |
| **Export XML** | Downloads XML for the selection. |

Filter by status and search as on a standard PrestaShop list. Open a row to edit.

### 3.5 Quote editor — how to manage a request

Open a quote from the list. The legend shows the reference and status, for example `Q-2026-00001 — Pending review`.

**Typical staff path for a new customer request**

1. Filter or open quotes in **Pending review**.
2. Check **Messages from customer** (request text, later change or decline reasons). Read-only.
3. Add or adjust **Line items** (catalog products and custom services).
4. Set **Global discount %** / **Global discount amount**, **Shipping label** and shipping amounts.
5. Write **General message to customer** and optionally **Internal note**.
6. Set **Validity period** and **Validity unit**, check current valid until.
7. Set **Status** if needed, then **Save** (**Quote saved.**) or **Save & send** (**Quote sent to customer by e-mail.**).

**Locking.** Accepted or converted quotes lock. Expired quotes show: **This quote has expired. Click Unlock to extend validity and send an updated offer.** Converted: **This quote is locked because it was converted to an order.** Accepted: **This quote is locked because the customer accepted it. Click Unlock to make changes.** Unlock: **Quote unlocked for editing.** Lock again: **Quote locked again.**

| Field | What it does (from field descriptions) |
|---|---|
| **Status** | Current stage in the sales workflow. Draft: internal only. Pending review: customer requested, awaiting your pricing. Sent: e-mailed to customer. Accepted: customer agreed. Converted: became an order. Only Sent and Negotiation can be accepted by the customer. Change status manually when needed. |
| **Validity period** | How long the customer has to accept, counted from save/send. Examples: 15 with Minutes, 1 with Hours, 30 with Days. Save recalculates expiry from now. Customer cannot accept after expiry. Short periods may expire before daily cron sends reminders. |
| **Validity unit** | Minutes, hours or days with the validity number. |
| **Payment hint** | Short note about expected payment, e.g. "30 days net transfer". Shown on customer view and PDF. Does not force a payment module. |
| **Global discount %** | Extra discount 0–100 on all product lines before shipping. At checkout it can apply as a cart rule. |
| **Global discount amount (tax excl.)** | Fixed discount on product subtotal. Percent is applied first when both are set. |
| **Shipping label** | Name on PDF, e.g. "Express delivery". |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Delivery charge. Tax incl. auto-calculates from excl. when a tax rule is set in module settings. Included in total and passed to checkout as fixed shipping. |
| **Messages from customer** | Everything the customer wrote (request, change request, decline). Read-only. Reply in the fields below. |
| **General message to customer** | Standing message always visible to the customer (scope, lead time, terms). Shown on quote view, PDF and e-mails. |
| **Internal note** | Private team note. Never shown to the customer. |
| **Line items** | Product lines and custom service lines. Add a catalog product (pick combination when required). Add a custom line: description, qty, unit price tax excl., tax %. Custom lines appear on PDF and at checkout go into the fee product. Messages: **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | One-time note for this **Save & send** only. Explains what changed. Cleared after send. Appears in timeline, optional PDF history, and that send’s e-mail. |
| **Version history** | Snapshots of previous versions. |
| **Save as template** | Enter a template name and save. Later create new quotes from that template for another customer. Messages: **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Chronology of staff and customer events on this quote. |

Duplicate from the list or editor: **Unable to duplicate quote.** on failure. After duplicate you edit the copy.

### 3.6 Audit log

Module tab: recent activity (requests, sends, accept/reject, negotiations). Use **View** for full context. Open **Orders**, **Audit log** for filters, export and full history.

Purpose: append-only trail for compliance and troubleshooting. Entries cannot be edited or deleted. Each row stores the actor name and ID (employee or customer) at the time of the action. Actor badges: Employee, Customer, System.

### 3.7 Settings — Theme & display

Open **Settings**. Click **Save** at the bottom after changes.

![Theme and display](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Field | At the start | What it does |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Selects which template and CSS set is used for My quotes, quote preview and customer account link. Leave on Auto-detect unless your theme fork is misdetected — then force Classic or Hummingbird. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | How line quantities show on front office, back office, PDF and e-mails. Or **Fixed decimals (e.g. 1.000, 2.500)**. Form inputs use the same format for defaults. |
| **Quantity decimal places** | 3 | Digits after the decimal when format is fixed decimals. Typically 3 for B2B or 2 for retail. Ignored in integer mode. |

### 3.8 Settings — General

![General](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Field | At the start | What it does |
|---|---|---|
| **Module enabled** | **Yes** | Master switch for the entire quote-to-order feature. Yes: customers request quotes and staff manage offers. No: hide all quote buttons and customer account links without uninstalling. When disabled, no new requests and no buttons on cart, product or category pages. Existing quotes stay in the back office. |
| **Product page quote button** | **Yes** | Shows **Request a quote** on each product page. For B2B shops where buyers ask for a price on a single SKU. Customer must be logged in (or guest flow allowed) and in an allowed group. Instant mode opens the form for that product. List mode adds quantity and combination to the floating quote list. |
| **Cart quote button** | **Yes** | Shows **Request a quote** on the shopping cart. Enable when customers request offers for several products at once. Respects minimum cart total below. Current cart contents become the basis of a new quote request after confirm. |
| **Category / list quote button** | **Yes** | Compact **Request quote** on listing pages (category, search, new products). Same eligibility rules. Instant mode opens the product quote flow. List mode adds the product (default combination, qty 1) to the floating list. |
| **Product quote mode** | **Instant — open form for this product** | Instant: open the form for the current product. List: add to a quote basket; floating button opens one form with all products. Cart quote requests stay independent. Floating button appears only in list mode when the list is not empty. |
| **Floating quote button position** | **Bottom right** | Or **Bottom left**. Only when product quote mode is List. Badge shows product count; opens the multi-product request form. |
| **Allow guests** | **No** | Whether visitors without an account may start a request. Keep off for strict B2B. Enable if guests should see the button — they are still asked to log in or register before the request is saved. Does not create anonymous quotes. |

### 3.9 Settings — Quote button visibility

![Visibility](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Field | At the start | What it does |
|---|---|---|
| Customer groups | all groups | Restricts who can see quote buttons. All groups, or only selected groups (e.g. Wholesale). Customers outside selected groups will not see buttons even when the module is enabled. |
| **Enable catalog visibility rules** | **No** | Turn catalog-based quote button rules on or off. Enable to limit quotes to specific products, categories, brands or suppliers. When disabled, every product can be quoted (group rules still apply). When enabled, whitelist/blacklist and filters below are enforced. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist: buttons only on matching products. Blacklist: hide buttons on matching products. A product matches if it is in the product list or belongs to a selected category, manufacturer or supplier. |
| Catalog pickers | empty | Categories (tree), products (search), manufacturers and suppliers. Leave empty to apply only auxiliary filters. Rules combine with OR — one match is enough. |
| **Minimum product price** | 0 | Hide quote buttons below this tax-included storefront price. 0 disables. Applied when catalog rules are enabled. |
| **Exclude virtual products** | **No** | Prevent quoting downloadable / virtual products when catalog rules are enabled. |
| **Exclude out-of-stock products** | **No** | Hide buttons when the product cannot be ordered out of stock (respects PrestaShop out-of-stock behaviour). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | When the cart mixes quotable and non-quotable products: Show = button visible, only eligible lines imported; Hide = button hidden until the cart is only quotable. All eligible → always show. All excluded → always hide. |

### 3.10 Settings — Product quote request form

| Field | At the start | What it does |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Mandatory privacy checkbox on the product quote request modal (GDPR). Customers must accept before submit. |
| **Privacy policy CMS page** | none | CMS page linked from the checkbox. If empty, checkbox text has no link. |
| **Enable reCAPTCHA** | **No** | Protect the product quote request form with Google reCAPTCHA v2. When enabled, site and secret keys below are required. |
| **reCAPTCHA site key** | empty | Public site key from Google reCAPTCHA admin (v2 checkbox). |
| **reCAPTCHA secret key** | empty | Secret key. Stored in shop configuration. |
| **Minimum cart total** | 0 | Minimum cart value before the cart quote button is shown. Shop default currency. 0 = no minimum. Only affects the cart button, not single-product requests. Small carts will not show the button. |

### 3.11 Settings — Offers & references

| Field | At the start | What it does |
|---|---|---|
| **Default validity** | 30 | Default duration a quote stays valid after creation. Number plus unit: minutes for flash offers, hours for same-day decisions, days for standard B2B. Sets valid_until on new quotes from storefront, back office and duplicates. Override per quote in the editor. |
| **Default validity unit** | **Days** | Minutes, hours or days with the number above. Reminder e-mails and automatic Expired status still rely on cron for reminders. |
| **Expiry reminder (days before)** | 3 | Reminder e-mail before expiry. Sent only by the daily cron job. Each eligible quote gets at most one reminder with a link to view and accept. Without cron, no reminders. |
| Cron URL | generated token | Automated expiry reminders and status updates. Add the URL to crontab once per day (example 08:00). Regenerate token if exposed. Expiry is also enforced when anyone opens the quote; reminder e-mails still need cron. |
| **Reference prefix** | Q | Prefix for quote numbers. Module appends year and sequence, e.g. Q-2026-00042. Helps staff and customers recognize documents in e-mail and PDF. |
| **Notify staff on new request** | **Yes** | E-mail to shop staff when a customer submits a request. Ensure Preferences > Contact e-mail is correct. Template: qe-request-staff in Emails tab. |

Yellow notice on screen: cron is required for validity automation; expiry also applies on open; reminders use the cron URL.

### 3.12 Settings — Checkout

| Field | At the start | What it does |
|---|---|---|
| **Shipping / service tax rule** | shop default tax rule | VAT rule for shipping and custom service lines when you enter tax-exclusive amounts. Pick a tax rules group from Catalog → Products. When selected, saving a quote recalculates shipping tax-incl from tax-excl. |
| **Fee product (custom lines)** | created on install | Hidden virtual product that carries custom service lines into checkout. Created automatically — change only if you must point custom lines at a different product. At checkout, service totals become one cart line with the locked quote price. |

### 3.13 PDF

Open the **PDF** tab. Legend: **PDF documents**. When PDF is disabled, download buttons are hidden and PDF URLs return not found.

| Field | At the start | What it does |
|---|---|---|
| **Enable PDF** | **Yes** | Master switch for PDF generation and download links. Disable if you do not want PDF proformas. When off, PDF buttons are hidden in back office, storefront and order detail; direct PDF URLs return not found. E-mail templates still get an empty PDF URL placeholder. |
| **Use shop logo on PDF** | **Yes** | Uses shop logo from Preferences > Themes. No: use only a custom logo uploaded below (if any). Logo appears at the top of PDF / proforma documents. |
| **Add negotiation history to PDF** | **No** | Append a short communication log (change requests, re-sends, accept, decline). Compact table before terms. Empty when there is no negotiation activity. |
| **Custom PDF logo** | empty | Optional PNG or JPG for quote PDFs only. Overrides shop logo when present. |
| **PDF terms & conditions** | empty | Legal or commercial terms at the bottom of every PDF. |
| **Authorized signature** | empty | Signatory name or line, e.g. "John Smith, Sales Director". Leave empty to omit. |

### 3.14 Emails

Open the **Emails** tab. Transactional e-mails for the quote lifecycle. Edit subject and body per language. Use placeholders from the editor sidebar (customer name, quote reference, link, totals). Built-in keys: qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Customers and staff receive these when a quote is requested, sent, accepted, or about to expire. Test after changes.

### 3.15 API

Open the **API** tab. Connect CRM, ERP or automation. Enter a key label and **Generate new API key**. Copy the key. **Revoke** disables it (confirm). Empty: **No API keys yet.** **API documentation** describes actions: list, get, pending, stats, update_status. Call the module API URL with the key.

### 3.16 Notifications

Open **Notifications** (**Staff digest notifications**). Periodic summary when quotes need action, without one e-mail per event.

What counts as waiting: **Pending review** (new request) or **Negotiation** (customer asked for changes). Sent, accepted, expired and converted are not included. Cron runs on your schedule. When digest is enabled, at least one quote is waiting, and the interval has elapsed, a message goes to every configured channel. Staff see a summary with references, status, customer name and back-office links (up to 20 quotes listed).

| Field | At the start | What it does |
|---|---|---|
| **Enable digest** | **No** | Master switch. Enable after at least one channel is set. Cron must be scheduled — digests are not sent by page visits. When off, cron still handles expiry reminders and status updates, but no digest. |
| **Interval (hours)** | 24 | Minimum time between digests (1–168). Run cron at least as often as this value. After a successful digest, the next waits until this many hours pass. |
| **E-mail recipients** | empty | Comma- or semicolon-separated. Empty uses shop e-mail from Preferences > Contact. Template qe-staff-digest. |
| **Slack webhook URL** | empty | Incoming webhook URL. Leave empty to skip Slack. |
| **Teams webhook URL** | empty | Connector webhook URL. Leave empty to skip Teams. |

**Save** stores settings. **Send test digest now** sends a test when quotes are waiting. Same cron URL as Settings.

### 3.17 Updates

Open **Updates**. **Check Now** checks for a new version. **Automatic Notifications** enabled or disabled. **Save** stores update settings.

### 3.18 Quote block on an order

On an order created from a quote, the back office shows **Source quote** with a link to the quote and optional **View quote PDF**.

## 4. Front office

Customers see quote tools when the module is enabled and their group is allowed.

**Product page.** **Request a quote** opens the form (instant) or adds to the quote list (list mode). Privacy checkbox and reCAPTCHA apply when enabled.

**Product list.** **Request quote** — same rules.

**Cart.** **Request a quote** — respects minimum cart total and mixed-cart rules. Confirmed cart becomes a pending quote.

**List mode.** Floating button with a count opens the multi-product request form.

**Customer account.** Link to **My quotes**: history, status, valid until, **View**, PDF when enabled, **Checkout** after accept, **Request re-opening** when expired/locked. Empty: **You have no quotes yet. Request a quote from a product page or your cart to get started.** After submit: **Your quote request has been submitted. Our team will prepare an offer shortly.**

**Quote view.** Accept, reject, request changes, download PDF, checkout when accepted. Locked expired: **Locked — validity expired**.

Guest visitors may see buttons if **Allow guests** is **Yes**, but the request is saved only for a logged-in customer.

There is no storefront screenshot in this pack because the test shop was not reachable when screens were finished.

## 5. Common problems

**No quote button on product or cart.** Check **Module enabled**, the matching button switch, customer group, and catalog visibility. For the cart, check **Minimum cart total** and **Mixed cart**.

**Guest cannot finish a request.** Submission always needs an account.

**Quote is locked / cannot edit.** Unlock if accepted or expired (extend validity). Converted quotes stay locked to the order.

**Customer cannot accept.** Status must be Sent or Negotiation, and valid until must be in the future.

**Reminder e-mails never arrive.** Schedule the cron URL and keep **Expiry reminder** above zero. Opening a quote can expire it without cron; reminders still need cron.

**PDF buttons missing.** Turn **Enable PDF** on.

**reCAPTCHA blocks the form.** Turn it off, or enter both keys.

**Staff digest never arrives.** Enable digest, set a channel, run cron at least as often as the interval.

**Uninstalled and menu is gone.** Reinstall. Uninstall drops quote tables. The fee product may remain in the catalog.

## 6. Developer guide

### 6.1 Overview

Technical name `quoteenterprise`, version 1.7.6, class `quoteenterprise` extends `Module`. Display name via `$this->l('Quote Enterprise')`. Author MyPresta.eu. Tab `checkout`. Product URL in `$this->mypresta_link`.

Flow: request → `quote` row → staff edit/send → customer accept/negotiate → checkout → order. Field copy for merchants lives in `QuoteSettingDescTrait` and quote-editor `desc*` methods.

### 6.2 Files

- `quoteenterprise.php` — install, hooks, configuration entry, cron URL.
- `classes/QuoteAdmin.php` — configure tabs and settings forms.
- `classes/QuoteAdminQuoteForm.php` — quote editor.
- `classes/QuoteQuotesManager.php` — overview, save/send/lines/templates.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Controllers

Admin under **Orders** (`AdminParentOrders`). Front controllers in `$this->controllers`. Cron expects `QE_CRON_TOKEN`. API expects an active key and an action name.

### 6.4 Hooks

Registered: `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. No custom hooks exposed.

### 6.5 Overrides

This module does not ship class or controller overrides.

### 6.6 Database

| Table | Contents |
|---|---|
| `quote` | Quote header. |
| `quote_detail` | Lines. |
| `quote_revision` | Version snapshots. |
| `quote_audit_log` | Append-only activity. |
| `quote_api_key` | API keys. |
| `qe_cart_quote` | Cart–quote link. |

Uninstall drops these tables. `QuoteSchema::ensure` and `inconsistency()` repair missing pieces when configuration is opened.

### 6.7 Keys and translations

`QE_*` configuration keys. Defaults in `installDefaults()`. New language: `translations/{iso}.php`. Merchant field help: `QuoteSettingDescTrait` and editor `desc*` methods. Strings via `$this->l()` and `{l s=... mod='quoteenterprise'}`.

### 6.8 Extending

Override front templates under `modules/quoteenterprise/` in the theme. Classic and Hummingbird are supported. A different PDF layout means changing the PDF template or module code.

## 7. Support

Module page: [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

To write about this module, log in to your customer account on [mypresta.eu](https://mypresta.eu/), open [Contact](https://mypresta.eu/contact.html) and choose the subject **Support for paid modules**. The form says login is required. After you log in, pick this module from your purchase history.
