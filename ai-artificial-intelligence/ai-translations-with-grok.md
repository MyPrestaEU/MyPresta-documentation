---
title: "AI Translations with Grok - documentation and user manual"
description: "Configuration and troubleshooting guide for shops that already use AI Translations with Grok."
sidebar:
  label: "AI Translations with Grok - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy AI Translations with Grok Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Requirements

The module works on PrestaShop 1.7.0.0 and newer, including PrestaShop 8 and 9.

- **PrestaShop:** 1.7.0.0 or newer.
- **PHP:** 5.6 or newer.
- **PHP extensions:** cURL, OpenSSL, SimpleXML and mbstring.
- **Other modules:** none required.
- **Outside the shop:** an xAI account and a Grok API key from the xAI console. Your shop server has to be able to reach `https://api.x.ai/v1/chat/completions`.
- **Optional:** a scheduled task on your server that calls the cron address from **Settings**. Without it, you process jobs yourself on **Jobs**.
- **Large catalogues:** a domain with thousands of strings means thousands of API calls. A job is split into slices of **Batch size**. Before you start, press **Estimate** on **Bulk** to see the string count and the expected cost.
- The shop needs at least two languages. With only one, the back office shows **The shop needs at least two languages.** and there is nothing to translate.

## 2. Installation

1. Go to **Modules**, then **Module Manager**. Choose **Upload a module**, upload the ZIP file and press **Install** next to **AI Translations with Grok**.
2. After installation, **AI Translations with Grok** appears in the **International** menu.
3. Installing the module does not clear the shop cache. The module clears it when it saves a translation.

Next, open **AI Translations with Grok**, go to **Settings** and paste your Grok key. Until a key is saved, every page of the module shows **No Grok API key.** with an **Open Settings** link.

**Uninstalling.** In **Module Manager**, press **Uninstall** and confirm **Delete this module and its data (jobs, glossary, cache)?**

- The menu entry disappears. Jobs, the glossary, exclude patterns, the call history, the **Review** queue, rollback copies, the cost ledger and the module settings (including the API key) are all deleted.
- Text the module has already written into your shop stays where it is. That means catalogue translations and the translation files of classic modules that the module wrote. Your choice for update checks stays too.
- Reinstalling does not bring back deleted jobs, glossary entries or history. It sets the default values and creates a new cron address.

## 3. Configuration and daily use

The whole module lives on one page: **International**, then **AI Translations with Grok**. The tabs are **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** and **Settings**. **Updates** is at the end of the bar. **Help** opens a panel with information about the tab you are on. The **Updates** tab does not have a **Help** button.

The button and field names in this manual are the ones from the English back office. In another language you will see the translated label for the same control.

A typical workflow has four steps.

1. **Connect.** On **Settings**, paste your key, choose a model and press **Test connection**, then **Save**.
2. **Run a small test.** On **Manual**, filter one domain, tick a few empty strings and translate them. Check the results before you translate the whole catalogue.
3. **Create a job.** On **Bulk**, choose the section, languages and domains, press **Estimate**, then **Start job**. Open the job and press **Process slice** or **Auto-process**, or leave it to the cron address.
4. **Check the results.** Open **Review** for rows the quality check held back, and **History** if a call failed. **Rollback** on a job restores the previous text, as long as the module kept a copy.

The module never starts a translation on its own. **Estimate**, **Filter** and **Save** on **Settings** don't write any catalogue text. A job waits on **Jobs** until you process it or the cron address calls it.

### 3.1. Module configuration

Go to **Modules**, then **Module Manager**, find **AI Translations with Grok** and press **Configure**. The **Dashboard** opens. Switch to **Settings**.

**Save** and **Test connection** are at the bottom of the form. Saving the form does not start a translation or overwrite translations that are already stored.

