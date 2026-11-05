---
title: "My AI Grok - AI content generation - documentation and user manual"
description: "A merchant guide for people who already have the module: connect your Grok (xAI) account, generate catalog text from the back office, and fix problems when something does not work."
sidebar:
  label: "My AI Grok - AI content generation - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy SEO meta and catalog descriptions with Grok AI Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Requirements

This chapter lists what your shop and your server need before the module can write text for you.

- **PrestaShop:** versions 1.6 up to 9.x.
- **PHP:** version 7.0 or newer. On an older PHP the installation is refused with a message.
- **PHP extensions:** cURL. The module talks to Grok through cURL.
- **Outbound connection:** the server must be allowed to open secure (HTTPS) connections to `https://api.x.ai/v1`. If a firewall blocks it, every generation fails.
- **Other modules:** none. The module works on its own.
- **An xAI account:** you need your own account on https://console.x.ai to get a Grok API key. Calls to Grok are billed by xAI to your account, not by the module.
- **Large catalogs:** the module writes one field of one product per request. A long mass run therefore takes as long as all those requests together. Use the batch limits on the Generate and Cron screens, and keep the API timeout high enough for slow models (see section 3.4).

## 2. Installation

### 2.1 Upload, install and enable

1. In the back office open **Modules**, then **Module Manager**.
2. Upload the module ZIP, or find it in the list if it is already on the server.
3. Click **Install**. The installation checks the PHP version, creates the module's data and then enables the module.
4. If the installation stops with a message, read section 5.1.

### 2.2 What appears in the menu

- A new entry named **AI Content Generator** appears under **Modules**. Clicking it opens the module's **Dashboard** screen.
- All other module screens (Settings, Generate, New product, Cron, History, Images, Updates) are reached from the navigation bar at the top of the module, not from the left-hand menu.
- On the product edit page a **My AI Grok** block appears in the **Modules** tab, and small **Generate with AI** buttons appear next to text fields (see section 3.16).
- A magic-wand shortcut can appear in the top bar of every back-office page (see **Admin Top Bar CTA** in section 3.4).

You can also reach the settings from **Modules**, **Module Manager**, the module name, **Configure**.

### 2.3 Cache

The installation does not clear the PrestaShop cache. If the menu entry or the product block does not show up right after installing, clear the cache yourself in **Advanced Parameters**, **Performance**, and reload the page.

### 2.4 Uninstalling and reinstalling

- **What disappears:** the **AI Content Generator** menu entry and its hidden screens, the 16 ready-made prompt templates together with any templates you added, the whole History (every stored prompt, reply and token count), and the module's saved settings (API key, model, Studio rules, cron choices, secrets).
- **What stays:** all text already written into products and categories. The module never removes generated text.
- **Leftovers:** a few remembered choices from the Generate screens (filters such as the last chosen language or status) can remain stored in the shop. They have no effect.
- **Reinstalling:** a new installation starts from the default values listed in section 3. Your API key, Studio rules, custom templates and History are not restored, so write them down or export what you need first.

## 3. Configuration and back-office work

This is the main chapter. It starts with the whole working process, then describes every screen in the order of the navigation bar.

### 3.1 The whole process, step by step

1. **Connect Grok.** Open **Settings**, then **Grok**. Paste your API key from https://console.x.ai and choose a model. Save.
2. **Set your house style (optional).** Open **Settings**, then **Studio**. Fill in voice, audience, tone, a glossary of names to keep, forbidden words, a monthly budget and the quality gate. Leave empty what you do not need.
3. **Test safely.** Use **Settings**, then **Playground** to send a free instruction and read the reply. On a product page use the **Simulate** tab and **Try**. Nothing is saved to the catalog in these two places.
4. **Fill one product.** Open the product, go to the **Modules** tab, **My AI Grok**, **Generate**, pick the language and press **Fill** next to the field. Or use the **Generate with AI** buttons next to the product's own fields and then save the product.
5. **Fill many products.** Open **Generate**, **Products**. Filter the list, press **Go to next step**, choose a template or write an instruction, choose what to generate, how to treat existing text and which languages, then press **Run on the list below**. Do the same for categories on **Generate**, **Categories**.
6. **Unattended batches.** Open **Cron**, save your choices, copy the address into the scheduler of your server (see sections 3.12 and 4.2).
7. **Audit and undo.** **History** shows every call with its prompt, reply, status and tokens. On a product, the **History** tab lets you put an earlier text back with **Restore**.

Generated text is written straight into the catalog as soon as each reply arrives. Before a first large run, test on a few products with **Simulate** or the **Product IDs** and **Product Limit** filters.

### 3.2 Navigation and the Help panel

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard: the navigation bar sits at the top of every module screen.*

The bar shows the module name with its version and these items, in this order:

| Item | What you find there |
|---|---|
| **Dashboard** | Charts of requests, tokens and errors. |
| **Settings** | Five sub-tabs: **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Two sub-tabs: **Products** and **Categories** for mass runs. |
| **New product** | Creates a new product from a short brief. |
| **Cron** | Builds addresses the server can call on a schedule. |
| **History** | The full list of calls with filters. |
| **Images** | Switch and instruction for the product image search. |
| **Updates** | Checks whether a newer version of the module is published. |

Hover over an item to read a short explanation. A round **Help** button at the edge of the screen opens a side panel with help for the page you are on. Close it with the cross.

Every field in the module is explained on screen in three parts: **What it does**, **How to configure** and **Effect**. The tables below restate those texts in plain words and add the value the field has right after installation.

### 3.3 Dashboard

Open **AI Content Generator** under **Modules**, or the **Dashboard** item of the bar.

- **Date presets:** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. The page opens on **30 days**.
- **From** and **To:** choose your own dates and press **Apply**. If From is later than To, the dates are swapped.
- **Active service:** shows Grok and the model that is selected on Settings.
- **Cards:** **Requests** (every stored call), **Success**, **Errors**, **Tokens sent** (size of the prompts) and **Tokens received** (size of the replies).
- **Charts:** **Requests and errors**, **Tokens sent and received**, and **Requests by model**. For ranges longer than about four months the days are grouped by week.

| Control | On install | What it does |
|---|---|---|
| **Presets** | 30 days | Counts the Grok generations stored in History inside the chosen dates. The API key and the model are not chosen here but on Settings. |
| **From / To / Apply** | last 30 days | Draws only that slice. Nothing in the catalog is generated or changed from this page and History is not deleted. |

### 3.4 Settings – General

Open **Settings**, then **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General: shop-wide switches and the API timeout.*

These switches decide what employees see in the back office. Saving here does not change product text by itself. Press **Save**; the confirmation reads **Settings Updated**.

