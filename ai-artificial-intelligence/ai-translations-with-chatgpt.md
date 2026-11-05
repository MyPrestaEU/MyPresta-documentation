---
title: "AI Translations with ChatGPT - documentation and user manual"
description: "Configuration and troubleshooting manual for shops that already have AI Translations with ChatGPT."
sidebar:
  label: "AI Translations with ChatGPT - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy AI Translations with ChatGPT Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Requirements

The module runs on PrestaShop 1.7.0.0 and newer, including PrestaShop 8 and 9.

- **PrestaShop:** 1.7.0.0 or newer.
- **PHP:** 5.6 or newer.
- **PHP extensions:** cURL, OpenSSL, SimpleXML, and mbstring.
- **Other modules:** this module does not require another module.
- **Outside the shop:** an OpenAI account and an API key. The shop server must be able to open `https://api.openai.com/v1/chat/completions`.
- **Optional:** a scheduled task on the server that opens the cron address from **Settings**. Without it, you process jobs yourself on **Jobs**.
- **Large catalogues:** a domain with thousands of strings is many API calls. The job is split into slices of **Batch size**. Run **Estimate** on **Bulk** before you start.
- The shop needs at least two languages. With one language the back office shows **The shop needs at least two languages.** and there is nothing to translate.

## 2. Installation

1. Open **Modules**, then **Module Manager**. Choose **Upload a module**, upload the ZIP, and press **Install** on **AI Translations with ChatGPT**.
2. After installation, **AI Translations with ChatGPT** appears in the **International** menu.
3. Installation does not clear the shop cache. The module clears the cache when it saves a translation.

Open **AI Translations with ChatGPT**, then **Settings**, and paste the ChatGPT key. Until a key is stored, every page of the module shows **No ChatGPT API key.** and a link **Open Settings**.

**Uninstall.** In **Module Manager**, press **Uninstall** and confirm **Delete this module and its data (jobs, glossary, cache)?**

- The menu entry disappears. Jobs, the glossary, exclude patterns, call history, the **Review** queue, rollback copies, the cost ledger, and the module settings (including the API key) are deleted.
- Text the module already wrote into the shop stays: catalogue translations, and the translation files of classic modules that this module wrote. The update-check choice also stays.
- A new install does not bring back the deleted jobs, glossary, or history. It sets the default values and creates a new cron address.

## 3. Configuration and daily work

The whole module is one page: **International**, then **AI Translations with ChatGPT**. The tabs are **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History**, and **Settings**. **Updates** sits at the end of the bar. **Help** opens a panel for the tab you are on.

Button and field names in this manual are the ones on the English back office. In another back-office language you see the translation of the same control.

A normal run has four parts.

1. **Connection.** On **Settings**, paste the key, pick the model, and press **Test connection**, then **Save**.
2. **A small test.** On **Manual**, filter one domain, tick a few empty strings, and translate them. Check the result before you run a whole catalogue.
3. **A job.** On **Bulk**, choose the section, the languages, and the domains, press **Estimate**, then **Start job**. Open the job and press **Process slice**, or **Auto-process**, or leave the cron address to call it.
4. **A check.** Open **Review** for rows the quality check held back, and **History** when a call fails. **Rollback** on the job restores the previous text where the module kept a copy.

The module does not start a translation by itself. **Estimate**, **Filter**, and **Save** on **Settings** do not write catalogue text. A job stays on **Jobs** until you process it or the cron address is called.

### 3.1. Module configuration

Open **Modules**, **Module Manager**, find **AI Translations with ChatGPT**, and press **Configure**. That opens **Dashboard**. Go to **Settings**.

**Save** and **Test connection** are at the bottom of the form. Saving this form does not start a translation and does not rewrite translations already stored.

