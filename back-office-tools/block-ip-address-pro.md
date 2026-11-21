---
title: Ban IP Pro - documentation and user manual
sidebar:
  label: Ban IP Pro - documentation and user manual
description: Configuration and troubleshooting manual for shops that already have Ban IP Pro.
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Block IP address Pro Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Requirements

Ban IP Pro runs inside PrestaShop. It does not need another module.

- PrestaShop 1.7.1.0 through PrestaShop 9.
- PHP 7.1 or newer, and at least the PHP version required by that PrestaShop release. Installation stops on PHP older than 7.1.
- Country lookup and country blocking need PHP 7.2 or newer and a MaxMind country file you upload yourself. Bans, the allow list, login checks and the request limit keep working without that file and on PHP 7.1.
- No extra PHP extension is required. The update check uses cURL when the server has it. When cURL is missing, the check reads the address only if the server allows remote reads.
- No other module is required. A MaxMind account is needed only if you want the country file. The module does not download that file for you.
- An import accepts up to 5000 lines and a file of up to 2 MB. A long rule list is read from a cache file on each visit, so a very large list makes that file large. Use **Rebuild cache** on **Tools** after a big import if the counters look stale.

## 2. Installation

1. In the back office open **Modules**, then **Module Manager**.
2. Upload the module zip and click **Install**.
3. Open **Configure** on **Ban IP pro**. The page opens on **Dashboard**. The bar also has **Statistics**, **Behavior**, **Automation**, **Network**, **Tools** and **Updates**.
4. The left menu gains **Ban IP** under **Advanced Parameters**. That page is the rule list. **Dashboard** on the module page links to the same list with **Manage rules**.

Installation writes an empty rule cache. It does not clear the PrestaShop cache. If the menu entry is missing after an update, open **Configure** once. The page updates the module tables. If that update fails, the page shows **The module database could not be updated.**

To turn the module off, use the switch in **Module Manager**. The checks stop. Rules, logs and settings stay. Turn the module on again and the same rules are used. The module has no separate enable or disable button of its own.

To remove it, click **Uninstall** and confirm. Uninstall removes the **Ban IP** menu entry and unregisters the checks. The rules, the block log, the daily totals, the failed-login counters, the staff action list and the settings stay in the database. The uploaded country file stays in the module folder. Installing again keeps those rules and fills only the settings that are still empty.

## 3. Configuration and daily work

A visitor opens the shop. Before the page is built, the module reads the visitor IP. An allow rule wins over a ban. If a ban matches the shop, or the visitor's country is on the block list, or the visitor opened a probe path, or the address crossed the request limit, the visitor gets the blocked page or the redirect you set. The block is written to the log. Staff work starts on **Dashboard** or on **Advanced Parameters**, **Ban IP**. You add a rule, import a list, or leave **Automation** to create bans. A ban can expire. On the first request of each day, expired rules are switched off and old log lines are removed. The path ends when the visitor is blocked, redirected, or let through.

Open **Modules**, **Module Manager**, **Ban IP pro**, **Configure**.

### 3.1 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

**Dashboard** is the home tab. **Manage rules** opens the rule list.

The seven counters only display numbers. They do not save a setting.

| Field | At the start | What it does |
|---|---|---|
| **Manage rules** | a button | Opens **Ban IP** under **Advanced Parameters**. |
| **Active bans** | 0 | Ban rules that are still on. Allow rules are not included. |
| **Blocked today** | 0 | Blocked requests since midnight, from the daily totals. |
| **Blocked in 7 days** | 0 | Blocked requests in the last 7 days, including today. |
| **Blocked in 30 days** | 0 | Blocked requests in the last 30 days, including today. |
| **Unique IPs today** | 0 | Different IP addresses in today's block log. |
| **Expiring in 48 hours** | 0 | Active bans whose end time is inside the next 48 hours. |
| **Active automatic bans** | 0 | Active bans whose reason is a failed login, a probe path or the request limit. |

**Blocked requests** is a chart of the last 30 days. It reads the daily totals. It does not save a setting.

**Recent blocks** lists the latest blocked requests: date, IP address, country, path and reason. The country stays empty until you upload the country file on **Network**. An empty list says **No blocked requests yet.**