| Field | On install | What it does |
|---|---|---|
| **Live mode** | Disabled | Marks the module as running on the real shop rather than a trial setup. Enable it on the production shop. Leave it disabled on a staging copy if you do not want staff to treat the tools as ready. Disabled keeps the same tools but signals that the setup is not the production one. |
| **Debug mode** | Disabled | Writes extra diagnostic detail when a call to Grok fails. Turn it on only while you investigate an error, then turn it off. Enabled adds technical messages to the PrestaShop log (**Advanced Parameters**, **Logs**). Disabled keeps the log to the normal generation history. Customers never see this. |
| **API timeout (seconds)** | 120 | How many seconds one call to Grok may run before the module gives up. Use 120 for normal descriptions. Raise it toward 600 for long SEO packs or slow models. Do not go below 10. Values below 10 are saved as 10 and values above 600 as 600; an empty or non-numeric value is saved as 120. A short timeout fails fast and records an error. A long timeout waits for a slow model instead of aborting a good reply. |
| **Product Edit History** | Enabled | Shows previous AI writes on the product page so you can put an old value back. Enable it if editors should undo a generation. Enabled adds a **History** tab with **Restore** to the product's module block. Disabled hides it. Past rows stay in History either way. |
| **Admin Top Bar CTA** | Enabled | Puts a shortcut in the back-office top bar that opens the generator. Enable it for shops where staff generate text often. Disable it if the bar is already crowded. Enabled shows the button on every back-office page. Disabled removes only that button. The module menu stays. |
| **Product edit page Form** | Enabled | Shows the generator panel on the product edit page: the **Generate**, **Simulate** and **Photos** tabs of the **My AI Grok** block. Enable it for catalog editors. Disable it if only mass generation and cron should be used. |
| **AI Image Finder** | Enabled | Lets an editor ask the model for pages that are likely to contain photos of the current product. Enable it when you want that button on the product page. You still choose which images to import. Disabled hides the **Photos** tab content. Nothing is downloaded until someone confirms an image. |
| **AI Image Search Prompt** | Asks for exactly 5 page addresses | The instruction sent when someone searches for product images. `{product_name}` and `{product_description}` are replaced with the current product. Keep the request for a list of page addresses. Change the wording if you want manufacturer sites or a different count. A tighter prompt returns more relevant pages. A vague prompt returns unrelated links. Nothing is saved until you pick images. |

The same **AI Image Finder** switch and prompt also exist on the **Images** screen (section 3.14); both places change the same setting.

### 3.5 Settings – Grok

Open **Settings**, then **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok: API key, model and the sampling values.*

This form holds the Grok account used for every generation, including cron and the product buttons. Sampling fields change how varied the wording is. They do not change which products are updated.

Messages you may see after **Save**: **OpenAi Settings Updated** (success; the wording is a leftover but the screen belongs to Grok), **Grok API KEY field is invalid!** (no key stored and the pasted one is shorter than 10 characters) and **OpenAi Model field is invalid!** (the model name is too short). A key with spaces around it is cleaned automatically and you may see **Grok API Key has been automatically cleaned (whitespace removed).**

| Field | On install | What it does |
|---|---|---|
| **Grok API KEY** | empty | The secret that lets this shop call your Grok account. Paste the key from https://console.x.ai. Spaces are removed when you save. Leave the field untouched to keep the key already stored. A valid key allows Grok generations. An empty or wrong key makes those calls fail and the error is written to History. |
| **Model** | grok-4.7 | The Grok model that writes the text. The built-in names are grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning and grok-4.20-0309-reasoning. They stay in the list. Names you add in the next row can be removed. The next generation uses that model. A model your key cannot access returns an error instead of text. |
| **Add a Grok model** | no extra models | Adds a Grok model id that is not in the built-in list so you can select it above. Type the exact id from your Grok account (for example grok-4.6), then click **Add model**. The new id appears in the **Model** list and becomes the active model. **Remove** next to an added id deletes only ids added here. Built-in ids cannot be deleted. If you remove the active model, grok-4.7 becomes active. Messages: **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Upper limit on how long the reply may be, counted in tokens rather than words. Use about 256 for a meta description and 1000 or more for a full HTML description. A low limit cuts the reply off. A high limit allows longer text and costs more on the provider bill. It does not change the prompt. |
| **Temperature** | 0.7 | How freely the model chooses words. Lower is steadier, higher is more varied. Stay between 0 and 1. Use about 0.2 for specs and meta text, about 0.7 for descriptions. Change this or **Top P**, not both. A low value repeats a similar structure. A high value produces more different wording and more risk of going off brief. |
| **Top P** | 1 | Another way to limit how surprising the next word can be. 1 considers the full range. Leave 1 if you already set **Temperature**. Use a lower value, such as 0.9, only if you want a tighter vocabulary. Lower values make replies safer and more repetitive. |
| **Frequency Penalty Value** | 0 | Reduces lines that repeat the same phrase inside one reply. Use 0 unless descriptions keep copying the same sentence. Try 0.3 to 0.6. Stay between -2 and 2. A positive value makes repeated wording less likely. It does not look at other products. |
| **Presence Penalty Value** | 0 | Pushes the reply toward new topics instead of staying on words it already used. Use 0 by default. Try a small positive number if every paragraph covers the same point. Stay between -2 and 2. Some newer models ignore this field. |

The module remembers on its own which of these values a model refuses and stops sending them to that model, so you will not see an error for it.

### 3.6 Settings – Studio

Open **Settings**, then **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio: house rules added to every prompt.*

Studio is applied on top of every prompt, including the product buttons, mass generation and cron. Empty fields are skipped. A budget of 0 means no monthly limit. The module also tells the model which language to write in, based on the language of the product, category or screen in use. Press **Save studio**; the confirmation reads **Studio settings saved.** Text already saved in the catalog is not rewritten.

| Field | On install | What it does |
|---|---|---|
| **Brand voice** | empty | Tells the model who is speaking, so product text matches the shop instead of a generic assistant. Write a short brief, for example: specialist workshop, short sentences, no hype. Every later generation starts from this voice. Changing it does not rewrite text that is already saved. |
| **Audience** | empty | Names the reader the model should write for. Use a plain phrase such as professional installers or first-time buyers. Replies use vocabulary and examples aimed at that reader. |
| **Tone** | empty | Sets the mood of the wording: formal, warm, technical, and so on. One or two words are enough. Leave it empty to let the prompt decide. It does not change the model or the temperature. |
| **Glossary** | empty | A list of brand names, materials and spellings the model must copy exactly. Put one term per line, in the form you want kept. New text prefers those spellings. Terms not listed can still be reworded. |
| **Forbidden words** | empty | Words and phrases that must not appear in a saved reply. One word or phrase per line. The list is checked only when the **Quality gate** is enabled. A reply that contains one of these lines is rejected and is not written to the product. The attempt is still stored in History as an error. |
| **Monthly generation budget** | 0 | Caps how many successful generations the shop can run in the current calendar month. Enter a whole number. Use 0 for no cap. The counter starts again on the first day of the month. Once the cap is reached, new generations stop with a budget message until next month. Failed calls are not counted. Negative numbers are saved as 0. |
| **Quality gate** | Enabled | Checks the model reply against the forbidden list before anything is saved. Enable it after you have filled **Forbidden words**. Disable it if you only want the list stored for later. Enabled blocks a matching reply. Disabled saves the reply even when it contains a listed word. |

The budget counts the rows in History, so using **Clear list** on the History screen starts the month's count from zero again.

### 3.7 Settings – Prompt templates

Open **Settings**, then **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates: the list of saved instructions.*

A template is a saved instruction. Editors pick it instead of typing the same brief again. Placeholders are replaced with the product or category you generate for. The shop starts with 16 ready-made templates for product names, descriptions, meta titles, meta descriptions and tags, all enabled.

**The list** shows **ID**, **Title**, **Prompt**, **Status** (click the tick or cross to switch a template on or off) and **Timestamp**. Each row has **Edit** and **Delete**. Tick several rows and use the bulk action **Delete** (you are asked: **Are you sure you want to delete the selected prompts?**). The **Add new** button above the list creates a template.

