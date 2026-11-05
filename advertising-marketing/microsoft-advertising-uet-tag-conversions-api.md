---
title: "Microsoft Advertising UET Tag & Conversions API - documentation and user manual"
description: "Use this manual to configure tracking, verify events with live diagnostics, and fix problems after installing the module."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Microsoft Advertising UET Tag & Conversions API Module on MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Requirements

Prepare the shop, Microsoft Advertising account, and scheduled task before configuration.

- Use PrestaShop 1.7, 8, or 9.
- Use PHP 7.1–8.x, according to the PHP version required by your PrestaShop installation.
- Enable the PHP cURL, JSON, OpenSSL, and hash extensions.
- Have a Microsoft Advertising account and a UET Tag ID. Also obtain a Conversions API bearer token for **Conversions API** or **UET + CAPI**.
- Have access to CRON when using CAPI, because its queue must run regularly.
- Configure an external CMP or cookie module before turning **Require marketing / analytics consent** to **Yes**.
- No other PrestaShop module is required. A Microsoft Merchant Center feed module is optional and can help align catalog IDs.

## 2. Installation

1. Open **Modules > Module Manager**.
2. Click **Upload a module** and upload the ZIP file.
3. Install **Microsoft Advertising UET / Conversions API**.
4. Find it in **Module Manager** and click **Configure**.
5. Complete **Setup Wizard** or configure all tabs manually.

The module does not create a visible **Catalog** menu item. Its data endpoint is a hidden back-office tab used internally.

Installation does not clear the PrestaShop cache. Clear it under **Advanced Parameters > Performance** only if old assets or an old configuration screen remain visible.

Uninstalling removes the module's event log, multi-tag rules, CAPI queue, hidden endpoint, and module configuration keys. Update-checker keys may remain. Reinstalling starts with default settings and does not restore deleted events or rules.

## 3. Configuration and back-office work

Open **Modules > Module Manager**, find **Microsoft Advertising UET / Conversions API**, and click **Configure**.

Follow this process:

1. Complete **Setup Wizard**.
2. Confirm the channel and credentials in **Tracking mode**.
3. Select signals in **Events**.
4. Match event product IDs to your feed in **Catalog IDs**.
5. Configure **Privacy & consent**.
6. Define paid and refund behavior in **Order lifecycle**.
7. Add **Multi-tag rules** only for context-specific credentials.
8. Schedule the displayed CRON URL every 1–5 minutes when CAPI is active.
9. Browse the storefront and verify events in **Live Statistics** and **Health & diagnostics**.
10. Confirm the events in Microsoft Advertising.

Screenshots in this manual come from an English back office.

### 3.1 Setup Wizard

Use the wizard for first-time setup. It guides you through **Mode**, **Tag ID**, **CAPI token**, **Test**, and **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Field | On start | What it does |
|---|---|---|
| **Mode** | Not selected | Choose **UET Tag** for browser tracking, **Conversions API** for server tracking, or **UET + CAPI** for both. Dual mode uses a shared event identifier for deduplication. |
| **Tag ID** | Empty | Paste the ID from Microsoft Advertising under UET Tag or Conversion Tracking. It is required in every mode. |
| **CAPI token** | Empty | In CAPI or dual mode, paste the bearer token from the Conversions API section of the UET Tag. Treat it as a password. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Yes | Collect Microsoft click and anonymous visitor identifiers in CAPI-capable modes without making UET tracking calls. Keep it enabled for stronger matching and session continuity. |
| **Test** | Not run | In UET mode, validate the Tag ID and then verify a storefront page view. In CAPI-capable modes, click **Send test purchase** to send a €1 test purchase. Allow 10–30 minutes for Microsoft Advertising to show it. |
| **Done** | Incomplete | Finish setup and open shortcuts to **Tracking mode**, **Health & Data Quality Coach**, or **Live Statistics**. |

Use **Start over** to run the wizard again. Existing credentials remain pre-filled until changed.

### 3.2 Tracking mode and credentials

