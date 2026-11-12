---
title: Contact page - spam protection PRO - documentation and user manual
sidebar:
  label: Contact page - spam protection PRO - documentation and user manual
description: Configuration and troubleshooting for shops that already have the contact-page spam protection.
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Contact page - spam protection PRO Module on MyPresta.eu](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Requirements

PrestaShop 1.7.7 through 9. PHP in the version that this PrestaShop requires. The shop's own contact page is enough. No other module is required.

A Google reCAPTCHA account is needed only when you want the checkbox or the invisible score. After installation the reCAPTCHA switch is on, but the check stays off until both keys are saved.

A CleanTalk account is needed only for the paid CleanTalk API. The free CleanTalk check uses the MyPresta proxy and does not need a CleanTalk account. Free CleanTalk needs the OpenSSL functions in PHP. If those functions are missing, that one check is skipped and the message is allowed.

StopForumSpam is a public lookup. An account and an API key are optional. The stored key is not used for the lookup.

The lookups use cURL when PHP has it. Without cURL, StopForumSpam, CleanTalk and the update check read the address directly when the server allows remote URLs. reCAPTCHA verification uses cURL when it is available.

## 2. Installation

Open **Modules**, then **Module Manager**. Upload the module zip and click **Install**.

The left menu gains **Contact protection**. Open it to reach the configuration. Under that entry are **Message attempts** and **Banned IP addresses**.

Installation does not run a separate cache clear.

To turn the module off, use the switch in Module Manager. The contact page is no longer checked. The saved settings, the attempts and the bans stay. Turn the module on again and they are used as before. The menu entries are hidden while the module is off.

To remove it, click **Uninstall** and confirm **Are you sure you want to uninstall this module?** Uninstall removes the menu entries, the saved settings and both lists. The module files stay on the server until you delete the module. Installing it again starts with empty lists and the settings from a fresh installation. The old attempts and bans are not restored.

## 3. Configuration and daily work

Open **Contact protection** in the left menu. The page has the tabs **Overview**, **Anti-flood**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Message filters**, **Whitelist**, **Protection** and **Email**. **Updates** sits at the end of that row. **Save** on a tab stores that tab and confirms with **Settings saved.** The Updates tab confirms with **Update settings saved.**

While the conditions last, a configuration page can show:

**reCAPTCHA is enabled, but the site key or the secret key is empty. The captcha stays off until both keys are saved.**

**CleanTalk paid API is enabled, but the access key is empty.**

The second warning appears when the paid switch is on and the key is empty. After a fresh installation the paid switch is off, so that warning is not shown until you turn the paid API on without a key.

A message is checked in this order. The first match decides.

1. An address on the whitelist, and a logged-in customer when **Skip checks for logged-in customers** is on, continues to the contact form. The try is not written to **Message attempts**.
2. If every check is off and the address is not on the ban list, the message continues and is not logged. The reCAPTCHA switch alone does not count as a check while both keys are empty.
3. Otherwise the checks run in this order: an active ban, the honeypot, the minimum time, an empty browser identifier, anti-flood, a duplicate of a message of 20 characters or more, too many links, a blocked word, a disposable email, reCAPTCHA (only when both keys are saved), StopForumSpam, free CleanTalk, then paid CleanTalk.
4. If nothing matches, the try is stored as allowed and the contact form sends the message.
5. A block for **Too fast** or **reCAPTCHA** only stops that message. It does not ban the address, does not email the shop, and does not redirect. The customer sees **Captcha verification failed. Please try again.** when the reason is reCAPTCHA, and **Your message could not be sent. Please try again in a few minutes.** when the reason is too fast.
6. Any other block can ban the address, email the shop, and redirect, according to the boxes on **Protection**. If more than one redirect is ticked, the homepage is used first, then the CMS page, then Google. With no redirect, the visitor stays on the contact page and sees **Your message could not be sent. Please try again in a few minutes.**

Anti-flood counts every try in the time window, including tries that were already blocked. Several captcha retries can therefore reach the message limit.

A duplicate looks at earlier tries with the same text. Tries that failed only for **Too fast** or **reCAPTCHA** are not counted as the earlier copy.

StopForumSpam and both CleanTalk checks allow the message when the service cannot be reached. reCAPTCHA does the opposite: if Google cannot be reached, the message is blocked.

### 3.1 Overview

![Overview](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

**Overview** counts contact messages, blocked messages and active bans for the dates set under **Analytics parameters**. A customer who passes is counted as a message. A visitor who fails a check is counted as blocked and listed below with the reason.

The cards are **Messages**, **Allowed**, **Blocked**, **Block rate**, **Blocked IP addresses** and **Active bans**.

The chart **Blocked and allowed** shows **Daily** and **Weekly** when the period has more than 7 days. **Weekly** groups the days in sevens from the start of the period. The last group can be shorter. The legend is **Allowed**, **Blocked** and **Total**. With no rows in the period the chart says **No messages in this period.**

**Blocked by reason** lists how many blocks each check produced. The names on this page are **Banned IP**, **Honeypot**, **Too fast**, **Empty user agent**, **Anti-flood**, **Duplicate message**, **Too many links**, **Blocked word**, **Disposable email**, **reCAPTCHA**, **StopForumSpam** and **CleanTalk**. An empty reason is shown as **Unknown**.

**Latest blocked messages** has the columns **Date**, **IP**, **Email** and **Reason**. With nothing blocked, the table says **Nothing has been blocked in this period.**

The buttons **Message attempts** and **Banned IP addresses** open those lists.

The coloured badges under the chart show which checks are on. **reCAPTCHA** is green only when both keys are saved. The switch alone does not turn that badge green. After installation, **Anti-flood**, **Honeypot**, **Minimum time** and **Link limit** are on.

The line under the badges reads like **0 messages between 2026-10-13 and 2026-11-11. 0 blocked, 0 allowed. 0 new bans in this period.** The dates follow the period you selected. A rolling period ends today. The dates are the shop's current window, not a fixed value from the module.

### 3.2 Analytics parameters

![Analytics parameters](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Open the closed panel **Analytics parameters** on **Overview**.

| Field | At the start | What it does |
|---|---|---|
| **Statistics period** | Last 30 days | **Last 7 days**, **Last 30 days**, **Last 90 days**, **Last 180 days**, **Last 365 days** or **Custom range**. The cards, the chart and the latest list use this window. Last 30 days is the starting choice. Last 7 days shows a short burst and drops older blocks from the chart. Last 365 days covers a year, so one busy day is a small slice. Custom range uses **From** and **To**. The other choices ignore those dates and always end today. |
| **From** | the start of the current window | Date as YYYY-MM-DD. Used when **Statistics period** is **Custom range**. A date later than **To** is swapped with **To**. A range longer than 366 days is shortened from this side. A future date is pulled back to today. An empty or invalid date is replaced by the date 30 days ago. Rolling periods ignore this field. |
| **To** | today | Date as YYYY-MM-DD. Used when **Statistics period** is **Custom range**. A future date is pulled back to today. If **To** is earlier than **From**, the two dates are swapped. An empty or invalid date is replaced by today. Rolling periods ignore this field and always end today. |

**Save** stores the period. The page confirms **Settings saved.**

### 3.3 Anti-flood

![Anti-flood](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

Anti-flood counts how many contact messages one IP address sends in a time window. A customer who writes a few times still passes. The next message past the limit is rejected, and **Protection** can ban that address when the ban box is ticked.

| Field | At the start | What it does |
|---|---|---|
| **Enable anti-flood** | Yes | On: each IP is counted in the time window, and the next contact message past the limit is blocked. Off: a script can keep sending from the same IP with no limit from this check. A low message limit also blocks a customer who sends a correction from the same office. Leave it on for a public contact page. Turn it off only while you send test messages from one address. |
| **Time window** | 10 minutes | Minutes. Only contact messages from the last X minutes count toward the limit. 1 or 2 minutes catches a burst and then forgets it, so a slow script can continue. 60 minutes or more also counts a customer who writes, waits and writes again from the same IP. A saved 0 is treated as 1. |
| **Allowed messages** | 5 | How many contact messages one IP may send in the time window. The next one is blocked. 5 lets a customer correct a message and send it again. 1 blocks the second send, which stops scripts and also a customer who clicks send twice. A high value such as 20 lets many messages through. The counter includes earlier sends from that IP, including blocked ones, so several captcha retries can reach the limit. A saved 0 is treated as 1. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk checks the visitor's IP and email against a spam database. Turn on the free option to use the MyPresta proxy without a CleanTalk account, or the paid option when you have your own access key. An unknown address is accepted. An address already reported as spam is rejected. If the service cannot be reached, the message is allowed.

| Field | At the start | What it does |
|---|---|---|
| **Enable free CleanTalk** | No | Asks the MyPresta CleanTalk proxy whether this IP or email is already known as spam. No CleanTalk account is required. Off skips this check. If the proxy cannot be reached, or PHP has no OpenSSL encrypt function, the message is allowed. A bot that is not in the database also passes. Turn it on when you do not have a paid key. |
| **Enable paid CleanTalk API** | No | Uses the access key from your CleanTalk account. Turn it on after you paste the key. Leave it off if you have no subscription. An empty or rejected key blocks nobody, so spam that only this check would catch is accepted. An address on the list is rejected, and a customer on the same IP can be rejected too. |
| **Access key** | empty | Paste the access key from your CleanTalk account, with no extra spaces. The paid check runs only when this field has a key. Empty, with the paid switch on, means no paid check, and the page shows **CleanTalk paid API is enabled, but the access key is empty.** A revoked key is treated as a failed check and the message is allowed. |
| **Spam rate threshold** | 1 | A score from 0.0 to 1.0. A CleanTalk spam rate equal to this value or higher is treated as spam. An address CleanTalk marks as appearing in spam is blocked at any value. 1 blocks addresses CleanTalk is sure about. A lower value such as 0.5 also blocks uncertain results and can stop a real customer on a shared IP. A saved 0 is treated as 1, so the check stays strict. |

The link **Open CleanTalk account page** opens the CleanTalk account page in a new browser tab.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam is a free database of IP addresses and emails reported for spam on forums and forms. The check does not need an API key. A customer who was never reported is accepted. An address with enough reports is rejected. If the service cannot be reached, the message is allowed.

| Field | At the start | What it does |
|---|---|---|
| **Enable StopForumSpam** | No | The visitor's IP and the email from the form are looked up. Off skips the check. If the service cannot be reached, the message is allowed, so a network problem does not block customers, and spam that this check would have caught also passes. Leave it on for a public contact page. |
| **Minimum reports** | 1 | Block when StopForumSpam has recorded this IP or email at least this many times. At 1, a single report blocks the address, including a customer reported once by mistake. At 5 or more, addresses with few reports pass, so more spam gets through. A saved 0 is treated as 1. |
| **API key** | empty | Optional. The public lookup works without a key. Leave it empty, or save a key if you already have a StopForumSpam account. The module still uses the public lookup, so a wrong key does not change who is blocked. |

The link **Sign up** opens the StopForumSpam registration page.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA runs in the browser on the contact page. Use it when bots send messages that look like ordinary text, and choose the same type that was chosen for the key in the Google admin console. v2 shows a checkbox the customer ticks. v3 scores the visit with no challenge: a passing score is accepted, and a failing score rejects the message without banning the IP.

The panel text **How to get the site key and the secret key** says: create the key in the Google admin console, then paste the site key and the secret key below. The type selected here must be the same type chosen for that key. A mismatched type makes every visitor fail, including a real customer.

| Field | At the start | What it does |
|---|---|---|
| **Enable reCAPTCHA** | Yes | The contact page asks the visitor to pass reCAPTCHA before the message is accepted. With empty keys the captcha stays off even when this switch is on, and the page shows **reCAPTCHA is enabled, but the site key or the secret key is empty. The captcha stays off until both keys are saved.** A customer who fails can try again. That failure does not ban the IP. |
| **reCAPTCHA type** | reCAPTCHA v2 | **reCAPTCHA v2** shows a checkbox. **reCAPTCHA v3** scores the visit in the background and shows no challenge. Use the same type that was chosen for the key in the Google admin console. A mismatch makes every send fail, including real customers. v2 is the clearer choice when you want a visible check. v3 is less visible and uses the score threshold below. |
| **Site key** | empty | The public key from the Google reCAPTCHA admin for this shop's domain. Paste the site key that belongs to the type selected above, with no spaces. Both keys are required. An empty site key leaves the captcha off. A key for another domain or another type makes real customers fail. |
| **Secret key** | empty | The secret key stays on the server. It is never sent to the browser. Use the secret key from the same pair as the site key. An empty secret key leaves the captcha off. A secret key from another site makes Google reject every visit, so customers cannot send the form. |
| **v2 theme** | Light | **Light** or **Dark** colour of the v2 checkbox. Light on a white contact page, Dark on a dark page. v3 ignores this setting and uses Google's standard badge. The theme does not change who is blocked. A dark widget on a white page is harder to see, so more people skip the checkbox and the message is rejected. |
| **v3 score threshold** | 0.5 | A score from 0.0 to 1.0. Used when the type is v3. Google scores the visit, and a score below this value is rejected. 0.5 is the starting value. A higher value such as 0.9 is stricter and can reject customers on a shared or unusual network. A lower value such as 0.1 lets more automated visits through. A rejection does not ban the IP. If the saved value is missing, 0.5 is used. |

### 3.7 Message filters

![Message filters, first fields](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Message filters, remaining fields](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

The filters run in the shop, before any external spam service. For a public contact page, leave the honeypot and the minimum time on, and add links, words, disposable emails or duplicates when the blocked list shows a repeating pattern. A customer who fills the form in the ordinary way is accepted. A script is rejected. A failed captcha or a too-fast send does not ban the IP. The other filters can ban it when the ban box is ticked on **Protection**.

| Field | At the start | What it does |
|---|---|---|
| **Honeypot field** | Yes | Adds a hidden field that people do not see. A customer leaves it empty and the message continues. A script that fills every field is blocked, and **Protection** can ban that IP. Turn it off if an autofill tool fills the hidden field and your customers are blocked. |
| **Minimum time on the page** | Yes | Blocks a send that happens faster than the limit after the page script starts. A customer who reads the page and writes needs more than a few seconds. A script that sends immediately is blocked. A missing timer is accepted, so a browser without JavaScript can still send. This block does not ban the IP. Off lets instant sends through this check. |
| **Minimum seconds** | 3 | Seconds. Used when the minimum time is on. 1 second still catches an instant script and rarely touches a customer. 15 seconds or more blocks a customer who already knows the message and sends quickly. The timer starts when the page script runs. A saved 0 is treated as 1. |
| **Limit links in the message** | Yes | Counts http://, https:// and www. in the message. On when the spam you receive is mostly links. Off when customers often paste a product address. Off accepts a message full of links. On, with a low maximum, also blocks a customer who pastes several addresses. |
| **Maximum links** | 3 | A message with more links is blocked. Counted only when the link limit is on. 3 lets a customer paste a few addresses. 0 blocks every message that contains a link, even one product page. A high value such as 20 lets a typical link-spam message through. |
| **Blocked words** | No | A case-insensitive search in the email and in the message. Turn it on after you add phrases you have seen in spam. Off, or on with an empty list, blocks nothing. A short common word also blocks a real customer who used it. |
| **Words and phrases** | empty | One word or phrase per line. Used when blocked words are on. Leave it empty until you copy phrases from real spam, then add those lines. A phrase matches anywhere in the email or the message, so a short piece such as win also matches window and blocks an ordinary question. A long, specific phrase blocks only that text. |
| **Block disposable emails** | No | Blocks a built-in list of temporary mailbox domains and the domains added below. On when you do not want messages from throwaway mailboxes. An ordinary address is accepted. A temporary mailbox on the list is blocked, and **Protection** can ban that IP. Domains that are not on the list still pass until you add them. Off accepts every domain. |
| **Extra disposable domains** | empty | One domain per line, for example dropmail.test. Used when disposable emails are blocked. Leave it empty until a domain shows up on the attempts list. A domain entered here also blocks its subdomains. Do not type @. Entering a real mail provider blocks every customer who uses that provider. |
| **Block duplicate messages** | No | Blocks the same message text sent again in the time window, from any IP. On when the same advertisement is sent from many addresses. Messages shorter than 20 characters are skipped, so a short greeting can be sent again. A captcha retry is not treated as a duplicate. A customer who sends the same long question twice in the window is blocked the second time. Off allows the same text to be sent again. |
| **Duplicate window** | 60 minutes | How long the message text is remembered. A short window such as 5 minutes forgets the text quickly, so the same spam can return. A long window such as 1440 minutes (one day) also blocks a customer who sends the same question again later the same day. Used only when duplicate blocking is on. A saved 0 is treated as 1. |
| **Block an empty user agent** | No | Blocks a request that does not send a browser identifier. Leave it off unless the attempts show spam with an empty identifier. Real browsers send one. On also blocks privacy tools that remove the identifier, so those customers cannot send. Off ignores an empty identifier. |
| **Skip checks for logged-in customers** | No | A logged-in customer skips every check, including an active ban. Leave it off in a shop where anyone can register. Turn it on when your customers have accounts you trust. Guests are still checked. On lets a logged-in bot through. Off checks logged-in customers the same way as guests, so a banned office address stays banned for an account too. |

### 3.8 Whitelist

![Whitelist](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

The whitelist is the list of IP addresses that skip every check, including an active ban. Add your office, an agency, or a monitoring tool that sends a test message. Everyone else is still checked. An empty list means no address is skipped. A line added by mistake lets that address through, including a bot that uses it.

| Field | At the start | What it does |
|---|---|---|
| **IP addresses** | empty | One address per line. A line that ends with * matches the start of the address, for example 192.168.1.*. Leave it empty unless an address must always be able to write, such as your office. A full address skips the checks only for that IP. A prefix with a star skips the whole range, including every bot in that range. A typo matches nothing, so that visitor stays protected. Compare IPv4 and IPv6 exactly as the shop shows them. |

### 3.9 Protection

![Protection](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

A failed check always rejects the message. The boxes under **What to do with spam** are extra steps for a ban, the honeypot, flood, the message filters, StopForumSpam and CleanTalk. They do not run when the only problem is the captcha or a too-fast send. A customer who passes the checks is not affected.

| Field | At the start | What it does |
|---|---|---|
| **Extra actions** | none ticked | **Ban the IP address**: on when the same address keeps coming back. The next message from that IP is rejected until you turn the ban off. A shared office IP then blocks every customer who uses it. **Email the shop**: on when you want a notice in the inbox. One email per IP, then silence for 30 minutes. Off leaves the blocked spam only on the attempts list. **Redirect to the homepage**, **Redirect to a CMS page** and **Redirect to Google**: leave them off so the visitor stays on the contact page and reads the error. If several redirects are ticked, the homepage is used first, then the CMS page, then Google. |
| **CMS page** | the first page in the shop's list | Used when **Redirect to a CMS page** is ticked. Choose a short page that tells the visitor the message was not sent. If the shop has no CMS pages, the list contains **No CMS page**. With no page selected, the CMS redirect is skipped. If **Redirect to Google** is also ticked, Google is used next. Otherwise the visitor stays on the contact page with the error. A customer who passes the checks never sees this page because of the module. The pages in the list are the shop's CMS pages. On a shop that already has pages, the stored empty choice is not in the list, so the list shows the first page. Click **Save** only when that page is the one you want. |

### 3.10 Email

![Email](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

The panel **Email to the shop** sets the subject of the email sent to the shop address when a message is blocked. The email is sent only when **Email the shop** is ticked on **Protection**, and only for blocks other than a failed captcha or a too-fast send. One email is sent on the first block from an IP. Further blocks from that IP for 30 minutes send no mail. An accepted customer does not trigger this email. If the shop email in Shop Parameters is empty, no mail is sent.

| Field | At the start | What it does |
|---|---|---|
| **Subject** | Contact form spam blocked | The subject of the shop notice. The short check name is added at the end, for example [flood]. The message goes to the shop email set in Shop Parameters. Use a short subject that your mailbox rules recognise, filled in for each language of the shop. An empty subject is replaced by Contact form spam blocked. The subject does not change who is blocked. |

The language button switches the subject to another shop language. The body of the mail is the module's mail template for that language. The English body starts with **Contact form blocked.** and then lists the check, the IP, the email, the date and the start of the message.

### 3.11 Updates

![Updates](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

This page asks MyPresta.eu whether a newer module version is available. The settings here only affect the update check. They do not change the contact-page protection.

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | **Check now** asks MyPresta.eu immediately whether a newer version exists. Use it after you install the module and again before a busy period. The button does not download or install a file. If the shop server cannot reach MyPresta.eu, the click does not show a new version. |
| **Updates notifications** | Enable | **Enable** checks MyPresta.eu for an update and shows a notice in the back office when a newer version is published. The automatic check runs about every 3 days while you work in the back office. **Disable** stops that check and the notice. A new version then stays unnoticed until you click **Check now**. This choice does not change the contact-form protection. |
| **Module page link** | Contact page - spam protection PRO | A direct link to the module page on MyPresta.eu. The changelog on that page shows what changed. Open it before you update. The link does not install a file. If the page does not load, open the address in a new browser tab. |

**Save** confirms **Update settings saved.**

When a newer version exists, the back office can show **New version available, check http://MyPresta.eu for more informations** and **More details in changelog**. **Check now** answers **New version available!** or **Module is up to date!**

### 3.12 Message attempts

![Message attempts](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Open **Message attempts** under **Contact protection**, or use the button of that name on **Overview**.

The shop writes a row when a contact message is checked. There is no add button. You do not edit a row from this list. You can delete a row.

The columns are **ID**, **IP**, **Email**, **Reason**, **Blocked** and **Date**. The newest row is first. An empty list says **No records found**.

**Reason** on this list is the short name, not the long name from **Overview**:

| On Overview | On this list |
|---|---|
| **Banned IP** | ban |
| **Honeypot** | honeypot |
| **Too fast** | timing |
| **Empty user agent** | user-agent |
| **Anti-flood** | flood |
| **Duplicate message** | duplicate |
| **Too many links** | links |
| **Blocked word** | keyword |
| **Disposable email** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

An allowed message has an empty reason and **Blocked** set to no.

The row action is delete. Tick rows and use **Delete selected**. The shop asks **Delete selected items?** before it removes them.

### 3.13 Banned IP addresses

![Banned IP addresses](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Open **Banned IP addresses** under **Contact protection**, or use the button of that name on **Overview**.

The columns are **ID**, **IP**, **Date** and **Active**. The newest row is first. An empty list says **No records found**.

The plus button opens **Add new**. The form title is **Banned IP address**.

![New banned IP address](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Field | At the start | What it does |
|---|---|---|
| **IP address** | empty | One IP address. Required. While the ban is active, contact messages from this IP are rejected. Paste the address from the attempts list, exactly as logged. A wrong digit blocks a different visitor, or blocks nobody. A shared office address also blocks real customers on that IP until you turn the ban off. |
| **Active** | No | **Yes** keeps the ban in force and the contact form rejects this IP. **No** keeps the row and stops blocking, so the address can write again unless another check stops it. Choose **Yes** while that address is still posting spam. Choose **No** when a customer at that IP needs to get through and you want to keep the record. A ban created from **Protection** is stored already active. |

**Save** stores the row. **Cancel** returns to the list without saving.

On an existing row, **Edit** opens the same form, **Delete** removes the row, and the **Active** icon turns the ban on or off. Tick rows and use **Delete selected**. The shop asks **Delete selected items?**

A ban created by **Protection** rejects the next contact message from that IP with the reason **Banned IP** (short name ban) and does not create a second ban for the same block.

## 4. Storefront

The module works on the shop's contact page only. It does not add a block to other pages.

With the settings from installation, and before you save both reCAPTCHA keys, the customer sees the ordinary contact form of the theme. There is nothing extra on the page to capture: the honeypot sits off the screen, the timer is hidden, and the reCAPTCHA checkbox is not shown.

After you save both keys and leave **Enable reCAPTCHA** on:

- **reCAPTCHA v2** adds the checkbox. If the customer sends without ticking it, the page says **Please confirm that you are not a robot.** and the form is not sent.
- **reCAPTCHA v3** adds no challenge. Google's badge can appear. A score below the threshold is rejected on the server.

| What happened | What the customer sees |
|---|---|
| v2 checkbox not ticked | **Please confirm that you are not a robot.** The form stays on the page. |
| Captcha failed, or Google could not be reached | **Captcha verification failed. Please try again.** |
| Any other block, and no redirect is ticked | **Your message could not be sent. Please try again in a few minutes.** |
| Homepage redirect ticked | The shop homepage. No error on the contact page. |
| CMS redirect ticked, a page is selected, and the homepage redirect is not ticked | That CMS page. |
| Google redirect ticked, and the other redirects are not used | https://www.google.com |

A message that passes is sent by the contact form as usual. The module does not change that confirmation.

The theme can replace the module's front stylesheet and script. It cannot replace a module template for the form, because the form is the shop's contact form. If the theme removes the contact form's send button, the honeypot, the timer and the captcha are not attached.

## 5. Problems

**The customer sees "Please confirm that you are not a robot."**

The v2 checkbox was not ticked. Ask the customer to tick it and send again. This does not ban the IP.

**The customer sees "Captcha verification failed. Please try again."**

The captcha did not pass, or the shop could not reach Google. Check that **reCAPTCHA type** matches the key in the Google console, that **Site key** and **Secret key** are the pair for this domain, and that the shop server can reach Google. A failed captcha does not ban the IP. The customer can try again.

**The customer sees "Your message could not be sent. Please try again in a few minutes."**

A check other than a passed-through captcha rejected the message, and no redirect is ticked. Open **Message attempts**, find the IP or the email, and read **Reason**. Then:

- flood: raise **Allowed messages** or **Time window**, or wait until the window passes.
- honeypot: a script filled the hidden field, or an autofill tool did. Turn **Honeypot field** off if your own customers are blocked.
- timing: the form was sent faster than **Minimum seconds**. Raise that number only if real customers are blocked. This block does not ban the IP.
- user-agent: turn **Block an empty user agent** off if a privacy tool is involved.
- duplicate: the same text of 20 characters or more was sent again inside **Duplicate window**.
- links: the message has more links than **Maximum links**.
- keyword: a line in **Words and phrases** matched the email or the message.
- disposable: the email domain is on the built-in list or in **Extra disposable domains**.
- stopforumspam or cleantalk: the address is in that service. Raise **Minimum reports** or **Spam rate threshold**, or add the address to **Whitelist** if it is a customer.
- ban: the address is on **Banned IP addresses** with **Active** set to **Yes**. Set **Active** to **No**, or delete the row.

**The customer is sent to the homepage, a CMS page, or Google.**

A hard block happened and a redirect is ticked on **Protection**. Untick **Redirect to the homepage**, **Redirect to a CMS page** and **Redirect to Google** if you want the error to stay on the contact page. When several are ticked, the homepage wins, then the CMS page, then Google.

**A whole office cannot write.**

The office shares one IP. That IP is banned, or it is over the anti-flood limit, or a service lists it. Open **Banned IP addresses** and set **Active** to **No**, or add the address under **Whitelist**. A whitelist line skips every check, including the ban.

**reCAPTCHA stays off.**

The warning says **reCAPTCHA is enabled, but the site key or the secret key is empty. The captcha stays off until both keys are saved.** Paste both keys and click **Save**.

**Paid CleanTalk blocks nobody.**

The warning says **CleanTalk paid API is enabled, but the access key is empty.** Paste **Access key** and click **Save**. A rejected key also lets the message through. If the service cannot be reached, the message is allowed.

**No email arrives at the shop.**

**Email the shop** must be ticked. The block must be something other than captcha or too fast. The same IP sends only one mail in 30 minutes. The shop email in Shop Parameters must be filled in. The subject gains the short check name, for example [flood].

**Check now shows nothing new.**

The shop server could not reach MyPresta.eu, or the module is already current. The answer **Module is up to date!** means no newer version was reported. **Check now** does not download the file.

**The lists are empty after you installed the module again.**

Uninstall deletes the attempts and the bans. A new installation does not bring them back.

## 6. For developers

### 6.1 Overview

Main class `mycontactprotectionpro`, version `1.0.0`, author MyPresta.eu, tab `administration`. The list name is **Contact page - spam protection PRO**. Compatibility in the file is PrestaShop 1.7.7.0 through 9.99.99.

Settings are read with `Configuration::get` in the shop context that is active when **Save** is clicked. A contact-page POST with `submitMessage` runs `hookActionFrontControllerInitAfter`. A pass writes an allowed row and lets the contact form send. A block writes a blocked row, and a hard reason can insert a ban, send the merchant mail and redirect.

`install()` calls the parent install, writes the configuration, creates the two tables, creates the menu and registers the three hooks. It does not clear the cache. There is no `enable()` or `disable()`. `uninstall()` deletes the configuration keys listed in 6.7, plus `update_mycontactprotectionpro` and `updatev_mycontactprotectionpro`, deletes the menu tabs, drops both tables and calls the parent uninstall. It does not delete `mypresta_updates`. The files stay until the module directory is removed.

### 6.2 Files

| File | Role |
|---|---|
| mycontactprotectionpro.php | install, uninstall, hooks, configuration forms, the check order, the dashboard, the merchant mail |
| controllers/admin/AdminMycontactprotectionpro.php | menu parent; redirects to the module configuration |
| controllers/admin/AdminMycontactprotectionproAttempts.php | attempts list and delete |
| controllers/admin/AdminMycontactprotectionproBans.php | bans list, add, edit, delete, active switch |
| models/attempt.php | attempts table and the counters |
| models/ban.php | bans table and `banIp()` |
| lib/sfs.php | StopForumSpam lookup |
| lib/ctalk.php | free and paid CleanTalk lookups |
| lib/updatesChecker.php | MyPresta update check, class `mycontactprotectionproUpdate` |
| lib/recaptcha/ | reCAPTCHA library used by the module |
| views/templates/admin/configure.tpl | tab bar and the overview markup |
| views/css/admin.css | back office layout of the configuration |
| views/css/front.css | places the honeypot off screen |
| views/js/front.js | honeypot, timer, v2 checkbox and v3 token on the contact form |
| mails/{iso}/mcpp_merchant.html | HTML body of the shop notice; not a `$this->l()` string |
| mails/{iso}/mcpp_merchant.txt | plain-text body of the shop notice |
| translations/{iso}.php | back office and customer strings |
| key.php | value sent with the free CleanTalk request |

There is no front controller and no front template for the contact form.

### 6.3 Controllers

| Class | Menu parent | What it accepts |
|---|---|---|
| AdminMycontactprotectionproController | id 0, icon security, title Contact protection | redirects to AdminModules with `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | table `mcpp_attempt`, order `id_mcpp_attempt` DESC, `list_no_link`, row delete, bulk delete. No add. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | table `mcpp_ban`, order `id_mcpp_ban` DESC, row edit and delete, bulk delete, status on `active`. Add form fields `ip` (required) and `active`. |

The configuration itself is `getContent()` on the module, not a separate controller. The tab query is `mcpp_tab`. Submitted form names are `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. The updates form posts `submit_settings_updates` and `submit_settings_updates_now`.

There is no front controller. The contact page is the shop's `ContactController`.

### 6.4 Hooks

| Hook | When it runs |
|---|---|
| actionFrontControllerSetMedia | on the contact page, when the honeypot, the timer or a ready reCAPTCHA is on; adds front.css and front.js and passes the public settings to the script |
| actionFrontControllerInitAfter | on a contact-page POST with submitMessage; runs the checks and either returns, stops the form, or redirects |
| displayBackOfficeHeader | adds views/css/admin.css |

The module does not register a display hook of its own. The contact page is recognised by `php_self` equal to `contact`, or by the controller class `ContactController` or `ContactControllerCore`.

In the back office the constructor calls `runUpdateSetUp()`. That method checks MyPresta about every 259200 seconds when `mypresta_updates` is not 0, stores the result in `updatev_mycontactprotectionpro`, and appends a controller warning when the stored version is newer.

### 6.5 Overrides

The module ships no class override and no controller override.

### 6.6 Database

The prefix is the shop prefix. No column is added when a page is opened. Uninstall drops both tables.

| Table | Contents |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int primary key, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 of the lower-case message), `reason` varchar 255 (short name, empty when allowed), `blocked` tinyint, `date_add` datetime. Keys `ip_date` (`ip`, `date_add`) and `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int primary key, `ip` varchar 64, `date_add` datetime, `active` tinyint default 1. Key `ip_active` (`ip`, `active`). The add form opens with Active No. `banIp()` inserts or updates the row with `active` 1. |

### 6.7 Configuration keys and translations

Value used when the key is missing:

| Key | When missing |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | empty |
| mcpp_ct_rate | 1, and a saved 0 is also treated as 1 |
| mcpp_sfs | 0 |
| mcpp_sfs_key | empty |
| mcpp_sfs_freq | 1, and a saved 0 is also treated as 1 |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, which is v2; 1 is v3 |
| mcpp_rc_site | empty |
| mcpp_rc_secret | empty |
| mcpp_rc_theme | light, unless the saved value is dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, and a saved 0 is treated as 1 |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | empty |
| mcpp_disp | 0 |
| mcpp_disp_extra | empty |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, and a saved 0 is treated as 1 |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, ban the IP |
| mcpp_ptype_4 | 0, email the shop |
| mcpp_ptype_7 | 0, homepage redirect |
| mcpp_ptype_6 | 0, CMS redirect |
| mcpp_ptype_5 | 0, Google redirect |
| mcpp_cms | 0 |
| mcpp_wh_ip | empty |
| mcpp_mtitle | Contact form spam blocked, per language; an empty subject uses this English sentence |
| mcpp_dash_preset | 30; any value other than 7, 30, 90, 180, 365 or custom falls back to 30 |
| mcpp_dash_from | empty until the overview builds the window |
| mcpp_dash_to | empty until the overview builds the window |

`mypresta_updates` is shared. When it is missing, notifications are treated as enabled. Uninstall does not delete it. `key.php` assigns `mkey`. If it is empty, the free CleanTalk request uses `nlc`. The update check uses `nokey` when the value is missing.

Built-in disposable domains, matched on the domain and its subdomains: mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. Domains from `mcpp_disp_extra` are added the same way.

Labels, field descriptions and the three customer sentences are `$this->l()` in `mycontactprotectionpro.php`, `lib/updatesChecker.php` (source `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (source `AdminMycontactprotectionproAttempts`) and `AdminMycontactprotectionproBans.php` (source `AdminMycontactprotectionproBans`). Add a language with `translations/{iso}.php`. Field descriptions live in the `desc` of each HelperForm input in the main class and in the bans controller.

The mail bodies in `mails/{iso}/mcpp_merchant.html` and `mails/{iso}/mcpp_merchant.txt` are not `$this->l()`. The English text body starts with `Contact form blocked.` The subject is `mcpp_mtitle` for the mail language, with the short reason appended, for example ` [flood]`. The mail goes to `PS_SHOP_EMAIL`. An empty shop email sends nothing. The message in the body is the first 500 characters with tags stripped.

### 6.8 Extending

A theme can override `views/css/front.css` and `views/js/front.js`. There is no front template for the contact form, so the theme has no module form template to override. The form markup is the shop contact form. `front.js` looks for `form [name=submitMessage]`. If that button is missing, the script returns and adds nothing.

The honeypot input name is `mcpp_website`. The timer input name is `mcpp_ts`. A filled honeypot is a hit. A missing timer is not a hit. A timer in the future is a hit. reCAPTCHA v3 uses the action `contact`.

The check order is fixed: ban, honeypot, timing, empty user agent, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, free CleanTalk, paid CleanTalk. The first match wins. Whitelist and the logged-in bypass return before a row is written. If `protectionEnabled()` is false and the IP is not banned, the hook returns without writing a row. `protectionEnabled()` is true when any of `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` is 1, or when reCAPTCHA is ready (switch on and both keys non-empty).

Hard reasons are every reason except `timing` and `recaptcha`. Only a hard reason can create a ban, send the merchant mail and redirect. Redirect priority is `mcpp_ptype_7` (homepage), then `mcpp_ptype_6` when `mcpp_cms` is greater than 0, then `mcpp_ptype_5` (`https://www.google.com`). Otherwise the module unsets `submitMessage` and adds the error. A recaptcha block uses the captcha sentence. Every other block that stays on the page uses the few-minutes sentence.

Free CleanTalk is skipped when `openssl_encrypt` does not exist. StopForumSpam and CleanTalk allow the message when the remote call fails. reCAPTCHA blocks the message when the remote call fails. Flood uses `countByIpSince`, which counts every attempt in the window. Duplicate uses `countDuplicateSince`, which ignores rows whose reason is `timing` or `recaptcha`, and only runs when the message length is at least 20.

PHP calls: `curl_init` when it exists, otherwise `file_get_contents` for StopForumSpam, CleanTalk and the update check when `allow_url_fopen` is on. `openssl_encrypt` for the free CleanTalk request. `json_decode` for the StopForumSpam, paid CleanTalk and reCAPTCHA replies. No other module is required.
## 7. Help

Module page: https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

To ask about this module, sign in at [https://mypresta.eu/](https://mypresta.eu/) and open the contact form. Choose the topic **Support for paid modules**. The form asks you to sign in. Then pick this module from the purchase history. The page is [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).