**The form** (**Generate Prompt Template**) has three fields. Press **Save Prompt**, or **Go Back to Module Settings** to leave without saving. Messages: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Double quotes typed into the prompt are saved as single quotes.

| Field | On install | What it does |
|---|---|---|
| **Status** | Disabled for a new template | Shows or hides this template in the dropdowns used on the product page, in mass generation and in cron. Enable the templates staff should use. Disable a draft instead of deleting it. Enabled templates appear in the lists. Disabled ones stay in this table but are not offered. |
| **Prompt title** | empty (required) | The name editors see in the template dropdown. It is not sent to the model. Use a short label such as HTML description with features. |
| **Prompt content** | empty (required) | The instruction sent to the model. Write the brief the way you would tell a copywriter and mention length, HTML and language if they matter. When someone runs the template, the placeholders are filled from the current item and the reply is written to the field they chose. |

**Placeholders** you can type into a prompt (they are filled for each product, category or page when the template runs):

| Placeholder | Replaced with |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | The product's own data in the language being written. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | The product's brand, its default category name and description, and all its category names. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | The product's combination attributes, feature names, feature name and value pairs, and links to its images. |
| `{category_name}` `{category_description}` `{category_parent_name}` | The category being written, and the name of its parent category. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | Data of the content page or brand open when you use the top-bar shortcut. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | Shop-wide data: name, domain, language, default country and default currency code. |

Use only the placeholders that make sense where the template will run. A product placeholder in a category brief stays as typed text.

### 3.8 Settings – Playground

Open **Settings**, then **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground: a scratch pad for one free instruction.*

The Playground sends one free instruction to the active model and prints the reply under the button. You may mention the shop name, shop URL, a product name, a reference or product features so the module can substitute catalog data. The reply stays on this page. No product or category field is saved.

| Field | On install | What it does |
|---|---|---|
| **Instruction box** | empty | Type the instruction in plain language and press **Generate**. The active provider receives this text together with the Studio rules. The reply appears under the button with the number of tokens used. The catalog is not updated. |

If you press **Generate** with an empty box you see **Write a prompt first.** Each call is stored in History with the type **general**.

### 3.9 Generate – Products

Open **Generate**, then **Products**. You can also click the **My AI Grok** button that appears next to the bulk actions on the product list.

Mass generation has two steps: a filter that builds a list, and a run on that list.

**Step 1: Filter products to update.** This step only builds the product list. Nothing is written to products until you choose a scope and languages on the next screen and press **Run**. These filters are not saved as shop settings. Press **Go to next step** when ready. Leave a filter empty to ignore it.

| Field | On install | What it does |
|---|---|---|
| **Product Categories** | none ticked | Limits the product list to items that sit in the ticked categories (or have one of them as the default category). Tick the categories you want. Leave the tree empty if category should not matter. |
| **Brand** | Select brand (no filter) | Keeps products from one manufacturer. Pick a brand, or leave the first empty option if every brand should be included. |
| **Product status** | Active | Keeps products that are on sale, disabled, or both. Choose **Active** for the live catalog, **Disabled** for drafts, or **Both**. |
| **Product stock** | All products | Optionally skips products that are out of stock. **Only in stock products** removes products with no available quantity from the list. **All products** leaves stock out of the filter. |
| **Update only** | Update all | Uses the generation history to include products never written by this module (**Products that have not been updated with OpenAi content**), only those that have (**Products that already have been updated with OpenAi content**), or every product (**Update all**). Pick not yet updated for a first pass and already updated when you want to rewrite. A product counts as already updated when History holds any entry for it, even a failed attempt. |
| **Product IDs** | empty | Restricts the list to specific product ids. Type ids separated by commas, for example 12,45,103. |
| **Product Reference** | empty | Restricts the list to specific reference codes. Type one or more references separated by commas. |
| **Product Add Date From** | empty | The earliest creation date a product may have to be included. Products created before this moment are left out. |
| **Product Add Date To** | empty | The latest creation date a product may have to be included. Products created after this moment are left out. |
| **Minimum product ID** | empty | The smallest product id that may appear in the list. Type a whole number. |
| **Maximum product ID** | empty | The largest product id that may appear in the list. Type a whole number. |
| **Product Limit** | empty (no limit) | Caps how many products are loaded into the generation list. Use a small number, such as 20, on a large catalog. The next screen never shows more than this count, so one run cannot walk the whole catalog by accident. |

**Step 2: Mass product generation.** The next screen shows a table of the matching products (**ID**, **Reference**, **Result**) with the run controls above it.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products: template, scope, existing text, languages and the list to run on.*

Writes the filtered products one by one with the active model. Each product in the table is updated in the ticked languages. Products that were not in the filter are left alone. A row shows its result as soon as that product finishes.

| Field | On install | What it does |
|---|---|---|
| **Template** | **Choose a template** (none) | Fills the prompt box from a template saved on Settings. Pick a title, or leave the first option and type your own prompt in the box below. The model receives the text in the box with product placeholders replaced for each row. The title itself is not sent. If the box stays empty a ready-made short brief for each field is used. |
| **What to generate** | Descriptions | **Descriptions** writes the long and the short description. **Meta title and meta description** writes both meta fields. **Descriptions and meta together** writes all four. Fields outside that choice stay as they are. Each field gets its own request. |
| **Existing text** | Replace | **Replace** overwrites the field. **Skip if filled** leaves a filled field alone and does not call the model for it. **Add above** and **Add below** keep the old text and attach the new text before or after it. Replace changes the stored value. Skip protects filled fields. Add keeps both versions in the same field. |
| **Languages** | the language of your own back-office session is ticked | Tick every language you want written. Untick a language to leave it untouched. Each ticked language is generated separately. Unticked languages keep their current text. |
| **Run on the list below** | – | Starts the run. A status line shows progress (for example 3 / 24 followed by the field name) and ends with **Finished N products.** If no language is ticked you see **Select at least one language.** |

Each row in the **Result** column reports one line per field and language, for example the field name followed by **success**, **skipped** or **error** and a short message. **skipped** with **Product skipped.** means the field already had text and **Skip if filled** was chosen. **error** lines carry the reason; the same failure is stored in History.

Keep this browser tab open until the run says **Finished**. The run is driven by the page: it sends one request at a time, and closing or reloading the tab stops it. Products already finished stay written. A very long text is shortened to fit PrestaShop's limits: names to 128 characters, short descriptions to 800, meta titles to 69 and meta descriptions to 159.

### 3.10 Generate – Categories

Open **Generate**, then **Categories**. It works like the product screen with fewer filters.

**Step 1: Filter categories to update.** This step only builds the category list. Nothing is sent to the model until you write a prompt on the next screen and start the run. Filters here are not saved as shop settings. Press **Go to next step**.

| Field | On install | What it does |
|---|---|---|
| **Categories** | none ticked | Picks the categories that will appear in the list on the next step. Tick one or more categories. Leave the tree empty to include every category that matches the status below. |
| **Category status** | Active | Keeps active categories, disabled ones, or both (**Active**, **Disabled**, **Both**). The next step lists only categories with that status. |

**Step 2: Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories: the instruction, field, existing text, language and the category list.*