Select how all events reach Microsoft Advertising, complete the fields shown for that mode, and click **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Field | On start | What it does |
|---|---|---|
| **Tracking mode** | Not selected | **UET Tag** sends from the browser. **Conversions API** queues server events. **UET + CAPI** sends both with the same event ID so Microsoft can deduplicate them. |
| **Tag ID(s)** | Empty | Type a UET Tag ID and press comma or Enter. The ID is required for UET, CAPI, and dual mode. |
| **Conversions API token** | Empty | Paste the bearer token from **Microsoft Advertising > UET tag > Use Conversions API > Copy Token**. |
| **CAPI endpoint override (advanced)** | Empty | Leave empty to use Microsoft's standard destination. Set it only when Microsoft documents a custom host for your account. |
| **Ghost collector (CAPI)** | Yes | Capture `msclkid` and anonymous visitor ID for CAPI matching. It does not call UET tracking. |
| **Bing ID Sync (remarketing)** | Yes | When UET is active, send the anonymous visitor ID through Bing ID Sync to improve remarketing audience matching. |

For CAPI or dual mode, copy the displayed **CRON URL** to your scheduler and run it every 1–5 minutes.

### 3.3 Events

Select and save a tracking mode first. Then enable only the signals you need and click **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Field | On start | What it does |
|---|---|---|
| **PAGE_VIEW** | Yes | Record every storefront page load. It supports traffic reporting and attribution; turning it off does not stop other events. |
| **view_item (+ select_item)** | Yes | Send `view_item` on product pages and `select_item` when a product is clicked in category, search, or bestseller lists. |
| **view_item_list** | Yes | Send approximately the first 20 products from category, search, and bestseller-style lists with IDs, names, prices, and positions. It has its own switch. |
| **add_to_cart** | Yes | Record cart additions. UET and dual mode use the native cart event plus optional CSS fallback. CAPI-only mode uses the server path and does not need CSS selectors. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Yes | Record cart removals as **Other**, because Microsoft has no native remove-from-cart type. |
| **CHECKOUT** | Yes | Fire when the customer enters the cart or order flow and mark purchase intent. |
| **CHECKOUT details** | Yes | Add value, currency, and product data to **CHECKOUT**. Turning it off sends minimal parameters. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Yes | Fire on the payment step as **Other**. Use it as an optional late-funnel signal for Live Statistics. |
| **purchase** | Yes | Send **OffMicrosoftPurchases** with order value, currency, and product lines. A stable client deduplication ID makes refreshes safe. Use **Order lifecycle** to delay it until payment. |
| **SEARCH** | Yes | Record storefront searches with the search term. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Yes | Record wishlist additions as **Other** when the theme exposes compatible controls. |
| **SIGN_UP (Signup)** | Yes | Send **Signup** when a customer account is created. |
| **LEAD / SUBSCRIBE (newsletter)** | Yes | Send **Lead** for newsletter subscriptions. Disable it if another tool tracks the same conversion. |
| **LEAD (legacy product interest)** | No | Preserve the old product-interest Lead behavior. Leave it off unless a historical campaign requires it; using it with `view_item` can inflate leads. |
| **CONTACT** | Yes | Fire when the contact form is submitted, using server and browser fallback detection. |
| **REFUND (Microsoft: Other)** | Yes | Fire when an order reaches a configured refund or cancellation state. Microsoft receives it as **Other** for local correction and statistics. |
| **Rich product payloads (productId / items)** | Yes | Include product IDs, quantities, and prices. Turning it off leaves minimal value/currency data except where list or click events require IDs. Keep it on for catalog matching. |
| **Add to cart CSS selector** | `.add-to-cart` | In UET and dual mode, identify the product-page button when the theme does not fire the native cart event. |
| **Product price CSS selector** | `.current-price span` | In UET and dual mode, read the visible fallback price. A wrong selector sends zero; combine it with **Reformat price string** when necessary. |

For CAPI, enable **Advanced matching (email / phone)** and **Ghost collector (CAPI)** for better matching.

### 3.4 Catalog IDs and Catalog ID Doctor

