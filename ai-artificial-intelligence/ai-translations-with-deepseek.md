---
title: "AI Translations with DeepSeek – documentation and user manual"
sidebar:
  label: "AI Translations with DeepSeek – documentation and user manual"
description: "Configuration and troubleshooting guide for the AI Translations with DeepSeek module, for store owners who already have the module."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy AI Translations with DeepSeek Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Requirements

The module runs in PrestaShop 1.7.0.0 or later and needs an API key from your own DeepSeek account.

- **PrestaShop:** version 1.7.0.0 or later.
- **PHP:** the module does not declare its own minimum PHP version. The server must run the PHP version required by your PrestaShop version.
- **PHP extensions:** cURL (connection to DeepSeek), mbstring (counting characters in texts), OpenSSL (encryption of the API key) and JSON (saving sent and received data).
- **Other modules:** the module does not require any other module.
- **Outside the shop:** your own DeepSeek account with an API key. Without a key the module cannot translate anything.
- **Cron on the server:** needed only if bulk jobs should run without clicking. See section 3.1.
- **Large catalogue:** a bulk job is split into slices, and each slice is one call to DeepSeek. Large ranges take a long time, so check them with **Estimate** before you start.

## 2. Installation

1. Upload the module ZIP file in **Module Manager** with the **Upload a module** button and click **Install**.
2. After installation, a new entry appears in the menu: **International → AI Translations with DeepSeek**. This entry opens the module panel.
3. Installation does not clear the shop cache. If the new menu entry does not show up, go to **Advanced Parameters → Performance** and click **Clear cache**.

After installation the panel is empty: there is no API key, and the settings have the starting values described in section 3.1.

**Uninstalling** removes the menu entry, bulk jobs with their history, the glossary, the exclude list, the translation memory, the backup copies used by **Rollback**, the call and error history, the review queue, the list shown on the **Catalog** tab and all settings, including the API key and the cron address.

Uninstalling **does not remove** translations already saved in the shop: product, category, CMS page and International → Translations texts stay as they are. After uninstalling you can no longer undo these translations with **Rollback**, because the backup copies are removed with the module.

Reinstalling **does not restore** removed data. The tables are created empty and the settings return to their starting values. The cron address also changes, so copy the new address from **Settings** and update the scheduler on the server.

## 3. Configuration and back-office work

The panel screens are in English. In this manual, field, tab and button names are given exactly as you see them on screen.

**Who starts the work:** always a member of staff in the back office. Customers do not start translations.

**The process from start to finish:**

1. In **Settings**, paste your DeepSeek key, select a model and click **Save**. Then click **Test connection** to check the key.
2. Set **Source locale** (the language of the original text) and check that **Allow publish / save** is on.
3. Choose what to translate. Single domains and strings are translated on **Manual**. Large ranges are sent through **Bulk**. Product, category and CMS page fields are translated on **Catalog**. The buttons next to fields in shop forms and on the International → Translations page work where you are working.
4. On **Manual** and next to fields you first get a proposed translation. You save it in a separate step: with the **Save approved** button on **Manual**, by ticking **Save now (skip review)**, or with the PrestaShop **Save** button on the form.
5. On **Bulk** click **Estimate**. Nothing is sent or saved. If the estimate looks right, click **Start job**. The job goes to **Jobs** and waits. It does not run by itself: click **Process slice** or **Auto-process**, or let a cron call on the server process the slices.
6. Translations that failed the quality check go to **Review**. The **Approve** button only changes the row status. It does not write the text to the shop.
7. **Glossary** and **Excludes** affect the next translations. Translations that are already saved do not change.
8. **Dashboard** shows gaps and costs, and **History** shows every call to DeepSeek.

**How the work ends:** a bulk job ends with the status **completed** (everything translated) or **completed_with_errors** (there were errors). If notification is on, an e-mail is then sent. A manual translation ends when the selected rows are saved to the shop.

### 3.1 Settings (module settings)

Path: **Modules** → **Module Manager** → the module name → **Configure**. The **Configure** button opens the module panel, and the **Settings** tab is in the bar at the top.