Writes one field for every category in the filtered list. Each listed category is updated in that language. Other fields and other languages stay as they are.

| Field | On install | What it does |
|---|---|---|
| **Instruction box** (above the field list) | empty | The instruction sent for every category. Describe the tone, length and HTML. Use `{category_name}` when you want the category name in the brief. Each category is generated from this same text. If left empty a ready-made short brief is used. |
| **Field selector** | Description | The category field this run writes: **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. Only that field is saved. The other category fields stay as they are. If your PrestaShop has no Additional description field for categories you see **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** overwrites the field. **Skip if filled** leaves it and does not call the model for that category. |
| **Language selector** | your back-office language | The language version that will be written. Pick one language. Run again for another language. Only that language changes. |
| **Run on the categories below** | – | Starts the run. Results appear per row, as on the product screen. |

Under the list the screen also shows a second form called **Generate category content**. Use the **Run on the categories below** button above it to generate. That second form only remembers its choices and brings you back to the category filter (see section 5.12).

### 3.11 New product

Open **New product**. This screen turns a short brief into a product draft and can insert that draft into the catalog.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product: brief, optional source page, language and default category.*

Generate data shows the draft and does not save a product. **Create product** adds an active product in that language and category, copies the name, descriptions, meta, tags, features, price and reference from the draft, gives it a starting stock of 100 pieces and places it in the chosen category.

| Field | On install | What it does |
|---|---|---|
| **What is the product?** | empty | The brief the model expands into a name, descriptions, meta, tags, features, reference and price. Write the product in a few sentences. Mention materials, audience and must-keep names. A richer brief produces a closer draft. An empty box is refused with **Prompt is required**. |
| **Optional source URL** | empty | Adds text read from a public page to the brief so the draft can follow an existing product page. Paste a full web address, or leave it empty. A readable page is appended as extra context. A page the shop cannot read is ignored and the brief alone is used. |
| **Language** | the shop's default language | The shop language the new product text is stored in. Other languages are not filled by this screen. Name, descriptions, meta and tags are saved only in that language. |
| **Default category ID** | 2 | The category id assigned as the product default category. Type the numeric id from **Catalog**, **Categories**. 2 is usually Home. The new product is placed in that category. |
| **Generate data** | – | Asks the model for the draft and prints it as structured text under the buttons. If the answer cannot be read you see **Failed to parse AI response. Please try again.** |
| **Create product** | – | Inserts the draft. On success the box shows **Product #** followed by the new product's id. Pressing it before generating shows **Generate the product first.** |

The product is created without photos, with the shop's first tax rule and a price taken from the draft; open it afterwards to check the price, tax, photos and stock. If no API key is stored the screen shows **Add an API key in the module settings first.**

### 3.12 Cron

Open **Cron**. This screen builds addresses that your server calls on a schedule to fill product or category fields in small batches. Nothing runs by itself. The shop does nothing until the server requests the address.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron: the category address panel, then the product form with its address and switches.*

**What the screen contains, from top to bottom:** a panel **Category cron** with the category address; the form **CRON JOB Settings – Generate product content using Grok**; the form **CRON JOB Settings - Generate category content using Grok**; and a panel **Cron parameters** with the product address, the chosen field, target and batch size.

**Important:** the addresses shown on this screen end at the secret. For the call to do any work you must add the action to the address. The complete address shapes are in section 4.2. Also, **Enable Cron Feature** must be **Yes**, otherwise every cron call, for products and for categories, answers that the feature is disabled.

**Product form** (press **Save** at the bottom of the form):

| Field | On install | What it does |
|---|---|---|
| **Enable Cron Feature** | No | Allows the server to generate text on a schedule, without an employee clicking through the catalog. Turn this on only after the secret, field, language and prompt below are saved. The server still has to call the address. Enabled makes the saved address do the work. This switch also gates the category address. |
| **Cron Job Secret Token** | a long random value created at install | A long password that must be present in the product address. Without it the shop refuses the call. Keep the generated value. If you replace it, copy the new address into the server scheduler. Anyone who does not know this secret cannot run the product cron. Changing it immediately invalidates the old address. Use at least 24 characters (see section 5.10). |
| **Update Field** | description | The single product field this cron command rewrites: **name**, **description**, **description_short**, **meta_title**, **meta_description** or **tags**. To fill description and meta, create two cron commands with two different fields. Each run writes only that field in the language selected below. |
| **Selected Products** | pendingGrok | Decides which products are still waiting. **pendingGrok** takes products never successfully written by this module in any field. **pendingField** takes products not yet written for this specific field, so you can run several cron jobs (for example description and name) over the same products. **emptyField** takes only products where the chosen field is empty in the chosen language. Each run skips products that no longer match, so a finished catalog stops changing. Failed earlier attempts do not count as written and are retried. |
| **Product Categories** | none ticked | Limits the cron to products that sit in the ticked categories. Tick one or more categories. Leave the tree empty to ignore category and use the other filters only. See section 5.10 before ticking categories. |
| **Product ID list** | empty | Restricts the run to an explicit list of product ids. Type ids separated by commas, for example 12,45,103. Letters and other characters are dropped when you save. Only those products can be updated by this command. |
| **Language** | the shop's default language at install time | The language version of the product field that this cron writes. Choose one shop language. Other languages need their own cron command. |
| **Product to update** | 5 products | How many matching products are processed each time the address is called (2 up to 1000). Start with 5 or 10 so a slow model does not hit the server time limit. Raise it once a run finishes cleanly. |
| **Prompt Template** | none selected | The saved instruction sent to the model for every product in this run. Pick an enabled template from Settings. Placeholders in that template are filled per product. Choose a template before the first call. Changing the template later affects only the next run. |
| **Enable Debug** | No | Shows what the cron would do when you open the address in a browser, without saving products. Enable it while you check the command. Disable it before the server scheduler uses the same address. Enabled prints the plan and does not write catalog text. |
| **CRON JOB interval** | Every Hour | The rhythm you plan to use on the server (**Every 1 Minute** up to **Every 6 Hours**). Match it to the scheduler you will create. The module does not start the scheduler by itself and does not enforce this value. |
| **Product Cron Job command** | – | Shows the base address. Copy it, add the action as described in section 4.2, and paste the result into your server scheduler. You can create as many cron commands as you like. |

**Category form** has the same logic with its own secret and its own batch:

| Field | On install | What it does |
|---|---|---|
| **Cron Job Secret Token** | a long random value created at install | A long password that must be present in the category address. It is separate from the product secret. Keep the generated value. Calls without this secret are refused. Changing it immediately invalidates the old category address. |
| **Update Field** | description | The single category field this command rewrites: **name**, **description**, **meta_title** or **meta_description**. Name, description and meta each need their own command if you want all of them filled. |
| **Selected categories** | pendingGrok | Same three choices as for products (**pendingGrok**, **pendingField**, **emptyField**), applied to categories. Each run skips categories that no longer match. |
| **Language** | the shop's default language at install time | The language version of the category field that this cron writes. Other languages need their own command. |
| **Categories to update** | 5 categories | How many matching categories are processed each time the address is called. Start with 5 or 10. |
| **Prompt Template** | none selected | The saved instruction sent to the model for every category in this run. Write the brief for a category, not a product (for example with `{category_name}`). |
| **Enable Debug** | No | Shows what the category cron would do when you open the address in a browser, without saving categories. Disable it before the scheduler uses the address. |
| **CRON JOB interval** | Every Hour | The rhythm you plan to use on the server. It is only a reminder. |
| **Category Cron Job command** | – | Shows the base address to copy. Add the action as described in section 4.2. |

