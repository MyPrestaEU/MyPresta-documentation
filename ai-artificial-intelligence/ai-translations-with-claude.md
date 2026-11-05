---
title: "AI Translations with Claude - documentation and user manual"
description: "Setup and troubleshooting guide for shops that already run AI Translations with Claude."
sidebar:
  label: "AI Translations with Claude - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy AI Translations with Claude Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Requirements

The module works on PrestaShop 1.7.0.0 and later, including PrestaShop 8 and 9.

- **PrestaShop:** 1.7.0.0 or later.
- **PHP:** 5.6 or later.
- **PHP extensions:** cURL, OpenSSL, SimpleXML, and mbstring.
- **Other modules:** the module does not depend on any other module.
- **Outside the shop:** an Anthropic account and an API key, which you can create at https://console.anthropic.com/settings/keys. The shop server must be able to reach `https://api.anthropic.com/v1/messages`.
- **Optional:** a scheduled task on the server that calls the cron address from **Settings**. Without it, you process jobs yourself on **Jobs**.
- **Large catalogues:** a domain with thousands of strings means many API calls. The module splits a job into slices of **Batch size**. Before you start, run **Estimate** on **Bulk** to see what the job will cost.
- The shop needs at least two languages. With only one language, the back office shows **The shop needs at least two languages.** and there is nothing to translate.

## 2. Installation

1. Open **Modules**, then **Module Manager**. Choose **Upload a module**, upload the ZIP file, and click **Install** next to **AI Translations with Claude**.
2. After installation, **AI Translations with Claude** appears in the **International** menu.
3. Installation does not clear the shop cache. The module clears the cache when it saves a translation.

Next, open **AI Translations with Claude**, go to **Settings**, and paste your Claude key. Until a key is saved, every page of the module shows **No Claude API key.** with an **Open Settings** link.

**Uninstalling.** In **Module Manager**, click **Uninstall** and confirm **Delete this module and its data (jobs, glossary, cache)?**

- The menu entry disappears. Jobs, the glossary, exclude patterns, the call history, the **Review** queue, rollback copies, the cost ledger, and the module settings (including the API key) are all deleted.
- Text the module has already written into the shop stays: catalogue translations and the translation files of classic modules written by this module. Your choice for update checks also stays.
- A fresh installation does not bring back deleted jobs, glossary entries, or history. It sets the default values and creates a new cron address.

## 3. Configuration and daily use

The whole module lives on one page: **International**, then **AI Translations with Claude**. The tabs are **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History**, and **Settings**. **Updates** sits at the end of the bar. **Help** opens a panel for the tab you are on.

Button and field names in this manual are the ones from the English back office. In another back-office language, you will see the translation of the same control.

**From the first click to a saved translation**

An employee starts the work in the back office. Customers never trigger it.

1. **Settings.** Paste your Claude key, choose the model and the source language, click **Test connection**, then **Save**. Without a key, no tool sends text to Claude.
2. **Choose how you want to work.**
   - A few strings, or one domain, with a check before saving: **Manual** (3.3).
   - A large domain, a theme, or a module: **Bulk**, then the job on **Jobs** (3.4 and 3.5).
   - Product, category, and CMS fields: **Catalog**, up to 100 records at a time (3.7).
   - Single fields on **International → Translations** (3.12) and on product, category, and CMS forms (3.13).
3. **Quality check.** Every translated string is checked for placeholders and HTML. A string that fails the check is not saved. A string scored below 70, a string more than two and a half times longer than the source, or a string that still contains English words such as *the*, *and*, *with*, *your*, or *please*, goes to **Review**.
4. **Saving.**
   - **Manual:** **Translate selected (review)** saves nothing until you click **Save approved**. **Save now (skip review)** writes the valid rows immediately.
   - **Bulk:** the job waits on **Jobs**. It writes only after **Process slice**, **Auto-process**, or a call to the cron address. A job with **Dry-run job** turned on writes nothing.
   - **Catalog:** valid rows are written straight away in the target language.
   - **International → Translations** and the shop forms: the buttons only fill in the fields. PrestaShop's **Save** button writes them.
   - With **Allow publish / save** turned off, **Manual**, **Bulk**, and **Catalog** do not write anything into the shop.
5. **End of the job.** On **Jobs**, the status changes to **completed** or **completed_with_errors**. Rows on **Review** disappear from the list after **Approve** or **Reject**. **Catalog** reports how many rows were saved and how many failed.

### 3.1. Module configuration

Open **Modules**, then **Module Manager**, find **AI Translations with Claude**, and click **Configure**. The **Dashboard** opens. Switch to **Settings**.

**Save** and **Test connection** are at the bottom of the form. Saving this form does not start a translation and does not change translations already stored in the shop.