![Settings tab](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

More parts of the same form:

![Settings – button and source locale switches](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – limits, budget and temperature](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – e-mail, saving and cron address with Test connection and Save buttons](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Saving the form with **Save** does not change finished translations. When the **DeepSeek API key** field is empty and no key was saved before, the message appears: “Settings saved. No API key is stored, so nothing can be translated until you paste one.”

| Field | Starting value | What it does |
|---|---|---|
| **DeepSeek API key** | empty | The key from your DeepSeek account. An empty field keeps the key already saved, and a new value replaces it. An empty field does not delete the key. Below the field the saved key is shown masked. Requests go to api.deepseek.com. |
| **Model** | deepseek-flash | The DeepSeek model that writes the translation. The built-in models are: deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat and deepseek-reasoner. A model the account cannot use fails with an error that is saved in **History**. |
| **Add a DeepSeek model** | empty | Adds a model identifier that is not on the list. Type it exactly as in your DeepSeek account and click **Add model**. The added model becomes the active model at once. **Remove** deletes only models added here. Built-in models cannot be removed. |
| **Tone** | Formal | A style added to every instruction for the model. **Formal** is for shop and back-office wording, **Casual** is lighter, and **Brand** works together with the **Brand voice** field. New translations follow the style. Saved translations do not change until you translate them again. |
| **Brand voice** | empty | A few sentences describing how the shop should sound. The field appears when **Tone** is set to **Brand**. The text is added to the next instruction and does not rewrite saved translations. |
| **Source locale** | empty (—) | The language treated as the original, for example English (en-US). The dash “—” means the screen you are translating provides the source language itself. Manual and bulk translations and the buttons on International → Translations send this language as the source. The default language of the shop does not change. |
| **Individual field buttons — shop forms** | Yes | A button next to each multilingual field in shop forms: product, category, CMS and other forms. The button translates only that one field. **No** hides these buttons across the whole shop. It does not affect International → Translations. |
| **Individual field checkboxes — shop forms** | Yes | A checkbox next to shop form fields and a bar at the bottom that translates the ticked fields. **No** hides the checkboxes and the bar. The buttons in the row above have their own switch. |
| **Individual field buttons — International → Translations** | Yes | A button next to each field on International → Translations. **No** hides these buttons on that page only. Shop forms are not changed. |
| **Individual field checkboxes — International → Translations** | Yes | Checkboxes and a bar on International → Translations. The bar translates the ticked fields one by one. **No** hides the checkboxes and the bar on that page. |
| **Batch size** | 25 | How many strings go into one call to DeepSeek. Allowed values are 1 to 100. For a first run choose 10 to 25. A larger batch finishes a job in fewer calls, but after an error a larger part is repeated. |
| **Dry-run sample** | 10 | How many example strings **Estimate** shows before a bulk job. Allowed values are 1 to 50. **Estimate** does not save translations. |
| **Max tokens (0 = default)** | 0 | A limit on the length of one reply. 0 means the DeepSeek default limit. Set a number if replies are cut off or too long. The limit applies only to later calls. |
| **Budget USD / month** | 0 | A monthly limit in US dollars, counted from the saved usage. 0 means no limit. When the limit is reached, new translations stop, and translations already saved stay. |
| **Rate limit / min** | 60 | How many calls the shop may make in one minute. 0 turns this local limit off. Calls above the limit are skipped and recorded in **History**. DeepSeek may apply its own limit too. |
| **Log retention days** | 30 | How many days of entries are kept in **History**. The minimum is 1 day. Older entries are deleted. Jobs, the glossary and saved translations are not deleted. |
| **Temperature** | 0.2 | How freely the model rephrases the text. A value around 0.2 stays close to the original, and values closer to 1 change the sentences more. Allowed range is 0 to 1. Placeholders and HTML are still checked after each translation. |
| **Email notify on complete** | No | Sends one e-mail when a bulk job finishes. The job itself works the same way; only the sending changes. |
| **Notify email** | empty | The address that receives the e-mail about a finished job. The field works only when **Email notify on complete** is on. An empty field sends the e-mail to the shop address from the company settings. Saving the address does not send a message. The subject and body are in English, for example “myaitranslationsdeepseek job #41 completed”, and the body contains the numbers of done, failed and skipped strings. |
| **Allow publish / save** | Yes | Whether the module may save translations to the shop. With **No**, saving is blocked on **Manual**, in bulk jobs and on **Catalog**. The buttons on International → Translations only fill the form, and the PrestaShop **Save** button saves it. |
| **CRON URL** | generated address | An address for the server scheduler. Each call processes one slice of one waiting job and ends. Do not publish this address, because anyone who knows it can start a slice. Opening **Settings** does not start a job. |

Buttons at the bottom of the form: **Save** saves the settings. **Test connection** checks the key and does not save any translation.

Recommended start: paste the key, select a model, set **Source locale**, click **Save**, then **Test connection**. Leave the other numbers at their starting values until a job does not behave as you expect.

### 3.2 Dashboard

The Dashboard shows how many texts are missing in each part of the catalogue for the chosen language, and the DeepSeek usage. Opening **Dashboard** sends no request and does not change translations.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** is the language whose gaps are counted. The first time, the first language in the shop list is selected. Change the language and click **Show** to recalculate the table.
- **Coverage table** has the columns **Section**, **Done**, **Missing** and **Total**. Each row is one part of the catalogue: back office, themes, modules, e-mails or others. The bar shows how much is already translated.
- **Cards and charts** count the calls from the chosen period. The filter fields are dates (presets and **From** and **To**), then **Model**, type, status, language, employee, and a word in the prompt or the reply. The **Filter** button applies the filter. The cards show the number of calls, tokens sent and received, average time and estimated cost. The cost is a local estimate, not an invoice.
- **Latest prompts** lists the ten newest calls. **View** opens the prompt and the reply in a window. **See all** takes you to **History**.
- Below the table is the cron address. It is the same secret as in **Settings**.

![Dashboard – charts and summaries](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

An empty coverage table means the shop has no catalogue for that language yet. The catalogue is created on International → Translations.

### 3.3 Manual

**Manual** translates a chosen domain, a few strings at a time. **Filter** only loads the list and saves nothing.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Section** | Back office | Chooses the PrestaShop catalogue to read: **Back office**, **Themes**, **Installed modules**, **Emails** or **Others**. Changing the section reloads the form and does not call DeepSeek. |
| **Theme** | — | Appears only for **Themes**. Limits the list to one theme. |
| **Module** | — | Appears only for **Installed modules**. Limits the list to one module. A module without domains loads all its strings at once. |
| **Source** | Source locale from **Settings** (en-US) | The language the texts are taken from. Choose the one that already has a trusted translation. The target language does not change. |
| **Target** | first shop language in the list | The language you want to fill. It must exist in International → Localization → Languages. The list and the later save apply only to this language. |
| **Domain** | — | The translation domain, the same groups as on International → Translations. Press **Filter** so the list fills, choose a domain and press **Filter** again. It does not appear for a module without domains. |
| **Only empty** | Yes | Hides strings that already have a translation. **No** shows all strings. The table changes; saved translations are not deleted. |
| **Search** | empty | Keeps only strings whose source contains the typed word. The catalogue does not change. |

**How to translate:**

1. Tick the rows, or click **Check all** (ticks the visible rows). **Uncheck all** clears the ticks.
2. Click **Translate selected (review)**. The module sends the ticked strings and shows a review table. Nothing is saved yet.
3. In the review table, untick a row you do not want to save, and correct the proposal in the **AI proposal** field.
4. Click **Save approved**. The ticked rows are saved.

If you tick **Save now (skip review)** before translating, accepted rows are saved at once, without the review table.

The result table has the columns **Source**, **Current** (the current translation), **AI proposal**, **Status** (**empty** or **filled**), **Tokens** and **Warnings**. A row with a broken placeholder or HTML is not saved.

Messages you may see:

- “No strings match this filter. Nothing was sent to DeepSeek.” — the filter found no strings. Nothing was sent.
- “Review is ready. Nothing is saved until you press Save approved.” — the proposals wait in the table. Only **Save approved** saves them.
- “Saved. The approved strings were written for the target language.” — the ticked rows were saved.
- “Not saved because of broken placeholders or HTML: N.” — N rows were not saved because the model changed a placeholder or an HTML tag. Correct them in the table or untick them.

### 3.4 Bulk

**Bulk** creates one job for many domains and languages. The job does not run on this page. It waits on **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Section** | Back office | The catalogue the job reads. The **Theme** field appears only for **Themes**, and the **Module** field only for **Installed modules**. Strings outside the chosen section are not in the job. |
| **Source** | Source locale from **Settings** (en-US) | The language the job treats as the original. Every target is translated from it. |
| **Targets** | empty | The languages the job fills. You can choose several: hold Ctrl or Cmd and click. The job creates separate strings for each chosen language. |
| **Domains** | empty | The domains included in the job. Domains you do not choose are not translated. |
| **Policy** | Fill empty | **Fill empty** skips strings that already have a translation. **Overwrite all** sends all strings, including translated ones, and may replace them. **Outdated if equals source** sends strings whose translation is identical to the original. |
| **Dry-run job** | No | The job calls the model and stores the result in the job history, but does not save translations in the shop. With **No** the job saves results, if **Allow publish / save** is on. |

**Estimate** shows the number of strings, the estimated tokens and cost, and sample strings. Nothing is sent or saved. Message: “Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved.”

**Start job** creates the job and takes you to **Jobs** with the new job open. Message: “Job #N is waiting (N strings, est. $…). It has not run yet.”

Messages for errors that stop the start:

- “Nothing was started. Select at least one target language.” — no target language chosen.
- “Nothing was started. Pick a theme.” or “Nothing was started. Pick a module.” — in the **Themes** or **Installed modules** section, no theme or module was chosen.
- “Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.” — no key. No job was created.

### 3.5 Jobs

**Jobs** is the queue of bulk jobs. Opening the list does not call DeepSeek. The catalogue changes only while a job is processed and is not a dry-run.

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**The job list** has the columns **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** and **Date**. Click a job to see its strings. The **Failed only** filter shows only errors, and **Error CSV** downloads the error list as a file.

Job statuses, exactly as they appear in the **Status** column: **pending** (waiting), **running** (in progress), **paused** (paused), **completed** (finished), **completed_with_errors** (finished with errors), **cancelled** (cancelled) and **failed** (ended with an error). String statuses in the details: **pending**, **processing**, **done**, **failed**, **skipped** and **rolled_back**. The **dry-run** label marks a test job.

**Buttons in a job:**

- **Process slice** sends the next batch (as many strings as **Batch size**) and stops. After the click you see which rows were saved, skipped or failed.
- **Auto-process** sends batches one after another until the job finishes or fails. Keep the page open, because the progress bar refreshes by itself.
- **Pause** stops the job. It does not translate further strings until you resume it.
- **Resume** puts the job back in the queue. The job does not start by itself: click **Process slice** or **Auto-process**, or wait for cron.
- **Retry failed** changes the failed strings back to waiting.
- **Rollback** restores the previous translations where the module saved a backup copy before the change. Before it runs you are asked “Roll back this job?”. Message after running: “Rollback: restored N translations.”
- **Error CSV** downloads the list of failed rows.

**This version of the module has no cancel button on the job screen.** Do not try to cancel a job here. Stop it with **Pause** and do not resume it.

If DeepSeek rejects too many calls, the job stops by itself. Its error shows: “Rate limit — job auto-paused. Resume later.”

### 3.6 Review

**Review** is the queue of translations that the quality check stopped. Rows with a broken placeholder or HTML, with a very long or very short translation, or with a score below 70 land here.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Column | What it shows |
|---|---|
| **ID** | The number of the row in the queue. |
| **Domain** | The domain the text comes from. |
| **Source** | The original text. |
| **AI** | The model's proposal. |
| **Score** | The automatic quality score from 0 to 100. |
| **Flags** | The reasons for holding the row, described below. |

**Flags:**

- **validation_failed** — a placeholder or HTML tag is missing or was changed.
- **length_explosion** — the translation has more than 2.5 times the characters of the original.
- **too_short** — the translation has less than 30% of the original length, and the original has more than 20 characters.
- **possible_untranslated** — English words such as “the”, “and”, “with” remain in the translation.
- **warning** — a check warning that lowers the score.

**Approve** marks the row as accepted and **Reject** marks it as rejected. Neither button saves text to the shop. An empty queue shows: “The queue is empty.” An empty queue does not mean every language is translated. Check **Dashboard** for that.

If the job was allowed to save and the string passed validation, the translation may already be in the shop. The **Review** queue is a list for manual checking, not a save block. Saving selected rows separately is done on **Manual**.

### 3.7 Catalog

**Catalog** translates product, category and CMS page fields. It does not cover the texts on International → Translations. One batch covers at most 100 records.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Entity** | product | Chooses the record type: **product**, **category** or **cms**. The field list changes with the choice. The choice alone translates nothing. |
| **Fields** | fields selected by default for the type | The texts the batch sends. For products: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** and **Friendly URL**. For categories: **Title**, **Description**, **Meta title**, **Meta description** and **Friendly URL**. For CMS: **Title**, **Meta description**, **Meta keywords**, **Content** and **Friendly URL**. Choose by holding Ctrl or Cmd. Fields that are not selected are not sent and do not change. |
| **Source language** | first language in the list | The language the text is copied from. It does not change. |
| **Target language** | first language in the list | The language that receives the translation. Choose one different from the source. |
| **Only empty** | Yes | Skips fields that already have text in the target language. **No** also sends filled fields, and the batch may then replace that text. |
| **Start after ID** | 0 | Skips records up to this ID. 0 starts from the first record. After each batch the field fills in by itself, and the next batch starts after that ID. |

The **Translate batch (max 100)** button runs a batch. The result shows how many rows were saved and how many failed.

Before you switch **Only empty** to **No**, run a small batch and open one product in the target language.

### 3.8 Glossary

**Glossary** is a list of terms that the model must keep or translate in one fixed way. Adding a term does not change saved translations. The next translations read the list.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Source term** | empty (required) | The word or phrase in the original language, including capitals if they matter. The model treats this term as fixed when it appears in the source text. |
| **Target locale** | empty | Limits the row to one language, e.g. pl-PL. An empty field applies the row to all target languages. |
| **Target term** | empty | The approved translation of the term. Leave it empty only when **Do not translate** is on. |
| **Do not translate** | No | The model copies the term unchanged. Turn it on for brand names, SKUs and placeholders. Turn it off when **Target term** should be the translation. |

The **Add** button adds the term. The table below the form has the columns **Source**, **Locale**, **Target** and **Do not translate**, and each row has a **Delete** button that removes only that row. An empty list shows: “No glossary terms yet.”

**Import CSV** adds rows from a file. The file must have the columns: source_term, target_locale, target_term, do_not_translate. The import adds only the rows it can read. **Export CSV** downloads the current list and changes nothing.

Short, exact terms work best. A very broad term will be forced every time it appears.

### 3.9 Excludes

**Excludes** are text patterns that must not be sent to DeepSeek. The text stays in PrestaShop unchanged. The module skips it at the next manual translation, bulk job and action on International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Pattern** | empty (required) | The text or expression compared with each source text. Depending on **Type**, it is the whole text, the beginning, a fragment or a regular expression. |
| **Type** | exact | **exact** is the whole text, **prefix** is the beginning, **contains** is a fragment anywhere, and **regex** is a PHP regular expression. A pattern that is too broad skips more than you expect. Start with a short one. |

The **Add** button adds the pattern. The table has the columns **Pattern**, **Type** and **On** (whether the pattern is active). Each row has a **Delete** button that removes only that pattern. Saved translations are not cleared. An empty list shows: “No patterns yet.”

Use patterns for texts that must stay in the source language, such as legal names or technical tokens. If a text should be translated in one fixed way, use **Glossary**.

### 3.10 History

**History** is the full list of saved DeepSeek calls: manual translation, the International → Translations page, bulk jobs, Catalog and the connection test. Each row keeps the prompt, the reply, the model, the languages, the token counts and the response time.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** is the date of the call. **Type** is where it started. For a bulk job the number after the type is the job number.
- **View** opens the prompt that was sent and the reply that came back, in a window on this page. A row with an error shows the error in place of the reply.
- Filters: dates, **Model**, type, status, language, employee, and a word in the prompt or the reply. The **Previous** and **Next** buttons move between pages.
- **HTTP 401** or **HTTP 403** means the key in **Settings** is wrong or the account has no access to the chosen model.
- **Clear history** deletes these entries, and saved translations stay. The question before deleting is: “Clear the stored history? Saved translations stay.”

This page sends no new request and changes no translation. If translations suddenly stop, open the newest row with an error before you change the glossary.

### 3.11 Updates

The **Updates** tab shows the **MyPresta Updates** section. The **Check Now** button next to **Manual Check** checks at once whether a newer module version exists. The **Automatic Notifications** field (**Enabled** or **Disabled**) decides whether the module checks by itself. Save your choice with **Save**.

When automatic notifications are on, the module checks the version every 3 days, when the back office is opened. It sends the module name, the module version, the shop address and the licence identifier, if one is saved, to the MyPresta server. Turning the option off stops these automatic checks.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

### 3.12 Buttons next to shop form fields

Next to multilingual fields in the product, category, CMS and other back-office forms, a translation button appears. When fields are ticked, a bar also appears at the bottom of the form.

![Product – field translation](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Product – meta fields](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Product – translation bar](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Category form with the translation bar](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**The bar** at the bottom has the **Source** and **Target** fields and the buttons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** and **Translate selected**. The **Selected** counter shows how many fields are ticked.

The button next to a field only fills that field. To keep the change in the shop, click the PrestaShop **Save** button at the bottom of the form. The bar works the same way: it fills the ticked fields and requires saving the form.

Messages on the bar:

- “Fill the source language field first.” — the source field is empty. Type text in the source language and try again.
- “Tick at least one field.” — nothing is ticked.
- “Target is not a language from this shop.” — the chosen target language does not belong to the shop.
- “Translating…” and “Done” — translation in progress or finished.

The buttons and the bar disappear when the switches in **Settings** are off. The **shop forms** switches control them on shop forms.

### 3.13 International → Translations page

On the International → Translations page, a translation button appears next to each field, and the same bar appears at the bottom. The bar has the **Source** field (en-US by default) and the **Target** field. Choose the language you want to fill.

![International → Translations page](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- The button next to a field fills it with the translation. Only the PrestaShop **Save** button on this page saves it.
- The bar translates the ticked fields one by one.
- **Translate empty in this section** translates the empty fields in the open section.
- In the **Emails** section the module reads the source file of the template. If it cannot find it, the message appears: “The source language mail file was not found.” Then choose another source language in **Settings**.
- The message “The source language field is not on this page.” means this page has no source language field. Open another tab or section that has that language.

The switches **Individual field buttons** and **Individual field checkboxes — International → Translations** in **Settings** hide the buttons and the bar on this page only.

## 4. Storefront

The module shows nothing to customers. It adds no page, block, button or message to the storefront, so the theme shows no effect of the module and no storefront screenshot is taken. Customers have no step in the module.

The only address through which an external server can call the module is the cron address in **Settings**. It is not meant for customers. The server uses it to process jobs.

What you see when you open this address in a browser:

| What you see | What to do |
|---|---|
| The text `{"ok":false,"error":"Forbidden"}` | The address is wrong or its token is outdated. Copy the CRON URL again from **Settings** and paste it into the scheduler. |
| The text `{"ok":true,"message":"No pending jobs"}` | No job is waiting. This is normal and nothing needs to be done. |
| The text `{"ok":true,...}` with slice data | A slice was processed. You will see the details on **Jobs**. |
| The text `{"ok":false,"error":"..."}` with a message | Read the message and go to section 5 of this manual. |

## 5. Problems

**No item in the International menu.** The usual cause is the shop cache. Go to **Advanced Parameters → Performance** and click **Clear cache**. If the item still does not appear, uninstall the module and install it again. Uninstalling removes the settings and the job history, so save your API key and settings first.

**“Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.”** No key was entered, or it was removed. Open **Settings**, paste the key from your DeepSeek account, click **Save**, then **Test connection**.

**“No DeepSeek API key. Nothing was translated.”** The same case: paste the key in **Settings** and save.

**“Settings saved. No API key is stored, so nothing can be translated until you paste one.”** The settings were saved without a key. Paste the key and save again.

**Test connection fails, or History shows HTTP 401 or 403.** The key is wrong, outdated, or the account has no access to the chosen model. Paste the key again. If the error concerns the model, choose another model from the list, or add a valid identifier in **Add a DeepSeek model**.

**“DeepSeek rate limit (429). Try again later.”** DeepSeek limited the number of calls. Wait a few minutes, then resume the job on **Jobs** with **Resume** and **Process slice**. If the error returns, lower **Batch size** in **Settings**.

**“Rate limit — job auto-paused. Resume later.”** The job paused by itself after too many rejected calls. After a while, click **Resume** in the job, then **Process slice** or **Auto-process**.

**“Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.”** The job waits for a manual start or for cron. Click **Process slice** or **Auto-process**. To have jobs run without clicking, add the CRON URL to the scheduler on the server and call it regularly.

**“Monthly API budget has been exhausted.”** The monthly **Budget USD / month** limit is reached. Open **Settings**, raise the amount, or set 0 to remove the limit. New translations run once the job is resumed.

**“Allow publish is off in Settings.”** Saving translations is blocked. Open **Settings** and turn on **Allow publish / save**. Without it, **Process slice** will not save text to the shop.

**“Not saved because of broken placeholders or HTML: N.”** N rows were not saved because the model changed a placeholder or an HTML tag. Open **Review** or the table on **Manual**, correct the proposal and save again, or reject the row.

**The job finished with status completed_with_errors.** Some strings failed. On **Jobs** turn on the **Failed only** filter, download the **Error CSV** and click **Retry failed** to retry the failed strings.

**A translation cannot be undone.** **Rollback** restores only translations for which the module saved a backup copy before the change. The copies belong to the job. They disappear when the module is uninstalled.

**The translation is saved, but the old text shows on the page.** Clear the cache: **Advanced Parameters → Performance → Clear cache**. On shop forms and on International → Translations, remember that the buttons and the bar only fill the fields. The PrestaShop **Save** button saves them.

**The translation buttons do not show next to fields.** The switches are off. Open **Settings** and turn on the relevant switch: **Individual field buttons** or **Individual field checkboxes** for shop forms, or for International → Translations.

**“Fill the source language field first.”** The source language field is empty. Type text in that language and try again.

**“The source language mail file was not found.”** There is no source-language file for this e-mail template. Choose another **Source locale** in **Settings**, or translate the template by hand.

**After Start job, nothing happens.** Start job only creates the job; it does not run it. Open **Jobs** and click **Process slice** or **Auto-process**.

**The e-mail about a finished job does not arrive.** Check that **Email notify on complete** is on and that the **Notify email** address is correct. An empty field sends to the shop address. The e-mail is sent only when the job finishes. Also check that the shop sends e-mail at all under **Advanced Parameters → E-mail**.

**A job cannot be cancelled.** This version of the module has no cancel button on the job screen. Stop the job with **Pause** and do not resume it.

**History is empty, or shows “No requests yet.”** No call to DeepSeek has been made yet. The Dashboard also shows zeros until you run a translation.

## 6. For developers

This section describes the module code. Configuration keys and class names appear only here.

### 6.1 Overview

- **Main class:** `myaitranslationsdeepseek` (extends `Module`), file `myaitranslationsdeepseek.php`.
- **Technical name:** `myaitranslationsdeepseek`. The prefix of configuration keys and tables is `MYAITDS_` and `myaitds_`.
- **Version:** 1.2.0.
- **Name in the module list:** AI Translations with DeepSeek.
- **Author in the code:** MyPresta.eu. Tab: `administration`.
- **Compatibility:** PrestaShop 1.7.0.0 to 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Menu tab:** class `AdminMyaitranslationsdeepseek`, parent `AdminInternational` (fallback: `IMPROVE`).

Data flow: settings are read by `MyaitdsConfigService` from `Configuration` (keys `MYAITDS_*`). The services `MyaitdsTranslateService`, `MyaitdsJobWorker` and `MyaitdsCatalogTranslateService`, and the back-office controller, call `MyaitdsDeepSeekTranslationProvider`, which sends a cURL request to `https://api.deepseek.com/chat/completions` (120 s timeout, 15 s connect timeout). The reply goes through the validators (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) and `MyaitdsQualityScorer`. Saving goes through `MyaitdsTranslationAdapterFactory` to the PrestaShop translation service, and to the `translation` table if the service is missing. For classic modules the save goes to that module's `translations/{iso}.php`. Calls are recorded in `myaitds_request` and `myaitds_api_log`, costs in `myaitds_usage_ledger`. The translation memory (`myaitds_memory`) lets the module skip an API call for the same source, language, model and glossary version.

### 6.2 Files

| File | Purpose |
|---|---|
| `myaitranslationsdeepseek.php` | Main class: install, uninstall, menu tab, back-office hooks, `getContent()` redirect to the controller. |
| `sql/install.php` | Creates the 11 tables (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Drops the 11 tables (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Back-office controller: all tabs, form actions, job actions and AJAX requests. |
| `controllers/front/cron.php` | Front controller `cron`: processes one job slice. |
| `src/Admin/MyaitdsForms.php` | HelperForm forms and their `desc` texts. |
| `src/Admin/MyaitdsSectionHelp.php` | Help text for each tab. |
| `src/Service/MyaitdsConfigService.php` | Reads and writes `MYAITDS_*`, model list, value ranges, API key. |
| `src/Service/MyaitdsTranslateService.php` | Manual and button translation: memory, budget, validation, save. |
| `src/Service/MyaitdsBulkJobFactory.php` | Estimation and job creation for bulk jobs. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Product, category and CMS fields, batches of at most 100 records. |
| `src/Service/MyaitdsDashboardService.php` | Coverage calculation (missing and translated texts). |
| `src/Service/MyaitdsRateLimiter.php` | Calls-per-minute limit, stored in `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Processes slices, saves, snapshots, review queue, completion e-mail. |
| `src/Job/MyaitdsJobRepository.php` | Reads and writes jobs and their strings. |
| `src/Job/MyaitdsJobStatuses.php` | Constants for job and string statuses. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | DeepSeek API call (cURL), error and HTTP code handling. |
| `src/Provider/MyaitdsPromptBuilder.php` | Builds the prompt with tone, brand voice and glossary. |
| `src/Provider/MyaitdsProviderFactory.php` | Creates the provider (currently DeepSeek only). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Translation provider interface. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Interface for access to the PrestaShop catalogue. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Shared logic: sections, domains, saving, cache clearing. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Scanning of XLF files and translation directories. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Reads and writes `translations/{iso}.php` of classic modules. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Concrete adapter implementation (extends the abstract adapter). |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Creates the adapter. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Checks placeholders in the translation. |
| `src/Quality/MyaitdsHtmlValidator.php` | Checks HTML tags. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Combines placeholder and HTML checks. Uses PrestaShop classes (`Validate::isCleanHtml`) when available. |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Protects tags and variables in e-mail templates from translation. |
| `src/Quality/MyaitdsQualityScorer.php` | Score 0–100, flags and the review decision (threshold 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Reads and writes the glossary. CSV import and export are in the controller. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Exclude patterns. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Call history (**History**): saving, filters, view and cleanup by retention. |
| `src/Audit/MyaitdsApiLogRepository.php` | API log and its retention. |
| `src/Audit/MyaitdsTranslationMemory.php` | Translation memory (hash of source, language, model and glossary). |
| `src/Audit/MyaitdsUsageLedger.php` | Monthly usage and costs, the source for the budget. |
| `src/Audit/MyaitdsSnapshotService.php` | Values saved before a change, and restoring them (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | API key encryption (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Panel skeleton with tabs. |
| `views/templates/admin/_partials/*.tpl` | Tab content: dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Back-office logic: jobs, auto-processing, forms. |
| `views/js/admin-help.js` | Help windows on the tabs. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Charts on **Dashboard**. |
| `views/js/entity-fields.js` | Buttons and bar next to shop form fields. |
| `views/js/translations-tool.js` | Buttons and bar on International → Translations. |
| `views/css/admin.css` | Styles of the panel and buttons. |
| `lib/updateChecker.php` | Version checks with MyPresta and the **Updates** tab. |
| `translations/*.php` | Module translations (27 languages, including `pl.php`). |
| `var/rate_limit.json` | State of the calls-per-minute limit. |
| `logo.png`, `logo.gif` | Logo in the module list and in the panel. |

### 6.3 Controllers

**Back office:** `AdminMyaitranslationsdeepseekController`, tab `AdminMyaitranslationsdeepseek`, parent `AdminInternational`. The tab is selected by the `myaitds_tab` parameter. Allowed values: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (the **History** tab), `review`, `catalog` and `updates`. Any other value opens `dashboard`. The controller defines no permissions of its own, so the tab permissions set in PrestaShop apply.

Form actions (`Tools::isSubmit`): `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

GET actions: `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors`; `cancel` is handled, but no template creates a link to it), `review_action` (`approve`, `reject`) with `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

AJAX actions (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), handled by the `displayAjax*` methods: `HistoryDetail` (history row details, parameter `hist_id`), `ProcessJob` (one slice, `id_job`), `JobStatus` (job state), `TranslatePageLines` (lines of the translation page), `MailSource` (source file of a mail template), `ListDomains` (domains for a section).

**Front:** `MyaitranslationsdeepseekCronModuleFrontController` in `controllers/front/cron.php`. The address has the form `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Controller settings: `$ssl = true`, `$ajax = true`. Parameters: `token` (required, compared with `MYAITDS_CRON_TOKEN` using `hash_equals`) and optional `id_job`. Without `id_job`, the module takes the first job with status `pending` or `running` among the 20 newest. A wrong token returns HTTP 403 with `{"ok":false,"error":"Forbidden"}`. No jobs returns `{"ok":true,"message":"No pending jobs"}`. A processed slice returns the result of `processSlice`.

### 6.4 Hooks

Registered on installation:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: renames the tab if the name is still technical, and loads the back-office assets.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: loads the same assets.

`loadBoAssets()` works as follows. On the `AdminMyaitranslationsdeepseek` tab it adds `admin.css`, `admin.js`, `admin-help.js`, and on **Dashboard** also `chart.min.js` and `history-charts.js`. On the `AdminTranslations` page it adds `translations-tool.js` when the buttons or bar for International → Translations are on (`MYAITDS_TR_BUTTONS` or `MYAITDS_TR_BULK`). On other back-office pages it adds `entity-fields.js` when the buttons or bar for shop forms are on (`MYAITDS_ENTITY_BUTTONS` or `MYAITDS_ENTITY_BULK`). It passes configuration through `Media::addJsDef` as `myaitdsTr` and `aitHelpLabels`.

The module **does not expose** its own hooks: it does not call `Hook::exec` and does not register front-office hooks.

The module **has no** `enable()` or `disable()` methods. Enabling and disabling runs no module action. PrestaShop removes the hooks when the module is uninstalled.

### 6.5 Overrides

The module has no `override/` directory and does not override any PrestaShop class or controller.

Files written by the module: translations go through the PrestaShop translation service (`prestashop.service.translation`), and to the `translation` table when the service is missing. For classic modules (keys in the format `<{name}>prestashop`) the module rewrites that module's `translations/{iso}.php`, first to a temporary file and then by renaming it. It clears the cache with `Tools::clearCache()`. It also writes `var/rate_limit.json` and the `update_<module>`, `updatev_<module>` and `mypresta_updates` values in `Configuration`.

### 6.6 Database

Tables use the shop prefix (`_DB_PREFIX_`). All are created with the `_MYSQL_ENGINE_` engine and the `utf8mb4_unicode_ci` collation.

| Table | Contents |
|---|---|
| `myaitds_glossary` | Glossary terms: `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, dates. Index `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Exclude patterns: `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Jobs: `uuid` (unique), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_*` counters, tokens, `cost_usd_estimate` and `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Job strings: `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Translation memory: `memory_hash` (unique), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Daily usage: `usage_date`, `id_myaitds_job`, `model`, tokens, `cost_usd`. The source for the monthly budget. |
| `myaitds_snapshot` | Values before a change: `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. The source for **Rollback**. |
| `myaitds_api_log` | API log: `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Cleaned up by `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Call history (**History**): type, status, model, languages, HTTP code, time, tokens, cost, `prompt`, `reply`, `error_message`. Cleaned up by retention. |
| `myaitds_review` | Review queue: `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Created on installation, but no code writes to it or reads from it. |

Installation creates tables only with `CREATE TABLE IF NOT EXISTS`. The module adds no columns when a page is opened (there is no `ALTER TABLE` in the code).

Uninstalling drops all 11 tables. Reinstalling creates them empty.

### 6.7 Keys and translations

**Configuration keys** (prefix `MYAITDS_`) and starting values from `installDefaults()`:

| Key | Starting value | Notes |
|---|---|---|
| `API_KEY_ENC` | `''` | Key encrypted with AES-256-CBC; the encryption key is derived from `_COOKIE_KEY_`. |
| `MODEL` | `deepseek-flash` | The call model. |
| `EXTRA_MODELS` | `''` | Added model identifiers (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | The only provider. It has no field in the panel. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Brand voice text. |
| `BATCH_SIZE` | `25` | Range 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = no limit. |
| `SOURCE_LOCALE` | `''` | Empty means the screen supplies the source. Fallback in code: `en-US`. |
| `TEMPERATURE` | `0.2` | Range 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Range 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | The form field is named `MYAITDS_RATE_LIMIT`. 0 turns the limit off. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | E-mail switch. |
| `NOTIFY_EMAIL` | `''` | Empty = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Blocks saving from **Manual**, jobs and **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Buttons and bar next to shop form fields. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Buttons and bar on International → Translations. |
| `MAX_TOKENS` | `0` | 0 = DeepSeek default limit. |
| `CRON_TOKEN` | random 16 bytes (hex) | The cron address token. |

Uninstalling removes the keys above, plus `DEEPL_API_KEY` and `CLAUDE_API_KEY`, which the module no longer uses.

**Texts not passed through `$this->l()`.** Field and help texts go through `l()` in the domains `myaitdsforms` (`MyaitdsForms`) and `sectionhelp` (`MyaitdsSectionHelp`). JavaScript labels go to `Media::addJsDef` through `translationClientConfig()`. The subject and body of the completion e-mail are in English in `MyaitdsJobWorker::notifyComplete()` and do not go through `l()`. Messages shown through `$this->module->l()` in the controller use the domain `adminmyaitranslationsdeepseekcontroller`.

**Adding a language:** add a `translations/{iso}.php` file modelled on the existing ones (for example `translations/pl.php`). PrestaShop loads the file that matches the shop's ISO code.

**Source of field texts:** `MyaitdsForms::help()` (the `desc` of each field) and `MyaitdsSectionHelp::pages()` and `brief()` (tab help text).

### 6.8 Extending

- **Theme:** nothing to override. The module does not render front-office templates.
- **Back-office templates:** `views/templates/admin/`. Changes made to module files are lost when the module is updated.
- **New DeepSeek models:** no code change needed; use **Add a DeepSeek model** (`EXTRA_MODELS`).
- **New provider:** implement `MyaitdsTranslationProviderInterface` and add an entry in `MyaitdsProviderFactory`.
- **Review threshold:** 70 points, set in `MyaitdsQualityScorer::score()`.
- **Glossary and exclusions:** managed in the panel, no code change needed.

## 7. Support

Module page: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Log in to your customer account on mypresta.eu, go to contact and choose the subject **Support for paid modules**. The form states that logging in is required for paid modules. After logging in, select this module from your purchase history.