The category cron never touches the home category itself.

### 3.13 History

Open **History**. This screen is a report of every call to Grok and works as your audit trail.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History: filters, totals, breakdown tables and the list of calls.*

Narrow the cards, the breakdown tables and the history list to one slice of generations. Click a date preset or set **From** and **To**. Then optionally limit by model, type, status, language, employee, a product or category id, or a word that must appear in the prompt or the reply. Press **Filter**. Only matching rows stay visible. The stored history is not deleted and no product is changed.

| Control | On install | What it does |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | first day of the month to today | A custom date range. |
| **Model** | Any | Only calls made with that model. |
| **Type** | Any | Only that kind of call (see the table below). |
| **Status** | Any | **Success** or **Error**. |
| **Language** | Any | Only calls for that language. |
| **Employee** | Any | Only calls started by that employee. Calls started by cron have no employee. |
| **Product / category ID** | empty | Only rows for that id (a product, category, content page or brand with that number). |
| **Prompt or reply contains** | empty | Only rows where the prompt, the reply or the error text contains the word. |
| **Filter** | – | Applies the filters. |

**Cards:** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** and **Average time**. A dash means Grok did not return a token count for that call.

**Breakdown tables:** **By day**, **By model**, **By type**, **By language**, **By employee**, each with **Group**, **Calls**, **Sent**, **Received** and **Total**. A small number next to Calls is the number of errors in that group.

**The list** is titled **Prompt history** and shows 50 rows per page with the columns **ID**, **Status** (a green **Success** or a red **Error** badge), **Prompt**, **Reply / Error**, **Provider** (service, model and time taken, plus a status code from Grok when there is one), **Sent**, **Received**, **Total**, **Entity ID**, **Type** and **Timestamp**. The row action **View** opens the full prompt and reply with the tokens, and **Back to the list** returns. If the row was deleted in the meantime you see **This log entry no longer exists.**

| Type value | Meaning |
|---|---|
| **general** | A free instruction from the Playground or the top-bar shortcut. |
| **singleCategory**, **singleCMS**, **singleBrand** | The top-bar shortcut used while a category, content page or brand was open. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | A product field was written (or tried) by a button, a mass run or cron. |
| **product_seo_pack** | The SEO pack wrote name, descriptions and meta in one go. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | A category field was written. |
| **error** | A failed product call. |

The toolbar button **Clear list** deletes every row in History for good and confirms with **Log list successfully deleted.** That also removes the restore points on product pages and resets the monthly budget count, so use it with care.

### 3.14 Images

Open **Images**. This screen turns the product-page image search on or off and stores the instruction sent to the model.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images: the AI Image Finder switch and its prompt.*

These two fields control the product-page image search. Saving them does not download images and does not change product text. Press **Save**; the confirmation reads **Settings saved.**

| Field | On install | What it does |
|---|---|---|
| **AI Image Finder** | Enabled | Shows or hides the image search on the product edit page. Enable it when editors should look for photos of the current product. Disable it to remove that button. Enabled shows the search. Disabled hides it. An image is imported only after someone confirms it. |
| **AI Image Search Prompt** | Asks for exactly 5 page addresses | The instruction sent when someone searches for product images. The product name and the product description placeholders are replaced with the current product. Keep the request for a list of page addresses (the screen calls it a JSON array of page URLs). Change the wording if you want manufacturer sites or a different number of links. A tighter prompt returns more relevant pages. A vague prompt returns unrelated links. Nothing is saved until an editor picks an image. |

### 3.15 Updates

Open **Updates** (at the far right of the bar).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates: manual check, automatic notifications and the product page link.*

The screen is titled **MyPresta Updates**. It checks MyPresta.eu for a newer module version and can warn you in the back office. The catalog and the generated texts stay as they are.

| Field | On install | What it does |
|---|---|---|
| **Manual Check** | – | Contacts the MyPresta.eu update servers once and compares the remote version with this shop. Click **Check Now** after installing or when you suspect a new release. It shows **Module is up to date!** or **New version available!** next to the button. |
| **Automatic Notifications** | Enabled | Periodically (about every 3 days) checks for updates in the back office. Set **Enabled** to receive a warning banner when a newer version exists. Employees then see a notification with a link to more details. Set **Disabled** if you manage updates manually only. Save with **Save**; the confirmation is **Update settings saved.** |
| **Product Page** | link | Opens the official MyPresta product page for this module in a new tab. |

### 3.16 Working on the product edit page

Open a product (**Catalog**, **Products**, the product), then the **Modules** tab, then **My AI Grok**. The block has up to four tabs: **Generate**, **Simulate**, **Photos** and **History**. Which tabs you see depends on **Product edit page Form** and **Product Edit History** in section 3.4. The product must be saved at least once.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Product edit page, Generate tab: language chips, existing text behavior and one card per field.*

**Generate tab.** Each button writes one product field and the text is saved on the product at once.

- **Language:** one chip per active language, plus **Every language**, which runs each language one after the other.
- **If the field already has text:** **Replace**, **Add above**, **Add below** or **Skip if filled**. They behave as described in section 3.9.
- **Field cards:** **Description** (long text with a short intro and a feature list), **Short description** (a short plain summary, under about 400 characters), **Name**, **Meta title** (about 70 characters), **Meta description** (about 160 characters) and **Tags** (a comma-separated list). Press **Fill** on the card.
- **SEO pack:** **Fill all** fills the name, both descriptions and both meta fields in one request. It is available only on the Generate tab. Afterwards refresh the product page to see the new values.
- **Use your own instruction or a saved prompt:** open this section to filter your saved templates by title or text, pick one (the first tile **Standard brief** uses a ready-made brief for the field you press), or type your own text in **Instruction**. Leave it empty to use the standard brief. If no template matches the filter you see **No prompt matches that filter.**
- The result is also printed in a panel under the cards, with the number of tokens.

After a **Fill**, reload the product page to see the new text in the form.

**Simulate tab.** Try a field first. The reply stays on this page and the product is not changed. It has the same language chips and field cards, but each card has **Try** instead of **Fill**. Every Try still creates a row in History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Simulate tab: **Try** shows the reply without saving.*

**Photos tab.** When **AI Image Finder** is enabled, Grok looks for photos of this product.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Photos tab: find pages, tick photos, add them to the product.*

1. Press **Find pages**. Grok suggests web pages, and the module reads photos from up to five of them (up to 24 photos).
2. Tick the photos you want.
3. Press **Add selected to this product**. The photos are downloaded and attached; the first photo you ticked becomes the cover. Nothing is saved before this step.

Private-network addresses are never opened. If the finder is switched off the tab says that you must enable **AI Image Finder** under Settings, General, and open the product again.

**History tab.** Lists earlier writes for this product with **When**, **Type**, **Status** and a **Restore** button. **Restore** asks **Restore the previous value?** and, once confirmed, puts the earlier text back and tells you to refresh the page. The shop-wide History is not deleted. **Restore** is offered only for successful rows that stored a previous value. The tab shows **No generations for this product yet.** when the list is empty.

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*History tab: earlier writes with a Restore button.*

### 3.17 Other places where the module appears