Make event product IDs exactly match your Microsoft Merchant Center feed, click **Save**, then review **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Field | On start | What it does |
|---|---|---|
| **Product identification** | `id_product` | Choose the product ID, combination ID, or product ID plus separator plus combination ID. Combined IDs suit feeds that list variants. A different feed format prevents matching. |
| **Separator** | `-` | Separate product and combination IDs in combined mode. Product 12 and combination 5 become `12-5`. Use the same separator in the feed. |
| **Product ID prefix** | Empty per language | Add a language-specific value before every ID only when the feed uses it too. |
| **Product ID suffix** | Empty per language | Add a language-specific value after every ID only when the feed uses it too. |
| **Exclude free products** | No | Omit zero-priced products from cart and purchase product lines and value calculations. |
| **Force currency conversion** | No | Convert all monetary values to one target currency. Enable only when the shop currency is not accepted by Microsoft Advertising. |
| **Target currency** | Store-dependent selection | Select the destination currency. It is ignored while forced conversion is off. |
| **Reformat price string** | No | In UET or dual mode, clean formatted theme prices before the CSS add-to-cart fallback reads them. It is not used in CAPI-only mode. |

**Catalog ID Doctor** shows generated examples from an active product and combination, recent IDs found in event data, and hints about the selected base ID, separator, prefix, and suffix. If it reports **No active products found to validate catalog productId values**, activate a product and reopen the tab.

### 3.5 Privacy and consent

Configure an external consent source first. The module does not display a cookie banner.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Field | On start | What it does |
|---|---|---|
| **Require marketing / analytics consent** | No | Block UET, CAPI, and Ghost until consent is granted. Without a connected CMP, tracking remains silent. |
| **Default consent state** | `auto` | `auto` waits for cookie, TCF, or browser-event consent; `grant` allows immediately; `revoke` blocks until granted. Use `auto` with a banner and `grant` only with an appropriate lawful basis. |
| **IAB TCF 2.x (__tcfapi)** | Yes | Listen to a certified CMP. Purpose 1 plus one of purposes 2, 3, or 4 unlocks ads and updates Microsoft UET advertising-storage consent. |
| **Include logged-in customer ID** | No | Add the PrestaShop customer ID to logged-in context and diagnostics as an optional external-ID signal. Disclose it in the privacy policy. |
| **Advanced matching (email / phone)** | No | Send email and available hashed email/phone fields for improved UET and CAPI attribution. Ensure the privacy policy covers this. It is strongly recommended for CAPI. |
| **Ignore admin / employee traffic** | Yes | Skip storefront tracking when an employee session is detected. |
| **Simple bot filter** | No | Skip requests whose browser identification resembles a bot or crawler. This is heuristic. |

For an EU setup, configure the CMP, use `auto`, enable required consent, and keep TCF enabled when supported. Test both accept and decline in a private browser. The guide recognizes common marketing/statistics cookies, its own consent cookie, and its TCF result. Cookiebot callbacks are supported directly; other CMPs can dispatch the module's consent event.

### 3.6 Order lifecycle

Control when sales and refunds enter conversion reporting.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Field | On start | What it does |
|---|---|---|
| **Purchase only when paid** | No | Delay purchase until an order state is paid. Enable it when unpaid bank transfer or cash-on-delivery orders inflate conversions. |
| **Paid statuses** | Empty | Select an optional whitelist of paid states. Leave empty to use PrestaShop's built-in paid flag. A filled list is used when paid-only tracking is on. |
| **Refund / cancel statuses** | Empty | Select states that trigger Refund. Empty uses automatic detection from status names containing refund or cancel. The Refund event must also be enabled. |

For delayed payment, enable paid-only tracking, move a test order into a paid state, and verify that purchase appears once.

### 3.7 Multi-tag rules

Use rules when a shop, language, country, or currency needs different credentials. The first matching active rule wins in ascending **Position** order. Without a match, global credentials are used.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

The **Active rules** list shows **Tag ID**, CAPI token source, **Shop**, **Language**, **Country**, **Currency**, **Active**, and **Actions**. Click **Delete** and confirm to remove a rule. There are no edit or bulk actions; recreate a rule to change it.