![Settings, English back office. The top of the form: Grok API key, Model, Add a Grok model, Tone, and Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Connection**

| Field | Default | What it does |
|---|---|---|
| **Grok API key** | empty | The secret key your shop sends to Grok. Paste the key from the xAI console. Leave the field empty to keep the key you already saved. Entering a new value replaces the stored key. An empty field does not delete it. Once a key is saved, the help text shows **Key saved:** followed by a masked version of the key. |
| **Model** | grok-4.7 | The Grok model that writes the translation. The built-in models are listed: grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning and grok-4.20-0309-reasoning. Models you add yourself can be removed. The next translation uses the selected model. If your account can't use a model, the call fails and the error shows up in **History**. |
| **Add a Grok model** | empty | Type the exact model ID from your xAI account and press **Add model**. The placeholder in the field is grok-4.7. The new ID appears in **Model** and becomes the active model. **Remove** only deletes IDs you added here. Built-in models can't be removed. |

Messages you may see: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example grok-4.7.**, **Built-in models cannot be removed.**

**Voice and source**

| Field | Default | What it does |
|---|---|---|
| **Tone** | Formal | Adds a style instruction to every prompt. **Formal** suits shop and back-office wording, **Casual** sounds lighter, and **Brand** works together with **Brand voice**. New translations follow the chosen style. Translations that already exist stay as they are until you run them again. |
| **Brand voice** | empty | Visible only when **Tone** is set to **Brand**. Write a few plain sentences about how the shop should sound, or leave it empty. The text is added to the next prompt. An empty field means no extra voice. Changing it does not rewrite existing translations. |
| **Source locale** | empty | The language the model treats as the original. The empty option appears as a dash in the list, which means the screen you're translating supplies the source. Usually you'll pick the locale your catalogues are written in, typically en-US. **Manual**, **Bulk** and the icons on **International → Translations** use this locale as the source. The shop's default language is not changed. |
| **Individual field buttons — shop forms** | Yes | Adds a button next to each multilanguage field in shop forms: products, categories, CMS pages and other back-office forms. The button translates only that one field. **No** hides these buttons across the whole shop. Saved translations are not affected. |
| **Individual field checkboxes — shop forms** | Yes | Each of those fields gets a checkbox, and the bar translates only the fields you tick. **No** hides the checkboxes and the bar. The buttons above have their own switch. |
| **Individual field buttons — International → Translations** | Yes | Adds a button to each field on **International → Translations**. **No** hides them. Shop forms are not affected. One click fills that field. PrestaShop's **Save** button is still what saves the page. |
| **Individual field checkboxes — International → Translations** | Yes | Checkboxes and the bar on **International → Translations**. **No** hides them. Shop forms are not affected. |

**Limits**

![Settings, English back office. Batch size and the limit fields under it.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Field | Default | What it does |
|---|---|---|
| **Batch size** | 25 | How many strings go into a single API call. For a first run, use 10 to 25. The value must stay between 1 and 100. Bigger batches finish a job in fewer calls, but if one fails, the module retries a larger chunk. |
| **Dry-run sample** | 10 | How many example strings **Estimate** shows before a bulk job. The value must stay between 1 and 50. **Estimate** lists that many source strings along with a cost estimate. It does not write any translations. |
| **Max tokens (0 = default)** | 0 | Caps how long a single reply can be. Leave it at 0 to use Grok's default length. Enter a number if replies are being cut off or you want them shorter. The limit applies only to the next call and does not shorten translations you've already saved. |
| **Budget USD / month** | 0 | A monthly ceiling in US dollars, calculated from the usage ledger. 0 means no limit. Enter the amount you're willing to spend, starting from the first day of the month. Once the ledger reaches that amount, new translations stop, and the screen shows **Monthly API budget has been exhausted.** Work that's already saved is kept. |
| **Rate limit / min** | 60 | How many API calls this shop may start in one minute. 60 is a sensible starting point. 0 turns this local limit off. Calls over the limit are skipped and recorded in **History**. Grok may apply its own limit on top. |
| **Log retention days** | 30 | How many days of rows to keep in **History**. The minimum is 1. Older rows are deleted when a new call is saved. This setting doesn't delete jobs, the glossary or saved translations. |
| **Temperature** | 0.2 | How freely the model may rephrase. Around 0.2 stays close to the source text. Values closer to 1 change the sentences more. The value must stay between 0 and 1. Placeholders and HTML are still checked afterwards. The next translation uses this value. |
| **Allow publish / save** | Yes | Whether the module may write translations into PrestaShop. **No** blocks saving from **Manual**, bulk jobs and **Catalog**. The icons on the translation page and on shop forms only fill in the form. PrestaShop's **Save** is separate. |

After you press **Save**, you'll see one of these messages:

- **Settings saved. No translation was started.** Your settings are stored and nothing has been translated.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Paste a key into **Grok API key** and press **Save** again.

**Mail and cron**

| Field | Default | What it does |
|---|---|---|
| **Email notify on complete** | No | Sends one email when a bulk job finishes. The job runs the same way either way. Only the email is added or skipped. |
| **Notify email** | empty | The address that receives that email. The field only appears when the switch above is on. If it's empty, the shop's email address is used. Saving an address doesn't send anything by itself. The subject line starts with the module name, the job number and the status. |
| **CRON URL** | an address with a token | A secret address your server can call to process one slice of a waiting job. Copy it into your server's scheduler and don't publish it. Anyone who has the address can start a slice. Opening **Settings** does not start a job. |

**Test connection** checks your key and model with one short request. It doesn't translate anything or save anything.

- **Connection OK (N ms). No translation was started.** The connection works.
- **Connection was not made. Nothing was translated.** followed by the reason. Check the key and the model. The details are in **History**.

A good way to start: paste your key, choose the model and source locale, press **Test connection**, then **Save**. Leave the numbers at their defaults until a job starts behaving badly.

### 3.2. Dashboard

Open the **Dashboard** tab. It counts the strings missing from your catalogue, then shows your Grok usage as cards, charts and the ten most recent prompts. The page doesn't translate anything or change any strings.

![Dashboard, English back office. Coverage for one locale, the cron line, and the history filters.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Coverage**

- **Locale:** the shop locale whose missing strings are counted.
- **Show:** redraws the table for that locale.
- Columns: **Section**, **Total**, **Missing**, **Done** and a progress bar. The sections are **Back office**, **Themes**, **Installed modules**, **Emails** and **Others**. **Missing** is the number of strings that have no translation in that locale.
- Below the table, **CRON** shows the same address as **CRON URL** on **Settings**.
- An empty table means the shop doesn't have a catalogue for that locale yet. Create one under **International → Translations**.

After you press **Show**, you'll see **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Usage**

- Presets: **Today**, **7 days**, **30 days**, **This month** and **All time**.
- Filters: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** and **Prompt or reply contains**. Press **Filter** to apply them.
- Cards: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** and **Estimated cost**. The estimated cost is the module's own calculation, not an invoice from xAI. A dash means Grok didn't return a token count for that call.
- Charts: **Requests and errors**, **Tokens sent and received** and **Requests by model**. Below them are the groups **By day**, **By model**, **By type**, **By language** and **By employee**, each with the columns **Group**, **Calls**, **Sent**, **Received** and **Total**. An empty group shows **No requests in this range.**
- **Latest prompts** lists the ten most recent calls. **View** opens the prompt and the reply. **See all** opens **History** (section 3.10). When the list is empty, you'll see **No requests yet.**

Filtering doesn't delete history or change translations.

If a section is mostly empty, open **Manual** to translate a few strings, or **Bulk** to translate a whole domain.

### 3.3. Manual

Open **Manual**. Use it to translate one domain or one classic module, a few dozen strings at a time. Filtering doesn't save anything.

![Manual, English back office. Section, Source, Target, Domain, Only empty, and Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Field | Default | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue is read: **Back office**, **Themes**, **Installed modules**, **Emails** or **Others**. Changing the section reloads the page and shows only the fields for that section. It does not call Grok. |
| **Theme** | empty | Shown only for **Themes**. Limits the list to one theme. |
| **Module** | empty | Shown only for **Installed modules**. Limits the list to one module. A classic module without a domain loads every string in that module. |
| **Domain** | empty | The same grouping as on **International → Translations**. Pick one and press **Filter**. Hidden for classic modules and for sections that have no domains. The empty row shows **— choose —**. |
| **Source** | the **Source locale** from **Settings**, or en-US | The language the strings are taken from. Pick a language that already has good text. |
| **Target** | the first language in the list | The language you want to fill in. It must exist under **International → Localization → Languages**. |
| **Only empty** | Yes | Shows only strings without a translation. Turning it off shows every string. Saved translations are not deleted. |
| **Search** | empty | Keeps only the source strings that contain the word you type. |

How to use it:

1. Set **Section**, **Source** and **Target**.
2. For **Themes**, choose a **Theme**. For **Installed modules**, choose a **Module**.
3. Press **Filter**. The **Domain** list refreshes. Pick a domain and press **Filter** again. For a classic module, skip the domain: **Filter** loads every string in the module.
4. Tick the rows you want. **Check all** and **Uncheck all** select or clear the whole list.
5. Press **Translate selected (review)**. A table called **Review before save** opens with **Source**, **AI proposal** and **Warnings** columns. Untick any rows you don't want, edit a proposal directly in its box, then press **Save approved**.
6. Alternatively, tick **Save now (skip review)** before you translate. Valid rows are saved right away, without the review table.

The string list has the columns **Source**, **Current** and **Status** (**empty** or **filled**).

Messages you may see:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** This is the list for a classic module.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Grok.**
- **No strings match this filter. Nothing was sent to Grok.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Grok.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Grok API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Those rows were skipped. Fix the placeholders and tags so they match the source, then save again.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Changing the section also shows a short note, for example **Section is Back office. Theme and module are not used.**, together with **Nothing was sent to Grok.** The same pattern applies to **Themes**, **Installed modules**, **Emails** and **Others**.

### 3.4. Bulk

Open **Bulk**. It creates one job covering many domains and languages. **Estimate** doesn't save anything. **Start job** adds a row to **Jobs**. Nothing is written until the job is processed and **Allow publish / save** is on.

![Bulk, English back office. Section, Source, Targets, Domains, Policy, and Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Field | Default | What it does |
|---|---|---|
| **Section** | Back office | Which catalogue the job reads. The page reloads and shows **Theme** only for **Themes**, and **Module** only for **Installed modules**. Strings outside the chosen section aren't included. Changing the section doesn't start a job. |
| **Theme** | empty | Shown only for **Themes**. Other themes are left out. |
| **Module** | empty | Shown only for **Installed modules**. A classic module has no domains, so **Estimate** and **Start job** cover every string in it. |
| **Source** | the **Source locale** from **Settings**, or en-US | The locale the job treats as the original. Every target is translated from this one. |
| **Targets** | nothing selected | The locales the job will fill in. Select one or more. A click without Ctrl replaces the current selection. The job keeps a separate set of strings for each selected locale. |
| **Domains** | nothing selected | The domains included in the job. Hold Ctrl or Cmd to select several rows. Unselected domains are skipped. Only leave them all unselected if you really want an empty job. Hidden for classic modules. |
| **Policy** | Fill empty | **Fill empty** skips strings that already have a translation. **Overwrite all** sends every string and replaces finished work, as long as the job is allowed to save. **Outdated if equals source** sends strings whose translation is still identical to the source. |
| **Dry-run job** | No | Runs the model but doesn't write the reply into PrestaShop. The job still appears on **Jobs**. Catalogue files and database translations stay as they were. |

How to use it:

1. Set **Section**, **Source** and **Targets**.
2. For **Themes**, choose a **Theme**. For **Installed modules**, choose a **Module**.
3. When the list appears, select **Domains**. Hold Ctrl or Cmd to pick several.
4. Press **Estimate**. Check the string count, the token estimate, the cost estimate and the **Sample**. Nothing has been sent to Grok or saved. You'll see **Estimate only: N strings, ~N tokens, ~$N. Nothing was sent to Grok and nothing was saved.**
5. Press **Start job**. The module opens that job. You'll see **Job #N is waiting (N strings, est. $N). It has not run yet.**

If a required choice is missing, you'll see one of these:

- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Grok API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Open **Jobs**. The list shows every job. When there are none, you'll see **No jobs yet.**

![Jobs, English back office. The job list with Status, Locales, Progress, Cost, Employee, and Date.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Columns: **#**, **Status**, **Locales**, **Progress**, **Cost**, **Employee**, **Date** and **Open**.

Status names on this screen stay in English: **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** and **failed**.

Press **Open** on a row. The details show **Status**, progress as done/total, **failed**, **skipped**, the cost, the employee number, and **dry-run** if that option was on. A progress bar sits below.

Buttons on an open job:

- **Process slice** translates one batch and then stops. Message: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** When nothing is left, you'll see **The job has no more strings waiting.**
- **Auto-process** keeps requesting the next slice until the job finishes or stops.
- **Pause** stops any further slices. Message: **Job paused. It will not translate more strings until you resume it.**
- **Resume** puts a paused job back in the queue. Message: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** puts the failed rows back in the queue. Message: **Retried N failed items.**
- **Rollback** asks **Roll back this job?** and restores the previous text wherever the module kept a copy. Message: **Rollback: restored N translations.**
- **Error CSV** downloads the failed rows.
- **Failed only** shows only rows with the status **failed**.
- **Review queue** opens **Review**.

There's no **Cancel** button on this screen. If you don't want a job to finish, leave it **paused**.

The row table has the columns **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** and **Error**. Item statuses stay in English as well: **pending**, **processing**, **done**, **failed**, **skipped** and **rolled_back**.

If the shop hits its own per-minute limit during a slice, the job pauses automatically and the error line reads **Rate limit — job auto-paused. Resume later.** Press **Resume** when you're ready, then **Process slice**.

A dry-run job calls Grok and stores the proposal on the job. It doesn't write to the catalogue.

### 3.6. Review

Open **Review**. This is the queue of bulk-job results that need a second look. The page says **Needs-review queue (quality score / flags).** When the queue is empty, you'll see **The queue is empty.**

![Review, English back office. The needs-review queue.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Columns: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, **Approve** and **Reject**.

A row ends up here when the quality check scores it below 70, when placeholders or HTML don't match, or when the translation is much longer than the source. If the job was allowed to publish and the string passed validation, the catalogue may already contain the proposal. **Approve** and **Reject** only change this queue. They don't write a new translation and they don't restore the old one. After either button you'll see **Review updated.** and the row leaves the queue.

The review table on **Manual** is a separate screen, and its button is **Save approved**.

### 3.7. Catalog

Open **Catalog**. Use it to translate product, category or CMS fields. This is not the same as the **International → Translations** catalogue. One press handles at most 100 records.

![Catalog, English back office. Entity, Fields, Source language, Target language, Only empty, and Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Field | Default | What it does |
|---|---|---|
| **Entity** | product | Which records are read: **product**, **category** or **cms**. The page reloads and shows only that entity's fields. Changing the entity doesn't translate anything. You'll see **Showing fields for {entity}. Nothing was translated.** |
| **Fields** | every field of the entity | The texts this batch sends. Hold Ctrl or Cmd to select several. **Title** is the product name, the category name or the CMS page title. **Content** is the body of a CMS page. If you want links to stay as they are, leave **Friendly URL** out. Only the selected fields are translated. |
| **Source language** | the shop's language list | The language the fields are copied from. The source language itself is not changed. |
| **Target language** | the shop's language list | The language that receives the translation. It must differ from the source. Up to 100 records are written at a time. |
| **Only empty** | Yes | Skips fields that already have text in the target language. **No** allows that text to be overwritten, as long as publishing is permitted. |
| **Start after ID** | 0 | Skips records up to this ID. Leave it at 0 to start from the first record. After each batch, the field shows the last ID that was read. Press the button again to continue. |

Product fields: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** and **Friendly URL**.

Category fields: **Title**, **Description**, **Meta title**, **Meta description** and **Friendly URL**.

CMS fields: **Title**, **Meta description**, **Meta keywords**, **Content** and **Friendly URL**.

Press **Translate batch (max 100)**. When it finishes, you'll see **Catalog finished: saved N, failed N.** The form also shows **Saved** and **failed** counts.

- **Nothing was translated. There is no Grok API key. Open Settings and paste the key.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was translated. Select at least one field.**

### 3.8. Glossary

Open **Glossary**. The list holds words the model must keep as they are or render in a fixed way. Adding a term doesn't rewrite translations that already exist, but the next translation will use the list.

![Glossary, English back office. Add glossary term and the CSV form.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Field | Default | What it does |
|---|---|---|
| **Source term** | empty | The wording as it appears in the source language. Type the exact word or phrase, with capitals if they matter. Required. |
| **Target locale** | empty | Limits the entry to one target locale, such as pl-PL. Leave it empty to apply the entry to every target. A filled-in locale is ignored for other languages. |
| **Target term** | empty | The wording that should appear in the translation. Leave it empty only when **Do not translate** is on. |
| **Do not translate** | No | **Yes** tells the model to copy the source term unchanged. Use it for brand names, SKUs and placeholders. **No** means the **Target term** is the translation you want. |

Press **Add**.

- **Glossary term added. Translations already stored were not changed.**
- **Nothing was added. Type a source term.**

The table columns are **Source**, **Locale**, **Target**, **Do not translate** (**Yes** or **No**) and **Delete**. When the table is empty, you'll see **No glossary terms yet.** **Delete** removes that row, and you'll see **Glossary term deleted.**

**Glossary CSV**

| Field | Default | What it does |
|---|---|---|
| **CSV file** | empty | The file needs the columns source_term, target_locale, target_term and do_not_translate. **Import CSV** adds the rows it can read. **Export CSV** downloads the current list and ignores the file field. Exporting doesn't change the glossary. |

- **Imported N rows.**
- **CSV file is missing.** Choose a file and press **Import CSV** again.
- **Cannot open the CSV file.** Save the file as CSV and try again.

### 3.9. Excludes

Open **Excludes**. This list holds source strings the module should skip. A matching string is not sent to Grok, and it isn't deleted from PrestaShop. Saving a pattern doesn't change strings that are already stored.

![Excludes, English back office. Pattern, Type, and the pattern table.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Field | Default | What it does |
|---|---|---|
| **Pattern** | empty | The text that's compared with each source string. Required. |
| **Type** | exact | **exact** matches the whole string, **prefix** matches the start, **contains** matches a fragment, and **regex** is a PHP regular expression applied exactly as written. Test a short pattern first, because the wrong type can skip too much or nothing at all. |

Press **Add**.

- **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.**
- **Nothing was added. Type a pattern.**

The table columns are **Pattern**, **Type**, **On** and **Delete**. **On** shows 1 for a pattern that is in use. When the table is empty, you'll see **No patterns yet.** **Delete** removes that row, and you'll see **Pattern deleted.**

### 3.10. History

Open **History**. This is the full list of calls to Grok, including connection tests and calls that were blocked before being sent. The charts and the ten latest prompts are on **Dashboard**, and **See all** there opens this tab.

![History, English back office. The request list and Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Columns: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time**, **Prompt** and **View**.

**Type** is one of **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** or **Not sent**. **Status** is **Success** or **Error**.

**View** opens the prompt and the reply, along with **HTTP**, **Sent**, **Received** and **Total**. **Back to the list** returns you to the table. If the row has been deleted, you'll see **This history row no longer exists.** If the details can't be loaded, the page shows **Could not load this request.**

**Previous** and **Next** move between pages. The line reads **Page N / N**.

**Clear history** asks **Clear the stored history? Saved translations stay.** Confirming deletes these rows only. You'll see **History cleared. Saved translations were not changed.** When the list is empty, it says **No requests yet.**

**Log retention days** on **Settings** also removes rows older than that number of days whenever a new call is saved.

### 3.11. Updates

Open **Updates**. This page checks whether a newer package is available. It doesn't translate anything.

![Updates, English back office. Manual Check, Automatic Notifications, and Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Field | Default | What it does |
|---|---|---|
| **Manual Check** | the **Check Now** button | Asks the publisher once. **Module is up to date!** means this installation is the current package. **New version available!** means a newer package has been published. Download it from the product page and install it through **Module Manager**. |
| **Automatic Notifications** | Enabled | **Enabled** lets the back office show a notice when a newer package exists. **Disabled** turns that notice off. Press **Save** to keep your choice. Uninstalling the module doesn't clear this setting. |
| **Product Page** | a link with the module name | Opens the module's page. The address is in section 7. |

When a newer package exists, the back office may also show **New version available, check MyPresta.eu for more information** with a **More details in changelog** link.

### 3.12. Buttons on International → Translations

Open **International**, then **Translations**, and open a catalogue. When **Individual field buttons — International → Translations** is **Yes**, each field gets a **Translate** button. One click fills that field. PrestaShop's **Save** still saves the page.

When **Individual field checkboxes — International → Translations** is **Yes**, the page also shows a bar titled **Grok translations**.

- **Source** is filled in from **Source locale** on **Settings**. If that setting is empty, the bar uses en-US. You can edit the field.
- **Target** is the language of the catalogue you have open.
- **Check all**, **Uncheck all** and **Check empty** change the ticks.
- **Translate empty** fills the empty fields. **Translate selected** fills the ticked fields.
- The hint reads **Fills the fields. Save with the PrestaShop button.**
- While it's working, the bar shows **Translating…**. When it finishes, it shows **Done**.
- **Selected** shows how many fields are ticked.
- **Tick at least one field.** appears when you press **Translate selected** with nothing ticked.
- **Fill the source language field first.** appears when the source text is empty.
- **The source language mail file was not found.** appears on the email screen when the source mail file is missing.
- **Translate empty in this section** fills the empty strings in the section you're viewing.

These buttons don't replace **Save** on the PrestaShop page. **Allow publish / save** doesn't block them, because they only fill in the form.

### 3.13. Buttons on product, category and CMS forms

Open a product, a category, a CMS page or another back-office form that has a field for each language. When **Individual field buttons — shop forms** is **Yes**, each of those fields gets a **Translate** button. One click fills that field from the source language on the same form.

![Product form, English back office. The Grok translations bar under the description fields.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

When **Individual field checkboxes — shop forms** is **Yes**, the form also shows the **Grok translations** bar.

- **Source** starts from **Source locale**, or en-US if that setting is empty.
- **Target** lists the other shop languages, plus **all other languages**.
- **Check all**, **Uncheck all**, **Check empty**, **Translate empty** and **Translate selected** work the same way as on the translation page.
- The hint reads **Fills the fields. Save with the PrestaShop button.**
- **Tick at least one field.**, **Fill the source language field first.** and **The source language field is not on this page.** tell you what to fix.
- **Target is not a language from this shop.** means the target doesn't match any language in this shop.
- The line above a field can read **Translate from** the source language name **to** the target language name.

Press the PrestaShop **Save** button on that form to keep the filled-in fields. The bar doesn't save the product on its own.

## 4. Storefront

The shop theme doesn't display anything from this module. Customers don't see a translation button, a form or a status page.

The only address outside the back office is **CRON URL** on **Settings**, which is also repeated below the coverage table on **Dashboard**. Copy that address into your server's scheduler. Each call processes one slice of the first waiting or running job, then stops. Opening **Settings** doesn't call it.

| What you see | What to do |
|---|---|
| A JSON line with the slice result | The slice ran. Open **Jobs** and read the rows. |
| **No pending jobs** | No job is waiting. Create one on **Bulk**, or the previous job has already finished, been paused or been cancelled. |
| **Forbidden** | The address is wrong, or the token was regenerated when the module was reinstalled. Copy **CRON URL** again. Don't publish the address. |

Don't add your own parameters. The address you copy is the one the module reads.

## 5. Troubleshooting

**No Grok API key.** and **Open Settings** appear on every tab. Paste the key on **Settings**, press **Test connection**, then **Save**.

**The shop needs at least two languages.** Add a language under **International → Localization → Languages**, then open the module again.

**Connection was not made. Nothing was translated.** The reason is shown right after this sentence. Check the key, the model and whether your server can reach the Grok address. Open **History** and press **View** on the error row.

**Monthly API budget has been exhausted.** Raise **Budget USD / month**, or set it to 0 if you don't want a ceiling, then press **Save**. Text that's already saved stays as it is.

**Grok rate limit (429). Try again later.** Wait and run the slice again. If the job shows **Rate limit — job auto-paused. Resume later.**, press **Resume**, then **Process slice**. If this keeps happening, lower **Batch size** or lengthen the interval between cron calls. **Rate limit / min** is the shop's own cap, and Grok may still refuse a call.

**Nothing was saved. Turn on Allow publish in Settings.** Set **Allow publish / save** to **Yes**, press **Save**, then try the save again. The icons on forms still only fill in the form.

**Not saved because of broken placeholders or HTML: N.** The proposal changed a placeholder or a tag. Edit the proposal so it matches the source, or leave that row unticked, then press **Save approved** again.

**Nothing was translated. Pick a theme, then press Filter.** or **Pick a module.** The section needs that choice before the list can load.

**No strings match this filter. Nothing was sent to Grok.** Turn off **Only empty**, clear **Search**, or pick a different domain.

**CSV file is missing.** or **Cannot open the CSV file.** Choose a CSV file with the four columns and press **Import CSV** again.

**The source language mail file was not found.** On **International → Translations**, open the email section for a language that already has the mail file, or generate the mail translations in PrestaShop first.

**This history row no longer exists.** The row was cleared, or removed by **Log retention days**. The translation that was saved is still in your shop.

The menu entry is missing, or the back office says the controller was not found. Open **Module Manager**, find **AI Translations with Grok** and press **Configure**. That recreates the **International** menu entry. If the module isn't in the list at all, install the ZIP again.

Installation stops with **Could not create the module tables.** The database user doesn't have permission to create tables. Fix the database rights and press **Install** again. **Could not add the menu tab.** means the menu entry couldn't be created. After a successful install, press **Configure**, or install again.

## 6. For developers

### 6.1. Overview

Technical name `myaitranslationsgrok`, version `1.2.0`, author MyPresta.eu, module tab `administration`. The name in the module list and the **International** menu label is **AI Translations with Grok**. The class is `myaitranslationsgrok`. The minimum in `ps_versions_compliancy` is `1.7.0.0`.

`getContent()` calls `ensureTab()` and redirects to `AdminMyaitranslationsgrok`. Settings are read through `MyaitgkConfigService` (`MYAITGK_*` keys). The API key is encrypted and stored in `MYAITGK_API_KEY_ENC`. Translation calls go through `MyaitgkTranslateService` to `MyaitgkGrokTranslationProvider`, which sends a JSON POST to `https://api.x.ai/v1/chat/completions`. Catalogue writes go through `MyaitgkTranslationAdapter`. Product, category and CMS writes go through `MyaitgkCatalogTranslateService`. After a catalogue translation is saved, the module calls `Tools::clearCache()`.

The module doesn't define `enable()` or `disable()`. Turning the module off in **Module Manager** doesn't run any extra cleanup. Uninstalling is what removes the menu tab, the tables and the `MYAITGK_*` keys.

### 6.2. Files

- `myaitranslationsgrok.php` - installation, uninstallation, hooks, tab, and configuration of the field buttons.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - every back-office tab and the AJAX actions.
- `controllers/front/cron.php` - processes one job slice for the cron address.
- `lib/updateChecker.php` - the **Updates** tab and the version check.
- `sql/install.php`, `sql/uninstall.php` - create and drop the tables.
- `src/Admin/MyaitgkForms.php` - HelperForm fields and `desc` texts.
- `src/Admin/MyaitgkSectionHelp.php` - the **Help** panel.
- `src/Service/MyaitgkConfigService.php` - keys, model list, cron token.
- `src/Service/MyaitgkTranslateService.php` - budget, rate limit, glossary, excludes, saving.
- `src/Service/MyaitgkBulkJobFactory.php` - creates a job from **Bulk**.
- `src/Service/MyaitgkCatalogTranslateService.php` - product, category and CMS batches.
- `src/Service/MyaitgkDashboardService.php` - coverage counts.
- `src/Service/MyaitgkRateLimiter.php` - per-minute limit stored in `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - the request to xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - system and user prompts.
- `src/Job/MyaitgkJobWorker.php` - slices, retries, completion email.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - job rows and status constants.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - checks run before saving.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - glossary and excludes.
- `src/Audit/MyaitgkRequestLogRepository.php` - **History** and the dashboard report.
- `src/Audit/MyaitgkSnapshotService.php` - rollback copies.
- `src/Security/MyaitgkApiKeyEncryptor.php` - OpenSSL encryption for the key.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - PrestaShop catalogues and classic `translations/{iso}.php` modules.
- `views/templates/admin/configure.tpl` and `views/templates/admin/_partials/*.tpl` - the tabs.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - back-office strings.

### 6.3. Controllers

`AdminMyaitranslationsgrok` extends `ModuleAdminController`. The parent tab class is `AdminInternational` (fallback `IMPROVE`). The query parameter is `myaitgk_tab` and accepts `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings` and `updates`. Unknown values fall back to `dashboard`.

The visible actions are the submit buttons described in chapter 3. Additional admin endpoints used by the page scripts: `ajax=1&action=HistoryDetail` for **View**, job status polling for **Auto-process**, and the field-translation actions used by `translations-tool.js` and `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) reads the `token` parameter. A missing or wrong token returns HTTP 403 with `{"ok":false,"error":"Forbidden"}`. A correct token without `id_job` processes one slice of the first `pending` or `running` job. With `id_job`, that specific job is processed. When nothing is waiting, the response body is `{"ok":true,"message":"No pending jobs"}`.

`job_action` on the jobs tab accepts `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` and `export_errors`. The template renders every one of them except `cancel`.

### 6.4. Hooks

Registered in `install()`:

- `displayBackOfficeHeader` - fixes the technical tab label and loads back-office assets.
- `actionAdminControllerSetMedia` - loads the same assets.

On `AdminMyaitranslationsgrok`, the module adds `views/css/admin.css`, `views/js/admin.js` and `views/js/admin-help.js`. **Dashboard** also loads `chart.min.js` and `history-charts.js`. On **International → Translations** it adds `translations-tool.js` when the translation-page switches are on. On other back-office forms it adds `entity-fields.js` when the shop-form switches are on. Both pass the `myaitgkTr` object to JavaScript.

The module doesn't register a front-office hook and doesn't expose its own hook.

### 6.5. Overrides

The module doesn't override any PrestaShop class or controller.

### 6.6. Database

Uninstalling runs `sql/uninstall.php` and drops every table listed below. Installation uses `CREATE TABLE IF NOT EXISTS`, so a table that somehow survived is kept.

| Table | Contents |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | One bulk job: locales, `scope_json`, `policy_json`, `dry_run`, counters, cost, status and employee. |
| `myaitgk_job_item` | One string in a job: domain, key, theme, locales, source, previous text, new text, status and warnings. |
| `myaitgk_memory` | A reused translation, identified by `memory_hash`, the model and `hit_count`. |
| `myaitgk_usage_ledger` | Daily token and cost rows, used to calculate **Budget USD / month**. |
| `myaitgk_snapshot` | The text from before a job write, used by **Rollback**. |
| `myaitgk_api_log` | Short error context. The API key is removed before saving. |
| `myaitgk_request` | Rows for **History**: prompt, reply, tokens, model, status and duration. The repository recreates the table if it's missing. |
| `myaitgk_review` | Queue rows with the status `needs_review`, `approved` or `rejected`, plus `quality_score` and `flags_json`. |
| `myaitgk_catalog_item` | Catalogue batch rows: entity, field, languages, source, previous text, new text and status. |

`var/rate_limit.json` is a file, not a table. Uninstalling doesn't delete `mypresta_updates`, `update_myaitranslationsgrok` or `updatev_myaitranslationsgrok`.

### 6.7. Keys and translations

The prefix is `MYAITGK_`. `installDefaults()` writes a key only when it's missing. Default values for missing keys:

| Key | Default when missing |
|---|---|
| `API_KEY_ENC` | empty |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | empty |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | empty |
| `BATCH_SIZE` | `25` (saved within 1–100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | empty |
| `TEMPERATURE` | `0.2` (saved within 0–1) |
| `DRY_RUN_SAMPLE` | `10` (saved within 1–50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (saved as at least 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | empty |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (left out of the translation request when 0; sent as `max_tokens` when greater than 0) |
| `CRON_TOKEN` | 32 hex characters, regenerated when empty |

Saving **Settings** forces `PROVIDER` to `grok` and deletes the `MYAITGK_DEEPL_API_KEY` and `MYAITGK_CLAUDE_API_KEY` keys if they exist from earlier versions. An empty API key field doesn't clear `API_KEY_ENC`.

The built-in model IDs are `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` and `grok-4.20-0309-reasoning`. A missing switch is treated as on, so shops installed before these switches existed keep their icons.

Field descriptions are built by `MyaitgkForms::help()` in the sections **What it does:**, **How to configure:** and **Effect:**. The help panels come from `MyaitgkSectionHelp`. Back-office strings go through `$this->l()`. To add a language, copy `translations/en.php` to `translations/{iso}.php`. A few messages are hard-coded in English in the PHP and will show up that way: `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.`, and the cron JSON messages.

### 6.8. Extending

The storefront theme has no template to override. The module doesn't render any front-office Smarty file. Back-office markup lives in `views/templates/admin/`. The field buttons are injected by `views/js/translations-tool.js` and `views/js/entity-fields.js`. There is no front-office hook to attach to.

## 7. Help

Module page: [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

To contact support about this module, log in to your customer account on mypresta.eu, open the contact form and choose **Support for paid modules**. The form notes that login is required for paid modules. Once you're logged in, select this module from your purchase history.