- **Generate with AI buttons beside fields.** On the product edit form, a small button appears beside the description, short description, meta title and meta description of every language. On the category edit form it appears beside description, additional description, meta title and meta description. Click it. If the shop has more than one language you are asked to choose **Current language**, **All languages** or **Cancel**. The text is placed in the form field. Save the product or category to keep it. A ready-made brief for that field is used, and your Studio rules still apply. If the item was never saved you see **Save the product once before generating.** (or **Save the category once before generating.**). The **Product edit page Form** switch hides only the module block in the **Modules** tab; it does not remove these small buttons.
- **Top-bar shortcut.** With **Admin Top Bar CTA** enabled, a magic-wand icon in the top bar opens a small window: pick a **Template** (optional), type the instruction and press **Generate**. When you are on a category, content page or brand edit screen the matching placeholders are filled. The reply shows in the window and nothing is saved.
- **Product list.** A **My AI Grok** button next to the bulk actions opens **Generate**, **Products**.

## 4. Front shop

The module has no customer-facing screen. It shows nothing in the header, footer or on any product, category or checkout page, and the theme has nothing to display or override. Customers never see any generated-text tool; they only see the text that you have already saved into the catalog.

### 4.1 Addresses used by the module itself

Two web addresses of your shop belong to the module. You never open the first one yourself.

- The **generator address** is called by the buttons inside the back office (Fill, Try, Run, Playground and so on). It is protected by a secret that is built into the back-office pages.
- The **cron address** is called by your server's scheduler, or by you in a browser while testing. It is described below.

### 4.2 Cron address

The address has the shape of your shop address, followed by the module path, the secret and the action. Replace the placeholders with your own values. Use the secret you see on the **Cron** screen and never post it publicly.

For products:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

For categories:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

The address shown on the Cron screen stops after the secret (the category panel adds a different ending that the shop does not use). Add the `action` part yourself. Without an action the shop answers **Invalid action!**

The batch uses the choices saved on the Cron screen: field, selection rule, language, template, batch size and debug. Each call updates one batch and then stops. Every successful write also appears in History with the method **cron**.

To schedule it on a Linux server, create a cron job that fetches the address, for example every ten minutes:

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Keep the address in quotes, because it contains an ampersand. On Windows use the Task Scheduler with a task that opens the address. To test, switch **Enable Debug** to **Yes**, save, and open the address in a browser: the page prints the plan (the parameters, the selected products or categories and the final instruction) and saves nothing. Do not share that output, because it contains your address parameters. Switch debug back to **No** before the scheduler uses the address.

### 4.3 What the cron address answers

| What you see | What to do |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Set **Enable Cron Feature** to **Yes** on the Cron screen and save. |
| **The token does not exist or it's wrong!** | The secret is missing or does not match. Copy the secret again from the Cron screen. |
| **Invalid action!** | The `action` part is missing or misspelled. Use one of the two shapes in section 4.2. |
| **All must include all mandatory parameters!** | A value such as field, target, batch size, language or template is empty. Open the Cron screen, fill it and save. |
| **No valid product IDs provided.** | The Product ID list contains no usable number. Correct or empty the list and save. |
| **No products to update.** or **No categories to update.** | Nothing matches the rule any more. This is the normal end of a finished job. Change the selection rule or the filters to process more. |
| **N products have been updated.** or **N categories have been updated.** | The batch finished. The scheduler will take the next batch on its next call. |
| **Error!** followed by a message (for example **Monthly generation budget reached.** or **Reply rejected by the studio quality gate.**) | Read the message and follow section 5. The run stops at the first error. |
| **Error! The model returned an empty response.** | Raise **Max Tokens** on Settings, Grok, or try another model. |
| **Error! Could not save product** followed by an id | The product could not be saved with the new text, for example because the text was refused by PrestaShop. Check that product and run again. |

## 5. Problems

### 5.1 The installation is refused

- **Symptom:** **This module requires PHP 7.0.0 or newer. This server is running PHP** followed by your version, or **Could not create the module database tables.**
- **Cause:** the server's PHP is too old, or the database user may not create tables.
- **What to do:** ask your hosting provider to switch to PHP 7.0 or newer, or to give the database user permission to create tables, and install again.

### 5.2 The menu entry or the product block is missing

- **Symptom:** no **AI Content Generator** under **Modules**, or no **My AI Grok** block in the product's **Modules** tab.
- **Cause:** a stale cache, missing permissions of your employee profile, or a disabled switch.
- **What to do:** clear the cache in **Advanced Parameters**, **Performance**. In **Advanced Parameters**, **Team**, **Permissions** check that your profile may open the module's screens. If the menu is still missing, uninstall and install the module again. For the product block, check **Product edit page Form** and **Product Edit History** on Settings, General, and save the product once so it has an id.

### 5.3 The key is refused or missing

- **Symptom:** **Grok API KEY field is invalid!** when saving, or **The Grok API key is not set. Add it in the module settings.** when generating, or an error row in History after every attempt.
- **Cause:** the key field is empty or too short, or the key was copied with a typo or has been revoked in xAI.
- **What to do:** open **Settings**, **Grok**, paste a fresh key from https://console.x.ai and press **Save**. Then open **History**, filter **Status** by **Error**, and open the newest row to read the exact answer from Grok.

### 5.4 The model is refused

- **Symptom:** **OpenAi Model field is invalid!**, or errors in History saying the model does not exist or you have no access.
- **Cause:** the model name is too short, mistyped, or your xAI account cannot call that model.
- **What to do:** on **Settings**, **Grok** choose one of the built-in models, or add the exact id from your xAI account with **Add model**, then save.

### 5.5 The call times out

- **Symptom:** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** or, on a screen, **The request timed out or the shop blocked it.**
- **Cause:** a slow model, a very long answer, a busy xAI service, or a server that blocks long requests.
- **What to do:** raise **API timeout (seconds)** on **Settings**, **General** (up to 600), lower **Max Tokens** for short fields, or try a faster model. For cron, lower **Product to update** so a batch fits into the server's time limit.

### 5.6 The answer is empty or cut off

- **Symptom:** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** or **The response was blocked by the provider content filter. Try rewording the prompt.** or **The model returned an empty response.**
- **What to do:** raise **Max Tokens** on **Settings**, **Grok**. For a blocked answer reword the instruction. Then try again.

### 5.7 The monthly budget is reached

- **Symptom:** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **What to do:** open **Settings**, **Studio**, raise **Monthly generation budget** or set it to 0, and save. Failed calls are not counted.

### 5.8 A reply is rejected for a forbidden word

- **Symptom:** **The reply was rejected because it contains a forbidden word from the studio settings.** (cron shows **Reply rejected by the studio quality gate.**). The product is left unchanged and History shows an error row.
- **What to do:** run the generation again (the wording differs each time), shorten **Forbidden words** on **Settings**, **Studio**, or switch **Quality gate** to **Disabled**.

### 5.9 A field is skipped or the text is wrong

- **Symptom:** a row says **skipped** with **Product skipped.** (or **Category skipped.**), or the text was added to the old text instead of replacing it.
- **Cause:** **Existing text** was set to **Skip if filled**, **Add above** or **Add below**.
- **What to do:** choose **Replace** and run again. To undo an unwanted write on a product, use the **History** tab of the product and press **Restore**.

### 5.10 Cron does nothing, repeats, or the address stops working

