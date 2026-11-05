---
title: "My AI DeepSeek - AI content generation - documentation and user manual"
description: "Setup, daily-use and troubleshooting manual for shop owners who already have the My AI DeepSeek module installed in PrestaShop."
sidebar:
  label: "My AI DeepSeek - AI content generation - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy SEO meta and catalog descriptions with DeepSeek AI Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Requirements

The module writes catalog text through the DeepSeek service, so your shop needs a working connection to DeepSeek and your own DeepSeek account.

- **PrestaShop:** versions 1.6 up to 9.99.99.
- **PHP:** 7.0 or newer. On an older PHP version the installation is refused with a message that names the required and the detected version.
- **PHP extension:** cURL. The shop server must be able to open outgoing HTTPS connections to `https://api.deepseek.com/v1`. If your host blocks outgoing connections, ask the host to allow them.
- **Other modules:** none. The module does not depend on any other module.
- **DeepSeek account:** you need an API key. Create it at https://platform.deepseek.com/api_keys. Usage is billed by DeepSeek to your account, not by MyPresta.eu.
- **Back office language:** the screens are shown in English in this manual. The names in bold are the names you see on screen.
- **Large catalogs:** every generated field is one request to DeepSeek and takes a few seconds. A run over hundreds of products takes a long time, and the browser tab must stay open for the whole run on the Generate screens. For big catalogs prefer the Cron screen, which works in small batches in the background.

## 2. Installation

### 2.1 Upload and install

1. Open **Modules**, then **Module Manager**.
2. Click **Upload a module** and select the ZIP file. Do not unpack it first.
3. When the upload ends, click **Install** (if the button is shown) and then **Configure**.

The installation stores default settings, creates the module tables, adds 16 ready-made prompt templates and adds the module to the back office menu.

### 2.2 What appears in the menu

A new menu entry **AI Content Generator** is added. Its first page is **Dashboard**. Inside the module you move between screens with the navigation bar at the top of every page:

| Navigation item | What it opens |
|---|---|
| **Dashboard** | Charts of requests, errors and tokens. |
| **Settings** | Five sections: **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Two lists: **Products** and **Categories**. |
| **New product** | Creates a product draft from a short brief. |
| **Cron** | Builds scheduled-task addresses for products and categories. |
| **History** | Every request with its prompt, reply, status and tokens. |
| **Images** | Switch and prompt of the product-photo search. |
| **Updates** | Checks whether a newer version is published. |

Hovering over a navigation item shows a short hint in the form What it does / How to configure / Effect.

### 2.3 Cache

The installation does not clear the PrestaShop cache. If the **AI Content Generator** entry is missing in the menu after the first install, clear the cache in **Advanced Parameters**, **Performance** and reload the back office.

### 2.4 Uninstall and reinstall

- **Removed:** the menu entry, the list of prompt templates, the History table with all its rows and the main module settings, including the API key.
- **Kept:** every text already written to products and categories. The module never removes catalog text.
- **Possible leftovers:** a few saved filter values of the Generate screens may remain in the shop configuration. They do no harm.
- **Reinstall:** a new installation starts from defaults. Prompt templates, History and the API key are gone, so note down your own templates and your Studio rules before you uninstall.

## 3. Configuration and daily work in the back office

### 3.1 The whole process at a glance

The module has no steps on the customer side. Your employees start every action in the back office.

1. **Once:** paste the DeepSeek API key and choose a model in **Settings**, **DeepSeek**. Optionally fill **Studio** (brand voice, forbidden words, monthly limit).
2. **Single product:** open a product, go to the **Modules** tab, **My AI DeepSeek**. Use **Generate** to write fields, **Simulate** to try first, **Photos** to find pictures and **History** to restore older text.
3. **Many products or categories:** open **Generate**, filter the list, choose a prompt and a scope and press **Run**. Every row shows its own result when it finishes.
4. **Unattended:** open **Cron**, save a batch definition, copy the address and give it to the server scheduler.
5. **Control:** **History** shows every request. **Dashboard** shows totals. Nothing is lost: the previous text of every written field is kept for **Restore** on the product.
6. **New product from an idea:** **New product** creates a draft and, after you accept it, a real product.

Every request is stored in **History** with its status **Success** or **Error**. A reply that breaks the **Forbidden words** list, or arrives after the **Monthly generation budget** is used up, is not written to the product.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Open **AI Content Generator**, then **Dashboard**. The page charts the DeepSeek requests, tokens and errors stored in **History** for the range you choose. Nothing in the catalog is generated or changed from this page.