![Settings, English back office. The top of the form: ChatGPT API key, Model, Add a ChatGPT model, Tone, and Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Connection**

| Field | On install | What it does |
|---|---|---|
| **ChatGPT API key** | empty | The secret this shop sends to ChatGPT. Paste the key from your OpenAI account. Leave the box empty to keep the key already saved. A new value replaces the stored key. An empty box does not delete it. When a key is stored, the help text shows **Key saved:** and a masked key. |
| **Model** | gpt-4.1-mini | The ChatGPT model that writes the translation. Built-in names stay in the list: gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini, and o1-mini. The next translation uses the selected model. A model the account cannot use fails the call, and the error is listed on **History**. |
| **Add a ChatGPT model** | empty | Type the exact id from the OpenAI account, then press **Add model**. The placeholder in the box is gpt-4.1. The new id appears in **Model** and becomes the active model. **Remove** deletes only ids added here. Built-in ids cannot be deleted. |

Messages: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Voice and source**

| Field | On install | What it does |
|---|---|---|
| **Tone** | Formal | Adds a style instruction to every prompt. **Formal** is for shop and back-office wording, **Casual** is a lighter voice, **Brand** is used together with **Brand voice**. New translations follow that style. Existing translations stay until you run them again. |
| **Brand voice** | empty | Shown when **Tone** is **Brand**. A few plain sentences about how the shop should sound, or an empty box. The text is added to the next prompt. Empty means no extra voice. It does not rewrite translations already saved. |
| **Source locale** | empty | The language the model treats as the original. The empty choice is a dash on the list: the screen you are translating supplies the source. Pick the locale your catalogues are written in, usually en-US. **Manual**, **Bulk**, and the icons on **International → Translations** send this locale as the source. The shop default language is not changed. |
| **Individual field buttons — shop forms** | Yes | A button on each multilang field of shop forms: product, category, CMS, and the other back-office forms. The button translates only that field. **No** hides those buttons in the whole shop. Saved translations are not changed. |
| **Individual field checkboxes — shop forms** | Yes | Each of those fields gets a checkbox, and the bar translates only the fields you tick. **No** hides the checkboxes and the bar. The buttons above follow their own switch. |
| **Individual field buttons — International → Translations** | Yes | A button on each field of **International → Translations**. **No** hides those buttons. Shop forms are not affected. One click fills that field. PrestaShop **Save** still writes the page. |
| **Individual field checkboxes — International → Translations** | Yes | Checkboxes and the bar on **International → Translations**. **No** hides them. Shop forms are not affected. |

**Limits**

![Settings, English back office. Batch size and the limit fields under it.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Field | On install | What it does |
|---|---|---|
| **Batch size** | 25 | How many strings are sent in one API call. Use 10 to 25 for a first run. The value is kept between 1 and 100. A larger batch finishes a job in fewer calls. A failure then retries a bigger chunk. |
| **Dry-run sample** | 10 | How many example strings **Estimate** shows before a bulk job. The value is kept between 1 and 50. **Estimate** does not write translations. |
| **Max tokens (0 = default)** | 0 | The form stores this number. The translation request does not send it, so it does not shorten the reply and it does not stop a reply that is cut off. The connection test uses its own short request. Translations already saved are not trimmed. |
| **Budget USD / month** | 0 | A monthly ceiling in US dollars, counted from the usage ledger. 0 means no ceiling. When the ledger reaches the amount, new translations stop. Work already saved stays. |
| **Rate limit / min** | 60 | How many API calls this shop may start in one minute. 0 turns this local limit off. Calls over the limit are skipped and listed on **History**. ChatGPT can still apply its own limit. |
| **Log retention days** | 30 | How many days of rows to keep on **History**. At least 1. Older rows are removed. Jobs, the glossary, and saved translations are not deleted by this number. |
| **Temperature** | 0.2 | How freely the model may rephrase. About 0.2 stays close to the source. Values near 1 vary the sentences more. The saved value is kept between 0 and 1. Placeholders and HTML are still checked afterwards. The translation request sends this value for every model in the list, including a model id you add. |
| **Allow publish / save** | Yes | Whether this module may write a translation into PrestaShop. **No** blocks save on **Manual**, bulk jobs, and **Catalog**. The icons on the translation page and on shop forms still only fill the form. PrestaShop **Save** is separate. |

After **Save**:

- **Settings saved. No translation was started.** The settings are stored and nothing was translated.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Paste a key in **ChatGPT API key** and press **Save** again.

**Mail and cron**

| Field | On install | What it does |
|---|---|---|
| **Email notify on complete** | No | Sends one email when a bulk job finishes. The job still runs either way. Only the email is added or skipped. |
| **Notify email** | empty | The address that receives that email. The field is shown only when the switch above is on. Saving the address does not send a message by itself. |
| **CRON URL** | an address with a token | A secret address the server can call to process one slice of a waiting job. Copy it into the server scheduler. Do not publish it. Anyone with the address can start a slice. Opening **Settings** does not start a job. |

**Test connection** checks the key and the model with one short request. It does not translate and it does not save.

- **Connection OK (N ms). No translation was started.** The connection works.
- **Connection was not made. Nothing was translated.** followed by the reason. Check the key and the model. The detail is on **History**.

A practical start: paste the key, pick the model and the source locale, press **Test connection**, then **Save**. Leave the numbers at their install values until a job behaves badly.

### 3.2. Dashboard

Open the **Dashboard** tab. It counts missing catalogue strings, then shows ChatGPT usage as cards, charts, and the ten newest prompts. The page does not translate and it does not change strings.

![Dashboard, English back office. Coverage for one locale, the cron line, and the history filters.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Coverage**

- **Locale:** the shop locale whose missing strings are counted.
- **Show:** redraws the table for that locale.
- Columns: **Section**, **Total**, **Missing**, **Done**, and a progress bar. Sections are **Back office**, **Themes**, **Installed modules**, **Emails**, and **Others**. **Missing** is the number of strings without a translation in that locale.
- Under the table, **CRON** shows the same address as **CRON URL** on **Settings**.
- An empty table means the shop does not have a catalogue for that locale yet. Create it under **International → Translations**.

After **Show**, the message is **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Usage**

- Presets: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filters: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee**, and **Prompt or reply contains**. Press **Filter**.
- Cards: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**, and **Estimated cost**. Estimated cost is a local estimate, not an invoice from OpenAI.
- Charts: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Under them, groups **By day**, **By model**, **By type**, **By language**, and **By employee**, with columns **Group**, **Calls**, **Sent**, **Received**, and **Total**. An empty group says **No requests in this range.**
- **Latest prompts** lists ten calls. **View** opens the prompt and the reply. **See all** opens **History** (3.10). An empty list says **No requests yet.**

Filtering does not delete history and does not change translations.

If a section is mostly missing, open **Manual** for a few strings or **Bulk** for a whole domain.

### 3.3. Manual

Open **Manual**. It translates one domain, or one classic module, a few dozen strings at a time. Filtering does not save anything.

![Manual, English back office. Section, Source, Target, Domain, Only empty, and Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Field | On install | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue is read: **Back office**, **Themes**, **Installed modules**, **Emails**, or **Others**. Changing the section reloads the page and shows only the fields for that section. It does not call ChatGPT. |
| **Theme** | empty | Shown only for **Themes**. Limits the list to one theme. |
| **Module** | empty | Shown only for **Installed modules**. Limits the list to one module. A classic module with no domain loads every string of that module. |
| **Domain** | empty | The same grouping as on **International → Translations**. Choose it and press **Filter**. Hidden for a classic module and for a section with no domains. |
| **Source** | the **Source locale** from **Settings**, or en-US | The language the strings are taken from. Pick a language that already has a good text. |
| **Target** | the first language on the list | The language you want to fill. It must exist under **International → Localization → Languages**. |
| **Only empty** | Yes | Shows only strings without a translation. Turning it off shows every string. Saved translations are not deleted. |
| **Search** | empty | Keeps only source strings that contain the word you type. |

Steps:

1. Set **Section**, **Source**, and **Target**.
2. For **Themes**, pick **Theme**. For **Installed modules**, pick **Module**.
3. Press **Filter**. The **Domain** list refreshes. Pick a domain and press **Filter** again. For a classic module, skip the domain: **Filter** loads every string of the module.
4. Tick the rows. **Check all** and **Uncheck all** select or clear the list.
5. Press **Translate selected (review)**. A table **Review before save** opens with **Source**, **AI proposal**, and **Warnings**. Untick rows you do not want. Edit the proposal in the box. Press **Save approved**.
6. Or tick **Save now (skip review)** before translating. Valid rows are written at once, without the review table.

The string list columns are **Source**, **Current**, and **Status** (**empty** or **filled**).

Messages:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** This is the classic-module list.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Those rows were skipped. Fix the placeholders and tags so they match the source, then save again.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Changing the section also shows a short line such as **Section is Back office. Theme and module are not used.** together with **Nothing was sent to ChatGPT.** The same pattern is used for **Themes**, **Installed modules**, **Emails**, and **Others**.

### 3.4. Bulk

Open **Bulk**. It creates one job for many domains and languages. **Estimate** does not save. **Start job** creates a row on **Jobs**. Nothing is written until the job is processed and **Allow publish / save** is on.

![Bulk, English back office. Section, Source, Targets, Domains, Policy, and Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Field | On install | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue the job reads. Same choices as **Manual**. |
| **Theme** / **Module** | empty | Shown only for the matching section, as on **Manual**. |
| **Source** | the **Source locale** from **Settings**, or en-US | The language treated as the original. Every target is translated from this language. |
| **Targets** | none | One or more languages to fill. Hold Ctrl, or Cmd on a Mac, to select several. A plain click replaces the selection. |
| **Domains** | none | Domains included in the job. Hold Ctrl or Cmd. Domains you do not select are not translated. Leave them all unselected only when you want an empty job. A classic module with no domain is the exception: the job then covers that module. |
| **Policy** | Fill empty | **Fill empty** sends only strings without a translation. **Overwrite all** sends every string, including ones that already have a translation, and can replace them. **Outdated if equals source** sends only strings whose translation is identical to the source. |
| **Dry-run job** | No | ChatGPT still runs and the job appears on **Jobs**, but the replies are not written into the shop. |

Steps:

1. Choose the section, the source, the targets, the domains, and the policy.
2. Press **Estimate**. The page shows **Estimate**, the string count, a token estimate, a cost estimate, and a **Sample**.
3. If the estimate is acceptable, press **Start job**. **Jobs** opens with the new job.
4. Process it on **Jobs** (3.5), or leave it for the cron address.

Messages:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Open **Jobs**. Each row is one run from **Bulk**.

![Jobs, English back office. The empty job list.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Columns: **#**, **Status**, **Locales** (source, then targets), **Progress** (done/total), **Cost**, **Employee**, **Date**, and **Open**. An empty list says **No jobs yet.**

Job statuses, as shown on the screen:

- `pending` - waiting. It does not start by itself.
- `running` - in progress.
- `paused` - stopped until you resume it.
- `cancelled` - stopped. Strings that were still waiting were not translated.
- `completed` - every string processed, with no failures.
- `completed_with_errors` - finished, and some strings failed.
- `failed` - the job ended on an error.

**The job screen**

**Open** shows **Job #N**, the status, progress (done/total), **failed**, **skipped**, the cost, the employee number, and the label **dry-run** when the job is a dry run. The progress bar refreshes by itself while the job is open. The table under it has **ID**, **Domain**, **Locale**, **Status**, **Source**, **New**, and **Error**.

Row statuses: `pending`, `processing`, `done`, `failed`, `skipped` (an exclude matched, or the string was already translated), and `rolled_back`.

Buttons:

- **Process slice** - one slice, the size of **Batch size**, then it stops. Message: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** When nothing is left: **The job has no more strings waiting.**
- **Auto-process** - repeats slices until the job ends or an error stops it. It runs in the browser, so the tab must stay open. Closing the tab stops the loop. The job remains and can be finished with **Process slice** or the cron address.
- **Pause** - message: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - message: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - failed strings go back to waiting and the job waits again. Message: **Retried N failed items.**
- **Rollback** - asks **Roll back this job?** and restores the previous translation where the module stored a copy before the change. Message: **Rollback: restored N translations.**
- **Error CSV** - downloads the failed rows. Columns: id, domain, locale, source, error.
- **Failed only** - shows only the failed rows.
- **Review queue** - opens **Review** (3.6).

The job screen has no Cancel button. Use **Pause** to stop further work.

**Automatic pause**

When ChatGPT rejects calls because of a rate limit, the job pauses itself. The error line is **Rate limit — job auto-paused. Resume later.** Wait, then press **Resume**. **Rate limit / min** on **Settings** lowers how many calls the shop starts in a minute.

Other messages on this screen:

- **Nothing was translated.** followed by **No ChatGPT API key. Nothing was translated.** Paste the key on **Settings**.
- **Allow publish is off in Settings.** A job that is not a dry run does not run until you turn **Allow publish / save** on.
- **Monthly API budget has been exhausted.** Raise **Budget USD / month**, or set it to 0.

### 3.6. Review

Open **Review**, or press **Review queue** on a job. The page title line is **Needs-review queue (quality score / flags).** It lists the newest rows that the quality check did not pass automatically, up to 100.

![Review, English back office. The empty needs-review queue.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Columns: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, then **Approve** and **Reject**. An empty list says **The queue is empty.**

How to read a row:

- **Score** is from 0 to 100. Under 70, the row is queued.
- **Flags:**
  - `validation_failed` - placeholders or HTML failed the check.
  - `warning` - a smaller check note.
  - `length_explosion` - the translation is more than two and a half times the source.
  - `too_short` - the translation is much shorter than a longer source.
  - `possible_untranslated` - English words such as the, and, with, your, or please are still in the translation.
- **Source** is the original. **AI** is the model proposal.

**Approve** and **Reject** only change the row status. The message is **Review updated.** The row leaves the list. This page does not paste the text into the catalogue by itself.

If the job was allowed to save, the proposal may already be in the shop. To undo a change from that job, use **Rollback** on the job in **Jobs**.

### 3.7. Catalog

Open **Catalog**. It translates product, category, or CMS fields stored on the shop languages. It does not edit **International → Translations**. One press handles at most 100 records. Saved rows are written on the target language.

![Catalog, English back office. Entity, fields, languages, and Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Field | On install | What it does |
|---|---|---|
| **Entity** | product | What is read: **product**, **category**, or **cms**. Changing it reloads the page and shows only that field list. The change itself does not translate. |
| **Fields** | every field of that entity | Which texts the batch sends. Hold Ctrl or Cmd. Unselected fields are not sent and stay as they are. Product: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Category: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. **Title** on a product or category is the name. On CMS, **Title** is the page title and **Content** is the page body. Leave **Friendly URL** unselected when the links should stay as they are. |
| **Source language** | the first shop language | The language the fields are copied from. That language is not modified. |
| **Target language** | the first shop language | The language that receives the translation. It must be different from the source. |
| **Only empty** | Yes | Skips fields that already have text in the target language. Turn it off only when you want to replace existing text. On: existing target text stays. Off: the batch may replace it when publish is allowed. |
| **Start after ID** | 0 | Skips records up to this ID. 0 starts from the first record. After a batch the field is set to the highest ID in that batch, including rows that failed. Press the button again to continue. To retry a failed row, set the ID back below that record before the next press. |

Button: **Translate batch (max 100)**.

Steps:

1. Choose **Entity** and tick the fields.
2. Choose **Source language** and **Target language**.
3. Leave **Only empty** on.
4. Press **Translate batch (max 100)**. The message is **Catalog finished: saved N, failed M.** The page also shows **Saved** and **failed** counts.
5. Open one record in the target language and check the result before you turn **Only empty** off or run the next batch.

Messages:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Changing **Entity** shows **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Open **Glossary**. The glossary is a list of words and phrases the model must keep or must always translate the same way. Adding a row does not change translations already stored. The next translation reads the list.

![Glossary, English back office. Add glossary term and the term list.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**One term**

| Field | On install | What it does |
|---|---|---|
| **Source term** | empty, required | The word or phrase in the source language. Type it exactly as it appears, including capitals when they matter. |
| **Target locale** | empty | Limits the row to one locale, for example pl-PL. Empty means the row is used for every target language. A filled locale is ignored for other languages. |
| **Target term** | empty | The approved translation. It may be empty only when **Do not translate** is on. |
| **Do not translate** | No | On: the model copies the term unchanged, for example a brand, an SKU, or a tag. Off: it uses **Target term**. |

Press **Add**. Messages: **Glossary term added. Translations already stored were not changed.** or **Nothing was added. Type a source term.**

**The table**

Columns: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** or **No**), and **Delete**. **Delete** removes only that row. Message: **Glossary term deleted.** An empty list says **No glossary terms yet.**

**CSV**

- Choose **CSV file** and press **Import CSV**. Message: **Imported N rows.** If the file is missing: **CSV file is missing.** If it cannot be read: **Cannot open the CSV file.**
- The first row is a header: `source_term`, `target_locale`, `target_term`, `do_not_translate`. That first row is always skipped. Rows with fewer than three columns are skipped. In the fourth column, an empty value or 0 means **No**. Any other value means **Yes**.
- Import adds the rows it can read. It does not look up an existing term and replace it, so importing the same file again adds duplicates.
- **Export CSV** downloads the current list as `glossary.csv`. It does not need an input file and it does not change the list.

Use short, exact terms. A very broad term is forced every time it appears.

### 3.9. Excludes

Open **Excludes**. An exclude is a pattern of source text that the module does not send to ChatGPT. The text stays in the shop unchanged. The pattern applies on **Manual**, **Bulk**, **Catalog**, and the translation pages.

![Excludes, English back office. Pattern, Type, and the pattern list.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Field | On install | What it does |
|---|---|---|
| **Pattern** | empty, required | The text compared with each source string. The comparison depends on **Type**. |
| **Type** | exact | **exact** is the whole string. **prefix** is the start. **contains** is a fragment anywhere in the string. **regex** is a PHP regular expression, applied as written. A wrong expression matches nothing. Start with a short pattern and check what was skipped. A wrong type can skip too much or nothing. |

Press **Add**. Message: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** An empty pattern: **Nothing was added. Type a pattern.**

Columns: **Pattern**, **Type**, **On**, and **Delete**. **On** shows 1 when the pattern is active. This screen has no switch to turn a pattern off. To stop using it, **Delete** it and add it again if you still need it. **Delete** removes only that pattern. Existing translations are not deleted. Message: **Pattern deleted.** An empty list says **No patterns yet.**

Use excludes for text that must stay in the source language, such as a legal name or a technical token. For a term that must always be translated one way, use **Glossary**.

### 3.10. History

Open **History**, or press **See all** on **Dashboard**.

![History, English back office. The request list.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** is the full list of stored ChatGPT calls: manual runs, the translation page, bulk jobs, catalog batches, and the connection test. Each row keeps the prompt, the reply, the model, the languages, the token counts, and how long the call took. The cards and charts are on **Dashboard**. Opening this page does not send a new request and does not change translations.

The filters are the same as on **Dashboard** (3.2).

Columns: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time**, and **Prompt**. Types: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate**, and **Not sent** (the call was not sent, for example because of the local limit or the budget). A **Bulk job** row shows the job number.

- **View** opens the prompt and the reply, with **HTTP**, **Sent**, **Received**, and **Total**. On an error, the reply is the error text. **Back to the list** returns to the table. If the row is gone: **This history row no longer exists.**
- An access error means the key on **Settings** is wrong, or the account cannot use the selected model.
- **Previous**, **Next**, and **Page** move through the list.
- **Clear history** asks **Clear the stored history? Saved translations stay.** After it runs: **History cleared. Saved translations were not changed.** The button help says **Clear history deletes these rows only. Saved translations stay.**

An empty list says **No requests yet.**

When translations stop suddenly, open the newest error row here before you change the glossary.

### 3.11. Updates

Open **Updates** at the right end of the module bar. The form title is **MyPresta Updates**.

![Updates, English back office. Manual Check, Automatic Notifications, and Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** holds **Check Now**. It checks the version immediately.
- **Automatic Notifications** is **Enabled** or **Disabled**. **Enabled** is the value when the choice has never been saved. When it is enabled, the module checks whether MyPresta has a newer version and can show a warning in the back office.
- **Product Page** is a link that opens the contact page used by this module.
- **Save** stores the choice. Message: **Update settings saved.**

After **Check Now**: **New version available!** or **Module is up to date!**

### 3.12. Buttons on International → Translations

Open **International → Translations**. Field buttons appear when **Individual field buttons — International → Translations** is on. Checkboxes and the bar appear when **Individual field checkboxes — International → Translations** is on.

What you see:

- A **Translate** button on each text field.
- A checkbox on each field, when checkboxes are on.
- A bar labelled **ChatGPT translations**, with **Source** (en-US, or the **Source locale** from **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected**, and the hint **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** fills the empty fields of the current section.

Steps:

1. Choose **Target**.
2. Tick the fields, or press **Check empty**.
3. Press **Translate selected**, or **Translate empty**.
4. Wait until the bar shows **Done**. While it works, the status is **Translating…** with the count. If you tick nothing, the bar says **Tick at least one field.**
5. Check the filled fields. Save the page with the PrestaShop **Save** button.

The buttons only fill the fields. Without PrestaShop **Save**, the text does not enter the shop. With **Allow publish / save** off, the fields are still filled, and PrestaShop **Save** writes the page.

Messages:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** For **Emails**, the source text comes from the mail template file, not from the field on the page. Pick another **Source locale** that has those mail files.

### 3.13. Buttons on product, category, and CMS forms

Open a product, category, CMS page, or another shop form with multilang fields. The buttons are visible when **Individual field buttons — shop forms** is on. The checkboxes and the bar are visible when **Individual field checkboxes — shop forms** is on.

What you see:

- A **Translate** button on each multilang field.
- A checkbox for the bar.
- A bar labelled **ChatGPT translations**, with **Translate from** and **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected**, and the hint **Fills the fields. Save with the PrestaShop button.**

Steps:

1. Fill the field in the source language. If it is empty, the bar says **Fill the source language field first.**
2. Choose the target language on the bar.
3. Press the button on one field, or tick fields and press **Translate selected**. **Translate empty** fills empty fields.
4. Press **Save** on the PrestaShop form. Without that, the text is not stored.

The button only fills the field in the form. Fields you do not tick stay unchanged.

## 4. Storefront

The module adds nothing to the page the customer sees. There is no storefront block, button, or message, so the theme has nothing to show for this module.

The only address outside the back office is the cron address. It is for a scheduled task on the server. It is not for customers.

- Copy it from **Settings**, **CRON URL**, or from the **CRON** line on **Dashboard**.
- Paste it into the server scheduler, for example every few minutes. Each call processes one slice of a waiting job.
- Use the `https://` address when the shop has SSL turned on.

| What you see when the address is opened | What to do |
|---|---|
| **Forbidden** | The address is incomplete or was changed. Copy it again from **Settings**. |
| **No pending jobs** | There is no job in `pending` or `running`. Create one on **Bulk**, or resume a paused job on **Jobs**. |
| A JSON result with `ok`, `finished`, and `counts` | One slice was processed. Check the progress on **Jobs**. |

The cron address processes only jobs in `pending` and `running`. A `paused` job has to be resumed on **Jobs**.

## 5. Problems

| What you see | Cause | What to do |
|---|---|---|
| **No ChatGPT API key.** on every module page | No key is stored. | Open **Settings**, paste the key in **ChatGPT API key**, and press **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Settings were saved without a key. | Paste the key and press **Save**. |
| **Connection was not made. Nothing was translated.** after **Test connection** | Wrong key, no route to OpenAI, or a model the account cannot use. | Check the key, pick another **Model**, or add the correct id under **Add a ChatGPT model**. Read the row on **History**. |
| Access errors on **History** | The key is wrong, or the account cannot use the selected model. | Correct the key, or choose a model the account can call. |
| **Nothing was started. There is no ChatGPT API key.** on **Bulk** | No key. | Paste the key on **Settings**, then run **Estimate** and **Start job** again. |
| A job stays on `pending` | A job does not start by itself. | Press **Process slice** or **Auto-process** on **Jobs**, or set up the cron address (section 4). |
| A job is `paused` with **Rate limit — job auto-paused. Resume later.** | ChatGPT rejected calls because of a rate limit. The reply on **History** can also say **ChatGPT rate limit (429). Try again later.** | Wait a few minutes and press **Resume**. Lower **Batch size** or **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** was reached. | Raise the amount, or set 0. A new month starts from zero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** is off. | Turn **Allow publish / save** on. |
| **Not saved because of broken placeholders or HTML: N.** on **Manual** | The translation changed placeholders or HTML tags. | Edit the row in **Review before save** so the placeholders and tags match the source, then press **Save approved**. |
| A job ends as `completed_with_errors` | Some strings failed. | Open the job, press **Failed only**, download **Error CSV**, then press **Retry failed**. |
| A row is on **Review** | The score is under 70, the length check failed, or placeholders failed. | Read **Flags**. **Approve** or **Reject** only changes the queue. Use **Rollback** on the job when the text was already written. |
| **The shop needs at least two languages.** | The shop has one language. | Add a language under **International → Localization → Languages**, then open the module again. |
| Buttons are missing on a product form | The shop-form switches are off. | On **Settings**, turn on **Individual field buttons — shop forms** and, if you want the bar, **Individual field checkboxes — shop forms**. |
| The translation page has no bar | The translation-page switches are off. | Turn on the two **International → Translations** switches on **Settings**. |
| **Max tokens** does not change the length of replies | The translation request does not send that number. | Leave it at 0. Shorten a single result by editing it before **Save approved**. |
| Importing a glossary CSV created duplicates | Import adds rows. It does not replace a term that is already stored. | Delete the extra rows, or export, clean the file, delete the old rows, and import once. |

## 6. For developers

### 6.1. Overview

- Main class: `myaitranslationsgpt`, file `myaitranslationsgpt.php`.
- Version: 1.2.0.
- Technical name: `myaitranslationsgpt`. Module list name: **AI Translations with ChatGPT**.
- Author: MyPresta.eu. Module Manager tab: `administration`.
- Back-office tab: `AdminMyaitranslationsgpt`, parent `AdminInternational`, fallback parent `IMPROVE`. The visible tab label is `AI Translations with ChatGPT`. `ensureTab()` repairs a missing tab. `renameTabIfTechnical()` replaces a tab name that is still the technical name.
- Install: `parent::install()`, tables from `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (writes a key only when it is missing), hooks `displayBackOfficeHeader` and `actionAdminControllerSetMedia`, then the tab.
- Uninstall: delete the tab, `sql/uninstall.php` (drops 11 tables), `removeConfiguration()` deletes the `MYAITGPT_*` keys listed there, then `parent::uninstall()`. It does not delete `mypresta_updates`, `update_myaitranslationsgpt`, or `updatev_myaitranslationsgpt`.
- There is no `enable()` and no `disable()`.
- `getContent()` calls `ensureTab()` and redirects to `AdminMyaitranslationsgpt` (default tab `dashboard`).

Data flow:

1. The settings form posts to `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` stores `MYAITGPT_*` in `Configuration`. `ApiKeyEncryptor` encrypts the API key with AES-256-CBC. The key is `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. The stored value is prefixed with `MYAITGPT1:`. An empty posted key, or a masked value, does not replace the stored key.
3. Translation: `TranslateService::translateMessages()` builds prompts (`PromptBuilder`), sends them through `OpenAiTranslationProvider` (cURL POST to `https://api.openai.com/v1/chat/completions`, header `Authorization: Bearer`), checks the reply (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), scores it (`QualityScorer`), and saves through `TranslationAdapter`.
4. `translateBatch()` sends `temperature` from settings and does not send `max_tokens`. The connection test (`ping`) sends `max_tokens` 5 and `temperature` 0. `MYAITGPT_MAX_TOKENS` is stored and is not read by `translateBatch()`.
5. Catalogue save uses the PrestaShop translation service when it exists, otherwise the table `_DB_PREFIX_translation`. Classic module keys are written to that module's `translations/{iso}.php` by `LegacyModuleCatalogue`.
6. Bulk: `BulkJobFactory` inserts `myaitgpt_job` and `myaitgpt_job_item`. An empty domain list produces no items, except a classic module, which uses `LegacyModuleCatalogue::DOMAIN`. `JobWorker::processSlice()` runs one slice of `BATCH_SIZE`. It is called by **Process slice**, by the **Auto-process** loop (`ProcessJob` AJAX), and by `controllers/front/cron.php`.
7. Catalog: `CatalogTranslateService::collect()` is called with a limit of 100. `translateAndSave()` writes `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang`, or `_DB_PREFIX_cms_lang`. Results are matched by id. After the batch, **Start after ID** becomes the highest `id_entity` in the collected set, including failed rows.
8. Each call is stored in `myaitgpt_request` (**History**). Errors also go to `myaitgpt_api_log` (column `provider` defaults to `openai`). Cost goes to `myaitgpt_usage_ledger`. `SnapshotService` copies the previous value into `myaitgpt_snapshot` for **Rollback**. `clearTranslationCache()` calls `Tools::clearCache()` after a catalogue save, a non-dry-run slice, and a rollback.

`QualityScorer` starts at 100. `validation_failed` subtracts 40. Each warning subtracts 5. A length ratio above 2.5 sets `length_explosion` and subtracts 20. A ratio under 0.3 when the source is longer than 20 characters sets `too_short` and subtracts 15. Leftover English words the, and, with, your, or please set `possible_untranslated` and subtract 10. The row needs review when the score is under 70, or when `validation_failed` or `length_explosion` is set.

### 6.2. Files

| File | Role |
|---|---|
| `myaitranslationsgpt.php` | Install, uninstall, tab, hooks, assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Update check for the **Updates** tab and the back-office warning. Class `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logo in the module header. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Every back-office tab, saves, job actions, glossary, excludes, catalog, CSV, AJAX. |
| `controllers/front/cron.php` | Cron address. Processes one slice and returns JSON. |
| `sql/install.php`, `sql/uninstall.php` | Create and drop the tables. |
| `src/Adapter/TranslationAdapterInterface.php` | Read and write interface for PrestaShop translations. |
| `src/Adapter/AbstractTranslationAdapter.php` | Sections, domains, locales, save through the service or the `translation` table, cache clear. |
| `src/Adapter/TranslationAdapter.php` | Concrete adapter. |
| `src/Adapter/TranslationAdapterFactory.php` | Builds the adapter. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Reads XLF catalogues from themes and modules. |
| `src/Adapter/LegacyModuleCatalogue.php` | Classic modules: read and write `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Back-office forms and field `desc` text. |
| `src/Admin/MyaitgptSectionHelp.php` | **Help** panel text for each tab. |
| `src/Audit/RequestLogRepository.php` | **History**: rows, cards, charts, filters, clear, retention. |
| `src/Audit/ApiLogRepository.php` | API error and warning log, retention. |
| `src/Audit/TranslationMemory.php` | Reuses a result for the same text, locale, model, and glossary. |
| `src/Audit/UsageLedger.php` | Cost estimate and the monthly budget. |
| `src/Audit/SnapshotService.php` | Copies before a write, and restores them on **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Glossary list, insert, delete. |
| `src/Glossary/ExcludePatternRepository.php` | Exclude insert, delete, and matching. |
| `src/Job/JobStatuses.php` | Status constants for jobs and rows. |
| `src/Job/JobRepository.php` | Jobs and rows: read, status, next slice, counters. |
| `src/Job/JobWorker.php` | Slice processing, retry, finish, review queue, completion email. |
| `src/Provider/TranslationProviderInterface.php` | Provider interface. |
| `src/Provider/OpenAiTranslationProvider.php` | ChatGPT calls, connection test, request log. |
| `src/Provider/PromptBuilder.php` | System and user prompts: tone, brand voice, glossary. |
| `src/Provider/ProviderFactory.php` | Builds the provider. |
| `src/Quality/PlaceholderValidator.php` | Placeholder and tag check. |
| `src/Quality/HtmlValidator.php` | HTML check. |
| `src/Quality/PsNativeValidator.php` | Check before a **Manual** save. |
| `src/Quality/EmailHtmlPipeline.php` | Protects email HTML before the call and restores it after the reply. |
| `src/Quality/QualityScorer.php` | Score 0-100, flags, review decision. |
| `src/Security/ApiKeyEncryptor.php` | Encrypt and decrypt the API key. |
| `src/Service/ConfigService.php` | Read and save settings, models, cron token, ranges. |
| `src/Service/RateLimiter.php` | Local per-minute limit, file `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Excludes, memory, calls, validation, score, save, estimate. |
| `src/Service/BulkJobFactory.php` | Builds a **Bulk** job and the estimate. |
| `src/Service/CatalogTranslateService.php` | Collects and saves **Catalog** rows. |
| `src/Service/DashboardService.php` | Coverage counts on **Dashboard**. |
| `translations/*.php` | Interface translations, one file per language. |
| `views/templates/admin/configure.tpl` | The module page and the **Help** drawer. |
| `views/templates/admin/_partials/*.tpl` | Tabs: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Back-office styles. |
| `views/js/admin.js` | **Jobs** progress and **Auto-process**, row checks, AJAX. Shows **Brand voice** only when **Tone** is **Brand**, and **Notify email** only when email notify is on. |
| `views/js/admin-help.js` | **Help** panel. |
| `views/js/translations-tool.js` | Buttons and bar on **International → Translations**. |
| `views/js/entity-fields.js` | Buttons and bar on product, category, and CMS forms. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Charts on **Dashboard**. |
| `var/rate_limit.json` | Counter for the local per-minute limit. |
| `index.php` in each directory | Blocks directory listing. |

### 6.3. Controllers

**Back office: `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsgpt&token=…`, optional `&myaitgpt_tab=` with `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (the tab label is **History**), `settings`, `updates`.
- Job actions, query `job_action` plus `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. The template does not render a Cancel button. `filter_failed=1` limits the row table. `cancel` sets the job to `cancelled` and leaves waiting strings untranslated. Message: **Job cancelled. Strings still waiting were not translated.**
- Review actions: `review_action=approve|reject` and `id_review`.
- Glossary: `delete_glossary`. Excludes: `delete_exclude`. Models: `delete_openai_model`, and POST `new_openai_model` with `submitMyaitranslationsgptAddModel`.
- Glossary CSV: `importGlossaryCsv()` skips the header and any row with fewer than three columns, then inserts each remaining row. It does not update an existing term.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource`, `displayAjaxListDomains`.

**Front: `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- Shop URL: `module/myaitranslationsgpt/cron`.
- Query `token` must match `MYAITGPT_CRON_TOKEN` (`hash_equals`). A missing or wrong token returns HTTP 403 and JSON `{"ok":false,"error":"Forbidden"}`.
- Optional `id_job` processes that job. Without it, the first `pending` or `running` job is processed.
- A successful slice returns JSON with `ok`, `finished`, and `counts`. When no job is waiting, the body is `{"ok":true,"message":"No pending jobs"}`.
- `ssl` is true on the controller.

### 6.4. Hooks

Registered hooks:

- `displayBackOfficeHeader` - renames a technical tab label, then loads CSS and JS.
- `actionAdminControllerSetMedia` - loads the same assets.

`translations-tool.js` is added on the translations controller. `entity-fields.js` is added on shop forms when the field switches are on. `Media::addJsDef` publishes `myaitgptTr` (ajax URL, source locale, languages, and the bar labels). The bar label is **ChatGPT translations**.

The module does not register any hook of its own for other modules to implement. There is no `enable()` and no `disable()`.

### 6.5. Overrides

The module does not override any PrestaShop class or controller.

### 6.6. Database

| Table | Contents |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, shop id, dates. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | One bulk run: locales, `scope_json`, `policy_json`, `dry_run`, counters, token totals, cost, employee, error, timestamps. |
| `myaitgpt_job_item` | One string of a job: domain, key, theme, locale, source, previous value, new value, status, skip reason, error, tokens, validation. |
| `myaitgpt_memory` | Translation memory: hash, source, locale, translation, model, hit count. |
| `myaitgpt_usage_ledger` | Daily token and cost rows, optional job id, model. |
| `myaitgpt_snapshot` | Value before a job write, used by **Rollback**. |
| `myaitgpt_api_log` | Error and warning rows: level, provider (default `openai`), HTTP code, message, context. |
| `myaitgpt_request` | **History** rows: type, status, model, locales, HTTP code, duration, tokens, cost, employee, job, prompt, reply, error. |
| `myaitgpt_review` | Review queue: job item, status, score, flags, employee. |
| `myaitgpt_catalog_item` | Catalog batch rows: entity, field, languages, source, previous, new, status, error. |

Uninstall drops all eleven tables. Install uses `CREATE TABLE IF NOT EXISTS`, so a reinstall on a database that still has the tables keeps those rows. A normal uninstall removes them first. No column is added on the first visit to a page.

### 6.7. Keys and translations

Prefix `MYAITGPT_`. Values when the key is missing, which is also the value written on install:

| Key | When missing |
|---|---|
| `API_KEY_ENC` | empty |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | empty |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | empty |
| `BATCH_SIZE` | `25` (saved again clamped to 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | empty |
| `TEMPERATURE` | `0.2` (saved again clamped to 0-1) |
| `DRY_RUN_SAMPLE` | `10` (saved again clamped to 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | empty |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (stored only; `translateBatch()` does not send it) |
| `CRON_TOKEN` | 16 random bytes as hex, generated on install |

`removeConfiguration()` also deletes leftover names `DEEPL_API_KEY` and `CLAUDE_API_KEY` under the same prefix. It does not delete the update-checker keys.

Field descriptions are the `desc` strings in `src/Admin/MyaitgptForms.php`, built by `help()` as purpose, how to set, and effect. The **Max tokens** help says to leave 0 for the ChatGPT default. The request ignores the stored value. Tab help is `src/Admin/MyaitgptSectionHelp.php`.

Interface strings go through `$this->l()` / `{l s=... mod='myaitranslationsgpt'}`. Add a language by adding `translations/{iso}.php`. The job error **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.**, and **Monthly API budget has been exhausted.** are English strings returned from `JobWorker` and `TranslateService`, not `$this->l()` calls. The **Updates** strings use the `updatechecker` translation domain. `OpenAiTranslationProvider` returns **ChatGPT rate limit (429). Try again later.** on HTTP 429.

### 6.8. Extending

The storefront does not render a module template, so the theme has nothing to override.

Back-office templates live in `views/templates/admin/`. PrestaShop does not offer a theme override for those admin templates. Change labels through `translations/{iso}.php`. The buttons on **International → Translations** and on shop forms are injected by `views/js/translations-tool.js` and `views/js/entity-fields.js` from `myaitgptTr`. There is no hook a theme can use to replace that bar.

## 7. Help

Module page: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

To write about this module, sign in to your customer account on mypresta.eu, open the contact form, and choose **Support for paid modules**. The form says that a login is required for paid modules. After you sign in, choose this module from the purchase history.