**Your current IP** shows the address this back office sees. **Add to allow list** saves that address as an allow rule for the shop and the back office. The page then says **Your current IP address is on the allow list.** If the address cannot be read, the page says **Your current IP address could not be detected.** If the row cannot be saved, the page says **The address could not be added to the allow list.**

**Module status** shows four lines.

| Line | At the start | What it does |
|---|---|---|
| **Front hook** | **Registered** after a normal install | **Registered** means the shop runs the check. **Missing** means the check is not attached. Reinstall the module or open **Configure** after an update. |
| **Cached rules** | 0 | How many active rules the cache accepted. |
| **Unreadable rules** | 0 | Active rows the cache could not read as an address. |
| PHP and PrestaShop | the versions on this server | Shown so you can compare them with the requirements. |

**Quick ban** writes one ban. The scope is whatever **Default scope of new bans** is on **Behavior**. A ban you add here does not send the alert email.

| Field | At the start | What it does |
|---|---|---|
| **IP address** | empty | One address, a pattern such as `192.168.1.*`, a network such as `10.0.0.0/8`, or a range such as `192.168.1.10-192.168.1.20`. |
| **Reason** | **Manual** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback** or **Competitor**. Statistics use this label. |
| **Duration** | **Permanent** | **1 hour**, **24 hours**, **7 days**, **30 days**, or **Permanent** until you delete the rule. |
| **Comment** | empty | A private note. The visitor never sees it. |
| **I confirm blocking my own IP** | off | Required only when the ban would match the IP you are using and the scope includes the back office. |
| **Ban this address** | a button | Saves the ban and shows **The address was banned.** |

**Test an address** does not create or delete a rule.

| Field | At the start | What it does |
|---|---|---|
| **IP address** | empty | The address you want to check. |
| **Test** | a button | Shows the shop result, the back-office result, and the country. |
| **Front office** | hidden until you test | **No matching rule.**, **Allowed by rule #…**, or **Blocked by rule #…**. |
| **Back office** | hidden until you test | The same three results for the panel. |
| Note under the back-office line | shown when protection is off | **Back office protection is disabled, so back-office bans are not enforced.** |
| **Country** | **Unknown** when the file is missing | The country code, plus **Blocked by country rule** when that country is on the block list. |

**Recent admin actions** lists the latest staff actions, such as create, import, allow, unlock and cache rebuild. An empty list says **No admin actions yet.**

### 3.2 Statistics