| Field | On start | What it does |
|---|---|---|
| **Tag ID (UET)** | Empty | Set the UET Tag for matching traffic. It may be empty only for a token-only CAPI override. |
| **Conversions API token** | Empty | Override the global token. Empty inherits the token from **Tracking mode**. |
| **Shop** | **All shops** | Limit the rule to one multistore shop or all shops. |
| **Language** | **All languages** | Limit it to one storefront language or all languages. |
| **Country** | **All countries** | Limit it to the current customer-country context. |
| **Currency** | **All currencies** | Limit it to the current currency. |
| **Active** | Yes | Enable or disable the rule. Inactive rules are ignored. |
| **Position** | `0` | Set evaluation order. Lower numbers win when several rules match. |

Click **Add rule**. **Property rule saved** confirms success. If **Could not save rule — provide a valid Tag ID and/or Conversions API token.** appears, correct the Tag ID or supply a token.

### 3.8 Live Statistics

Open this tab in one window and browse the storefront in another. Events appear on the 30-minute real-time timeline.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** shows purchases without add-to-cart, add-to-cart without product detail views, refunds versus purchases, and CAPI/Ghost recovery. Use event checkboxes to filter the timeline; PageView is hidden by default. **Pause** stops polling without stopping tracking, and **Refresh** fetches current data.

| Field | On start | What it does |
|---|---|---|
| **Enable live dashboard** | Yes | Turn timeline polling on or off. Turning it off pauses the feed, while tracking and Health/Radar records continue. |
| **Also log PageView into the event database** | No | Add noisy PageView rows to the local log. It does not control Microsoft PageView firing or other event logging. Enable only for debugging. |
| **Keep events for (days)** | `14` | Purge rows older than this age. Accepted values are 1–365; 7–30 is typical. |
| **Live poll interval (seconds)** | `5` | Poll every 2–60 seconds. Lower values are faster but create more back-office requests. |

Use **Purge older than retention**, **Delete failed only**, or **Clear entire event log** for immediate cleanup. Clearing all requires confirmation and cannot be undone. **Export recent events (CSV)** downloads recent non-PageView records.

### 3.9 Health and diagnostics

Use this tab after setup and whenever conversions are missing.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

**Health Score** audits mode, credentials, queue freshness, Ghost, PageView, consent, TCF, purchase, deduplication, recent errors, catalog format, and data quality. Read each failed check, not only the **Excellent**, **Good**, **Fair**, or **Needs work** label.

For CAPI, schedule **CAPI CRON URL** every 1–5 minutes. Review **Last CAPI flush**, processed, sent, pending, failed, queue totals, and rows older than 10 minutes.

**Data Quality Coach** estimates matching coverage from recent server payloads or a current purchase sample. It lists present and missing identifiers, expected lifts, averages by event, and shop-level fixes. Improve anonymous ID, `msclkid`, advanced email/phone matching, and optional customer ID where appropriate. Confirm final diagnostics in Microsoft Advertising.

| Field | On start | What it does |
|---|---|---|
| **Enable front debug inspector** | No | Show a floating storefront overlay with events, payloads, CAPI destination, queue state, and errors. Turn it off after testing. Temporarily append `?mybing_debug=1` to a storefront URL to enable it without saving. |

Under **Test & queue**:

- **Send test purchase** sends a test conversion; check Microsoft Advertising after 10–30 minutes.
- **Test CAPI token** checks that Tag ID and token are present.
- **Process CAPI queue** runs the same queue path as CRON.

**Recent events log** shows event, ID, channel, status, response/error, date, and result. Use **Re-send** for an immediate attempt or **Re-add to queue** for the next CRON run.

**Recent queue rows** show event details, status, attempts, last error, and update time. Use per-row actions or **Re-send all failed now** and **Re-add all failed to queue**.

### 3.10 Updates