| Element | Starting value | What it does |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | the module opens with a default range | Quick date ranges. Click one to redraw the page. |
| **From** / **To** and **Apply** | empty | Your own range. The cards and charts follow it. |
| Line **Active service** | – | Shows which service the module uses. |
| Cards **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Number of stored calls, failed calls, size of the prompts and size of the replies inside the range. |
| Charts **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Day-by-day curves and a split by model. |

The page also appears as a small block on the standard PrestaShop **Dashboard** with quick links to **Generate**, **History** and **Cron**.

### 3.3 Settings – General

Open **Settings**, then **General**. These switches decide how long a call may run and which tools employees see. Saving here does not change any product text.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Live mode** | Disabled | Marks the module as running on the real shop rather than on a trial setup. Enable it on the production shop. On a staging copy leave it disabled if you do not want staff to treat the tools as ready. The tools work the same in both states. |
| **Debug mode** | Disabled | Writes extra diagnostic detail when a DeepSeek call fails. Turn it on only while you investigate an error, then turn it off. Technical messages go to the PrestaShop log. Customers never see them. |
| **API timeout (seconds)** | 120 | How many seconds one call to DeepSeek may run before the module gives up. Use 120 for normal descriptions. Raise it toward 600 for long SEO packs or the reasoning model. Do not go below 10. A short timeout fails fast and writes an error to History. A long timeout waits for a slow reply. |
| **Product Edit History** | Enabled | Shows previous AI writes on the product page so an editor can put an old value back. Disabled hides that list. Past rows stay in **History** either way. |
| **Admin Top Bar CTA** | Enabled | Adds a shortcut in the back office top bar that opens the generator on every page. Disabled removes only that button. The module menu stays. |
| **Product edit page Form** | Enabled | Shows the generator panel and the Generate with AI buttons on the product edit page (PrestaShop 1.7, 8 and 9). Disable it if only mass generation and cron should be used. |
| **AI Image Finder** | Enabled | Lets an editor ask the model for pages that probably hold photos of the current product. Nothing is downloaded until someone confirms an image. Disabled hides the search, and the **Photos** tab then explains how to switch it on. |
| **AI Image Search Prompt** | ready-made English instruction | The instruction sent when someone searches for product images. The product name and the product description are filled in for the current product. Keep the request for a list of page addresses. A tighter prompt gives more relevant pages. |

Press **Save**. A green confirmation appears. The same two image fields exist on **Images**.

### 3.4 Settings – DeepSeek

Open **Settings**, then **DeepSeek**. This is the account and the sampling used by every generation: the product buttons, mass runs, cron and the playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Field | Starting value | What it does |
|---|---|---|
| **DeepSeek API KEY** | empty | The secret that lets this shop call your DeepSeek account. Paste the key from https://platform.deepseek.com/api_keys. Spaces are removed on save (you see a note that the key was cleaned). Leave the field untouched to keep the stored key. An empty or wrong key makes calls fail and the error is written to History. |
| **Model** | `deepseek-chat` | The model that writes the text. Built-in models: `deepseek-chat` (fast, the normal choice) and `deepseek-reasoner` (reasoning model, slower). Models you add yourself are shown too. The next generation uses the selected model. A model your key cannot use returns an API error instead of text. |
| **Add a DeepSeek model** | empty row | Type a model id and press the add button in this row. You see **Model added.** Built-in models cannot be removed (**Built-in models cannot be removed.**). A model that is already built in answers **That model is already built in.** Models you added can be removed from the same row (**Model removed.**). |
| **Max Tokens** | 3200 | Upper limit of the reply length, counted in tokens rather than words. Use about 256 for a meta description and 1000 or more for a full HTML description. A low limit cuts the reply off. A high limit allows longer text and costs more. With `deepseek-reasoner` part of the limit is spent on reasoning, so give it a larger value. |
| **Temperature** | 0.7 | How freely the model chooses words. Stay between 0 and 1. Use about 0.2 for specifications and meta text and about 0.7 for descriptions. Change Temperature or Top P, not both. |
| **Top P** | 1 | Another way to limit how surprising the next word can be. Leave 1 if you already set Temperature. A lower value such as 0.9 gives a tighter vocabulary. |
| **Frequency Penalty Value** | 0 | Reduces lines that repeat the same phrase inside one reply. Try 0.3 to 0.6 only if descriptions keep copying one sentence. Range –2 to 2. |
| **Presence Penalty Value** | 0 | Pushes the reply toward new topics. Use 0 by default. A small positive number helps when every paragraph repeats the same point. Range –2 to 2. |