![Statistics](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

**Statistics** reads the block log. **24h**, **7 days** and **30 days** reload the page for that period. **30 days** is the period when you first open the tab.

| Field | At the start | What it does |
|---|---|---|
| **24h** | a button | Last 24 hours. The chart uses one point per hour. |
| **7 days** | a button | Last 7 days, including today. The chart uses one point per day. |
| **30 days** | a button, selected on first open | Last 30 days, including today. |
| **Export CSV** | a button | Downloads `banippro-hits.csv` for the period on screen. It does not change rules. |
| **From** | the first day of the open period | Used with **To** and **Apply**. |
| **To** | today | Used with **From** and **Apply**. If **From** is later than **To**, the two days are swapped. |
| **Apply** | a button | Reloads the tab for those days. It does not save a setting. |
| **Blocked requests** | 0 | How many blocks fall in the period. |
| **Unique IPs** | 0 | How many different addresses were blocked in the period. |

The **Blocked requests** chart follows the buttons above. Under it:

| Block | What it shows |
|---|---|
| **Top IP addresses** | A bar chart of the 10 addresses with the most blocks in the period. |
| **Top paths** | The 10 paths blocked most often, with a count. |
| **Top reasons** | The 10 reasons on the matching rules, with a count. |
| **Top countries** | The 10 country codes, with a count. Empty until the country file is uploaded. |
| **Block log** | Date, IP address, country, path, the rule address and the reason. Up to 100 rows. |

An empty breakdown says **No data for this period.** An empty log says **No blocked requests in this period.**

The day totals behind the dashboard chart are kept when you shorten **Keep logs for days**. That setting deletes the line-by-line log and the staff action list. It does not delete the daily totals.

### 3.3 Behavior

![Behavior](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

Click **Save**. The page shows **Settings updated**.

| Field | At the start | What it does |
|---|---|---|
| **Message for blocked visitors** | **You are blocked** in English. Polish, Spanish and Portuguese shops also get a sentence in that language. Any other language gets the English sentence. | The text on the blocked page. Fill every language the shop uses. Visitors see the sentence for the language of the page. |
| **Redirect blocked visitors** | **No** | **Yes** sends blocked visitors to **Redirect URL** instead of the message. **No** keeps the blocked page. |
| **Redirect URL** | empty | A full `http` or `https` link. Ignored while the switch above is **No**. A bad link turns the switch back to **No** and shows **Enter a valid http or https URL for the redirect.** |
| **Default scope of new bans** | **Front office** | Used by **Quick ban** and **Import** when those screens do not ask for a scope. **Front office** is the shop. **Back office** is this panel. **Front office and back office** is both. |
| **Protect the back office** | **No** | **Yes** also enforces bans in this panel. Save refuses **Yes** until your current IP is on the allow list, and shows **Add your current IP to the allow list before you protect the back office.** The switch stays **No**. |

The form also shows this notice: **Back office protection stays off until your current IP is on the allow list. Rules still apply to the shop front by default.**

### 3.4 Automation

![Automation](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

Click **Save**. The page shows **Settings updated**. Automatic bans apply to the shop front, for every shop in the installation. They do not turn on **Protect the back office**. An address that already matches an allow rule is not banned. An address that already has an active ban is left as it is.

| Field | At the start | What it does |
|---|---|---|
| **Block known probe paths** | **Yes** | **Yes** bans a shop visitor who opens a path in the list below. Your admin folder is never banned this way. **No** stops this check. |
| **Probe ban length in hours** | 24 | How long that ban lasts. 24 is one day. 0 keeps it until you delete it. |
| **Probe paths** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, one per line | A request whose path contains one of these lines is banned at once. A blank list is replaced with this default list on save. A line that is only `/`, and a line that is your admin folder, are dropped. |
| **Ban customers after failed logins** | **No** | **Yes** counts wrong customer passwords. A successful customer login clears the count. |
| **Ban employees after failed logins** | **No** | The same count for the employee login form. Put your own IP on the allow list before you turn this on. The ban still applies to the shop front, not to the panel, unless that IP is also covered by a ban whose scope includes the back office. |
| **Failed logins before a ban** | 5 | With 5, the next failed login inside the window creates the ban. The smallest saved value is 1. |
| **Failed login window in minutes** | 15 | Failures older than this are forgotten. The smallest saved value is 1. |
| **Login ban length in hours** | 24 | How long the login ban lasts. 0 keeps it until you delete it. |
| **Limit requests per IP** | **No** | **Yes** counts shop page requests. Pictures and other files that never enter PrestaShop are not counted. Leave this **No** during normal traffic. On a busy shop a low limit will ban real customers. |
| **Requests allowed in the window** | 120 | How many page requests one IP may make during the window. The smallest saved value is 1. |
| **Rate limit window in minutes** | 1 | Length of that window. 1 means the limit above is per minute. |
| **Rate limit ban in minutes** | 15 | How long the ban lasts after the limit is crossed. The smallest saved value is 1. |
| **Email me when an automatic ban is created** | **No** | **Yes** sends one email when the module creates a ban. Bans you add by hand do not send it. At most one email goes out per hour. |
| **Alert email** | empty | The mailbox that receives the alert. Leave it empty to use the shop email. A value that is not an email is cleared and the page shows **Enter a valid alert email address.** |

The mail subject is **Ban IP Pro alert**. The message names the IP, the reason (`auto-login`, `auto-honeypot` or `auto-rate`), the end time or the word `permanent`, and the shop name.

### 3.5 Network

![Network](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

Click **Save**. The page shows **Settings updated**.

| Field | At the start | What it does |
|---|---|---|
| **Trust Cloudflare** | **No** | Turn this on only when the shop domain goes through Cloudflare. The module then reads the visitor IP from Cloudflare, and only if the connection really comes from Cloudflare. Leave it **No** when you are not sure, or every visitor can look like the proxy. |
| **Trusted reverse proxies** | empty | If a proxy or load balancer sits in front of the shop, put its IP address or network here, one per line. The module reads the visitor IP from that proxy only. Leave this empty when you are not sure. |
| **Block selected countries** | **No** | **Yes** blocks every visitor whose country is on the list below. This starts working after you upload the country database. Do not list your own country. A country block does not add a row on **Ban IP**. It blocks that request and writes a log line with reason **Country**. |
| **Country codes** | empty | Two-letter codes, for example `PL`, `DE` or `US`. Separate them with commas, spaces or new lines. Anything that is not two letters is dropped. |
| **Keep logs for days** | 90 | How many days the block history and the staff action list are kept. Older rows are removed on the first request of a later day. The smallest saved value is 1. Values over 3650 are saved as 3650. |
| **GeoLite2 country database** | no file | Optional. Choose a file whose name ends in `.mmdb`. After **Save**, statistics can show the country and country blocking can work. The rest of the module does not need this file. |

Above the file field the page shows one of these lines:

| What you see | What to do |
|---|---|
| **GeoIP database is ready.** | Nothing. Country lookup works. |
| **Country lookup needs PHP 7.2 or newer. The rest of the module keeps working.** | Bans still work. Country stats and country blocks stay off until PHP is 7.2 or newer. |
| **Upload GeoLite2-Country.mmdb to enable country statistics and country blocks. MaxMind distributes that file.** | Upload the file and click **Save**. |

A wrong file shows **Upload a GeoLite2 Country file that ends with .mmdb.** If the file cannot be stored, the page shows **The GeoIP database could not be saved.** A good upload shows **The GeoIP database was uploaded.**

### 3.6 Tools

![Tools](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

**Import rules** creates bans. The scope is **Default scope of new bans**. Each new row is active, permanent, and uses reason **Manual** unless the line says otherwise.

| Field | At the start | What it does |
|---|---|---|
| **Addresses** | empty, with a sample in the placeholder | One address per line. A CSV line can be address, comment, reason. Lines that start with `#` are ignored. An address that already exists is skipped. |
| **File** | empty | A text file. Its lines are added to the box above. A file larger than 2 MB shows **The import file is larger than 2 MB.** and nothing is imported. |
| **Import** | a button | Creates the bans and shows **%d rules were imported.** Skipped lines also show **%d lines were skipped.** The import stops after 5000 lines. |
| **Export rules CSV** | a button | Downloads `banippro-rules.csv` for every rule. It does not change the list. |

**Web server snippet** shows two boxes, Apache 2.4 and nginx. The heading includes how many addresses were exported. Only active, permanent bans that are a single IP or a network are included. A pattern such as `192.168.1.*` is written as a network. Ranges and temporary bans are left out. **Copy** copies the box. The module does not edit your server files. You paste the text into the server configuration yourself. With nothing to export, both boxes say that there is nothing to export.

**Emergency unlock** shows an address. Open it from a browser that is locked out. The module adds that browser's IP to the allow list, for the shop and the back office, and lets that request through.

| Button | What it does |
|---|---|
| **Copy** | Copies the unlock address. The key stays the same. |
| **Create a new key** | Replaces the key. The page says **A new emergency key was created. The previous unlock link no longer works.** |
| **Rebuild cache** | Rewrites the rule cache from the current list. The page says **The rule cache was rebuilt.** |

Keep the unlock address outside the shop. Anyone who opens it is added to the allow list.

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

| Field | At the start | What it does |
|---|---|---|
| **Check now** | a button | Asks MyPresta whether a newer version exists. **New version available!** or **Module is up to date!** The shop front never makes this call. |
| **Updates notifications** | **Disable** | **Enable** runs the same check when you open this tab, and at most once every three days. A newer version also shows a notice on the module page: **New version available, check MyPresta.eu for more informations**, with **More details in changelog**. |
| **Save** | a button | Stores **Enable** or **Disable**. It does not download a file. The page says **Settings updated**. |

The link under the form opens the module page on mypresta.eu, where the changelog is published. This manual does not list versions.

### 3.8 Ban IP, the rule list

![Ban IP, the rule list](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

Open **Advanced Parameters**, **Ban IP**, or **Manage rules** on **Dashboard**. The line above the list says that dashboard, statistics and automation are on the module configuration page, and offers **Open dashboard**.

**Add new** opens a blank rule. On a new rule you can paste several addresses, one per line. They share the comment, reason, rule type, scope, expiry, active flag and shop.

The list columns are **ID**, **IP address**, **Match**, **Rule**, **Scope**, **Hits**, **Last hit**, **Expires**, **Reason** and **Active**. When the shop uses more than one shop, **Shop** is added.

| Column | What you see |
|---|---|
| **Match** | **Exact**, **Wildcard**, **CIDR** or **Range**. |
| **Rule** | **Ban** or **Allow**. |
| **Scope** | **Front office**, **Back office**, or **Front office and back office**. |
| **Hits** | How many blocked requests were logged against this rule. |
| **Last hit** | Date of the latest one. |
| **Expires** | A date and time, or **Permanent**. |
| **Reason** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback**, **Competitor**, **Auto ban (login)**, **Auto ban (probe)**, **Auto ban (rate limit)** or **Country**. |
| **Active** | The status icon. Click it to turn the row on or off. An inactive rule stays on the list and matches nobody. |
| **Shop** | **All shops**, or one shop name. Shown only when multishop is on. |

Use the filter row to search. Filtering does not block or allow anyone.

Row actions:

| Action | What it does |
|---|---|
| **Edit** | Opens the rule. Only one address can be saved on an existing row. |
| **Whitelist** | Shown on a ban. Changes that row to **Allow** and rebuilds the cache. Hidden on a row that is already **Allow**. |
| **Delete** | Removes the row and rebuilds the cache. |

Bulk actions, after you tick rows:

| Action | What it does |
|---|---|
| **Enable selection** | Turns the ticked rows on and rebuilds the cache. |
| **Disable selection** | Turns the ticked rows off and rebuilds the cache. They stay on the list. |
| **Delete selected** | Asks **Delete selected items?** and then removes the ticked rows and rebuilds the cache. |

An allow rule is checked before bans. A matching allow rule lets the visitor through even when a ban would also match.

A rule whose end time has passed stops matching at once. On the first request of the next day it is also switched to inactive.

### 3.9 The rule form

![The rule form](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

**Save** writes the rule, rebuilds the cache, and returns to the list when every line is valid.

| Field | At the start | What it does |
|---|---|---|
| **IP address** | empty | On a new rule, one address per line. On an edit, one address. A single IP, a pattern such as `192.168.1.*`, a network such as `10.0.0.0/8`, or a range such as `192.168.1.10-192.168.1.20`. Patterns are IPv4, and the stars have to sit at the end. IPv6 works for a single address, a network and a range. |
| **Comment** | empty | A private note only you see in this list. Visitors never see it. |
| **Reason** | **Manual** | Why this address is listed. Statistics use it so you can tell a manual ban from an automatic one. The automatic reasons are not in this dropdown. The module writes those itself. |
| **Rule** | **Ban** | **Ban** blocks the address. **Allow** always lets it through, even when another rule would block it. |
| **Scope** | the value of **Default scope of new bans** | **Front office** is what customers see. **Back office** is this admin panel. **Front office and back office** means the rule works in the shop and in the panel. |
| **Expires at** | empty | Leave empty to keep the rule until you delete it. Or type the date and time it should stop, for example `2026-12-31 18:00`. A bad value shows **The expiry date is not valid.** |
| **Active** | **Yes** | **No** keeps the rule on the list but it does not block or allow anyone. |
| **I confirm blocking my own IP** | **No** | The help line shows your current IP, or **unknown**. Confirmation is required when a ban would match this IP in the back office. |
| **Shop** | **All shops** | Shown only when multishop is on. **All shops** means the rule works in every shop of this installation. Pick one shop to limit the rule to it. |
| **Save** | a button | Saves the rows. |

Empty input shows **Enter an IP address.** A pattern that would match every address, such as `*.*.*.*` or a network with prefix `0`, shows **This rule would block every address.** A bad address shows **This IP address or range is not valid.** A second active rule with the same address and the same ban-or-allow type shows **This rule already exists.** A ban that matches your current IP in the back office, without the confirmation switch, shows **This ban matches your current IP in the back office. Confirm it before saving.** More than one line on an edit shows **Edit one address at a time.** A bad line on a new rule is skipped with **Line … was skipped:** and the reason. A duplicate line is skipped with **Line was skipped because it already exists:** and the address. When some lines were saved and some were not, the page also shows **%d rules were saved.** and stays on the form. If the row cannot be written, the page shows **The rule could not be saved.** A missing row shows **Rule not found.**

## 4. Front of the shop

The shop theme does not print a block, a badge or a widget for this module. There is nothing to screenshot on a normal product, cart or home page.

A visitor who is not blocked sees the shop as usual. A visitor who is blocked sees a plain page: the shop logo when the shop has one, the heading 403, the **Message for blocked visitors** for the language of the page, and the visitor IP. The page asks search engines not to index it. If **Redirect blocked visitors** is **Yes** and **Redirect URL** is a valid `http` or `https` link, the visitor is sent to that address instead, and does not see the message.

The same blocked page is used in the back office when **Protect the back office** is **Yes** and the employee IP matches a ban there and does not match an allow rule.

These checks run only on requests that enter PrestaShop. Files served directly by the web server, such as pictures, are not checked and are not counted by **Limit requests per IP**.

There is no customer account page and no form for the visitor to appeal. The visitor either gets through, sees the blocked page, or lands on the redirect.

| What the visitor sees | What you do |
|---|---|
| The shop, as usual | No matching ban, or an allow rule matched. |
| The blocked page with your message and their IP | A ban matched, the country is blocked, a probe path was opened, or the request limit was crossed. Redirect is **No**. |
| Another website, with no message | Redirect is **Yes** and the URL is valid. |
| The back office, as usual | **Protect the back office** is **No**, or this IP is on the allow list. |

## 5. Problems

**The module page says Ban IP Pro requires PHP 7.1 or newer.**  
The server is on PHP older than 7.1. Install is refused and **Configure** only shows that sentence. Move the shop to PHP 7.1 or newer, then install again.

**Configure says The module database could not be updated.**  
The tables could not be created or updated. Ask the host to allow the database user to create and alter tables, then open **Configure** again.

**Front hook says Missing.**  
The check is not attached. Reinstall the module, or disable it and enable it again from **Module Manager**. Existing rules stay.

**Save on Behavior refuses Protect the back office.**  
The page says **Add your current IP to the allow list before you protect the back office.** On **Dashboard**, click **Add to allow list**, then set the switch to **Yes** and save again.

**You locked yourself out of the back office.**  
Open the emergency address from **Tools**, **Emergency unlock**, on a browser that can still reach the shop. That browser's IP is added to the allow list and the request is let through. If you cannot open **Tools**, use a copy of the address you saved earlier. **Create a new key** makes the old address useless, so update your copy after you use it.

**A ban of your own IP is refused.**  
The page says **This ban matches your current IP in the back office. Confirm it before saving.** Turn on **I confirm blocking my own IP**, or change the scope to **Front office** if you only want to block that IP on the shop.

**Import says The import file is larger than 2 MB.**  
Split the file. Each import stops after 5000 lines and then shows that the import stopped. Run the rest in another import. Skipped lines show **%d lines were skipped.** Existing addresses are skipped on purpose.

**The address was saved but the shop still lets it through.**  
Check **Active**, **Scope** and **Expires at**. A rule for the back office does not affect the shop. An allow rule for that IP wins. On **Dashboard**, use **Test an address**. Then click **Rebuild cache** on **Tools**.

**Back-office bans do nothing.**  
**Test an address** adds **Back office protection is disabled, so back-office bans are not enforced.** Turn on **Protect the back office** on **Behavior** after your IP is on the allow list.

**Country blocking does nothing.**  
**Block selected countries** must be **Yes**, the codes must be two letters, and the page must say **GeoIP database is ready.** On PHP older than 7.2 the page says country lookup needs PHP 7.2 or newer. Do not put your own country in the list.

**Customers are banned during a normal sale.**  
**Limit requests per IP** is on and the limit is low for this shop. Set it to **No**, or raise **Requests allowed in the window**. Delete the automatic bans on **Ban IP**. Their reason is **Auto ban (rate limit)**.

**A failed employee login did not block the back office.**  
That automatic ban applies to the shop front. The panel is blocked only when **Protect the back office** is **Yes** and a ban whose scope includes the back office matches that IP.

**The alert email never arrives.**  
**Email me when an automatic ban is created** must be **Yes**. Manual bans do not send mail. A second automatic ban inside the same hour does not send another mail. The mailbox is **Alert email**, or the shop email when that field is empty. The shop must already be able to send mail.

**The chart still shows old days after you shorten the log.**  
**Keep logs for days** removes the line-by-line log and the staff actions. The daily totals used by the dashboard chart stay.

**New version available, check MyPresta.eu for more informations.**  
Open **Updates** and use the link, or click **Check now**. This manual does not list the changes.

## 6. For developers

### 6.1 Overview

Technical name `banippro`, version 2.0.0, class `banippro`, display name **Ban IP pro**, author MyPresta.eu, tab `administration`. Product page: `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` calls `BanIpGuard::protect()`. The guard resolves the IP, applies an emergency unlock, then `BanIpMatcher::decide()` on the cache from `cache/rules.php`. Allow wins over ban. Country blocks, probe bans and the rate limit run on the shop front. A block logs a hit and either redirects or renders `blocked.tpl` with status 403 and exits. `actionDispatcherAfter` runs `BanIpAutoBan::evaluate()` for a login that was armed earlier. Settings are global configuration values read through `BanIpInstaller`. The menu controller `AdminBanIpPro` edits the `ban` table.

There is no `enable()` or `disable()` override. PrestaShop's own disable unregisters the hooks, so the guard does not run. Data stays.

### 6.2 Files

| File | Role |
|---|---|
| `banippro.php` | Install, hooks, configuration tabs, quick ban, import, test. |
| `controllers/admin/AdminBanIpProController.php` | Rule list, rule form, CSV export, whitelist row action. |
| `models/banip.php` | Object model for `ban`, plus `storeRule()` and `importLines()`. |
| `classes/BanIpGuard.php` | Request check, blocked page, daily maintenance. |
| `classes/BanIpMatcher.php` | Parse exact, wildcard, CIDR and range. Decide allow then ban. |
| `classes/BanIpClientIp.php` | Remote address, Cloudflare, trusted proxies. |
| `classes/BanIpCache.php` | Builds and includes `cache/rules.php`. |
| `classes/BanIpAutoBan.php` | Probe, failed login, rate limit, alert mail. |
| `classes/BanIpStats.php` | Dashboard, report, CSV, server snippets. |
| `classes/BanIpGeo.php` | Reads `geo/GeoLite2-Country.mmdb` without the MaxMind library. |
| `classes/BanIpInstaller.php` | Tables and default configuration. |
| `classes/BanIpUpdate.php` | Version check against `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Dashboard, statistics, tools, shell. |
| `views/templates/front/blocked.tpl` | Blocked page. |
| `views/js/dashboard.js` | Charts and copy buttons. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Alert bodies. Subject is hardcoded in `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Runs `BanIpInstaller::upgrade()`, swaps legacy hooks for the 2.0.0 set, rebuilds the cache. |
| `lib/searchTool/` | Loaded on the configuration page. No configuration field calls it. |
| `tests/matcher_test.php` | CLI checks for the matcher. |

### 6.3 Controllers

`AdminBanIpPro` extends `ModuleAdminController`. The parent tab is `AdminAdvancedParameters`. Class name `AdminBanIpPro`. Table `ban`, identifier `id_ban`, object `banip`.

List filters use the standard helper names (`banFilter_ip` and the other list fields). Row actions: edit, `displayWhitelistLink` (`banippro_whitelist`), delete. Bulk: delete, enable, disable. `exportHits` streams the hit CSV. `exportRules` streams the rule CSV.

There is no front controller. The blocked response is rendered inside the dispatcher hook and the request exits.

`?banippro_unlock=` is read by `BanIpGuard::tryUnlock()`. The value must match `banippro_emergency_key` with `hash_equals`. A match calls `BanIpAutoBan::ensureAllow()` with scope front and back office (`apply_to` 3, `id_shop` 0) and audits `unlock`.

### 6.4 Hooks

Registered on install:

| Hook | Call |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. Also registered after the main install check. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` unregisters `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` and `actionAdminControllerSetMedia`.

The module does not register a hook of its own. Login arming looks for `submitLogin` in the request. A successful customer login clears the customer failure counter. Employee success is detected when the employee is logged in at `evaluate()`.

### 6.5 Overrides

The module does not override a PrestaShop class or controller.

### 6.6 Database

Uninstall does not drop these tables and does not delete the configuration keys. `BanIpInstaller::ensure()` adds missing columns on `{prefix}ban` when **Configure** is opened, so an older `ban` table is kept and extended. Reinstall does not wipe rows.

| Table | Contents |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 front, 2 back office, 3 both), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 means all shops), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | One row per block: `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. Not deleted when logs are pruned. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` runs once per calendar day. It sets `active` to 0 on rules whose `date_end` is in the past, rebuilds the cache when any row changed, and deletes hit and audit rows older than `banippro_log_days`.

### 6.7 Keys and translations

All keys are global (`id_shop` 0). Missing keys fall back to the default in parentheses.

| Key | Default |
|---|---|
| `banippro_emergency_key` | 32 hex characters from `random_bytes`, or OpenSSL, or `md5` |
| `banippro_msg` | Per language. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` and `br` O acesso foi bloqueado. Other languages use the English sentence. HTML is allowed in storage. |
| `banippro_redirect` | 0 |
| `banippro_url` | empty |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | empty |
| `banippro_alert_last` | unix time of the last alert mail, written when a mail is sent |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | empty |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | empty |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` of the last daily maintenance |
| `mypresta_updates` | not seeded; the form treats a missing value as 0 |
| `update_banippro` | 0, then the unix time of the last update check |
| `updatev_banippro` | remote version string from the last check |

`BanIpInstaller::seedConfig()` copies a legacy shop-scoped `banippro_redirect` and `banippro_url` into the global keys when the global value is empty. A non-empty legacy `banippro_msg` is copied into every language before the default sentences are used.

Back-office strings go through `$this->l()` / `$this->module->l()`. Translation files live in `translations/{iso}.php`. The blocked-page message is the configuration value, not a translation key. The mail subject `Ban IP Pro alert` is a literal in `BanIpAutoBan::alert()`. Field help is the `desc` on each HelperForm input in `banippro.php` and `AdminBanIpProController.php`.

Automatic `reason` values written by the module are `auto-login`, `auto-honeypot` and `auto-rate`. Country blocks log `country` and do not insert a `ban` row. `banip::importLines()` stops after 5000 non-empty, non-comment lines. Uploads over 2097152 bytes are refused. `BanIpMatcher` rejects an empty value, a `/0` network, and a wildcard of four stars (`too_broad`). Duplicate detection is an active row with the same stored IP and the same `rule_type`.

`BanIpAutoBan::ensureBan()` always stores `apply_to` 1 and `id_shop` 0. `ensureAllow()` stores `apply_to` 3 and `id_shop` 0.

### 6.8 Extending

The shop theme can override `views/templates/front/blocked.tpl`. The module calls `$module->fetch('blocked.tpl')`. Assigned variables are `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` and `banippro_lang`. If the fetch fails, the guard prints a minimal HTML page with the same message and still exits with status 403.

No product, cart or home template is rendered. There is no hook for a theme to add a storefront widget. Admin templates live under `views/templates/admin/` and are not part of the theme.

## 7. Help

Module page: [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Log in to your customer account on [mypresta.eu](https://mypresta.eu), open the contact form and choose **Support for paid modules**. The form says that login is required for that topic. After you log in, choose this module from the purchase history.