Check for a newer module version here.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Field | On start | What it does |
|---|---|---|
| **Manual Check** | No result | Click **Check Now** to contact the update service once. It shows **Module is up to date!** or **New version available!**. |
| **Automatic Notifications** | Existing shared update preference | **Enabled** checks approximately every three days and can warn employees. **Disabled** leaves update management manual. |
| **Product Page** | Link displayed | Open the official module page for release information, documentation, and support access. |

Click **Save** after changing notifications.

## 4. Storefront

The module adds no visible storefront block, form, button, or customer-account page. Customers use the normal product, cart, checkout, registration, newsletter, contact, and confirmation screens.

Product pages contain a hidden product-data block used by tracking. It does not alter the visible theme. When debug is enabled, a floating inspector becomes visible; disable it after testing because it exposes tracking details.

For CAPI, copy **CAPI CRON URL** from **Tracking mode** or **Health & diagnostics** into the hosting scheduler and run it every 1–5 minutes. The protected URL processes queued events and retention. Do not publish it because it contains an access key.

The storefront data endpoint is called automatically for consent, visitor IDs, cart, page view, checkout, contact, and debug actions. Do not construct or open it manually.

| Visible message | What to do |
|---|---|
| Debug inspector shows consent denied | Accept marketing consent through the CMP or repair the CMP connection. |
| Debug inspector shows queued | Run CRON or **Process CAPI queue**, then check **Health & diagnostics**. |
| Debug inspector shows failed | Read the response in **Health & diagnostics**, correct credentials or connectivity, and click **Re-send**. |

## 5. Problems

| Symptom | Cause and action |
|---|---|
| Wizard remains incomplete | Save a valid mode, Tag ID, and token when applicable; run **Test** and finish **Done**. |
| No UET events appear | Save a valid Tag ID, include UET in the mode, enable the event, review consent, and test in a private customer session. |
| **Missing Tag ID and/or Conversions API token** | Enter both in **Tracking mode**, save, and run **Test CAPI token** again. |
| CAPI events remain queued | Schedule **CAPI CRON URL** every 1–5 minutes, click **Process CAPI queue** once, and inspect **Last CAPI flush**. |
| CAPI test or re-send fails | Read **Response / error**, correct Tag ID/token/connectivity, leave the endpoint override empty unless Microsoft supplied one, and retry. |
| Tracking stops after consent is required | Configure the external CMP, use `auto`, connect TCF or its callbacks, then accept marketing consent and retest. |
| Catalog products do not match | Align **Product identification**, separator, prefix, and suffix with the feed and review **Catalog ID Doctor**. |
| Purchases appear before payment | Enable **Purchase only when paid** and optionally select exact paid states. |
| Paid orders do not create purchase | Enable **purchase** and ensure the order state is paid or included in **Paid statuses**. |
| Refunds do not appear | Enable Refund and select the correct **Refund / cancel statuses**. |
| Your tests are ignored | Use a private browser without an employee session or temporarily disable **Ignore admin / employee traffic**. |
| Bot-like test traffic is absent | Disable **Simple bot filter** for the test, then restore it as needed. |
| UET add-to-cart is absent | Update the button and price CSS selectors to match the theme. |
| Add-to-cart value is zero or malformed | Correct the price selector and enable **Reformat price string** when required. |
| Payment-step Other event is absent although its toggle is Yes | The theme or payment step did not fire the module path. Treat this signal as optional and verify the remaining funnel. |
| Live Statistics waits for events | Enable the dashboard, resume it, clear filters, click **Refresh**, and browse the storefront as a customer. |
| PageView reaches Microsoft but is absent locally | Enable local PageView logging temporarily; it is off by default. |
| Wrong multi-tag credential is used | Delete/recreate overlapping rules and give the most specific one the lowest position. |
| Rule cannot be saved | Supply a valid Tag ID and/or token, then click **Add rule**. |
| Health warns about data quality | Follow **Highest-impact fixes**, enable Ghost and Advanced matching where lawful, and collect valid checkout phone data. |
| Module screen looks stale | Clear cache under **Advanced Parameters > Performance** and reload. |

## 6. Developer reference