Press **Save**. The sampling fields do not change which products are updated.

> The reasoning model can ignore Temperature, Top P and the two penalties. If a change in these fields has no visible effect with `deepseek-reasoner`, switch to `deepseek-chat`.

### 3.5 Settings – Studio

Open **Settings**, then **Studio**. Studio adds your house rules on top of every prompt: the product buttons, mass runs and cron. Empty fields are skipped. Text already saved in the catalog is not rewritten when you change a rule.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Brand voice** | empty | Tells the model who is speaking, so product text matches your shop instead of a generic assistant. Write a short brief, for example: specialist workshop, short sentences, no hype. |
| **Audience** | empty | Names the reader the text is written for, for example professional installers or first-time buyers. |
| **Tone** | empty | Sets the mood: formal, warm, technical and so on. One or two words are enough. It does not change the model or the temperature. |
| **Glossary** | empty | Brand names, materials and spellings the model must copy exactly. One term per line. Terms not listed can still be reworded. |
| **Forbidden words** | empty | Words and phrases that must not appear in a saved reply. One per line. Used only when **Quality gate** is enabled. A reply that contains a listed line is rejected and is not written to the product. The attempt stays in History as an error. |
| **Monthly generation budget** | 0 | Caps how many successful generations the shop may run in the current calendar month. Enter a whole number. 0 means no limit. The counter starts again on the first day of the month. After the cap you see **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Failed calls are not counted. |
| **Quality gate** | Enabled | Checks the model reply against **Forbidden words** before anything is saved. Enabled blocks a matching reply. Disabled saves it even if it contains a listed word. |

Press **Save studio**. You see **Studio settings saved.**

### 3.6 Settings – Prompt templates

Open **Settings**, then **Prompt templates**. A template is a saved instruction. Editors pick it instead of typing the same brief again. Only enabled templates are offered on the product page, in mass generation and in cron.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

The installation adds **16 templates**: Product name 1 and 2; Product description 1 to 7 (number 7 uses the product images); Product meta title 1 to 3; Product meta description 1 to 3; Product tags.

**List columns:** ID, **Title**, **Prompt**, **Status** (click the tick to switch Enabled/Disabled), **Timestamp**. Row actions: **Edit** and **Delete**. Bulk action: **Delete** for the ticked rows (confirmation: *Are you sure you want to delete the selected prompts?*).

Use the **+** button in the list header to create a template. The form **Generate Prompt Template** has these fields:

| Field | Starting value | What it does |
|---|---|---|
| **Status** | Enabled / Disabled switch | Shows or hides the template in the lists used on the product page, in mass generation and in cron. Disable a draft instead of deleting it. |
| **Prompt title** | empty (required) | The name editors see in the template list, for example HTML description with features. It is not sent to the model. |
| **Prompt content** | empty (required) | The instruction sent to the model. Write it the way you would brief a copywriter and mention length, HTML and language if they matter. You can use the placeholders `{product_name}`, `{product_brand}`, `{product_features}` and `{product_tags}`. They are replaced with the product you generate for. |

Press **Save Prompt**. Messages: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** If the form is incomplete you see **Failed to edit prompt template! Please fill the form with the right informations!** The button **Go Back to Module Settings** returns to the list.

Write category templates without product placeholders. The category screens do not insert them.

### 3.7 Settings – Playground

Open **Settings**, then **Playground**. It is a scratch pad that calls the active model and prints the reply under the button. No product, category or meta field is changed.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Field | Starting value | What it does |
|---|---|---|
| Large text box (**Ask the model anything about your catalog**) | empty | The instruction for this single call. Write it in plain language. You can mention the shop name, the shop address, a product name, a reference or product features if you want the reply grounded in catalog data. Your Studio rules are added as well. |
| **Generate** | – | Sends the instruction. The reply appears below the button. |

### 3.8 Generate – Products

Open **Generate**, then **Products**. This is a two-step screen. The first step only builds a list. Nothing is sent to DeepSeek until you press **Run** in the second step.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Step 1 – Filter products to update.** The filters are not saved as shop settings. Empty filters do not narrow the list.