![Settings, English back office. Top of the form: Claude API key, Model, Add a Claude model, Tone, and Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Connection**

| Field | On install | What it does |
|---|---|---|
| **Claude API key** | empty | The secret key this shop sends to Claude. Paste the key from https://console.anthropic.com/settings/keys. Leave the box empty to keep the key you already saved. A new value replaces the stored key. An empty box does not delete it. Once a key is saved, the help text shows **Key saved:** and a masked version of the key. |
| **Model** | claude-haiku-4-5 | The Claude model that writes the translations. The built-in names stay in the list: claude-haiku-4-5, claude-sonnet-4-5, and claude-opus-4-5. The next translation uses the model you select. If your account cannot use a model, the call fails, and the error is recorded on **History**. |
| **Add a Claude model** | empty | Type the exact model ID from your Anthropic account, then click **Add model**. The new ID appears in **Model** and becomes the active model. **Remove** deletes only the IDs you added here. Built-in IDs cannot be deleted. |

Messages: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Tone and source**

| Field | On install | What it does |
|---|---|---|
| **Tone** | Formal | Adds a style instruction to every prompt. **Formal** suits shop and back-office text, **Casual** gives a lighter, more relaxed voice, and **Brand** works together with **Brand voice**. New translations follow the chosen style. Translations already in place stay as they are until you run them again. |
| **Brand voice** | empty | Visible when **Tone** is set to **Brand**. A few plain sentences describing how the shop should sound. The text is added to the next prompt. Leaving it empty adds no extra voice. It does not rewrite translations already saved. |
| **Source locale** | empty | The language the model treats as the original. The empty choice is a dash in the list, which means the screen you are translating supplies the source. Pick the locale your catalogues are written in, usually en-US. **Manual**, **Bulk**, and the icons on **International → Translations** send this locale as the source. The shop's default language does not change. |
| **Individual field buttons — shop forms** | Yes | A button next to each multilingual field on shop forms: product, category, CMS, and the other back-office forms. The button translates only that one field. **No** hides these buttons across the whole shop. Saved translations are not changed. |
| **Individual field checkboxes — shop forms** | Yes | Each of those fields gets a checkbox, and the bar translates only the fields you tick. **No** hides the checkboxes and the bar. The buttons above have their own switch. |
| **Individual field buttons — International → Translations** | Yes | A button next to each field on **International → Translations**. **No** hides these buttons. Shop forms are not affected. One click fills that field. PrestaShop's **Save** still saves the page. |
| **Individual field checkboxes — International → Translations** | Yes | Checkboxes and the bar on **International → Translations**. **No** hides them. Shop forms are not affected. |


![Settings, English back office. Lower part of the form: limits, mail, the cron address, Test connection, and Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Limits**

| Field | On install | What it does |
|---|---|---|
| **Batch size** | 25 | How many strings go into one API call. For a first run, use a value between 10 and 25. The value is kept between 1 and 100. A bigger batch finishes a job with fewer calls. If a call fails, the retry covers a larger chunk. |
| **Dry-run sample** | 10 | How many sample strings **Estimate** shows before a bulk job. The value is kept between 1 and 50. **Estimate** does not write any translations. |
| **Max tokens (0 = default)** | 0 | A cap on the length of one reply. 0 sends a cap of 4096 tokens. Set a number if replies get cut off or if you want them shorter. Only the next call uses the cap. Translations already saved are not shortened. |
| **Budget USD / month** | 0 | A monthly ceiling in US dollars, counted from the usage ledger. 0 means no ceiling. When the ledger reaches that amount, new translations stop. Work already saved stays in place. |
| **Rate limit / min** | 60 | How many API calls this shop may start in one minute. 0 turns off this local limit. Calls above the limit are skipped and listed on **History**. Claude may still apply its own limit. |
| **Log retention days** | 30 | How many days of rows to keep on **History**. Minimum 1. Older rows are removed. This number does not delete jobs, the glossary, or saved translations. |
| **Temperature** | 0.2 | How freely the model may rephrase. Around 0.2 keeps the text close to the source. Values nearer 1 change sentences more. The saved value is kept between 0 and 1. Placeholders and HTML are still checked afterwards. The built-in models receive this value. A model ID you add that is not Claude Haiku, Sonnet, or Opus 4.0, 4.1, 4.5, or 4.6 does not receive it, so this field has no effect on that model. |
| **Allow publish / save** | Yes | Whether this module may write a translation into PrestaShop. **No** blocks saving on **Manual**, in bulk jobs, and on **Catalog**. The icons on the translation page and on shop forms still only fill in the form. PrestaShop's **Save** is separate. |

After **Save**, you will see one of these messages:

- **Settings saved. No translation was started.** The settings are stored, and nothing was translated.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Paste a key into **Claude API key** and click **Save** again.

**Mail and cron**

| Field | On install | What it does |
|---|---|---|
| **Email notify on complete** | No | Sends one email when a bulk job finishes. The job runs either way. Only the email is added or skipped. |
| **Notify email** | empty | The address that receives that email. The field is used only when the switch above is on. Saving the address alone sends no message. |
| **CRON URL** | an address with a token | A secret address that the server can call to process one slice of a waiting job. Copy it into your server's scheduler. Do not publish it. Anyone with the address can start a slice. Opening **Settings** does not start a job. |

**Test connection** checks the key and the model with one short request. It does not translate anything and does not save anything.

- **Connection OK (N ms). No translation was started.** The connection works.
- **Connection was not made. Nothing was translated.** followed by the reason. Check the key and the model. The details are on **History**.

To get started: paste the key, choose the model and the source locale, click **Test connection**, then **Save**. Leave the numbers at their installation values until a job causes trouble.

### 3.2. Dashboard

Open the **Dashboard** tab. It counts the missing catalogue strings, then shows your Claude usage as cards, charts, and the ten most recent prompts. The page does not translate anything and does not change any strings.

![Dashboard, English back office. Coverage for one locale, the cron line, and the history filters.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Coverage**

- **Locale:** the shop locale whose missing strings are counted.
- **Show:** redraws the table for that locale.
- Columns: **Section**, **Total**, **Missing**, **Done**, and a progress bar. The sections are **Back office**, **Themes**, **Installed modules**, **Emails**, and **Others**. **Missing** is the number of strings without a translation in that locale.
- Under the table, **CRON** shows the same address as **CRON URL** in **Settings**.
- An empty table means the shop has no catalogue for that locale yet. Create one under **International → Translations**.

After **Show**, the message reads **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Usage**

- Time presets: **Today**, **7 days**, **30 days**, **This month**, and **All time**.
- Filters: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee**, and **Prompt or reply contains**. Click **Filter**.
- Cards: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**, and **Estimated cost**. The estimated cost is a local calculation, not an invoice from Anthropic.
- Charts: **Requests and errors**, **Tokens sent and received**, and **Requests by model**. Below them are the groups **By day**, **By model**, **By type**, **By language**, and **By employee**, with the columns **Group**, **Calls**, **Sent**, **Received**, and **Total**. An empty group shows **No requests in this range.**
- **Latest prompts** lists ten calls. **View** opens the prompt and the reply. **See all** opens **History** (3.10). An empty list shows **No requests yet.**

Filtering does not delete history and does not change translations.

If most of a section is missing, open **Manual** to translate a few strings, or **Bulk** to translate a whole domain.

### 3.3. Manual

Open **Manual**. It translates one domain, or one classic module, a few dozen strings at a time. Filtering on its own saves nothing.

![Manual, English back office. Section, Source, Target, Domain, Only empty, and Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Field | On install | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue is read: **Back office**, **Themes**, **Installed modules**, **Emails**, or **Others**. Changing the section reloads the page and shows only the fields for that section. Claude is not called. |
| **Theme** | empty | Visible only for **Themes**. Limits the list to one theme. |
| **Module** | empty | Visible only for **Installed modules**. Limits the list to one module. A classic module without a domain loads every string of that module. |
| **Domain** | empty | The same grouping as on **International → Translations**. Choose one and click **Filter**. Hidden for a classic module and for a section that has no domains. |
| **Source** | the **Source locale** from **Settings**, or en-US | The language the strings are read from. Pick a language that already has good text. |
| **Target** | the first language on the list | The language you want to fill. It must exist under **International → Localization → Languages**. |
| **Only empty** | Yes | Shows only strings without a translation. Turning it off shows every string. Saved translations are not deleted. |
| **Search** | empty | Keeps only source strings that contain the word you type. |

Steps:

1. Set **Section**, **Source**, and **Target**.
2. For **Themes**, choose a **Theme**. For **Installed modules**, choose a **Module**.
3. Click **Filter**. The **Domain** list refreshes. Choose a domain and click **Filter** again. For a classic module, skip the domain: **Filter** loads every string in the module.
4. Tick the rows you want. **Check all** and **Uncheck all** select or clear the whole list.
5. Click **Translate selected (review)**. A **Review before save** table opens with **Source**, **AI proposal**, and **Warnings**. Untick any rows you do not want. Edit a proposal directly in its box if it needs fixing. Click **Save approved**.
6. Or tick **Save now (skip review)** before translating. Valid rows are then written straight away, without the review table.

The string list has the columns **Source**, **Current**, and **Status** (**empty** or **filled**).

Messages:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** This is the list for a classic module.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Those rows were skipped. Fix the placeholders and tags so they match the source, then save again.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Changing the section also shows a short line, such as **Section is Back office. Theme and module are not used.**, together with **Nothing was sent to Claude.** The same pattern applies to **Themes**, **Installed modules**, **Emails**, and **Others**.

### 3.4. Bulk

Open **Bulk**. It creates one job covering many domains and languages. **Estimate** saves nothing. **Start job** adds a row to **Jobs**. Nothing is written into the shop until the job is processed and **Allow publish / save** is on.

![Bulk, English back office. Section, Source, Targets, Domains, Policy, and Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Field | On install | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue the job reads. The same choices as on **Manual**. |
| **Theme** / **Module** | empty | Visible only for the matching section, as on **Manual**. |
| **Source** | the **Source locale** from **Settings**, or en-US | The language treated as the original. Every target language is translated from this one. |
| **Targets** | none | One or more languages to fill. Hold Ctrl (or Cmd on a Mac) to select several. A plain click replaces the selection. |
| **Domains** | none | The domains included in the job. Hold Ctrl or Cmd. If you select none, the job covers every domain in the chosen section. |
| **Policy** | Fill empty | **Fill empty** sends only strings without a translation. **Overwrite all** sends every string, including those that already have a translation, and may replace them. **Outdated if equals source** sends only strings whose translation is identical to the source. |
| **Dry-run job** | No | Claude still runs and the job appears on **Jobs**, but the replies are not written into the shop. |

Steps:

1. Choose the section, the source, the target languages, the domains, and the policy.
2. Click **Estimate**. The page shows **Estimate**, the number of strings, a token estimate, a cost estimate, and a **Sample**.
3. If the estimate looks acceptable, click **Start job**. **Jobs** opens with the new job.
4. Process it on **Jobs** (3.5), or leave it for the cron address to pick up.

Messages:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Open **Jobs**. Each row is one run started from **Bulk**.

![Jobs, English back office. The job list. This shop has no jobs yet.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Columns: **#**, **Status**, **Locales** (source first, then the target languages), **Progress** (done/total), **Cost**, **Employee**, **Date**, and **Open**. An empty list shows **No jobs yet.**

Job statuses, as they appear on screen:

- `pending` - waiting. It does not start on its own.
- `running` - in progress.
- `paused` - stopped until you resume it.
- `cancelled` - stopped. Strings that were still waiting were not translated.
- `completed` - every string processed, with no failures.
- `completed_with_errors` - finished, but some strings failed.
- `failed` - the job ended with an error.

**The job screen**

**Open** shows **Job #N**, the status, progress (done/total), **failed**, **skipped**, the cost, the employee number, and the **dry-run** label if the job is a dry run. While the job is open, the progress bar updates by itself. The table below has the columns **ID**, **Domain**, **Locale**, **Status**, **Source**, **New**, and **Error**.

Row statuses: `pending`, `processing`, `done`, `failed`, `skipped` (an exclude pattern matched, or the string was already translated), and `rolled_back`.

Buttons:

- **Process slice** - runs one slice, the size of **Batch size**, then stops. Message: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** When nothing is left: **The job has no more strings waiting.**
- **Auto-process** - repeats slices until the job finishes or an error stops it. It runs in the browser, so the tab must stay open. Closing the tab stops the loop. The job stays in place and can be finished with **Process slice** or the cron address.
- **Pause** - message: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - message: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - failed strings go back to waiting, and the job waits again. Message: **Retried N failed items.**
- **Rollback** - asks **Roll back this job?** and restores the previous translation wherever the module saved a copy before changing it. Message: **Rollback: restored N translations.**
- **Error CSV** - downloads the failed rows. Columns: id, domain, locale, source, error.
- **Failed only** - shows only the failed rows.
- **Review queue** - opens **Review** (3.6).

The job screen has no Cancel button. To stop further work, use **Pause**.

**Automatic pause**

When Claude rejects calls because of a rate limit, the job pauses by itself. The error line reads **Rate limit — job auto-paused. Resume later.** Wait a while, then click **Resume**. **Rate limit / min** on **Settings** lowers the number of calls the shop starts per minute.

Other messages on this screen:

- **Nothing was translated.** followed by **No Claude API key. Nothing was translated.** Paste the key on **Settings**.
- **Allow publish is off in Settings.** A job that is not a dry run will not run until you turn on **Allow publish / save**.
- **Monthly API budget has been exhausted.** Raise **Budget USD / month**, or set it to 0.

### 3.6. Review

Open **Review**, or click **Review queue** on a job. The page heading reads **Needs-review queue (quality score / flags).** It lists the newest rows that the quality check did not pass automatically, up to 100.

![Review, English back office. The review queue is empty.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Columns: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, then **Approve** and **Reject**. An empty list shows **The queue is empty.**

How to read a row:

- **Score** runs from 0 to 100. Rows below 70 land in the queue.
- **Flags:**
  - `validation_failed` - placeholders or HTML did not pass the check.
  - `warning` - a minor note from the check.
  - `length_explosion` - the translation is more than two and a half times longer than the source.
  - `too_short` - the translation is much shorter than a long source.
  - `possible_untranslated` - English words such as *the*, *and*, *with*, *your*, or *please* remain in the translation.
- **Source** is the original text. **AI** is the model's proposal.

**Approve** and **Reject** only change the row's status. The message reads **Review updated.** and the row leaves the list. This action does not write text into the shop and does not change the rest of the domain.

If the job was allowed to save, the proposal may already be in the shop. To undo changes from that job, use **Rollback** on the job in **Jobs**.

### 3.7. Catalog

Open **Catalog**. It translates product, category, or CMS fields stored in the shop's languages. It does not edit **International → Translations**. One click handles at most 100 records. Saved rows are written in the target language.

![Catalog, English back office. Entity, Fields, languages, Only empty, and Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Field | On install | What it does |
|---|---|---|
| **Entity** | product | What is read: **product**, **category**, or **cms**. Changing it reloads the page and shows only that entity's field list. The change itself translates nothing. |
| **Fields** | every field of that entity | Which texts the batch sends. Hold Ctrl or Cmd. Unselected fields are not sent and stay as they are. Product: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Category: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. For a product or category, **Title** is the name. For CMS, **Title** is the page title and **Content** is the page body. Leave **Friendly URL** unselected if your links should stay the same. |
| **Source language** | the first shop language | The language the fields are copied from. That language is not changed. |
| **Target language** | the first shop language | The language that receives the translation. It must differ from the source. |
| **Only empty** | Yes | Skips fields that already contain text in the target language. Turn it off only when you want to replace existing text. On: existing target text stays. Off: the batch may overwrite it, if saving is allowed. |
| **Start after ID** | 0 | Skips records up to this ID. 0 starts from the first record. After a batch, the field is set to the highest ID in that batch, including rows that failed. Click the button again to continue. To retry a failed row, set the ID back below that record before the next click. |

Button: **Translate batch (max 100)**.

Steps:

1. Choose **Entity** and tick the fields.
2. Choose the **Source language** and the **Target language**.
3. Leave **Only empty** on.
4. Click **Translate batch (max 100)**. The message reads **Catalog finished: saved N, failed M.** The page also shows the **Saved** and **failed** counters.
5. Open one record in the target language and check the result before you turn off **Only empty** or run the next batch.

Messages:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Changing **Entity** shows **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Open **Glossary**. The glossary is a list of words and phrases that the model must keep unchanged, or always translate the same way. Adding a row does not change translations already stored. The next translation reads this list.

![Glossary, English back office. Adding a term and the CSV import.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**One term**

| Field | On install | What it does |
|---|---|---|
| **Source term** | empty, required | The word or phrase in the source language. Type it exactly as it appears, including capital letters where they matter. |
| **Target locale** | empty | Limits the row to one locale, for example pl-PL. Empty means the row applies to every target language. A filled-in locale is ignored for other languages. |
| **Target term** | empty | The approved translation. It can be empty only when **Do not translate** is on. |
| **Do not translate** | No | When on, the model copies the term unchanged, for example a brand name, a SKU, or a tag. When off, it uses **Target term**. |

Click **Add**. Messages: **Glossary term added. Translations already stored were not changed.** or **Nothing was added. Type a source term.**

**The table**

Columns: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** or **No**), and **Delete**. **Delete** removes only that row. Message: **Glossary term deleted.** An empty list shows **No glossary terms yet.**

**CSV**

- Choose **CSV file** and click **Import CSV**. Message: **Imported N rows.** If the file is missing: **CSV file is missing.** If it cannot be read: **Cannot open the CSV file.**
- The first row is a header: `source_term`, `target_locale`, `target_term`, `do_not_translate`. That first row is always skipped. Rows with fewer than three columns are skipped too. In the fourth column, an empty value or 0 means **No**. Any other value means **Yes**.
- The import adds rows from the file. It does not check whether a term already exists, so importing the same file twice creates duplicates.
- **Export CSV** downloads the current list as `glossary.csv`. It needs no input file and does not change the list.

Use short, precise terms. A very broad term is enforced every time it appears.

### 3.9. Excludes

Open **Excludes**. An exclude is a pattern of source text that the module will not send to Claude. The text stays in the shop unchanged. Patterns apply on **Manual**, **Bulk**, **Catalog**, and the translation pages.

![Excludes, English back office. Pattern, Type, and the empty list.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Field | On install | What it does |
|---|---|---|
| **Pattern** | empty, required | The text compared with each source string. How the comparison works depends on **Type**. |
| **Type** | exact | **exact** matches the whole string. **prefix** matches the beginning. **contains** matches a fragment anywhere in the string. **regex** is a PHP regular expression, applied exactly as you type it. An invalid expression matches nothing. Start with a short pattern and check what gets skipped. A wrong type can skip too much, or nothing at all. |

Click **Add**. Message: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** An empty pattern gives **Nothing was added. Type a pattern.**

Columns: **Pattern**, **Type**, **On**, and **Delete**. **On** shows 1 when the pattern is active. This screen has no switch to turn a pattern off. To stop using a pattern, click **Delete**, and add it again if you still need it. **Delete** removes only that pattern. It does not delete existing translations. Message: **Pattern deleted.** An empty list shows **No patterns yet.**

Use excludes for text that must stay in the source language, such as a legal company name or a technical token. For a term that must always be translated one particular way, use the **Glossary**.

### 3.10. History

Open **History**, or click **See all** on **Dashboard**.

![History, English back office. The call list and Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** is the full list of stored Claude calls: manual runs, the translation page, bulk jobs, catalogue batches, and the connection test. Each row keeps the prompt, the reply, the model, the languages, the token counts, and how long the call took. The cards and charts are on **Dashboard**. Opening this page sends no new request and changes no translations.

Filters and charts stay on **Dashboard**. This page is just the list.

Columns: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time**, and **Prompt**. Types: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate**, and **Not sent** (the call was never sent, for example because of the local rate limit or the budget). A **Bulk job** row shows the job number.

- **View** opens the prompt and the reply, along with **HTTP**, **Sent**, **Received**, and **Total**. For an error, the reply is the error text. **Back to the list** returns to the table. If the row no longer exists: **This history row no longer exists.**
- An access error means the key on **Settings** is wrong, or the account cannot use the selected model.
- **Previous**, **Next**, and **Page** move through the list.
- **Clear history** asks **Clear the stored history? Saved translations stay.** After it runs: **History cleared. Saved translations were not changed.** The button's help text reads **Clear history deletes these rows only. Saved translations stay.**

An empty list shows **No requests yet.**

If translations suddenly stop, open the newest error row here before you change the glossary.

### 3.11. Updates

Open **Updates** at the right end of the module bar. The form title is **MyPresta Updates**.

![Updates, English back office. Manual Check, Automatic Notifications, and Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** contains **Check Now**, which checks the version immediately.
- **Automatic Notifications** is set to **Enabled** or **Disabled**. **Enabled** is the default if you have never saved a choice. When enabled, the module checks whether MyPresta has a newer version and may show a warning in the back office.
- **Product Page** is a link that opens the contact page this module uses.
- **Save** stores your choice. Message: **Update settings saved.**

After **Check Now**: **New version available!** or **Module is up to date!**

### 3.12. Buttons on International → Translations

Open **International → Translations**. Field buttons appear when **Individual field buttons — International → Translations** is on. Checkboxes and the bar appear when **Individual field checkboxes — International → Translations** is on.

What you will see:

- A **Translate** button on each text field.
- A checkbox on each field, when checkboxes are on.
- A bar labelled **Claude translations**, with **Source** (en-US, or the **Source locale** from **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected**, and the hint **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** fills the empty fields in the current section.

Steps:

1. Choose **Target**.
2. Tick the fields, or click **Check empty**.
3. Click **Translate selected** or **Translate empty**.
4. Wait until the bar shows **Done**. While it works, the status reads **Translating…** with a counter. If you have ticked nothing, the bar says **Tick at least one field.**
5. Check the filled fields. Save the page with PrestaShop's **Save** button.

The buttons only fill in the fields. Without PrestaShop's **Save**, the text does not reach the shop. With **Allow publish / save** off, the fields are still filled in, and PrestaShop's **Save** saves the page.

Messages:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** For **Emails**, the source text comes from the email template file, not from a field on the page. Choose a different **Source locale** that has those email files.

### 3.13. Buttons on product, category, and CMS forms

Open a product, a category, a CMS page, or another shop form that has multilingual fields. The buttons appear when **Individual field buttons — shop forms** is on. The checkboxes and the bar appear when **Individual field checkboxes — shop forms** is on.

What you will see:

- A **Translate** button next to each multilingual field.
- A checkbox for the bar.
- A bar labelled **Claude translations**, with **Translate from** and **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected**, and the hint **Fills the fields. Save with the PrestaShop button.**

Steps:

1. Fill in the field in the source language. If it is empty, the bar says **Fill the source language field first.**
2. Choose the target language on the bar.
3. Click the button next to one field, or tick several fields and click **Translate selected**. **Translate empty** fills the empty fields.
4. Click **Save** on the PrestaShop form. Without this, the text is not stored.

The button only fills in the field on the form. Fields you do not tick stay unchanged.

## 4. Storefront

The module adds nothing to the page your customers see. There is no storefront block, button, or message, so the theme has nothing to display for this module.

The only address outside the back office is the cron address. It is for a scheduled task on your server. Customers do not use it.

- Copy it from **Settings**, the **CRON URL** field, or from the **CRON** line on the **Dashboard**.
- Paste it into your server's scheduler, for example to run every few minutes. Each call processes one slice of a waiting job.
- Use the `https://` address if SSL is enabled on the shop.

| What you see when you open the address | What to do |
|---|---|
| **Forbidden** | The address is incomplete or has been changed. Copy it again from **Settings**. |
| **No pending jobs** | No job is in `pending` or `running`. Create one on **Bulk**, or resume a paused job on **Jobs**. |
| A JSON result with `ok`, `finished`, and `counts` | One slice was processed. Check progress on **Jobs**. |

The cron address only processes jobs in `pending` and `running`. A `paused` job must be resumed on **Jobs**.

## 5. Problems

| What you see | Cause | What to do |
|---|---|---|
| **No Claude API key.** on every module page | No key is saved. | Open **Settings**, paste the key into **Claude API key**, and click **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Settings were saved without a key. | Paste the key and click **Save**. |
| **Connection was not made. Nothing was translated.** after **Test connection** | Wrong key, no route to Anthropic, or a model the account cannot use. | Check the key, pick another **Model**, or add the correct ID under **Add a Claude model**. Read the row on **History**. |
| Access errors on **History** | The key is wrong, or the account cannot use the selected model. | Correct the key, or choose a model the account is allowed to call. |
| **Nothing was started. There is no Claude API key.** on **Bulk** | No key. | Paste the key on **Settings**, then run **Estimate** and **Start job** again. |
| A job stays on `pending` | A job does not start by itself. | Click **Process slice** or **Auto-process** on **Jobs**, or set up the cron address (section 4). |
| A job is `paused` with **Rate limit — job auto-paused. Resume later.** | Claude rejected calls because of a rate limit. | Wait a few minutes and click **Resume**. Lower **Batch size** or **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** has been reached. | Raise the amount, or set it to 0. A new month starts from zero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** is off. | Turn on **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** on **Manual** | The translation changed placeholders or HTML tags. | Edit the row in **Review before save** so the placeholders and tags match the source, then click **Save approved**. |
| A job ends as `completed_with_errors` | Some strings failed. | Open the job, click **Failed only**, download the **Error CSV**, then click **Retry failed**. |
| Rows on **Review** have a low **Score** | The quality check placed them in the queue. | Read **Source** and **AI**. Click **Approve** or **Reject**. If a bad text was already saved, use **Rollback** on the job. |
| The translation was saved, but the shop still shows the old text | The page cache did not refresh. The module clears the cache when it saves a catalogue translation, a bulk slice, or a rollback. | Clear the cache in the PrestaShop back office. |
| An exclude does not skip a string | The wrong **Type**, or a **regex** that matches nothing. | On **Excludes**, delete the pattern and add a shorter one with the correct **Type**. |
| A new glossary term does not change saved translations | The glossary is read at the next translation, and saved texts stay as they are. | Run those strings again on **Bulk** with **Overwrite all**, after reviewing **Estimate**. |
| **The source language mail file was not found.** | The chosen source has no email file. | Pick another **Source locale** on **Settings**, or another **Source** on the translation page, that has the email files. |
| **No strings match this filter. Nothing was sent to Claude.** | The filter matches nothing. | Turn off **Only empty**, clear **Search**, or choose another domain. |
| **Nothing was translated. Tick at least one row.** | No row was ticked. | Tick some rows and click **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** on **Catalog** | The source and target are the same language. | Choose a different **Target language**. |
| **Catalog finished** moved **Start after ID** past rows that failed | The field is set to the highest ID in the batch, including failed rows. | Set **Start after ID** below the failed record and run the batch again. |
| Dashboard coverage is empty | The shop has no catalogue for that locale yet. | Create one under **International → Translations**, then return to **Dashboard**. |
| **History** shows **Not sent** | The local rate limit or the budget stopped the call before it was sent. | Check **Rate limit / min** and **Budget USD / month** on **Settings**. |
| **The shop needs at least two languages.** | The shop has only one language. | Add a language under **International → Localization → Languages**. |

## 6. For developers

### 6.1. Overview

- Main class: `myaitranslationsclaude`, file `myaitranslationsclaude.php`.
- Version: 1.2.0.
- Technical name: `myaitranslationsclaude`. Name in the module list: **AI Translations with Claude**.
- Author: MyPresta.eu. Module Manager tab: `administration`.
- Back-office tab: `AdminMyaitranslationsclaude`, parent `AdminInternational`, fallback parent `IMPROVE`. The visible tab label is `AI Translations with Claude`. `ensureTab()` repairs a missing tab. `renameTabIfTechnical()` replaces a tab name that is still the technical name.
- Installation: `parent::install()`, tables from `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (writes the key only when it is missing), the hooks `displayBackOfficeHeader` and `actionAdminControllerSetMedia`, then the tab.
- Uninstallation: deletes the tab, runs `sql/uninstall.php` (drops 11 tables), `removeConfiguration()` deletes the `MYAITCL_*` keys listed there, then `parent::uninstall()`. It does not delete `mypresta_updates`, `update_myaitranslationsclaude`, or `updatev_myaitranslationsclaude`.
- There is no `enable()` and no `disable()`.
- `getContent()` calls `ensureTab()` and redirects to `AdminMyaitranslationsclaude` (default tab `dashboard`).

Data flow:

1. The settings form POSTs to `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` stores `MYAITCL_*` in `Configuration`. `MyaitclApiKeyEncryptor` encrypts the API key with AES-256-CBC, using a key derived from `_COOKIE_KEY_`, and stores it as `MYAITCL_API_KEY_ENC`. An empty posted key, or a masked value, does not replace the stored key.
3. Translation: `MyaitclTranslateService::translateMessages()` builds the prompts (`MyaitclPromptBuilder`), sends them through `MyaitclClaudeTranslationProvider` (a cURL POST to `https://api.anthropic.com/v1/messages` with the header `anthropic-version: 2023-06-01`), checks the reply (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), scores it (`MyaitclQualityScorer`), and saves it through `MyaitclTranslationAdapter`.
4. When **Max tokens** is 0, the provider sends `max_tokens` 4096. `acceptsTemperature()` sends **Temperature** only when the model ID matches `claude-(opus|sonnet|haiku)-4-(0|1|5|6)`.
5. Catalogue saves use the PrestaShop translation service when it exists, and the `_DB_PREFIX_translation` table otherwise. Classic-module keys are written to that module's `translations/{iso}.php` by `MyaitclLegacyModuleCatalogue`.
6. Bulk: `MyaitclBulkJobFactory` inserts into `myaitcl_job` and `myaitcl_job_item`. `MyaitclJobWorker::processSlice()` runs one slice of `BATCH_SIZE`. It is called by **Process slice**, by the **Auto-process** loop (AJAX `ProcessJob`), and by `controllers/front/cron.php`.
7. Catalog: `MyaitclCatalogTranslateService::collect()` reads at most 100 rows. `translateAndSave()` writes `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang`, or `_DB_PREFIX_cms_lang`. Results are matched by ID. After a batch, **Start after ID** becomes the highest `id_entity` in the collected set, including rows that failed.
8. Each call is stored in `myaitcl_request` (**History**). Errors also go to `myaitcl_api_log`. Cost goes to `myaitcl_usage_ledger`. `MyaitclSnapshotService` copies the previous value into `myaitcl_snapshot` for **Rollback**. `clearTranslationCache()` calls `Tools::clearCache()` after a catalogue save, after a non-dry-run slice, and after a rollback.

### 6.2. Files

| File | Role |
|---|---|
| `myaitranslationsclaude.php` | Install, uninstall, tab, hooks, assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Update check for the **Updates** tab and the back-office warning. Class `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logo in the module header. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Every back-office tab, saves, job actions, glossary, excludes, catalogue, CSV, AJAX. |
| `controllers/front/cron.php` | Cron address. Processes one slice and returns JSON. |
| `sql/install.php`, `sql/uninstall.php` | Create and drop the tables. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Read and write interface for PrestaShop translations. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Sections, domains, locales, saving through the service or the `translation` table, cache clearing. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Concrete adapter. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Builds the adapter. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Reads XLF catalogues from themes and modules. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Classic modules: reads and writes `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Back-office forms and field `desc` text. |
| `src/Admin/MyaitclSectionHelp.php` | **Help** panel text for each tab. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History**: rows, cards, charts, filters, clearing, retention. |
| `src/Audit/MyaitclApiLogRepository.php` | API error and warning log, with retention. |
| `src/Audit/MyaitclTranslationMemory.php` | Reuses a result for the same text, locale, model, and glossary. |
| `src/Audit/MyaitclUsageLedger.php` | Cost estimate from the price table in this file, and the monthly budget. |
| `src/Audit/MyaitclSnapshotService.php` | Copies before a write, and restores them on **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Glossary list, insert, delete. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Exclude insert, delete, and matching. |
| `src/Job/MyaitclJobStatuses.php` | Status constants for jobs and rows. |
| `src/Job/MyaitclJobRepository.php` | Jobs and rows: read, status, next slice, counters. |
| `src/Job/MyaitclJobWorker.php` | Slice processing, retry, finish, review queue, completion email. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Provider interface. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Claude calls, connection test, request log. |
| `src/Provider/MyaitclPromptBuilder.php` | System and user prompts: tone, brand voice, glossary. |
| `src/Provider/MyaitclProviderFactory.php` | Builds the provider. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Placeholder and tag check. |
| `src/Quality/MyaitclHtmlValidator.php` | HTML check. |
| `src/Quality/MyaitclPsNativeValidator.php` | Check before a **Manual** save. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Protects email HTML before the call and restores it after the reply. |
| `src/Quality/MyaitclQualityScorer.php` | Score 0-100, flags, review decision. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Encrypts and decrypts the API key. |
| `src/Service/MyaitclConfigService.php` | Reads and saves settings, models, the cron token, and value ranges. |
| `src/Service/MyaitclRateLimiter.php` | Local per-minute limit, file `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Excludes, memory, calls, validation, scoring, saving, estimates. |
| `src/Service/MyaitclBulkJobFactory.php` | Builds a **Bulk** job and its estimate. |
| `src/Service/MyaitclCatalogTranslateService.php` | Collects and saves **Catalog** rows. |
| `src/Service/MyaitclDashboardService.php` | Coverage counts on **Dashboard**. |
| `translations/*.php` | Interface translations, one file per language. |
| `views/templates/admin/configure.tpl` | The module page and the **Help** drawer. |
| `views/templates/admin/_partials/*.tpl` | Tabs: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Back-office styles. |
| `views/js/admin.js` | **Jobs** progress and **Auto-process**, row selection, AJAX. |
| `views/js/admin-help.js` | **Help** panel. |
| `views/js/translations-tool.js` | Buttons and bar on **International → Translations**. |
| `views/js/entity-fields.js` | Buttons and bar on product, category, and CMS forms. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Charts on **Dashboard**. |
| `var/rate_limit.json` | Counter for the local per-minute limit. |
| `index.php` in each directory | Blocks directory listing. |

### 6.3. Controllers

**Back office: `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsclaude&token=…`, optionally with `&myaitcl_tab=` set to `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (the tab label is **History**), `settings`, or `updates`.
- Job actions, passed as the query parameter `job_action` together with `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, and `export_errors`. The template does not render a Cancel button. `filter_failed=1` limits the row table.
- Review actions: `review_action=approve|reject` and `id_review`.
- Glossary: `delete_glossary`. Excludes: `delete_exclude`. Models: `delete_claude_model`, and a POST with `new_claude_model` and `submitMyaitranslationsclaudeAddModel`.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, plus the field-translation endpoints used by `translations-tool.js` and `entity-fields.js`.

**Front: `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- Shop URL: `module/myaitranslationsclaude/cron`.
- The `token` query parameter must match `MYAITCL_CRON_TOKEN` (compared with `hash_equals`). A missing or wrong token returns HTTP 403 and the JSON `{"ok":false,"error":"Forbidden"}`.
- The optional `id_job` parameter processes that job. Without it, the first `pending` or `running` job is processed.
- A successful slice returns JSON with `ok`, `finished`, and `counts`. When no job is waiting, the body is `{"ok":true,"message":"No pending jobs"}`.
- `ssl` is set to true on the controller.

### 6.4. Hooks

Registered hooks:

- `displayBackOfficeHeader` - renames the technical tab label, then loads CSS and JS.
- `actionAdminControllerSetMedia` - loads the same assets.

`translations-tool.js` is added on the translations controller. `entity-fields.js` is added on shop forms when the field switches are on. `Media::addJsDef` publishes `myaitclTr` (the AJAX URL, the source locale, the languages, and the bar labels).

The module does not register any hook of its own for other modules to implement. There is no `enable()` and no `disable()`.

### 6.5. Overrides

The module does not override any PrestaShop class or controller.

### 6.6. Database

| Table | Contents |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, shop ID, dates. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitcl_job` | One bulk run: locales, `scope_json`, `policy_json`, `dry_run`, counters, token totals, cost, employee, error, timestamps. |
| `myaitcl_job_item` | One string in a job: domain, key, theme, locale, source, previous value, new value, status, skip reason, error, tokens, validation. |
| `myaitcl_memory` | Translation memory: hash, source, locale, translation, model, hit count. |
| `myaitcl_usage_ledger` | Daily token and cost rows, optional job ID, model. |
| `myaitcl_snapshot` | Value saved before a job write, used by **Rollback**. |
| `myaitcl_api_log` | Error and warning rows: level, provider `claude`, HTTP code, message, context. |
| `myaitcl_request` | **History** rows: type, status, model, locale, HTTP code, duration, tokens, cost, employee, job, prompt, reply, error. |
| `myaitcl_review` | Review queue: job item, status, score, flags, employee. |
| `myaitcl_catalog_item` | Catalog batch rows: entity, field, languages, source, previous value, new value, status, error. |

Uninstalling drops all eleven tables. Installation uses `CREATE TABLE IF NOT EXISTS`, so reinstalling on a database where the tables still exist keeps those rows. A normal uninstall removes them first. No column is added on the first visit to a page.

### 6.7. Keys and translations

Prefix: `MYAITCL_`. The values used when a key is missing, which are also the values written on installation:

| Key | Default when missing |
|---|---|
| `API_KEY_ENC` | empty |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | empty |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | empty |
| `BATCH_SIZE` | `25` (clamped to 1-100 again on save) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | empty |
| `TEMPERATURE` | `0.2` (clamped to 0-1 again on save) |
| `DRY_RUN_SAMPLE` | `10` (clamped to 1-50 again on save) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | empty |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (the provider then sends 4096) |
| `CRON_TOKEN` | 16 random bytes in hex, generated on installation |

`removeConfiguration()` also deletes the legacy keys `DEEPL_API_KEY` and `CLAUDE_API_KEY` under the same prefix. It does not delete the update-checker keys.

Field descriptions are the `desc` strings in `src/Admin/MyaitclForms.php`, assembled by `help()` from the purpose, how to set it, and its effect. Tab help lives in `src/Admin/MyaitclSectionHelp.php`.

Interface strings go through `$this->l()` / `{l s=... mod='myaitranslationsclaude'}`. To add a language, add `translations/{iso}.php`. The job errors **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.**, and **Monthly API budget has been exhausted.** are English strings returned by `MyaitclJobWorker` and `MyaitclTranslateService`, not `$this->l()` calls. The **Updates** strings use the `updatechecker` translation domain.

### 6.8. Extending

The storefront does not render a module template, so the theme has nothing to override.

Back-office templates live in `views/templates/admin/`. PrestaShop does not offer a theme override for those admin templates. Change labels through `translations/{iso}.php`. The buttons on **International → Translations** and on shop forms are injected by `views/js/translations-tool.js` and `views/js/entity-fields.js` using `myaitclTr`. No hook exists that a theme could use to replace that bar.

## 7. Help

Module page: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html

To write to us about this module, sign in to your customer account on mypresta.eu, open the contact form, and choose **Support for paid modules**. The form says that a login is required for paid modules. After you sign in, pick this module from your purchase history.