- **Symptom:** the scheduler runs but nothing is written, or the same products are rewritten, or an address that worked yesterday now answers **The token does not exist or it's wrong!**
- **Cron disabled:** **Cron Job feature is disabled.** Set **Enable Cron Feature** to **Yes** on the Cron screen and save.
- **No action in the address:** you get **Invalid action!** Add the action as shown in section 4.2.
- **Debug left on:** debug prints the plan and never saves. Set **Enable Debug** to **No** and save.
- **No template:** if **Prompt Template** is empty the instruction sent is empty. Choose an enabled template and save.
- **Secret replaced:** the **Generate Token** button next to the secret has no function in this version, so type or paste a long random secret yourself. A secret shorter than 24 characters is replaced by a new random one the next time any back-office page opens, and the old address then stops working. Copy the secret again from the Cron screen.
- **Same products over and over:** when you tick **Product Categories**, products whose default category is ticked are selected on every call, even if the selection rule says they are no longer pending. Leave the category tree empty and limit the cron with **Product ID list** instead, or use the **Generate** screen for category-limited work.
- **Server errors:** cron errors are printed in the response of the address only; they are not stored in History. Run the address in a browser with debug on to read them.

### 5.11 A mass run stops half way

- **Symptom:** the status line stops moving, or some rows have no result.
- **Cause:** the browser tab was closed or reloaded, the computer went to sleep, or a call timed out.
- **What to do:** press **Run** again. Choose **Skip if filled** under **Existing text** so finished fields are not paid for twice. Rows that show an error list the reason; the same reason is in History.

### 5.12 The Generate category content form does nothing

- **Symptom:** after pressing **Generate content** in the form under the category list, you land on the category filter and nothing is written.
- **What to do:** use the **Run on the categories below** button above that form. For product or category filters, the **Module settings** button on the filter screens does not open this module's settings; use the **Settings** item of the navigation bar.

### 5.13 Product Photos problems

- **Symptom:** **Find pages** shows no photos, or you see **No images could be imported.** followed by details.
- **Cause:** Grok suggested pages without usable photos, the page blocked the shop's download, the address pointed to a private network, or the file was not a valid image.
- **What to do:** press **Find pages** again, reword **AI Image Search Prompt** on the **Images** screen (for example ask for manufacturer sites), or upload the photos by hand.

### 5.14 The New product screen fails

- **Symptom:** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** or **Failed to create product**.
- **What to do:** store the API key on **Settings**, **Grok**, write a brief, and press **Generate data** again. Raise **Max Tokens** if the answer looks cut off. If **Create product** fails, check the draft for an empty name.

### 5.15 Restore is not possible

- **Symptom:** **Error! This log entry has no previous value to restore.** or **Error! Nothing to restore for this entry.**
- **Cause:** that row did not store an earlier value (for example a free prompt, or a field that was empty).
- **What to do:** use another row of the same product, or correct the text by hand.

### 5.16 The screen says the token is invalid

- **Symptom:** **Error! Invalid token!** when pressing a button after a long break.
- **Cause:** the back-office page was opened before the module's internal secret was renewed.
- **What to do:** reload the page and try again.

### 5.17 Text is shorter than expected

- **Cause:** PrestaShop limits some fields. The module shortens a name to 128 characters, a short description to 800, a meta title to 69 and a meta description to 159.
- **What to do:** use a more concise instruction, for example by asking for a title under 60 characters.

### 5.18 Technical log and debug

- **Symptom:** you need more detail about a failed call, or the PrestaShop log grows.
- **What to do:** switch **Debug mode** on under **Settings**, **General**, repeat the action, read the new entries in **Advanced Parameters**, **Logs**, and switch debug off again. Also set **Enable Debug** on the Cron screen back to **No** after testing.

### 5.19 Update notifications

- **Symptom:** **Check Now** does not show **Module is up to date!** or **New version available!**
- **Cause:** your server cannot reach the MyPresta.eu update server, which is checked with a short time limit.
- **What to do:** allow outbound connections or try again later. The module works without this check.

## 6. For developers

### 6.1 Overview

- **Main class:** `myaigrok` (file `myaigrok.php`), extends `Module`, version `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Name on the module list:** `My AI Grok - AI content generation`. **Author:** `MyPresta.eu`. **Tab:** `front_office_features`.
- **Compatibility:** PrestaShop 1.6 up to 9.99.99 (`ps_versions_compliancy`). Minimum PHP 7.0.0 (`MIN_PHP_VERSION`); `install()` refuses an older PHP with a translated message.
- **Classes:** the namespace `MyAIGrok\` is loaded by `autoload.php` (no Composer). `MyAIGrok\OpenAIService` is a cURL client for `https://api.x.ai/v1` (`/chat/completions`, `/models`); `MyAIGrok\Studio` applies the house style, the monthly budget and the quality gate. The update checker `myaigrokUpdate` (in `lib/updateChecker.php`) extends `myaigrok`.
- **Data flow:** settings live in `ps_configuration` (prefix `MYPRESTA_MYAIGROK_`). Back-office buttons and mass runs call the front controller `ajax`; schedulers call the front controller `cron`. Both read the settings, pass the prompt through `Studio::gate()` (budget check and `Studio::decorate()`), send it with `OpenAIService::createChatCompletion()`, check the reply with `Studio::inspect()`, write the text to the product or category object, and insert a row in `myaigrok_log`.
- **Provider calls:** model parameters `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty` are sent; parameters a model rejects are learned and stored in `MYPRESTA_MYAIGROK_MODEL_CAPS`. Certificate verification is switched off only when the shop itself runs on localhost.

### 6.2 Files