### 6.1 Architecture

The technical name is `mybing`, version `1.4.0`. The main class is `mybing extends Module`; list name is **Microsoft Advertising UET / Conversions API**, author `MyPresta.eu`, category `front_office_features`.

`MybingTrackerFactory` selects `MybingUetTracker`, `MybingCapiTracker`, or `MybingHybridTracker`. `MybingEvents` builds events; `MybingEventId` generates and persists deduplication IDs. `MybingProductIdResolver`, `MybingCurrencyHelper`, and `MybingUserData` normalize catalog, money, and identity data. `MybingCapiClient` builds requests, sends them, and manages retries. `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach`, and `MybingCatalogDoctor` power diagnostics.

Dual mode shares an event ID between browser and server channels. The default endpoint is `https://capi.uet.microsoft.com/v1/{tagId}/events`. Each CRON call processes up to 50 queue rows and applies retention.

### 6.2 Files and classes

| File or class | Responsibility |
|---|---|
| `mybing.php` | Install/uninstall, defaults, forms, actions, CRON, front configuration, and hooks. |
| `classes/MybingTrackerInterface.php` | Tracker contract. |
| `classes/MybingTrackerFactory.php` | Mode and event-switch resolution. |
| `classes/MybingUetTracker.php` | Browser payloads and local UET records. |
| `classes/MybingCapiTracker.php` | Server delivery and queueing. |
| `classes/MybingHybridTracker.php` | Dual output and deduplication. |
| `classes/MybingCapiClient.php` | Payloads, cURL, responses, queue, retries, and flush summaries. |
| `classes/MybingEvents.php` | Commerce event implementation. |
| `classes/MybingEventMap.php` | Internal-to-Microsoft event map. |
| `classes/MybingEventId.php` | Event IDs, deduplication, and event-table healing. |
| `classes/MybingUserData.php` | Click/visitor IDs, customer data, normalization, and hashing. |
| `classes/MybingConsent.php` | Consent requirement, defaults, cookies, and TCF. |
| `classes/MybingPropertyRules.php` | Context rule schema, matching, and credential resolution. |
| `classes/MybingProductIdResolver.php` | Catalog ID generation. |
| `classes/MybingCurrencyHelper.php` | Currency context and conversion. |
| `classes/MybingLiveStats.php` | Feed, summaries, Radar, retention, and cleanup. |
| `classes/MybingHealthScore.php` | Weighted health checks and queue diagnostics. |
| `classes/MybingDataQualityCoach.php` | Identity coverage estimates. |
| `classes/MybingCatalogDoctor.php` | Sample and recent product IDs. |
| `controllers/admin/AdminMybingAjaxController.php` | Authenticated JSON back-office bridge. |
| `controllers/front/ajax.php` | Token-protected tracking JSON endpoint. |
| `controllers/front/cron.php` | Key-protected queue JSON endpoint. |
| `views/js/mybing.js` | Main front bindings and dispatch. |
| `views/js/mybing-tcf.js` | TCF consent bridge. |
| `views/js/mybing-ghost.js` | Visitor/click-ID sync. |
| `views/js/mybing-debug.js` | Front inspector. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Back-office forms, wizard, and live dashboard. |
| `views/templates/hook/header.tpl` | UET, consent, matching, page view, events, script, and ID Sync. |
| `views/templates/hook/product-details.tpl` | Hidden product JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Browser purchase output. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | CAPI page view, Ghost, and inspector output. |
| `views/templates/hook/payment.tpl` | Payment-event template not invoked by a hook handler in 1.4.0. |
| `sql/install.php`, `sql/uninstall.php` | Create/heal and drop custom tables. |
| `lib/updateChecker.php` | Manual and periodic update checks. |

### 6.3 Controllers

`AdminMybingAjaxController extends ModuleAdminController` is installed as hidden tab `AdminMybingAjax` with parent `-1`. It requires an employee and emits JSON. Actions: `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport`, and `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` is SSL and JSON-only. It accepts the secure key or generated front token. Actions: `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping`, and debug-only `inspect`. Errors include `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off`, and `unknown_action`.