| Field | Starting value | What it does |
|---|---|---|
| **Product Categories** | none ticked | Keeps products from the ticked categories. An empty tree leaves this filter off. |
| **Brand** | first (empty) option | Keeps products of one manufacturer. |
| **Product status** | – | **Active** (on sale), **Disabled** (drafts) or **Both**. |
| **Product stock** | – | **Only in stock products** removes products with no quantity. **All products** ignores stock. |
| **Update only** | – | Uses the generation history: products never written by this module, products already written, or **Update all**. Use "not yet updated" for a first pass and "already updated" to rewrite. |
| **Product IDs** | empty | Product numbers separated by commas, for example 12,45,103. |
| **Product Reference** | empty | One or more reference codes separated by commas. |
| **Product Add Date From** / **Product Add Date To** | empty | Creation-date range. Empty means no limit on that side. |
| **Minimum product ID** / **Maximum product ID** | empty | Lowest and highest product number to include. |
| **Product Limit** | empty | Caps how many products are loaded into the list. Use a small number such as 20 on a large catalog so one run cannot walk the whole catalog by accident. |

Press **Go to next step**. The button **Module settings** returns to the module settings.

**Step 2 – Run.** You see **Mass product generation** with the table of the filtered products (columns **ID**, **Reference**, **Result**).

| Field | Starting value | What it does |
|---|---|---|
| **Template** | **Choose a template** | Fills the prompt box from an enabled template. Leave the first option and type your own prompt if you prefer. The title itself is not sent. |
| Prompt box | empty | The text sent for every row. Product placeholders are replaced per row. |
| **What to generate** | **Descriptions** | **Descriptions** writes the long and the short description. **Meta title and meta description** writes both meta fields. **Descriptions and meta together** writes all four. Each field is a separate request. Other fields stay as they are. |
| **Existing text** | **Replace** | **Replace** overwrites. **Skip if filled** keeps filled fields and does not call DeepSeek for them. **Add above** and **Add below** keep the old text and attach the new text. |
| **Languages** | the language of your back office, ticked | Tick every language you want. Unticked languages keep their text. Each ticked language is generated separately. |
| **Run on the list below** | – | Starts the run. Each row shows its result as soon as that product finishes. Products outside the filter are untouched. |

Keep the browser tab open until every row shows a result. A failed row shows the reason; the other rows continue.

### 3.9 Generate – Categories

Open **Generate**, then **Categories**. It works like the product screen, with fewer filters.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Step 1 – Filter categories to update.**

| Field | Starting value | What it does |
|---|---|---|
| **Categories** | none ticked | The categories offered in the list. Leave the tree empty to include every category that matches the status. |
| **Category status** | – | **Active**, **Disabled** or **Both**. |

Press **Go to next step**.

**Step 2 – Mass category generation.**

| Field | Starting value | What it does |
|---|---|---|
| Prompt box | empty | The instruction sent for every category. Describe tone, length and HTML. Product placeholders are not available here. |
| Field select | **Description** | The one field this run writes: **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. |
| Existing data | **Replace** | **Replace** overwrites. **Skip if filled** protects filled fields and does not call DeepSeek for that category. |
| **Language** | your back office language | One language per run. Run again for another language. |
| **Run on the categories below** | – | Starts the run. The table shows **ID** and **Result** per category. |

### 3.10 New product

Open **New product**. It turns a short brief into a product draft and can insert that product into the catalog.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Field | Starting value | What it does |
|---|---|---|
| **What is the product?** | empty | The brief the model expands into a name, descriptions, meta fields, tags, features, reference and price. A few sentences with materials, audience and names to keep give a closer draft. An empty box is refused. |
| **Optional source URL** | empty | A public page (http or https) that describes the product. Its text is added as context. An empty box, or a page the shop cannot read, is ignored. |
| **Language** | your back office language | The language in which name, descriptions, meta and tags are stored. Other languages are not filled here. |
| **Default category ID** | 2 | The number of the category from **Catalog**, **Categories**. 2 is usually Home. The new product is placed there. |
| **Generate data** | – | Shows the draft as text. No product is saved. |
| **Create product** | – | Adds an **active** product in that language and category with name, descriptions, meta, tags, features, price and a stock quantity from the draft. |

If no key is stored you see **Add an API key in the module settings first.** Review the draft, price and stock before you sell: the draft is written by a model.

### 3.11 Cron

Open **Cron**. The page builds addresses that the server's scheduler calls. Each call fills **one batch** and stops. The shop does nothing until your server requests the address.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