| Path | Purpose |
|---|---|
| `myaigrok.php` | Module class: install, uninstall, hooks, Settings screens (HelperForm), Dashboard, menu placement, product Modules tab. |
| `autoload.php` | Class loader for the `MyAIGrok\` namespace. |
| `src/OpenAIService.php` | cURL client for Grok: chat completions, model list, timeouts, parameter adaptation. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, SEO pack and alt text prompts. |
| `controllers/admin/AdminMyAIGrok.php` | Generate screens (product and category filters, mass panels). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | New product screen and its Ajax actions. |
| `controllers/admin/AdminMyAIGrokCron.php` | Cron forms. |
| `controllers/admin/AdminMyAIGrokUsage.php` | History report and list. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Images screen and image search/import actions. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Redirect to the module configuration page. |
| `controllers/front/ajax.php` | Generation endpoint used by the back office. |
| `controllers/front/cron.php` | Cron endpoint. |
| `lib/sectionHelp.php` | Content of the Help side panel. |
| `lib/updateChecker.php` | MyPresta.eu update check (`dev.mypresta.eu/update/get.php`; sends module name, version, license key placeholder and shop address). |
| `lib/prestashop9compatibility.php` | Compatibility helpers (token encryption for PS 9). |
| `lib/searchTool/` | Small autocomplete helper loaded on the configuration page. |
| `views/templates/hook/*.tpl` | Hook and screen templates (nav, subnav, dashboard, usage, mass generators, playground, product tabs, cron panels). |
| `views/templates/admin/product_creator.tpl` | New product screen. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Back-office scripts. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Back-office styles. |
| `translations/{iso}.php` | Translation files (many languages). |

### 6.3 Controllers

| Controller | Parent and route | Notes |
|---|---|---|
| `AdminMyAIGrokMain` | Child of the Modules parent tab (`AdminParentModulesSf`, else `AdminParentModules`, else `AdminModules`), menu name **AI Content Generator** | Redirects to `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Hidden child (`active = 0`) of Main | Redirects to `mds_tab=settings`. |
| `AdminMyAIGrok` | Hidden child of Main | `mds_sub=products` or `categories`; submit actions `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Hidden child of Main | Ajax actions `generateProductData`, `extractImages`, `createProduct`, `generateImages` (placeholder). |
| `AdminMyAIGrokCron` | Hidden child of Main | Submit `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Hidden child of Main | Filters `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`; `clear_log` deletes all rows; `view` row action. |
| `AdminMyAIGrokImageFinder` | Hidden child of Main | Actions `searchImages`, `extractImages`, `saveImages`; private-network hosts refused; up to 5 pages and 24 photos. |

Permissions are the standard back-office tab rights of these controllers. Every admin controller redirects to `AdminHome` when the module is disabled. `AdminModules` with `configure=myaigrok` accepts `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` is the Grok tab) and `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) plus `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`): requires `secret_token` equal to `MYPRESTA_MYAIGROK_TOKEN`, otherwise `Error! Invalid token!`. There is no employee check; the token in the page is the only guard. Actions: `initiatePrompt`, `updateSettings` (writes the sampling keys), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (no button in the UI). `updateProduct` and `updateCategory` accept `behavior` values `replace`, `keep`, `keep_top`, `keep_end` and `single_product` / `single_category` (dry run, nothing saved).

**Front `cron`** (`module/myaigrok/cron`): the constructor does all the work. It exits with a message when `ENABLE_CRON` is 0, then requires `secret` equal to either `MYPRESTA_MYAIGROK_SECRET` or `MYPRESTA_MYAIGROK_CAT_SECRET` (either secret is accepted for either action). `action` must be `generateProductContent` or `generateCategoryContent`, otherwise `Invalid action!`. The `entity` parameter shown in the category address of the Cron screen is not read. Optional parameters override the saved choices: for products `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`; for categories `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Allowed targets: `pendingGrok`, `pendingField`, `emptyField`; a wrong value answers `productTarget parameter is wrong! Allowed values: ...`, a wrong field `updatedField parameter is wrong!`. The category list condition for products is added as `p.id_product IN (...) OR p.id_category_default IN (...)` without parentheses, so it is combined with the other conditions by SQL precedence (see section 5.10). Cron errors are echoed and the request exits; they are not written to `myaigrok_log`.

Assets referenced but not shipped in the package: `views/js/admin.js` and `views/css/admin.css` (Main and Settings controllers, unreachable because they redirect first) and `views/js/product_creator.js` and `views/css/product_creator.css` (New product screen; the screen uses `back.js`). The functions `generateTokenAndFill()` and `generateCategoryTokenAndFill()` called by the **Generate Token** buttons are not defined in any shipped script. The **Module settings** buttons on the Generate filter forms link to `configure=mychatgpt`.

### 6.4 Hooks

Registered in `install()`:

| Hook | Behavior |
|---|---|
| `displayAdminProductsExtra` | Renders the My AI Grok block (`product-tab-wrapper.tpl`) in the product Modules tab. Returns nothing when both `PRODUCT` and `PRODUCT_LOG` are 0. |
| `displayBackOfficeHeader` | Calls `ensureLongSecrets()` and `placeModuleMenu()`, adds CSS and JS, publishes JS variables, registers the Image Finder tab once (`IMAGEFINDER_TAB_OK`), loads `product-fields.js` on product and category pages and the product list button script. |
| `displayBackOfficeTop` | Publishes `admin_controller_url` and ids of the category, CMS page or brand being edited, and returns the top-bar generator when `TOPCTA` is 1. |
| `dashboardZoneTwo` | Renders `dashboard.tpl`. Re-registered in `displayBackOfficeHeader` if missing. |
| `displayHeader`, `displayFooter` | Registered; the methods are empty. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Registered; the methods return an empty string or nothing. |

The module overrides neither `enable()` nor `disable()`. Disabling the module only makes its admin controllers redirect to the dashboard of PrestaShop. The method `hookActionProductGridDataModifier` exists but is not registered. The module exposes no hooks of its own.

### 6.5 Overrides

The module has no overrides.

### 6.6 Database

| Table | Content |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Seeded with 16 templates at install. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, `old_` and `new_` pairs for name, description, description_short, meta_title, meta_description and tags, `date_updated`. Keys on `id_product` and `status`. |

The three token columns are added by `ensureUsageColumns()` on the first use when an older table lacks them. Uninstalling drops both tables, deletes all admin tabs (including the legacy `AdminMyAIGrokChangelog`) and the main configuration keys. Generated product and category text is not touched.

### 6.7 Keys and translations

All keys start with `MYPRESTA_MYAIGROK_`. Values after installation:

| Key | Value |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (clamped to 10–600 on save) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 each |
| `IMAGEFINDER_PROMPT` | Default prompt asking for 5 page URLs as a JSON array |
| `TOKEN`, `SECRET`, `CAT_SECRET` | Random 32 characters; `ensureLongSecrets()` regenerates any shorter than 24 characters |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | single space, `grok-4.7`, empty, empty |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | empty |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, empty, shop default language, empty, 0, empty, empty |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, empty, shop default language, 0 |
| `IMAGEFINDER_TAB_OK` | Set after the first back-office load |

The Generate screens also store their last filter values under `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. Uninstalling does not delete these. The update checker uses `mypresta_updates`, `update_myaigrok` and `updatev_myaigrok`. Each admin page load of the configuration deletes the obsolete keys `GEMINI_API_KEY`, `GEMINI_MODEL` and `ACTIVE_SERVICE`.

**Translations:** add a language by creating `translations/{iso}.php`. Module strings use `$this->l()` and `{l s='...' mod='myaigrok'}`. The admin controllers use `trans()` with domains such as `Admin.MyAIGrok` and `Admin.MyAIGrokCron` on PrestaShop 8 and 9, and the module's `l()` on 1.6 and 1.7. These strings are not translated: messages built in `back.js` and `product-fields.js` fallbacks, cron plain-text answers, Image Finder and New product error texts, and the English prompts built by `Studio`. The field descriptions (What it does / How to configure / Effect) are built by `fieldHelp()` in `myaigrok.php` and by the `help()` wrapper in each admin controller; mass generator and Playground texts sit in the templates; the Help panel texts are in `lib/sectionHelp.php`.

### 6.8 Extending

- Add or edit prompt templates in `myaigrok_prompt` (or on the Prompt templates screen); placeholders are replaced in `ajax.php` and `cron.php`.
- Add model ids in **Add a Grok model**; they are stored in `EXTRA_MODELS`.
- Shape output with the Studio rules; they are applied in `Studio::decorate()`.
- Call the cron endpoint with parameter overrides to run different jobs without touching the saved form.
- The front office renders no module template, so the theme has nothing to override.

## 7. Help

Product page of the module: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

To contact support about the module:

1. Log in to your customer account on mypresta.eu.
2. Go to the contact form.
3. Choose the topic **Support for paid modules**.
4. Describe what you did and what you saw. Add the version number shown next to the module name at the top of its screens and, if a generation failed, the text of the error from the **Reply / Error** column of **History**.
