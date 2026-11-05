---
title: "AI Translations with Mistral – documentation and user manual"
description: "Configuration and troubleshooting guide for people who use the AI Translations with Mistral module."
sidebar:
  label: "AI Translations with Mistral – documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy AI Translations with Mistral Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Requirements

The module works with PrestaShop 1.7.0.0 and newer.

- **PrestaShop:** 1.7.0.0 or newer.
- **PHP:** the version your PrestaShop release requires. The module does not set its own minimum.
- **PHP extensions:** cURL (connection to Mistral), OpenSSL (API key encryption), SimpleXML (reading XLF translation files), mbstring.
- **Other modules:** the module doesn't depend on any other module.
- **Outside the shop:** a Mistral AI account and an API key, which you create at https://console.mistral.ai/api-keys. The shop server must be able to reach `api.mistral.ai` over outgoing HTTPS.
- **Optional:** a scheduled task on the server that calls the cron address (described in 3.1). Without it, you process jobs by hand in the **Jobs** tab.
- **Large catalogs:** translating a whole domain with thousands of texts means many API calls and a longer wait. The job is split into slices whose size is set by **Batch size**. Always run **Estimate** in **Bulk** before you start.
- The shop needs at least two languages. With only one language, the back office shows a warning, because there is nothing to translate.

## 2. Installation

1. Go to **Modules** → **Module Manager**. Click **Upload a module**, upload the module's ZIP file and click **Install** next to **AI Translations with Mistral**.
2. After installation, **AI Translations with Mistral** appears in the **International** menu.
3. Installation doesn't clear the shop cache. The module clears the PrestaShop cache itself when it saves a translation.
4. Go to **AI Translations with Mistral** → **Settings** and paste your Mistral key. Until a key is saved, the back office shows **No Mistral API key.**

**Uninstalling.** In **Module Manager**, click **Uninstall** and confirm the prompt **Delete this module and its data (jobs, glossary, cache)?**

- Removed: the menu entry, all jobs, the glossary, excludes, the call history, the **Review** queue, the saved copies used for rollback, the cost summary and the module settings (including the API key).
- Kept: the texts the module saved in the shop, meaning the translations in the PrestaShop catalog and the translation files of classic modules that the module wrote to. The update-check settings are also kept.
- Reinstalling doesn't bring back deleted jobs, glossary entries or history. It restores the default settings and creates a new cron address.

## 3. Setup and daily use

The whole module lives on one page: **International** → **AI Translations with Mistral**. The tabs across the top are **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** and **Settings**. The **Updates** tab sits at the far end of the bar. The **Help** button opens a panel that explains the tab you're on.

Field and button names in this manual match the English back office. If your back office is set to another language, you'll see the translated labels instead. The screenshots are from the English back office too.

Each tab starts with a sentence explaining what it does, how to use it and what happens when you do. The same explanation, split into three parts, also appears below the form fields. The **Help** button in the bottom-right corner shows it for the current tab. Opening **Help** doesn't translate anything.

**How it works, start to finish**

A member of your shop staff starts every translation from the back office. Customers never trigger anything.

1. **Settings.** In **Settings**, paste your Mistral key, choose a model and a source language. Click **Test connection**, then **Save**. Without a key, nothing can be sent to Mistral.
2. **Pick a way of working.**
   - A few sentences, or one domain, with a review before anything is saved: **Manual** (3.3).
   - A large domain, a theme or a module: **Bulk**, then work through the job in **Jobs** (3.4, 3.5).
   - Product, category and CMS fields: **Catalog** (batches of up to 100 records, 3.7).
   - Individual fields on the **International → Translations** page (3.12), and in product, category and CMS forms (3.13).
3. **Quality check.** Every translated text is checked for variables, tags and HTML. A text that fails the check isn't saved. A text that scores below 70, runs more than two and a half times longer than the original, or still contains English words goes to **Review**.
4. **Saving.** This depends on the way you work:
   - **Manual:** after **Translate selected (review)**, nothing is saved until you click **Save approved**. Ticking **Save now (skip review)** saves the correct rows right away.
   - **Bulk:** the job waits in **Jobs** and only saves once you process it (**Process slice**, **Auto-process**) or the cron does. A dry-run job never saves anything.
   - **Catalog:** saves rows right away in the chosen target language.
   - **The International → Translations page and the shop forms:** the buttons only fill in the fields. The text reaches the shop when you click **Save** in PrestaShop.
   - With **Allow publish / save** turned off, none of these paths writes text to the shop.
5. **Finishing.** A job in **Jobs** ends as **completed** (everything saved) or **completed_with_errors** (some texts failed, see 3.5). Rows in **Review** disappear after **Approve** or **Reject**. The **Catalog** result tells you how many rows were saved and how many failed.

### 3.1. Module settings page

Go to **Modules** → **Module Manager**, find **AI Translations with Mistral** and click **Configure**. The **Dashboard** opens. Switch to the **Settings** tab.

**Settings** is a single form. The fields appear in the order described below. The **Save** and **Test connection** buttons are at the bottom of the form, not the top.