`MybingCronModuleFrontController` accepts `key` or `secure_key`, returns JSON, emits HTTP 403 with `access_denied` for invalid access, and calls `runCapiCron()`.

`controllers/front/index.php` only sends no-cache headers and redirects upward.

### 6.4 Hooks

| Registered hook | Implementation |
|---|---|
| `displayHeader` | Filters traffic; dispatches page, list, product, checkout, search, contact, and newsletter signals; renders UET/Ghost/CAPI output. |
| `displayOrderConfirmation` | Resolves order, tracks allowed purchase, renders browser output. |
| `actionValidateOrder` | Tracks purchase at creation unless paid-only delays it. |
| `actionOrderStatusPostUpdate` | Tracks delayed paid purchase and refund/cancel transitions. |
| `actionCustomerAccountAdd` | Tracks signup and stores browser output for the next page. |
| `actionFrontControllerSetMedia` | Adds front configuration and main, TCF, Ghost, and debug assets. |
| `displayPaymentTop` | Registered, but `hookDisplayPaymentTop()` is not implemented in 1.4.0. |
| `displayFooter` | Renders debug inspector and queue bootstrap when enabled. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Track server cart quantity changes; the latter delegates to the former. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Snapshot then track full cart-line deletion. |
| `displayProductAdditionalInfo` | Renders hidden product details. |
| `actionNewsletterRegistrationAfter` | Tracks newsletter lead. |
| `displayContactContent` | Adds the hidden contact marker. |

There are no custom `enable()` or `disable()` methods.

### 6.5 Database

The actual PrestaShop prefix replaces `ps_`.

| Table | Contents |
|---|---|
| `ps_mybing_events` | Event name/ID, order/cart/shop, channel, payload, status, HTTP code, response, date, lookup indexes, and unique event/name/shop dedupe key. |
| `ps_mybing_properties` | Tag, token, shop/language/country/currency selectors, active, position, and date. |
| `ps_mybing_queue` | Payload, attempts, status, last error, created/updated dates. |

Installation retries with `utf8` if `utf8mb4` fails. `MybingPropertyRules::ensureSchema()` can add `tag_id` and `access_token` when configuration is opened and migrate a legacy refresh token. The event schema soft-adds its unique index. Uninstall drops all three tables.

### 6.6 Configuration keys

| Keys | Defaults and purpose |
|---|---|
| `MYBING_MODE` | Empty; tracker mode. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Empty; global credentials/destination. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1`; click-ID life and ID Sync. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | All `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | All `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | All `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, empty per language, empty per language. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | Empty comma-separated state IDs. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Runtime install diagnostics. |
| `MYBING_LAST_FLUSH` | Runtime JSON flush summary; not in the uninstall key list. |

Setup/uninstall also deletes legacy `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS`, and `MYBING_ADS_ID`. `MYBING_DEBUG_MODE` is purged during setup but is absent from the uninstall list.

The updater uses `mypresta_updates`, `update_mybing`, and `updatev_mybing`; these may remain after uninstall. `mypresta_updates` is shared.

### 6.7 Uninstall, translations, and extension

`uninstall()` deletes the hidden tab, drops all module tables, deletes `getConfigurationKeys()` values and installation diagnostics, then calls `parent::uninstall()`. It does not delete updater keys or `MYBING_LAST_FLUSH`.

There are no PrestaShop overrides. Translations live in `translations/{iso}.php`; most UI strings use `$this->l()` or Smarty `{l}`, while event names and some class diagnostics remain English.

Themes can reposition supported hooks and style the inspector, but the product block is intentionally hidden. Preserve data attributes and scripts when overriding hook templates. A custom CMP can dispatch `mybing.consent` with grant `1` or `0`, or provide a signal recognized by `MybingConsent`.

## 7. Help

Open the module page: https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Log in to your customer account on mypresta.eu, open the contact page, and choose **Support for paid modules**. Login is required; then select this module from your purchase history and include the tracking mode, visible error, and diagnostic result.