The page has two forms: **CRON JOB Settings – Generate product content using DeepSeek** and the matching form for categories. You can create unlimited command variants, one per field.

**Product cron form**

| Field | Starting value | What it does |
|---|---|---|
| **Enable Cron Feature** | No | One switch for the whole shop (products and categories). Turn it on only after the secret, field, language and prompt below are saved. The server still has to call the address. |
| **Cron Job Secret Token** | generated | A long password that must be part of the product address. Without it the shop refuses the call. Keep the value shown after install. If you replace it, copy the new address into the server scheduler at once. The **Generate Token** button on the form may not fill a new value; type a long random string yourself if you need to rotate it. |
| **Update Field** | description | The single product field this command rewrites: name, description, short description, meta title, meta description or tags. To fill several fields create several commands. |
| **Selected Products** | pendingDeepSeek | Which products still wait. **pendingDeepSeek**: products never edited by this module (any field). **pendingField**: products not yet generated for this field, for several commands over the same products. **emptyField**: only products whose field is empty. |
| **Product Categories** | none ticked | Limits the run to the ticked categories. Empty means category is not a filter. |
| **Product ID list** | empty | Only these product numbers, separated by commas. Letters are dropped on save. |
| **Language** | shop default language | One language per command. Other languages need their own command. |
| **Product to update** | 5 products | Batch size per call, from 2 to 1000. Start with 5 or 10 so a slow model does not hit the server time limit. |
| **Prompt Template** | none | An enabled template. Every product in the run is written from that brief. |
| **Enable Debug** | No | **Yes** prints the plan when you open the address in a browser and saves nothing. Set **No** before the scheduler uses it. |
| **CRON JOB interval** | Every Hour | Only a suggestion used to build the command text (from **Every 1 Minute** to **Every 6 Hours**). The module does not start a scheduler. |
| **Product Cron Job command** | – | The finished command to copy. Save the form first. |

**Category cron form** has its own **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (same three rules), **Language**, **Categories to update** (batch size), **Prompt Template** (write the brief for a category), **Enable Debug**, **CRON JOB interval** and **Category Cron Job command**. Defaults: description, pendingDeepSeek, 5 categories, Every Hour.

**Complete the address.** The address shown on the page can be incomplete. Always check that the final address contains the action. Use this shape, replacing the placeholders:

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Use `&action=generateProductContent` for products and `&action=generateCategoryContent` for categories. Without it the call does nothing. If your shop does not use friendly addresses, copy the base address from the page and append the parts with `&`. Do not publish these addresses: the secret in them is the only protection.

Recommended first test: set **Enable Debug** to **Yes**, open the address in your browser and read the plan. Then set it to **No**, schedule the address, and check **History** after the first call.

### 3.12 History

Open **History**. It lists every prompt, reply, status and token count. The page is a report: filtering it does not delete rows and does not change products.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Element | What it does |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Date presets. |
| **From** / **To** | Own date range. |
| **Model**, **Type**, **Status** (**Success** or **Error**), **Language**, **Employee** | Narrow the page to one slice. |
| **Product / category ID** | Only requests for that item. |
| **Prompt or reply contains** | A word that must appear in the prompt or the reply. |
| **Filter** | Applies the filters. |
| Cards **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Totals for the filtered rows. A dash means DeepSeek did not return a token count for that call. |
| Groups **By day**, **By model**, **By type**, **By language**, **By employee** | Breakdown tables. |
| List columns **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | One row per request. Open a row to read the full prompt and reply and the tokens. **Back to the list** returns. |
| **Clear list** | Deletes the history rows. You see **Log list successfully deleted.** The product-page **Restore** points disappear with them. Catalog text is not changed. |

### 3.13 Images

Open **Images**. It stores the switch and the instruction of the product-photo search. Opening this page downloads nothing.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Field | Starting value | What it does |
|---|---|---|
| **AI Image Finder** | Enabled | Shows or hides the photo search on the product edit page. An image is imported only after someone confirms it. |
| **AI Image Search Prompt** | ready-made English instruction | The instruction sent when someone searches. The product name and short description are filled in. Keep the request for a plain list of page addresses. |

Press **Save**. These are the same two settings as in **Settings**, **General**.

### 3.14 Updates