![Settings: key, model, tone and source language. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Switches for the field buttons and the limits. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Cost, email, cron address and the Test connection and Save buttons. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Connection**

| Field | Default | What it does |
|---|---|---|
| **Mistral API key** | empty | Your key from the Mistral account. Copy it from https://console.mistral.ai/api-keys. Leave the field empty to keep the key you already saved. A new value replaces the saved key; an empty field doesn't delete it. The saved key is displayed masked. |
| **Model** | mistral-small-latest | The Mistral model that does the translating. The list includes mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest and codestral-latest. The new choice applies from the next translation. If your account can't use a model, the call fails and the error is logged in **History**. |
| **Add a Mistral model** | empty | A field below the model list. Type the exact model ID from your account and click **Add model**. The model shows up in the list and becomes active. Below the field you'll see the models you added yourself, each with a **Remove** button. Built-in models can't be removed. |

Messages after these actions: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Style and language**

| Field | Default | What it does |
|---|---|---|
| **Tone** | Formal | Adds a style to every request: **Formal** for an official tone in the shop and the back office, **Casual** for a lighter tone, and **Brand** combined with the **Brand voice** field. New translations use the chosen style. Existing ones stay as they are until you send them again. |
| **Brand voice** | empty | Shows up once you pick **Tone: Brand**. A few sentences describing how the shop should sound. Leaving it empty adds no extra description. The text goes into future requests but doesn't change translations that are already saved. |
| **Source locale** | — | The language the model treats as the original. Usually this is en-US, the language you write your catalog in. The **—** sign means the source language comes from the screen you're translating on. Changing this field doesn't change the shop's default language. |
| **Individual field buttons — shop forms** | Yes | A translate button next to each multilingual field in shop forms: products, categories, CMS pages and so on. Each button translates only its own field. **No** hides these buttons across the whole shop. Saved translations stay the same. |
| **Individual field checkboxes — shop forms** | Yes | Multilingual fields in shop forms get checkboxes. The bar at the bottom of the form translates the ticked fields one after another. With **No**, the checkboxes and the bar disappear. |
| **Individual field buttons — International → Translations** | Yes | A button next to each field on the **International → Translations** page. Shop forms aren't affected. |
| **Individual field checkboxes — International → Translations** | Yes | Checkboxes and the bar on the **International → Translations** page. With **No**, they disappear from that page only. |

**Limits and costs**

| Field | Default | What it does |
|---|---|---|
| **Batch size** | 25 | How many texts go into a single call. For your first run, 10–25 is a good range. The value must stay between 1 and 100. Larger batches mean fewer calls to finish a job; if a call fails, a larger slice is retried. |
| **Dry-run sample** | 10 | How many sample texts **Estimate** shows in **Bulk**. The value must stay between 1 and 50. An estimate saves nothing. |
| **Max tokens (0 = default)** | 0 | The length limit for a single reply. Enter 0 to use Mistral's default. Set a number if replies get cut off or run too long. The change applies from the next call. |
| **Budget USD / month** | 0 | A monthly cap in dollars, based on the cost summary. Enter 0 for no cap. Once the amount is reached, new translations stop. Work already done is kept. |
| **Rate limit / min** | 60 | How many API calls the shop may make in one minute. Enter 0 to switch off this local limit. Calls over the limit are skipped and logged in **History**. Mistral may apply its own limits as well. |
| **Temperature** | 0.2 | How freely the model rewords the text. Around 0.2 stays close to the original; values nearer 1 change sentences more. The range is 0–1. Variable and HTML checks still run either way. |
| **Log retention days** | 30 | How many days entries stay in **History**. The minimum is 1. Older entries are deleted. Jobs, the glossary and saved translations are not affected. |
| **Allow publish / save** | Yes | Whether the module may save translations to the shop. With **No**, saving is blocked in **Manual** (the **Save approved** and **Save now** buttons), in **Bulk** (jobs that aren't dry runs) and in **Catalog**. Buttons on the pages only fill in fields; PrestaShop does the saving. |

Messages after **Save**:

- **Settings saved. No translation was started.** (green) – your settings are saved, nothing was translated.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (yellow) – there's no key yet; paste one.

**Email and cron**

| Field | Default | What it does |
|---|---|---|
| **Email notify on complete** | No | Sends one email when a **Bulk** job finishes. The job itself runs the same way; only the sending changes. |
| **Notify email** | empty | The address that receives the job-finished email. The field appears once **Email notify on complete** is turned on. Saving the address alone doesn't send anything. |
| **CRON URL** | address with a token | An address your server can call to process one slice of a waiting job. Each call handles one slice and then stops. Keep this address private: anyone who has it can trigger a slice. Opening **Settings** doesn't start any job. |

**Test connection** checks your key and model with one short request. It translates nothing and saves nothing. The result is one of:

- **Connection OK (N ms). No translation was started.** – the connection works.
- **Connection was not made. Nothing was translated.** plus a reason – check the key and the model.

A good way to start: paste your key, choose a model and a source language, then click **Test connection**. Leave the other numbers at their defaults until something misbehaves.

### 3.2. Dashboard

Where: the first tab, **Dashboard**.

![Missing-text summary, history filters and call cards. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Charts of calls and tokens. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Summaries and the ten latest calls. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

The Dashboard has two sections. The first shows which texts are still missing a translation. The second shows the history of Mistral calls, as cards and charts. The page doesn't translate anything or change any texts.

**Missing-text summary**

- **Locale:** pick the language whose missing texts you want to count.
- **Show:** refreshes the table for the selected language.
- The table has the columns **Section**, **Total**, **Missing** and **Done**. The **Done** column includes a progress bar. The sections are **Back office**, **Themes**, **Installed modules**, **Emails** and **Others**. **Missing** is the number of texts that have no translation in that language.
- After you click **Show**, you'll see **Coverage for [language]. This page only counts strings. Nothing was translated.**
- Below the table is a **CRON** row with the cron address, the same one shown in **Settings**.
- An empty table means the shop doesn't have a catalog for that language yet. You create one in **International → Translations**.

**Call history**

- **Filter** works with the presets **Today**, **7 days**, **30 days**, **This month** and **All time**, plus the fields **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** and **Prompt or reply contains**.
- The cards show **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** and **Estimated cost**. The cost is an estimate, not an invoice.
- Charts: **Requests and errors**, **Tokens sent and received**, **Requests by model**.
- Below the charts are five summaries: **By day**, **By model**, **By type**, **By language** and **By employee**. If the range contains calls, each summary is a table with the columns **Group**, **Calls**, **Sent**, **Received** and **Total**. If it doesn't, you'll see **No requests in this range.**
- **Latest prompts** lists the ten most recent calls, with the columns **When**, **Status**, **Type**, **Languages** and **Preview**. If the list is empty, it says **No requests yet.** **View** opens a window with the prompt that was sent and the reply. **See all** takes you to **History** (3.10).

What to do next: if most texts in a section are missing, open **Manual** to translate a handful, or **Bulk** to translate the whole domain.

### 3.3. Manual

Where: the **Manual** tab.

![Manual filter. The Filter button is under the Search field. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** translates one domain or one module, several dozen texts at a time. Filtering alone saves nothing.

**Filter fields**

| Field | Default | What it does |
|---|---|---|
| **Section** | Back office | Chooses which PrestaShop catalog to read: **Back office**, **Themes**, **Installed modules**, **Emails** or **Others**. Changing the section reloads the page, shows only that section's fields and doesn't call Mistral. |
| **Theme** | — | Visible only for **Themes**. Narrows the list to one theme. Other themes are skipped. |
| **Module** | — | Visible only for **Installed modules**. Narrows the list to one module. A module without domains (a classic module) shows all of its texts at once. |
| **Domain** | — | A group of texts, the same as on **International → Translations**. Pick one and click **Filter**. Hidden for classic modules and for sections that don't use domains. |
| **Source** | en-US or the value from **Settings** | The language you take texts from. Pick a language that already has good translations. |
| **Target** | the first language in the list | The language you want to fill in. It has to exist under **International → Localization → Languages**. |
| **Only empty** | Yes | Shows only texts without a translation. Turn it off to see every text. Saved translations are not deleted. |
| **Search** | empty | Keeps only the source texts that contain the word you type. |

Steps:

1. Set **Section**, **Source** and **Target**.
2. For **Themes**, pick a **Theme**. For **Installed modules**, pick a **Module**.
3. Click **Filter**. The **Domain** list refreshes. Choose a domain and click **Filter** again. For a classic module, skip the domain: **Filter** loads all of the module's texts.
4. Tick the rows you want. Use **Check all**, **Uncheck all** or the checkboxes beside each row.
5. After **Filter**, the list shows the columns **Source**, **Current** and **Status** (**empty** or **filled**). Above the list you'll find **Translate selected (review)** and the **Save now (skip review)** checkbox.
6. Click **Translate selected (review)**. A **Review before save** table appears with the columns checkbox, **Source**, **AI proposal** and **Warnings**. Rows that passed the check are already ticked. Untick any you don't want, and edit a proposal directly in its field if needed. Click **Save approved** to save the ticked rows.
7. Instead of step 6, you can tick **Save now (skip review)** before translating. Then the rows that pass the check are saved immediately, without the review table.

**Messages**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – the list is ready.
- **No strings match this filter. Nothing was sent to Mistral.** – change the filter or turn off **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – pick a domain first.
- **Nothing was translated. Tick at least one row.** – tick some rows.
- **Review is ready. Nothing is saved until you press Save approved.** – the translations are ready, and nothing is saved until you click **Save approved**.
- **Saved. The approved strings were written for the target language.** – after **Save now (skip review)**, the rows that passed were saved.
- **Saved N. Only the ticked rows were written.** – after **Save approved**, the ticked rows were saved.
- **Nothing was saved. Tick OK on the rows you want to keep.** – no rows were ticked in the review table. Tick the rows you want and click **Save approved** again.
- **Not saved because of broken placeholders or HTML: N.** – N rows failed the check and were skipped. Correct them by hand in the table so that variables and HTML tags match the original.
- **Nothing was saved. Turn on Allow publish in Settings.** – turn on **Allow publish / save**.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – the list has changed. Click **Filter** and tick the rows again.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – a classic module with no domains. The full list is loaded.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – the same case, shown before you click **Filter**.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – pick a theme or a module first.

### 3.4. Bulk

Where: the **Bulk** tab.

![Bulk job scope. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Policy, dry run and the Start job and Estimate buttons. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** creates a single job covering several domains and languages. An estimate saves nothing. **Start job** adds the job to the **Jobs** list. Nothing gets saved until the job is processed and **Allow publish / save** is on.

**Fields**

| Field | Default | What it does |
|---|---|---|
| **Section** | Back office | Which catalog the job reads. The same choice as in **Manual**. |
| **Theme** / **Module** | — | Shown only for the matching section, as in **Manual**. |
| **Source** | en-US or the value from **Settings** | The language treated as the original. Every target language is translated from this one. |
| **Targets** | none | One or more languages to fill in. Hold Ctrl (Cmd on a Mac) to select several. A plain click replaces the current selection. |
| **Domains** | none | The domains the job covers. Hold Ctrl or Cmd to select several. If you select none, the job covers every domain in the chosen section. |
| **Policy** | Fill empty | **Fill empty** sends only texts with no translation yet. **Overwrite all** sends every text, including translated ones, and may replace them. **Outdated if equals source** sends only texts whose translation is identical to the original. |
| **Dry-run job** | No | The model does the work and the job appears in **Jobs**, but the replies don't reach the shop. Useful for checking cost and quality. |

**Steps**

1. Choose the section, source language, target languages, domains and policy.
2. Click **Estimate**. Above the form you'll see the estimate: the number of texts, the estimated token count, the cost and a sample of texts.
3. If the estimate looks right, click **Start job**. **Jobs** opens with the new job in it.
4. Process the job in **Jobs** (3.5), or leave it for the cron.

**Messages**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – the estimate result.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – the job was created and is waiting.
- **Nothing was started. Select at least one target language.** – no target language selected.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – pick a theme or a module first.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – no key yet.

### 3.5. Jobs

Where: the **Jobs** tab.

![Job list. An empty list shows No jobs yet. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Job list**

If there are no jobs, the table says **No jobs yet.**

Each row is one run started from **Bulk**. Columns: **#**, **Status**, **Locales** (source language → target languages), **Progress** (done/total), **Cost**, **Employee** and **Date**. Click **Open** to view a job.

Job statuses, exactly as they appear on screen:

- `pending` – waiting, nothing processed yet. It won't start on its own.
- `running` – in progress.
- `paused` – on hold. It won't process anything until you resume it.
- `cancelled` – cancelled. Texts that were still waiting were not translated.
- `completed` – every text processed without errors.
- `completed_with_errors` – finished, but some texts failed.
- `failed` – the job stopped with an error.

**Job screen**

When you open a job, you see the **Job #N** heading, its status, progress (**done/total**), the **failed** and **skipped** counts, the cost, the employee, and a **dry-run** label if it's a test job. The progress bar refreshes itself every 2–3 seconds while the job stays open. The table below shows the job's rows: **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** and **Error**.

Row statuses: `pending`, `processing`, `done`, `failed`, `skipped` (the text matched an exclude or was already translated) and `rolled_back` (reverted).

**Buttons**

- **Process slice** – processes one slice (**Batch size** texts) and then stops. Message: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** When there's nothing left: **The job has no more strings waiting.**
- **Auto-process** – keeps running slices until the job ends or an error occurs. It runs in your browser, so it only works while the tab is open. Closing the tab stops it, but the job remains and you can finish it with another **Process slice** or let the cron handle it.
- **Pause** – puts the job on hold. Message: **Job paused. It will not translate more strings until you resume it.**
- **Resume** – returns the job to the queue. Message: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** The job won't start on its own.
- **Retry failed** – failed texts go back to waiting, and the job returns to the waiting state. Message: **Retried N failed items.**
- **Rollback** – restores the previous translation wherever the module saved a copy before changing it. You'll be asked to confirm **Roll back this job?** When it's done: **Rollback: restored N translations.**
- **Error CSV** – downloads a CSV file of the failed rows. Columns: **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – narrows the table down to the failed rows.
- **Review queue** – opens **Review** (3.6).

The job screen has no cancel button. To stop a job, use **Pause**.

**Automatic pause**

If Mistral rejects calls because of a rate limit, the job pauses itself with the status `paused`. The error field shows **Rate limit — job auto-paused. Resume later.** Wait a while, then click **Resume**. The **Rate limit / min** setting in **Settings** lowers the number of calls per minute.

**Error messages**

- **Nothing was translated.** followed by **No Mistral API key. Nothing was translated.** – there's no key, so the job doesn't run. Paste the key in **Settings**.
- **Allow publish is off in Settings.** – a job that isn't a dry run won't run until you turn on **Allow publish / save**.
- **Monthly API budget has been exhausted.** – the monthly budget has run out. Raise **Budget USD / month** or set it to 0.

### 3.6. Review

Where: the **Review** tab, or the **Review queue** button on a job's screen.

![Review queue. An empty list shows The queue is empty. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Above the table is the heading **Needs-review queue (quality score / flags).** **Review** lists the texts that didn't pass the automatic quality check. It shows up to 100 of the most recent rows.

Columns: **ID**, **Score**, **Domain**, **Source**, **AI** (the proposal), **Flags**, plus the **Approve** and **Reject** buttons. An empty list says **The queue is empty.**

**Reading a row**

- **Score** – a value from 0 to 100. Anything below 70 lands in review.
- **Flags** – the reasons the row was held back:
  - `validation_failed` – the text didn't pass the variable or HTML check.
  - `warning` – a minor note from the check.
  - `length_explosion` – the translation is more than two and a half times longer than the original.
  - `too_short` – the translation is noticeably shorter than a longer original.
  - `possible_untranslated` – English words were left in the translation, such as the, and, with, your or please.
- **Source** – the original text. **AI** – the model's proposal.

**Approve** and **Reject** change only the row's status. Message: **Review updated.** The row disappears from the list. These actions don't push text to the shop or touch the rest of the domain.

If the job was already saving results, the proposal may have reached the shop. To undo a job's changes, use **Rollback** on that job's screen in **Jobs**.

### 3.7. Catalog

Where: the **Catalog** tab.

![Catalog batch. The Translate batch (max 100) button is under the Start after ID field. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** translates product, category and CMS page fields stored in your shop's languages. It doesn't cover **International → Translations**. A single click handles at most 100 records. Results are saved straight into the chosen target language.

**Fields**

| Field | Default | What it does |
|---|---|---|
| **Entity** | product | What you're translating: **product**, **category** or **cms**. Changing it reloads the page and shows only the fields for that type. The change alone translates nothing. |
| **Fields** | every field in the list | Which texts the batch sends. Tick only the ones you want changed. Unticked fields aren't sent and stay as they are. For a product: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. For a category: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. For CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | the first language in the list | The language the texts are taken from. |
| **Target language** | the first language in the list | The language the translation goes into. It must differ from the source. |
| **Only empty** | Yes | Skips fields that already have text in the target language. Turn it off only if you want to replace existing text. |
| **Start after ID** | 0 | Skips records whose ID is less than or equal to the value entered. After a batch, the field moves to the last ID processed. Click the button again to continue. |

Button: **Translate batch (max 100)**.

**Steps**

1. Choose **Entity** and tick the fields.
2. Choose **Source language** and **Target language**.
3. Leave **Only empty** on.
4. Click **Translate batch (max 100)**. The result looks like: **Catalog finished: saved N, failed M.**
5. Open one product in the target language and check the result. Only then turn off **Only empty** or move on to the next batch.

**Messages**

- **Nothing was translated. Select at least one field.** – tick some fields.
- **Nothing was translated. Source and target language must be different.** – pick two different languages.
- **Nothing was saved. Turn on Allow publish in Settings.** – turn on **Allow publish / save**.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – no key yet.

### 3.8. Glossary

Where: the **Glossary** tab.

![Adding a term. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![CSV import and export and an empty term list. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

The glossary is a list of words and phrases that the model must either keep as they are or always translate the same way. Adding a row won't change translations that already exist, but the next translation will follow the list.

**Adding one term**

| Field | Default | What it does |
|---|---|---|
| **Source term** | empty, required | A word or phrase in the source language. Type it exactly as it appears, using capitals where they matter. |
| **Target locale** | empty | Limits the entry to one language, for example pl-PL. Leave it empty if the entry applies to every target language. |
| **Target term** | empty | The approved translation of the term. It can only be empty when **Do not translate** is on. |
| **Do not translate** | No | On: the model keeps the term unchanged, for example a brand name, a SKU or a tag. Off: the model uses **Target term**. |

Button: **Add**. Messages: **Glossary term added. Translations already stored were not changed.** or **Nothing was added. Type a source term.**

**Table**

Columns: **Source**, **Locale**, **Target**, **Do not translate** (Yes or No) and a **Delete** button on each row. It removes only that row. Message: **Glossary term deleted.** Empty list: **No glossary terms yet.**

**CSV import and export**

- **CSV file** – choose a file and click **Import CSV**. Message: **Imported N rows.**
- File format: the first row is a header: `source_term`, `target_locale`, `target_term`, `do_not_translate`. The header is always skipped. Rows with fewer than three columns are skipped too. In the fourth column, an empty value or 0 means **No**; any other value means **Yes**.
- Import adds rows from the file. It doesn't check whether a term already exists, so importing the same file twice creates duplicates.
- **Export CSV** downloads the current list as `glossary.csv`. It doesn't need an input file and changes nothing.

Tip: keep terms short and precise. A very general term will be enforced every time it shows up.

### 3.9. Excludes

Where: the **Excludes** tab.

![Exclude patterns. An empty list shows No patterns yet. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

An exclude is a pattern for source text that the module never sends to Mistral. That text stays in the shop exactly as it is. Excludes apply to every way of working: **Manual**, **Bulk**, **Catalog** and the translation pages.

**Adding a pattern**

| Field | Default | What it does |
|---|---|---|
| **Pattern** | empty, required | A text or expression compared against every source text. How it's compared depends on **Type**. |
| **Type** | exact | **exact** – the whole text must match. **prefix** – the text starts with the pattern. **contains** – the pattern appears anywhere in the text. **regex** – a PHP regular expression. |

Button: **Add**. Message: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** If the field is empty: **Nothing was added. Type a pattern.**

A **regex** pattern is applied exactly as you typed it. A broken expression matches nothing. Start with a short pattern and check what it skipped.

**Table**

Columns: **Pattern**, **Type**, **On** and **Delete**. The **On** column shows 1 for an active pattern. There's no toggle on this screen, so to switch a pattern off, delete it and add it again. **Delete** removes only that pattern; existing translations stay. Message: **Pattern deleted.** Empty list: **No patterns yet.**

Use excludes for text that should stay in the source language, such as a legal name or a technical tag. For text that should always be translated the same way, use **Glossary**.

### 3.10. History

Where: the **History** tab, or the **See all** button on the **Dashboard**.

![History list. An empty list shows No requests yet. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** is the complete list of logged Mistral calls: manual translations, translation pages, **Bulk** jobs, **Catalog** runs and connection tests. Each entry holds the text that was sent, the reply, the model, the languages, the token count and the call time. Cards, charts and filters live on the **Dashboard**, not on this page. Opening this page sends no requests and changes no translations. The note under the **Model** field in **Settings** refers to **Logs**. Those entries are shown right here; there's no separate Logs tab.

**List columns:** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** and **Prompt**. Types: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** and **Not sent** (the call never went out, for example because of the local rate limit or the budget). Entries from a **Bulk job** show the job number.

- **View** opens a window with the prompt that was sent and the reply. For an error, the error message appears instead of a reply.
- An entry with an access error means the key in **Settings** is wrong, or the account isn't allowed to use the chosen model.
- **Previous**, **Next** and the **Page** field move you through the list.
- **Clear history** deletes these entries. You'll be asked to confirm with **Clear the stored history? Saved translations stay.** Afterwards you'll see **History cleared. Saved translations were not changed.**

If translations suddenly stop, open the newest error entry on this page before you change the glossary.

### 3.11. Updates

Where: the **Updates** tab on the right side of the menu.

![Update check. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

The panel is called **MyPresta Updates**.

- **Manual Check** – the **Check Now** button checks for a new version right away.
- **Automatic Notifications** – **Enabled** or **Disabled**. When enabled, the module checks the MyPresta server for a newer version and shows a warning in the back office.
- **Product Page** – a link to the module's page.
- **Save** – saves your **Automatic Notifications** choice.

Messages: **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Buttons on the International → Translations page

Where: **International** → **Translations**. Choose a translation type and a language, then click **Modify**. The buttons next to the fields show up when **Individual field buttons — International → Translations** is on in **Settings**. The checkboxes and the bar show up when **Individual field checkboxes — International → Translations** is on.

![The Mistral translations bar at the bottom of the International → Translations page. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**What you'll see**

- A translate button next to every text field.
- A checkbox next to every field (when checkboxes are enabled).
- A bar labeled **Mistral translations** with the **Source** field (en-US by default, or the value from **Settings**), the **Target** list, the buttons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** and **Translate selected**, plus the hint **Fills the fields. Save with the PrestaShop button.**

**Steps**

1. Choose a **Target**.
2. Tick the fields you want to fill, or click **Check empty**.
3. Click **Translate selected**, or **Translate empty**, which fills every empty field in the section.
4. Wait until the bar shows **Done (N)**. While it runs, you'll see **Translating… N/M**.
5. Check the filled fields, then save the page with PrestaShop's **Save** button.

The buttons only fill in fields. Without **Save** in PrestaShop, the text never reaches the shop. With **Allow publish / save** off, fields still get filled in, and PrestaShop does the saving.

**Messages**

- **Target is not a language from this shop.** – the chosen language doesn't exist in this shop.
- **Fill the source language field first.** – complete the source language field first.
- **The source language field is not on this page.** – this page has no source language field.
- **The source language mail file was not found.** – the source email file couldn't be found. Choose a different **Source locale** in **Settings** that has email files.

In the **Emails** section, the source text comes from the source file of the email template, not from a field on the page.

### 3.13. Buttons in product, category and CMS forms

Where: a product, category or CMS page form, or any other shop form with multilingual fields. The buttons appear when **Individual field buttons — shop forms** and **Individual field checkboxes — shop forms** are on in **Settings**.

![The bar at the bottom of the product form and a checkbox next to a multilingual field. The screen is in English.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**What you'll see**

- A translate button next to every multilingual field.
- A checkbox next to each field, for adding it to the bar.
- A bar at the bottom of the product page labeled **Mistral translations**, with the language selector **Translate from … to …**, the buttons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** and **Translate selected**, and the hint **Fills the fields. Save with the PrestaShop button.**

**Steps**

1. Fill in the field in the source language. Without it, the bar shows **Fill the source language field first.**
2. Choose the target language on the bar.
3. Click the button next to a single field, or tick several fields and click **Translate selected**. **Translate empty** fills the empty fields.
4. When it's done, click **Save** in the PrestaShop form. Without that, the text isn't saved.

The button only fills in the form field. The product, category or CMS **Save** button is what actually saves it. Fields you don't tick stay unchanged.

## 4. Storefront

The module adds nothing to the shop pages customers see. Customers have no screen or button related to the module, so there's nothing to check in the theme.

The only address outside the back office is the cron address. It's meant for a scheduled task on your server, not for customers.

- **Where to copy the address:** **Settings** → **CRON URL**, or **Dashboard** → the **CRON** row.
- **What to do:** paste the address into your server's task scheduler, for example to run every few minutes. Each call processes one slice of a waiting job.
- **The address uses HTTPS.** If your shop has SSL enabled, use the address that starts with `https://`.

| What you see after opening the address | What to do |
|---|---|
| The message **Forbidden** | The address is incomplete or has changed. Copy it again from **Settings**. |
| The message **No pending jobs** | No jobs are waiting or running. Create one in **Bulk**, or resume a paused job in **Jobs**. |
| JSON data with the slice result (fields `ok`, `finished`, `counts`) | A slice of the job was processed. Check the progress in **Jobs**. |

The cron only handles jobs with the status `pending` or `running`. A `paused` job has to be resumed by hand.

## 5. Troubleshooting

| Symptom (what you see) | Cause | What to do |
|---|---|---|
| **No Mistral API key.** on every module page | The key wasn't saved. | Open **Settings**, paste the key into **Mistral API key** and click **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Settings were saved without a key. | Paste the key into **Mistral API key** and click **Save**. |
| **Connection was not made. Nothing was translated.** after **Test connection** | Wrong key, no connection to the server, or the model isn't available on your account. | Check the key, pick a different **Model**, or add a correct ID under **Add a Mistral model**. Details are in **History**. |
| Calls fail with an access error in **History** | The key is wrong, or the account isn't allowed to use the chosen model. | Correct the key or pick a model your account can use. |
| **Nothing was started. There is no Mistral API key.** in **Bulk** | No key yet. | Paste the key in **Settings**, then run **Estimate** and **Start job** again. |
| A job sits in `pending` and nothing happens | Jobs don't start on their own. | Click **Process slice** or **Auto-process** in **Jobs**, or set up the cron (section 4). |
| A job is `paused` with **Rate limit — job auto-paused. Resume later.** | Mistral rejected calls because of a rate limit. | Wait a few minutes and click **Resume**. Lower **Batch size** or **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** was reached. | Raise the amount or set it to 0. The count starts over each month. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** is off. | Turn on **Allow publish / save** in **Settings**. |
| **Not saved because of broken placeholders or HTML: N.** in **Manual** | The translation changed variables or HTML tags. | Fix the row by hand in the review table so the variables and tags match the original, then save. |
| A job ends as `completed_with_errors` | Some texts failed. | Open the job, tick **Failed only**, download the **Error CSV** and then click **Retry failed**. |
| Rows in **Review** have a low **Score** | The quality check didn't pass them. | Compare **Source** and **AI**. Click **Approve** if the translation is fine, or **Reject** if it isn't. If a bad translation was already saved, use **Rollback** on the job. |
| The translation is saved, but the shop still shows the old text | Saving clears the PrestaShop cache, but the theme or your browser may still show the old page. | Go to **Advanced Parameters** → **Performance**, clear the cache and refresh the shop page. |
| An **Exclude pattern** doesn't skip the text | The **Type** is wrong, or the **regex** is invalid. | In **Excludes**, change the type, or delete the pattern and add a shorter one. |
| A new glossary term doesn't show up in saved translations | Glossary entries apply to new translations only. Saved texts aren't changed. | Re-run these texts in **Bulk** with the **Overwrite all** policy, after checking the **Estimate**. |
| **The source language mail file was not found.** | The chosen source language has no email file. | In **Settings**, or on the translation page, pick a different **Source locale** that has email files. |
| **No strings match this filter. Nothing was sent to Mistral.** | The filter matches no texts. | Turn off **Only empty**, clear **Search**, or pick another domain. |
| **Nothing was translated. Tick at least one row.** | No rows are ticked. | Tick some rows and click **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** in **Catalog** | The source and target languages are the same. | Choose a different **Target language**. |
| The Dashboard shows an empty summary | The shop has no catalog for the chosen language yet. | Create the catalog under **International → Translations**, then return to the **Dashboard**. |
| **History** contains **Not sent** entries | The local rate limit or the budget blocked the call. | Check **Rate limit / min** and **Budget USD / month** in **Settings**. |

## 6. For developers

### 6.1. Overview

- **Main class:** `myaitranslationsmistral`, file `myaitranslationsmistral.php`.
- **Version:** 1.2.0.
- **Technical name:** `myaitranslationsmistral`. It appears in the module list as **AI Translations with Mistral**.
- **Author:** MyPresta.eu. The module's tab in Module Manager: `administration`.
- **Back office tab:** `AdminMyaitranslationsmistral`, parent `AdminInternational` (fallback `IMPROVE`).
- **Install:** `parent::install()`, tables from `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), default values through `installDefaults()` (only missing keys are set), registration of the `displayBackOfficeHeader` and `actionAdminControllerSetMedia` hooks, and creation of the tab.
- **Uninstall:** removes the tab, runs `sql/uninstall.php` (drops 11 tables), removes the `MYAITMI_*` keys via `removeConfiguration()`, then calls `parent::uninstall()`.
- The module has **no** `enable()` or `disable()` methods.
- **Configuration:** `getContent()` redirects to `AdminMyaitranslationsmistral` (the `dashboard` tab by default).

**Data flow**

1. The forms built by `MyaitmiForms` (the `settings` tab) post their values to `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` stores the `MYAITMI_*` keys in `Configuration`. `MyaitmiApiKeyEncryptor` encrypts the API key (AES-256-CBC, key derived from `_COOKIE_KEY_`) and stores it under `MYAITMI_API_KEY_ENC`.
3. Translation: `MyaitmiTranslateService::translateMessages()` builds the prompts (`MyaitmiPromptBuilder`), sends them through `MyaitmiMistralTranslationProvider` (cURL, POST to `https://api.mistral.ai/v1/chat/completions`), checks the reply (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), scores it (`MyaitmiQualityScorer`) and saves it through `MyaitmiTranslationAdapter`.
4. Saving: through the `prestashop.service.translation` service. If that service is missing, the module writes straight to the `_DB_PREFIX_translation` table. Keys belonging to classic modules (format `<{name}prestashop>…`) go into that module's `translations/{iso}.php` file (`MyaitmiLegacyModuleCatalogue`).
5. Bulk: `MyaitmiBulkJobFactory` creates the job and its rows in `myaitmi_job` and `myaitmi_job_item`. `MyaitmiJobWorker::processSlice()` processes one slice (size from `BATCH_SIZE`). It's triggered by the **Process slice** button (a request from the **Jobs** tab), by the **Auto-process** loop in the browser (AJAX `ProcessJob`), or by the cron (`controllers/front/cron.php`).
6. Catalog: `MyaitmiCatalogTranslateService` selects records (`collect()`, max 100) and saves them directly to `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` or `_DB_PREFIX_cms_lang`.
7. Every call is logged in `myaitmi_request` (the **History** tab), and errors go to `myaitmi_api_log`. Costs are written to `myaitmi_usage_ledger`. Before a job changes a text, `MyaitmiSnapshotService` copies the old value to `myaitmi_snapshot`, which makes **Rollback** possible.

### 6.2. Files

| File | Purpose |
|---|---|
| `myaitranslationsmistral.php` | Main class: install, uninstall, menu tab, hooks, asset loading, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Update checking (the **Updates** tab and the back-office warning). |
| `logo.png`, `logo.gif` | Logo in the tab header and the module menu. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | The whole back office: tabs, saving, job actions, glossary, excludes, catalog, CSV, AJAX responses. |
| `controllers/front/cron.php` | The cron address: processes one slice of a job and returns JSON. |
| `sql/install.php`, `sql/uninstall.php` | Create and drop the tables. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Interface for reading and writing PrestaShop translations. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Shared adapter logic: lists of sections, domains and languages, saving through the service or the `translation` table, cache clearing. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | The concrete adapter (created by the factory). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Creates the adapter. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Reads XLF catalogs from themes and modules (domains). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Classic modules: reads and writes `translations/{iso}.php`, clears OPcache after a save. |
| `src/Admin/MyaitmiForms.php` | Builds every back-office form and the field descriptions (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Texts for the **Help** panel on each tab. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Call history, cards, charts, filters, clearing, retention. |
| `src/Audit/MyaitmiApiLogRepository.php` | API error and warning log, retention. |
| `src/Audit/MyaitmiTranslationMemory.php` | Translation memory (cache): reuses a result for the same text, language, model and glossary. |
| `src/Audit/MyaitmiUsageLedger.php` | Cost based on the price table in the code, monthly budget. |
| `src/Audit/MyaitmiSnapshotService.php` | Copies made before saving, and job rollback. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glossary: listing, saving, deleting. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Excludes: adding, deleting, matching. |
| `src/Job/MyaitmiJobStatuses.php` | Constants for job and row statuses. |
| `src/Job/MyaitmiJobRepository.php` | Jobs and rows: reading, status changes, fetching slices, recounting totals. |
| `src/Job/MyaitmiJobWorker.php` | Slice processing, retrying errors, finishing jobs, review queue, email on completion. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Translation provider interface. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Mistral calls (cURL), connection test, saving call history. |
| `src/Provider/MyaitmiPromptBuilder.php` | Builds the system and user prompts (tone, brand voice, glossary). |
| `src/Provider/MyaitmiProviderFactory.php` | Creates the provider. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Checks variables and tags in the text. |
| `src/Quality/MyaitmiHtmlValidator.php` | Checks HTML validity. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Pre-save check in the **Manual** section. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Protects the HTML of email templates before sending and restores it after the reply. |
| `src/Quality/MyaitmiQualityScorer.php` | Score 0–100, flags, review decision. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Encrypts and decrypts the API key. |
| `src/Service/MyaitmiConfigService.php` | Reads and saves settings, models, cron token, range validation. |
| `src/Service/MyaitmiRateLimiter.php` | Local per-minute call limit (file `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Main translation pipeline: excludes, memory, calls, validation, scoring, saving, estimates. |
| `src/Service/MyaitmiBulkJobFactory.php` | Builds the **Bulk** job and the estimate. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Collects and saves **Catalog** records. |
| `src/Service/MyaitmiDashboardService.php` | Missing-text summary on the **Dashboard**. |
| `translations/*.php` | Interface translations (one file per language). |
| `views/templates/admin/configure.tpl` | Template for the whole back-office page and the **Help** panel. |
| `views/templates/admin/_partials/*.tpl` | Tabs: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Back-office styles. |
| `views/js/admin.js` | The **Jobs** tab (progress, **Auto-process**), row selection, AJAX responses. |
| `views/js/admin-help.js` | The **Help** panel. |
| `views/js/translations-tool.js` | Buttons and bar on **International → Translations**. |
| `views/js/entity-fields.js` | Buttons and bar on product, category and CMS forms. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Charts on the **Dashboard**. |
| `var/rate_limit.json` | Counter for the local call limit in the current minute. |
| `index.php` (in every directory) | Blocks directory browsing. |

### 6.3. Controllers

**Back office: `AdminMyaitranslationsmistralController`** (class `ModuleAdminController`, tab under `AdminInternational`).

- URL: `index.php?controller=AdminMyaitranslationsmistral&token=…`, optionally `&myaitmi_tab=…`.
- Allowed `myaitmi_tab` values: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Any other value falls back to `dashboard`.
- Input parameters (GET/POST):
  - Settings: the `MYAITMI_*` form fields, `new_mistral_model`, `delete_mistral_model`, and the buttons `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filters and translation: `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk: `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Jobs: `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Review: `review_action` (`approve`, `reject`) and `id_review`.
  - Catalog: `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glossary and excludes: `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (file), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - History and cards: `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Returns either an HTML page (`configure.tpl`) or a file: `glossary.csv` (glossary export) or `job-{id}-errors.csv` (job errors).
- Success and error messages are passed in the `flash` and `flash_kind` parameters (`info`, `success`, `warning`, `danger`).

**Back-office AJAX actions** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`):

| `action` | Parameters | Returns |
|---|---|---|
| `ProcessJob` | `id_job` | Slice result: `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` and the `job` object. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → text), `error`. Doesn't save. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | The source email file. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | The `domains` list. |
| `HistoryDetail` | `hist_id` | Call details. |

**Front: `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- URL: `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, optionally `&id_job=N`.
- `token` is required and checked against `MYAITMI_CRON_TOKEN` with `hash_equals()`. A wrong token returns HTTP 403 and the JSON `{"ok":false,"error":"Forbidden"}`.
- With `id_job`: processes one slice of that job.
- Without `id_job`: picks the first job with status `pending` or `running` among the 20 most recent. If there isn't one, it returns `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hooks

Registered during installation:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: swaps the technical tab name for its label (`renameTabIfTechnical()`) and loads the back-office assets (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: loads assets (`loadBoAssets()`).

Assets loaded by `loadBoAssets()`:

- On the module tab: `admin.css`, `admin.js` and `admin-help.js`. On the **Dashboard** tab, also `chart.min.js` and `history-charts.js`. `Media::addJsDef` passes `aitHelpLabels`.
- On **International → Translations** (`AdminTranslations` or `/international/translations`), when that page's buttons are enabled: `admin.css` and `translations-tool.js`.
- On other back-office pages (product, category and CMS forms), when the form buttons are enabled: `admin.css` and `entity-fields.js`.
- Data for JS: `Media::addJsDef(['myaitmiTr' => …])` with the language list, locales, button flags and labels (`translationClientConfig()`).

The module doesn't expose hooks of its own (there's no `Hook::exec`).

### 6.5. Overrides

The module doesn't override any PrestaShop class or controller. There's no `override` directory.

### 6.6. Database

Tables are created in `sql/install.php` (`_DB_PREFIX_` is the shop's table prefix, `ps_` by default). All of them use the `_MYSQL_ENGINE_` engine and `utf8mb4_unicode_ci`.

| Table | Contents |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Key `idx_shop_locale` (`id_shop`, `target_locale`). Read condition: `id_shop` IN (0, shop). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (always 1 on insert), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (unique), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Key `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Key `idx_job_status`. One slice covers one target language. |
| `myaitmi_memory` | Translation memory: `memory_hash` (unique), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. The monthly total is what counts against the budget. |
| `myaitmi_snapshot` | Copy made before a save: `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Log of errors and warnings: `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Retention follows `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | Review queue: `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Created on install and dropped on uninstall. The module code never writes to it; **Catalog** writes directly to the shop's language tables. |
| `myaitmi_request` | Call history: `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. `ensure()` also creates this table on the first save or when **History** is opened, if it's missing. |

Uninstalling drops all 11 tables in the list above. PrestaShop's translation table (`_DB_PREFIX_translation`) and the language tables for products, categories and CMS pages are left alone.

### 6.7. Configuration keys and translations

**`Configuration` keys** (prefix `MYAITMI_`), with default values from `installDefaults()`:

| Key | Default | Notes |
|---|---|---|
| `API_KEY_ENC` | `''` | Encrypted API key. Read through `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Active model. |
| `EXTRA_MODELS` | `''` | Model IDs added by hand, one per line. |
| `PROVIDER` | `mistral` | Always `mistral` once the form is saved. |
| `TONE` | `formal` | `formal`, `casual` or `brand`. |
| `CUSTOM_VOICE` | `''` | The **Brand voice** text. |
| `BATCH_SIZE` | `25` | Range 1–100. |
| `MONTHLY_BUDGET` | `0` | USD; 0 = no cap. |
| `SOURCE_LOCALE` | `''` | Empty = the language comes from the screen. |
| `TEMPERATURE` | `0.2` | Range 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Range 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 disables the local limit. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Sends an email when a job finishes (template `contact`). |
| `NOTIFY_EMAIL` | `''` | Recipient address. If empty, `PS_SHOP_EMAIL` is used. |
| `PERM_ALLOW_PUBLISH` | `1` | Saving to the shop. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Buttons and bar in shop forms. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Buttons and bar on the translation page. |
| `MAX_TOKENS` | `0` | 0 = the provider's default limit. |
| `CRON_TOKEN` | random 32-character hex | Token for the cron address. Also generated on first read if it's missing. |

Keys removed when the form is saved or on uninstall: `DEEPL_API_KEY` and `CLAUDE_API_KEY` (leftovers from earlier versions). The update-check keys (`mypresta_updates`, `update_{name}`, `updatev_{name}`) are not deleted.

**Interface translations.** Each language lives in `translations/{iso}.php` (for example `pl.php`, `de.php`, `fr.php`). `en.php` is the source for all strings. Strings pass through `$this->l()` or through the `myaitmiforms` and `sectionhelp` domains (field descriptions and the **Help** panel). Template strings use `{l s='…' mod='myaitranslationsmistral'}`. Strings passed to JS (`labels` in `translationClientConfig()` and `aitHelpLabels`) also pass through `$this->l()`.

To add a language: copy `translations/en.php` to `translations/{iso}.php`, translate the values and keep the key identifiers unchanged.

### 6.8. Extending

- **Shop theme:** the module renders nothing in the theme, so there's no template to override.
- **Translation provider:** a new provider needs a class implementing `MyaitmiTranslationProviderInterface`, plus a change in `MyaitmiProviderFactory`. Right now the factory returns only Mistral.
- **Catalog adapter:** the interface `MyaitmiTranslationAdapterInterface` and the factory `MyaitmiTranslationAdapterFactory`.
- **Price list:** per-million-token rates live in `MyaitmiUsageLedger::estimateCost()`. When Mistral changes its prices, update them in the code.
- **Local limit:** `var/rate_limit.json` is created in the module directory.

## 7. Support

Module page: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

If you need help with the module:

1. Log in to your customer account at mypresta.eu.
2. Go to the contact page and choose the topic **Support for paid modules**. The form notes that paid modules require you to be logged in.
3. Once logged in, select this module from your purchase history.