Open **Updates**. It asks MyPresta.eu whether a newer release of this module is published.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Element | Starting value | What it does |
|---|---|---|
| **Automatic Notifications** | follows the saved setting | Lets the back office warn you when a newer version exists. |
| **Check Now** | – | Asks once, immediately. The page then says that this copy is current or that a newer version exists. |
| Link to the module page | – | Opens the module page on MyPresta.eu. |

Your catalog and generated texts are not touched by this page.

### 3.15 The product edit page

Open **Catalog**, then **Products**, edit a product and open the **Modules** tab, then **My AI DeepSeek**. Depending on your PrestaShop version and the settings of **General**, you may also see small **Generate with AI** buttons next to the description, short description and meta fields.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

The tab has four parts: **Generate**, **Simulate**, **Photos** and **History**. If **Product edit page Form** is disabled only **History** remains (when **Product Edit History** is enabled).

**Generate** – each button writes one field and saves the text on the product.

| Control | What it does |
|---|---|
| **Language** buttons | Choose one shop language. **Every language** writes all of them. |
| **If the field already has text** | **Replace** (default), **Add above**, **Add below** or **Skip if filled**. |
| **Description** | The long text, with a short intro and a feature list. |
| **Short description** | A short plain summary, under about 400 characters. |
| **Name** | The product title customers see. |
| **Meta title** | The search-result title, about 70 characters. |
| **Meta description** | The search-result text, about 160 characters. |
| **Tags** | A comma-separated word list. |
| **SEO pack** – **Fill all** | Writes the name, both descriptions and both meta fields in one go. If the reply cannot be used you see **The model did not return a usable SEO pack.** |
| **Fill** | Appears on each field card: generates and saves that field. |
| **Use your own instruction or a saved prompt** | Opens a filter box, tiles with the enabled templates (**Standard brief** is the default) and an **Instruction** box. Leave the box empty to use the standard brief of the field you press. |

**Simulate** – the same field cards with a **Try** button. The reply is shown on this page and the product is **not** changed. Use it to test a prompt, then switch back to **Generate**.

**Photos** – see section 3.16.

**History** – the table **When**, **Type**, **Status** and a **Restore** button. **Restore** puts the previous text of that write back on the product. Rows without a previous value, or with an error, have no button. The shop-wide **History** report is not deleted. An empty list says **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Product photos

Open the **Photos** tab on a product. If **AI Image Finder** is disabled the tab explains how to switch it on under **Settings**, **General**.

1. Click **Find pages**. DeepSeek suggests web pages that probably contain photos of the product.
2. Pages and pictures appear. Tick the pictures you want.
3. Click **Add selected to this product**. Nothing is saved before this click.

The model suggests pages from its own knowledge, not from a live web search. Check the pictures for copyright and quality before you publish them.

## 4. Shop front

The module shows nothing to customers. The two front hooks it registers are empty, and no template, button or block is added to your theme. Text written by the module appears on your shop only as ordinary product and category fields (name, descriptions, meta tags, tags). You do not need to change the theme.

The module also has two addresses that a browser or a server can open:

| Address | Who uses it | What happens |
|---|---|---|
| The **Cron** address with `&action=generateProductContent` or `&action=generateCategoryContent` | Your server scheduler, or you when testing | One batch is written. With **Enable Debug** set to **Yes**, the plan is printed and nothing is saved. A wrong or missing secret is refused. |
| The internal request address used by the buttons of the back office | Your browser while you work in the back office | It needs a token that the back office adds automatically. You never type it. If it is refused, reload the back office page. |

## 5. Problems

**A generation fails and History shows an Error.**
Open **History**, open the row and read the message. The common causes are below.

**The API key is rejected or missing.**
Open **Settings**, **DeepSeek**, paste the key again from https://platform.deepseek.com/api_keys and press **Save**. On the new-product page the warning **Add an API key in the module settings first.** disappears after that. If DeepSeek reports no balance, top up the account at DeepSeek.

**The call ends with a time-out.**
Raise **API timeout (seconds)** in **Settings**, **General** (for `deepseek-reasoner` use several hundred seconds). For cron, lower **Product to update**.

**The text is cut off in the middle of a sentence.**
Raise **Max Tokens** in **Settings**, **DeepSeek**. With `deepseek-reasoner` the limit also covers its reasoning.

**Settings do not seem to change the style.**
With `deepseek-reasoner`, **Temperature**, **Top P** and the two penalty fields can be ignored. Use `deepseek-chat`. Also check that **Studio** is saved and that you used the right language.

**A reply is not saved and nothing changes on the product.**
Possible causes: the reply contains a line from **Forbidden words** and **Quality gate** is enabled (edit the list or disable the gate); **Existing text** is **Skip if filled** and the field has text; the monthly cap is reached (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**The model name I typed does not work.**
You added an id your account cannot call. Select the built-in `deepseek-chat` again and remove your own entry.

**The Generate list is empty or too short.**
Check **Product status**, **Product stock**, **Update only** and **Product Limit**. A common mistake is **Update only** left on "already updated" for a first run.

**The cron does nothing.**
Check in this order: **Enable Cron Feature** is **Yes**; the address ends with the correct `&action=…`; the secret is the one currently shown; **Enable Debug** is **No**; **Selected Products** still has waiting items; the server really calls the address. A finished set stops changing on purpose. For several fields use **pendingField** instead of **pendingDeepSeek**, because the second skips a product as soon as any field has been generated.

**Cron stopped after I changed the secret.**
The old address is no longer valid. Copy the new address (with `&action=…`) into the scheduler.

**The page says "Error! Invalid token!" or buttons stay silent.**
The page was open too long. Reload the back office page and try again.

**The Modules tab of the product has no My AI DeepSeek content.**
Check that **Product edit page Form** or **Product Edit History** is enabled, that the module is active and that the cache is cleared.

**There is no "Restore" button.**
The row was an error, the write had no previous value, or **Clear list** removed the History rows.

**Some labels still say "OpenAi".**
A few messages and filter labels keep an older name, for example **OpenAi Settings Updated** after saving the **DeepSeek** form, the "updated with OpenAi content" options of the **Update only** filter, or an older example model name in a hint. The service used is DeepSeek. In History the **Provider** column can show the older internal name. This does not affect results.

**Nothing changes in the shop front.**
The module writes ordinary product fields. Check the product in the **Catalog** and your theme's cache.

## 6. For the developer

### 6.1 Overview

- **Technical name:** `myaideepseek`
- **Module name in the list:** My AI DeepSeek - AI content generation
- **Version:** 1.0.0
- **Author:** MyPresta.eu
- **PrestaShop compatibility:** 1.6 – 9.99.99
- **PHP:** 7.0 or newer (the installation refuses older versions)
- **Network:** cURL and HTTPS to `https://api.deepseek.com/v1`
- **Configuration prefix:** `MYPRESTA_MYAIDEEPSEEK_`
- **Flow:** settings are read from the configuration table; prompts are built from the template or instruction plus Studio rules; one chat request is sent per field; the reply is checked (Quality gate, budget), saved on the product or category and logged to `myaideepseek_log` with the previous value.

### 6.2 Files

| File | Purpose |
|---|---|
| `myaideepseek.php` | Main class: install, uninstall, settings forms, navigation, hooks, product tab. |
| `autoload.php` | Class loading for `src/` and `lib/`. |
| `src/OpenAIService.php` | HTTP client for the chat completion call (kept under the older file name). |
| `src/Studio.php` | Adds Studio rules and the quality check. |
| `lib/updateChecker.php` | Update check against MyPresta.eu. |
| `lib/sectionHelp.php` | Texts of the help hints. |
| `lib/searchTool/` | Autocomplete helper. |
| `lib/prestashop9compatibility.php` | Compatibility helper for PrestaShop 9. |
| `controllers/admin/` | Seven admin controllers (see 6.3). |
| `controllers/front/ajax.php` | Back office AJAX actions (generate, restore, image search). |
| `controllers/front/cron.php` | Scheduled generation. |
| `views/templates/hook/*.tpl` | Product tab, mass generators, dashboard, cron, history, playground, navigation. |
| `views/templates/admin/product_creator.tpl` | New product screen. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Module translations. |

### 6.3 Controllers

| Class | Role |
|---|---|
| `AdminMyAIDeepSeekMain` | Menu parent **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` or `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Settings entry (the forms live on the module configuration page). |
| `AdminMyAIDeepSeekCron` | **Cron** forms. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Needs the parameter `secret_token` equal to `MYPRESTA_MYAIDEEPSEEK_TOKEN`; otherwise it answers *Error! Invalid token!* |
| `ModuleFrontController` cron | Needs `secret` equal to the product or the category secret. |

The module configuration page uses `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = the **DeepSeek** section, `studio`, `templates`, `playground`) and `mcg_preset` for the date presets.

Cron query parameters read by `controllers/front/cron.php`:

| Parameter | Used for | Default when absent |
|---|---|---|
| `secret` | Product or category secret (required) | – |
| `action` | `generateProductContent` or `generateCategoryContent` (required) | – |
| `updatedField` | Field to write | stored value |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | stored value |
| `productsToUpdate` / `categoriesToUpdate` | Batch size | stored value |
| `languageId` | Language | stored value |
| `promptTemplateId` | Template | stored value |
| `debug` | Print the plan only | stored value |
| `categories` | Category filter (products) | stored value |
| `productIds` | Product id filter | stored value |

### 6.4 Hooks

Registered: `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (both return an empty string), `actionProductFormBuilderModifier` (returns without output), `displayAdminProductsExtra` (the **Modules** tab content), `displayBackOfficeHeader` (assets, product page loader), `displayBackOfficeTop` (top bar shortcut), `dashboardZoneTwo` (block on the PrestaShop dashboard), `displayHeader` and `displayFooter` (both empty). The module exposes no hooks of its own. It has no `enable()` or `disable()` override.

### 6.5 Overrides

None.

### 6.6 Database

| Table | Content |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 rows after install. |
| `myaideepseek_log` | One row per request: ids of product, category, CMS, manufacturer, language and employee; `type`, `method`, `status`, service, `model`, HTTP code, duration, token counts, error message, `prompt`, `reply`, and the old and new values of name, descriptions, meta fields and tags. |

Uninstall drops both tables. Tabs are removed. Product and category text is not touched.

### 6.7 Keys and translations

All keys carry the prefix `MYPRESTA_MYAIDEEPSEEK_`.

| Key suffix | Default | Meaning |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Call timeout in seconds. |
| `PRODUCT_LOG` | 1 | Product edit history. |
| `TOPCTA` | 1 | Top bar shortcut. |
| `PRODUCT` | 1 | Product page generator. |
| `IMAGEFINDER_ENABLE` | 1 | Photo search switch. |
| `IMAGEFINDER_PROMPT` | built-in English text | Photo search instruction. |
| `API_KEY` | empty | DeepSeek key. |
| `MODEL` | `deepseek-chat` | Active model. |
| `EXTRA_MODELS` | empty | Models added by the merchant, one per line. |
| `MODEL_CAPS` | empty | Parameters learned per model at runtime. |
| `TEMPERATURE` | 0.7 | Sampling. |
| `MAX_TOKENS` | 3200 | Reply limit. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Sampling and penalties. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | empty | Studio rules. |
| `BUDGET` | 0 | Monthly cap, 0 = none. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | random | Token of the AJAX address. |
| `SECRET`, `CAT_SECRET` | random | Product and category cron secrets. |
| `ENABLE_CRON` | 0 | Global cron switch. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Suggested interval (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Cron field. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Cron rule. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Cron batch. |
| `promptTemplateId`, `catpromptTemplateId` | empty | Cron template. |
| `languageId`, `catlanguageId` | default language | Cron language. |
| `debug`, `catdebug` | 0 | Cron debug. |
| `productIdsList`, `categories` | empty | Cron filters. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | empty / set at runtime | UI state. |

The default model is `deepseek-chat`. Built-in models are `deepseek-chat` and `deepseek-reasoner`. Uninstall deletes the keys above. Generate filter keys (for example the category, brand and status filters of the **Generate** forms) are not in the uninstall list and may remain.

Translations: add `translations/{iso}.php` in the standard PrestaShop format. Field help texts are built by `fieldHelp()` in the form What it does / How to configure / Effect and pass through `$this->l()`. Some strings in the product tab and the generate templates are defined in the `.tpl` files with `{l s=…}`. A few leftover strings still contain the older provider name (see Problems).

### 6.8 Extending

The product tab, mass screens and cron use the same prompt placeholders and the same AJAX actions, so a custom template that follows `{product_name}`, `{product_brand}`, `{product_features}` and `{product_tags}` works everywhere. The front controllers render no template, so a theme has nothing to override. Admin templates in `views/templates/hook/` can be overridden through the standard module template override of your back office theme.

## 7. Help

Module page: https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

To write about the module:

1. Log in to your customer account at mypresta.eu.
2. Open the contact page.
3. Choose the subject **Support for paid modules**. The form says that you must be logged in. After logging in, select this module from your purchase history.
4. Describe the problem. Add the row from **History** (status and message) and the PrestaShop and PHP versions. Never send the API key or the cron secret.
