---
title: My AI Gemini - AI content generation - documentation and user manual
description: Setup, daily-work and troubleshooting guide for shop owners who already have the My AI Gemini module installed in their PrestaShop back office.
sidebar:
  label: My AI Gemini - AI content generation - documentation and user manual
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product and Category Descriptions with Gemini Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Screenshots in this manual come from an English back office. Every button and field name is written exactly as it appears on screen.

## 1. Requirements

Before you start, check that your shop and server meet the points below.

- **PrestaShop:** 1.6, 1.7, 8 and 9 (all versions from 1.6 up to 9.99.99).
- **PHP:** 7.0 or newer. The installer refuses to continue on an older PHP and shows the message "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **PHP extensions:** cURL (every call to Gemini and every page download), JSON, DOM (reading web pages for New product and for the photo search), mbstring and fileinfo (checking downloaded pictures).
- **Outgoing connection:** your server must be allowed to open secure (HTTPS) connections to the Google Gemini service. If the server blocks outgoing connections, nothing can be generated.
- **Other modules:** the module does not need any other module.
- **Google account:** you need your own Google Gemini API key. Create it at https://aistudio.google.com/apikey and keep it private. Google bills or limits usage according to your own Google account, not through this module.
- **Time and size:** every field is one request to Gemini. Long texts and slow models can take more than a minute per request. A large mass run or a large cron batch takes as long as all its requests added together, so start with small lists.

## 2. Installation

1. Open **Modules**, then **Module Manager**.
2. Click **Upload a module** and drop the ZIP file, or upload it with your usual method.
3. Click **Install** next to the module when it appears on the list, and confirm.
4. After installation a new entry named **AI Content Generator** appears in the left menu inside the **Modules** section. Click it: it opens the module **Dashboard**. The same screens are also reachable from **Module Manager**, **Configure**.
5. Before anything can be generated, open **Settings**, then **Gemini**, paste the key into **Google Gemini API KEY** and save (details in chapter 3).

The installation creates 16 ready-made prompt templates (product names, descriptions, meta titles, meta descriptions and tags) so you can try the module immediately. It does not clear the shop cache. If the menu entry does not appear, open any back-office page once more: the module puts the menu entry back in place every time a back-office page loads.

**Uninstalling.** Uninstalling removes the **AI Content Generator** menu entry, deletes the prompt templates and the whole History (so the restore lists on products disappear too), and deletes the module settings, including the API key and the cron secrets. It does not touch texts, pictures and products that were already written or created with the module. A few screen filters that you used on the **Generate** pages may stay stored in the shop settings; they are harmless. Installing again starts from a clean state: the 16 default templates come back, and old settings, templates and History are not restored.

## 3. Configuration and daily work in the back office

### 3.1 The whole process, step by step

1. **Connect Gemini.** **Settings**, **Gemini**: paste the API key, keep or change the model, save.
2. **Test.** **Settings**, **Playground**: type a short instruction and press **Generate**. If you see a reply, the connection works. Nothing is saved in your catalog.
3. **Set the shop style (optional).** **Settings**, **Studio**: write the brand voice, audience, tone, words to keep and words to ban.
4. **Prepare instructions.** **Settings**, **Prompt templates**: keep the default templates or add your own. Enabled templates are offered everywhere else.
5. **Choose how to work:**
   - One product at a time: open the product, then **Modules**, **My AI Gemini**, and press **Fill** next to a field (3.16).
   - Many products or categories: **Generate**, **Products** or **Categories** (3.9 and 3.10).
   - A product that does not exist yet: **New product** (3.11).
   - Automatically, in small batches, without anyone clicking: **Cron** (3.12).
6. **Check the result.** **History** lists every request with its prompt, reply, status and token use. **Dashboard** shows the same numbers as charts.
7. **Undo.** On a product, **Modules**, **My AI Gemini**, **History**: **Restore** puts the previous text back.

Texts are saved straight into the product or category as soon as Gemini answers, except where this manual says otherwise (the **Try** buttons, the **Playground**, **Generate data**, and the **Generate with AI** buttons next to fields, which only put the text into the open form until you save).

### 3.2 Opening the module and moving around

Open **AI Content Generator** in the left menu. The bar at the top of every screen has these items: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images**, and on the far right **Updates**. Hold the mouse over an item to see a short explanation. Under **Settings** a second row appears with **General**, **Gemini**, **Studio**, **Prompt templates** and **Playground**. Under **Generate** the second row shows **Products** and **Categories**.

The round **Help** button at the edge of every module page opens a side panel with a short explanation of the page you are on. One line in that panel still refers to an OpenAI account (see chapter 5); use your Google Gemini key.

You can also reach the module from **Module Manager** with the **Configure** button, from the shortcut button in the top bar (3.18) and from a link on the product list (3.18).

### 3.3 Dashboard

The **Dashboard** is a report. It never writes product or category text.

![My AI Gemini – Dashboard with date range, cards and charts](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

At the top you pick the period. The line **Active service** always shows Gemini and the model saved on the **Gemini** screen.

| Field | On start | What it does |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Quick period buttons. The chosen one is highlighted. Only the numbers and charts on this page change. |
| **From** and **To** | Dates of the last 30 days | Your own period. Press **Apply** to redraw. If From is later than To, the module swaps them. |
| **Apply** | – | Redraws the cards and charts for the dates you typed. |
| **Requests** | Counted from History | Every stored call in the period, successful or failed. |
| **Success** | Counted from History | Calls that did not end with an error. |
| **Errors** | Counted from History | Calls that ended with an error. |
| **Tokens sent** | Counted from History | Total size of your instructions sent to Gemini. |
| **Tokens received** | Counted from History | Total size of the replies. |
| **Requests and errors** chart | – | Line chart, one point per day. For periods longer than 120 days one point covers a week. |
| **Tokens sent and received** chart | – | Same period, two lines. |
| **Requests by model** chart | – | Bar chart: how many requests each model handled. |

If the charts are empty, nothing was generated in that period. The Dashboard also exists as a small block on the main PrestaShop dashboard, but that block does not receive the History figures, so its cards and charts stay empty. Use the module **Dashboard**.

### 3.4 Settings – General

Open **Settings**, then **General**. These switches decide what employees see in the back office. Saving does not rewrite any product text.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Field | On start | What it does |
|---|---|---|
| **Live mode** | Disabled | Marks the module as running on the real shop. Enable it on the production shop. Leave it disabled on a test copy to signal that the setup is not the production one. The same tools work in both states. |
| **Debug mode** | Disabled | Writes extra technical messages to the PrestaShop log (**Advanced Parameters**, **Logs**) when a Gemini call fails. Turn it on only while you investigate an error, then turn it off. Customers never see it. |
| **API timeout (seconds)** | 120 | How many seconds one call to Gemini may run before the module gives up. 120 suits normal descriptions. Raise it up to 600 for long SEO texts or slow models. Values below 10 become 10, values above 600 become 600, an empty or non-numeric value becomes 120. A short timeout fails fast and records an error. |
| **Product Edit History** | Enabled | Shows the **History** tab with **Restore** buttons on the product page (**Modules**, **My AI Gemini**). Disabled hides that list. Past rows stay in the shop-wide **History** either way. |
| **Admin Top Bar CTA** | Enabled | Puts a small magic-wand button in the top bar of every back-office page that opens a prompt box. Disabled removes only that button. The module menu stays. |
| **Product edit page Form** | Enabled | Shows the generator panel under **Modules**, **My AI Gemini** on the product page. Enable it for catalog editors. Disable it if only mass generation and cron should be used. |
| **AI Image Finder** | Enabled | Shows the **Photos** tab on the product page. Disabled hides it. A picture is imported only after someone ticks it and confirms. |
| **AI Image Search Prompt** | A built-in English instruction asking for 5 page addresses | The instruction sent when someone looks for product pictures. Words {product_name} and {product_description} are replaced with the current product. Keep the request for a list of page addresses. A tighter prompt gives more relevant pages. |
| **Save** | – | Stores all fields above. Message: **Settings Updated**. |

The two image fields appear both here and on the **Images** screen (3.14). They are the same two settings.

### 3.5 Settings – Gemini

Open **Settings**, then **Gemini**. Here you connect the Google account and set how varied the wording is. Every generation (product buttons, mass runs, cron, New product, photo search, Playground) uses these values.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Field | On start | What it does |
|---|---|---|
| **Google Gemini API KEY** | Empty | The secret that lets your shop call your Gemini account. Paste the key from https://aistudio.google.com/apikey. Spaces at the start and end are removed. If you leave the box untouched, the stored key stays. An empty or wrong key makes calls fail and the error is written to History. |
| **Model** | gemini-2.0-flash | The Gemini model that writes the text. Built-in choices: gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. The next generation uses the model you save. A model your key cannot use returns an error instead of text. |
| **Add a Gemini model** (box with **Add model**) | – | Adds a model name that is not in the built-in list. Type the exact name from your Gemini account, press **Add model**. The name appears in **Model** and is selected at once. Added names have a **Remove** link next to them. Built-in names cannot be removed. |
| **Max Tokens** | 3200 | Upper limit on the length of a reply, counted in tokens, not words. About 256 is enough for a meta description, 1000 or more for a full HTML description. A low limit cuts the reply off. A high limit allows longer text. Some Gemini 2.5 models spend part of this limit on thinking, so keep it generous for them. |
| **Temperature** | 0.7 | How freely the model picks words. Stay between 0 and 1. About 0.2 suits specifications and meta text, about 0.7 suits descriptions. A low value repeats a similar structure. A high value gives more varied wording and more risk of leaving the brief. |
| **Top P** | 1 | A second way to narrow the choice of the next word. In this version the value is saved but not sent to Gemini, so changing it does not change the replies. |
| **Frequency Penalty Value** | 0 | Intended to discourage repeated phrases. Saved but not sent to Gemini in this version, so it has no effect on replies. |
| **Presence Penalty Value** | 0 | Intended to push the text toward new points. Saved but not sent to Gemini in this version, so it has no effect on replies. |
| **Save** | – | Stores the form. Message: **OpenAi Settings Updated** (the module still uses the older wording here). |

Messages you can see on this screen:

| Message | Cause | What to do |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | The key box is shorter than 10 characters and no key is stored yet. | Paste the full key and press **Save** again. |
| **OpenAi Model field is invalid!** | The model name is shorter than 3 characters. | Choose a name from the **Model** list. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | The stored key had spaces around it. | Nothing: the module fixed it. |
| **Model added.** | The new name was stored and selected. | Press **Save** if you also changed other fields. |
| **That model is already built in.** | The name you typed is already in the list. | The module selects it for you. |
| **Model removed.** | An added name was deleted. | If it was the active model, choose a Gemini model again (see chapter 5). |
| **Built-in models cannot be removed.** | You tried to remove a built-in name. | Nothing to do. |
| **Enter a model id such as gpt-4.1.** | The model name box was empty or had illegal characters. | Type a Gemini name, for example gemini-2.5-flash. The example in this message is a leftover. |

### 3.6 Settings – Studio

Open **Settings**, then **Studio**. Studio adds house rules on top of every prompt: product buttons, mass runs, cron and the Playground. Empty fields are skipped. The module also always tells Gemini to write in the language of the item being generated.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Field | On start | What it does |
|---|---|---|
| **Brand voice** | Empty | Tells the model who is speaking so the text sounds like your shop. Write a short brief, for example: specialist workshop, short sentences, no hype. Changing it does not rewrite text that is already saved. |
| **Audience** | Empty | Names the reader, for example professional installers or first-time buyers. New replies use vocabulary aimed at that reader. |
| **Tone** | Empty | One or two words for the mood: formal, warm, technical. It does not change the model or the temperature. |
| **Glossary** | Empty | Brand names, materials and spellings the model must copy exactly. One term per line. Terms not listed can still be reworded. |
| **Forbidden words** | Empty | Words and phrases that must not appear in a saved reply. One per line. The list is also sent to the model as words to avoid. Rejecting a matching reply happens only when **Quality gate** is enabled. |
| **Monthly generation budget** | 0 | Maximum number of successful generations in the current calendar month, counted from History. 0 means no limit. When the cap is reached, new requests stop with a budget message until the next month. Failed calls are not counted. |
| **Quality gate** | Enabled | Checks every reply against **Forbidden words** before anything is saved. Enabled rejects a matching reply: the product stays unchanged and History records an error. Disabled saves the reply even when it contains a listed word. With an empty Forbidden words list the gate has nothing to check. |
| **Save studio** | – | Stores the form. Message: **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Open **Settings**, then **Prompt templates**. A template is a saved instruction. Editors pick it by title instead of typing the same brief again.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

The list shows these columns: **ID**, **Title**, **Prompt**, **Status** (click the tick or cross to enable or disable the template), **Timestamp**. Each row has **Edit** and **Delete**. Tick several rows and use the bulk action **Delete** (you are asked "Are you sure you want to delete the selected prompts?"). The green plus button above the list creates a new template.

The template form:

| Field | On start | What it does |
|---|---|---|
| **Status** | Enabled / Disabled switch | Shows or hides the template in the lists used on the product page, in the top-bar prompt box, in mass generation and in cron. Enable templates your staff should use. Disable a draft instead of deleting it. |
| **Prompt title** | Empty (required) | The name editors see in the list. It is not sent to Gemini. Use a short label, for example HTML description with features. |
| **Prompt content** | Empty (required) | The instruction sent to Gemini. Write it as you would brief a copywriter: length, HTML, language. You can use placeholders (3.19). Double quotation marks are changed to single quotation marks when you save. |
| **Save Prompt** | – | Stores the template. |
| **Go Back to Module Settings** | – | Returns to the list without saving. |

Messages: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** followed by a number, **Failed to edit prompt template! Please fill the form with the right informations!**.

The 16 default templates are: Product name 1–2, Product description 1–7 (the seventh embeds the product picture links), Product meta title 1–3, Product meta description 1–3 and Product tags. Two of the meta description templates mention a smartwatch; edit them before use if you sell something else. Template texts are stored in the language the shop used at installation.

### 3.8 Settings – Playground

Open **Settings**, then **Playground**. It is a scratch pad: it sends one free instruction to the active model and shows the reply on the page.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Type the instruction in the large box ("Ask the model anything about your catalog").
2. Press **Generate**.
3. Read the reply under the button, with the number of tokens used.

You can mention the shop name, shop address, a product name, reference or features if you want the reply based on catalog data. Studio rules are applied. No product, category or meta field is changed, and the call is recorded in History. If the box is empty you see "Write a prompt first." Use the Playground to test the key and to polish a prompt before you turn it into a template.

### 3.9 Generate – Products

Open **Generate**, then **Products**. Mass generation has two steps. Nothing is sent to Gemini during step 1.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Step 1 – filter the products.** All filters are optional and are not saved as shop settings.

| Field | On start | What it does |
|---|---|---|
| **Product Categories** | Nothing ticked | Keeps products that sit in, or have as main category, any ticked category. An empty tree does not filter by category. |
| **Brand** | **Select brand** | Keeps products of one manufacturer. The first option means every brand. |
| **Product status** | **Active** | **Active** keeps products on sale, **Disabled** keeps switched-off products, **Both** keeps all. |
| **Product stock** | **All products** | **Only in stock products** drops products with no available quantity. |
| **Update only** | **Update all** | Uses History. The first option keeps products that were never written by this module. The second keeps products that already were. The labels still say "OpenAi content" (see chapter 5). |
| **Product IDs** | Empty | Type ids separated by commas, for example 12,45,103. Only those products can appear. |
| **Product Reference** | Empty | Type one or more references separated by commas. |
| **Product Add Date From** / **Product Add Date To** | Empty | Keep products created after the first date and before the second. |
| **Minimum product ID** / **Maximum product ID** | Empty | Keep products inside that id range. |
| **Product Limit** | Empty | Maximum number of products loaded into the list. Use a small number such as 20 the first time. |
| **Go to next step** | – | Builds the list. |
| **Module settings** | – | Button next to **Go to next step**. It opens another module's settings page (see chapter 5); use **Settings** in the module bar instead. |

**Step 2 – write.** The page now shows the panel **Mass product generation** with a table of the found products (columns **ID**, **Reference**, **Result**).

| Field | On start | What it does |
|---|---|---|
| **Template** | **Choose a template** | Copies the text of an enabled template into the box below. The title itself is not sent. |
| Large prompt box | Empty | The instruction sent for every product. Placeholders are filled for each product (3.19). If you leave it empty, a standard instruction for each field is used. |
| **What to generate** | **Descriptions** | **Descriptions** writes the long and short description. **Meta title and meta description** writes both meta fields. **Descriptions and meta together** writes all four. Each field is its own request. Other fields (including the product name and tags) are never changed here. |
| **Existing text** | **Replace** | **Replace** overwrites the field. **Skip if filled** leaves a filled field alone and sends nothing to Gemini for it. **Add above** and **Add below** keep the old text and attach the new text before or after it. |
| **Languages** | The language you use in the back office is ticked | Tick every language you want. Each ticked language is generated separately. At least one must be ticked ("Select at least one language."). |
| **Run on the list below** | – | Starts the run. |

During the run the line above the button shows progress, for example "3 / 40 – description". Each table row shows a result such as "description: success Content successfully generated and updated to product." or "description: skipped Product skipped." or an error text. The run takes products one by one and saves each reply immediately, so a failure on one product does not undo the ones already saved. Do not close the page until you see "Finished … products."

### 3.10 Generate – Categories

Open **Generate**, then **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Step 1 – filter the categories.**

| Field | On start | What it does |
|---|---|---|
| **Categories** | Nothing ticked | Tick the categories to include. An empty tree includes every category matching the status. |
| **Category status** | **Active** | **Active**, **Disabled** or **Both**. |
| **Go to next step** | – | Builds the list. Nothing is generated yet. |
| **Module settings** | – | Opens another module's settings page (see chapter 5). |

**Step 2 – write.** The panel **Mass category generation** lists the categories (columns **ID**, **Result**).

| Field | On start | What it does |
|---|---|---|
| Large prompt box | Empty | The instruction sent for every category. You can use {category_name}, {category_description}, {category_parent_name} and the shop placeholders (3.19). Always type a prompt here: for categories there is no standard instruction. |
| Field list | **Description** | **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. Only that field is saved. |
| Existing text list | **Replace** | **Replace** overwrites. **Skip if filled** leaves a filled field alone. |
| Language list | Your back-office language | One language per run. Run again for another language. |
| **Run on the categories below** | – | Starts the run. Each category is saved as soon as its reply arrives. |

Below the table there is a second form titled **Generate category content** with a **Generate content** button. It does not generate anything: it only returns you to the category filter. Always use **Run on the categories below**.

### 3.11 New product

Open **New product**. This screen turns a short brief into a draft of a product that does not exist yet.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Field | On start | What it does |
|---|---|---|
| **What is the product?** | Empty | The brief. Write a few sentences with materials, audience and names that must stay. A richer brief gives a closer draft. An empty brief is refused. |
| **Optional source URL** | Empty | A full address of a public page about the product. Text from the page (title, description, price) is added to your brief. An empty box or a page the shop cannot read is ignored. |
| **Language** | Shop default language | The language in which name, descriptions, meta and tags are stored. Other languages are not filled. Choose the shop default language, because PrestaShop expects a name in it. |
| **Default category ID** | 2 | The number of the category in Catalog, Categories. 2 is usually Home. The new product is placed in that category and it becomes the default category. |
| **Generate data** | – | Asks Gemini for a draft and prints it below as structured text (name, descriptions, meta, tags, reference, price, features). No product is saved. |
| **Create product** | – | Saves the draft as a new active product. It sets name, descriptions, meta, tags, features, reference and price from the draft, visibility everywhere, and a stock quantity of 100. No pictures are attached; add them afterwards (3.16). Result line: "Product #" followed by the new product number. |

If no API key is saved you see "Add an API key in the module settings first." Pressing **Create product** before **Generate data** shows "Generate the product first." After creating, check the price, tax and pictures: the module sets the first tax rule group and the price suggested by Gemini.

### 3.12 Cron

Open **Cron**. Cron is for the server, not for a person: your server calls a secret web address on a schedule and the shop fills a small batch of products or categories each time. Nothing happens until the server requests the address.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

The screen has two forms: one for products and one for categories. Each has its own **Save** button, and no confirmation message is shown after saving.

**Product cron form**

| Field | On start | What it does |
|---|---|---|
| **Enable Cron Feature** | **No** | Switch for the whole cron (products and categories). While it is **No**, every call is refused with "Cron Job feature is disabled. You can enable it from the module settings." Turn it on only after the other fields are saved. |
| **Cron Job Secret Token** | A long random value | The password that must be in the address. Without it the shop refuses the call. Replacing it invalidates the old address. The **Generate Token** button next to the field may not do anything in this version; if it does not, type a long value yourself. |
| **Update Field** | **description** | Which single product field the cron rewrites: **name**, **description**, **description_short**, **meta_title**, **meta_description** or **tags**. To fill several fields, create several cron commands. |
| **Selected Products** | **pendingGemini** | Which products are still waiting. **pendingGemini**: products this module never wrote successfully (any field). **pendingField**: products not yet generated for the chosen field, so one catalog can be processed by several cron jobs. **emptyField**: only products whose chosen field is empty in the chosen language. |
| **Product Categories** | Nothing ticked | Limits the run to ticked categories (see chapter 5 for a caution). |
| **Product ID list** | Empty | Explicit product ids separated by commas. Characters other than digits are dropped when you save. |
| **Language** | Shop default language | The language version that is written. |
| **Product to update** | 5 products | Batch size per call: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 or 1000. Start with 5 or 10 so a slow model does not hit the server time limit. Products are taken in order of ID. |
| **Prompt Template** | First template on the list | The saved instruction used for every product. Placeholders are filled per product (3.19). |
| **Enable Debug** | **No** | **Yes** makes the address print the plan (query, selected products, final prompts) and save nothing. Turn it off before the server scheduler uses the address. |
| **CRON JOB interval** | **Every Hour** | A suggestion shown for your own scheduling. The module does not run a scheduler. Set the real timing in your server. |
| **Product Cron Job command** | – | Shows the address prefix. In this version the command line on screen is incomplete (see below). |
| **Save** | – | Stores the product cron settings. |

**Category cron form** has its own **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (same three modes), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** and **Save**. It always skips the shop root category.

**The address you give to the server.** Above the forms the screen prints a product address and a category address, each ending after the secret. The server also needs to be told which job to run. Add this to the end of the address on screen:

| Job | Complete address | Notes |
|---|---|---|
| Products | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Use the secret from the product form. |
| Categories | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | The category line on screen ends with `&entity=category`; replace that ending with `&action=generateCategoryContent`. |

Optional extras you may append to override the saved form for one command: for products `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (ids separated by commas), `productIds`; for categories `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. Values not appended come from the saved form.

**Scheduler.** In your hosting panel create a scheduled task that opens the complete address, for example with `curl -s "ADDRESS"` every hour. First test in a browser with **Enable Debug** set to **Yes**: you see which products would be processed and the final prompts. Then set it to **No** and open the address once more. Each real call updates one batch and stops.

Answers you may see when the address is opened:

| Answer | Cause | What to do |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | The batch worked. | Nothing. |
| **N pending products.** | Debug is on, nothing was saved. | Turn debug off when satisfied. |
| **No products to update.** / **No categories to update.** | Nothing matches **Selected Products** and the other filters any more. | The job is finished, or change the rule. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** is **No**. | Set it to **Yes** and press **Save**. |
| **The token does not exist or it's wrong!** | The secret is missing or does not match. | Copy the address again from the screen. |
| **Invalid action!** | The address has no `action` part, or a wrong one. | Add the `action` part from the table above. |
| **updatedField parameter is wrong!** | The field is not allowed for that job. | Choose a field from the form. |
| **All must include all mandatory parameters!** | A saved value (for example the template) is empty. | Choose a **Prompt Template** and save. |
| **productTarget parameter is wrong! Allowed values: …** | The mode name in the address is wrong. | Use one of the three modes. |
| **Error!** followed by a message | Gemini refused or failed. | Read the message, then check History. |
| **Error! The model returned an empty response.** | Gemini returned nothing, for example the Max Tokens limit was too low. | Raise **Max Tokens** on the **Gemini** screen. |
| **Monthly generation budget reached.** | The Studio budget is used up. | Raise the budget or wait for next month. |
| **Reply rejected by the studio quality gate.** | The reply contained a forbidden word. | Edit the list or the template. |
| **Error! Could not save product …** | PrestaShop refused the new text (for example too long). | Check the field and the prompt. |

A cron call stops at the first error and reports how many items were already updated before it.

### 3.13 History

Open **History**. It is the log of what was asked and what came back. Opening or filtering the page does not delete anything and does not change products.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Field | On start | What it does |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Date presets. |
| **From** / **To** | The current month | Your own period. |
| **Model** | **Any** | Only requests made with that model. |
| **Type** | **Any** | Only one kind of job, for example a product description or a category meta title. |
| **Status** | **Any** | **Success** or **Error**. |
| **Language** | **Any** | Only requests for that language. |
| **Employee** | **Any** | Only requests started by that back-office user. |
| **Product / category ID** | Empty | One product or category number. |
| **Prompt or reply contains** | Empty | A word that must be in the prompt, the reply or the error text. |
| **Filter** | – | Applies the filters. |

Cards: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. A dash in a token column means Gemini returned no count for that call. Below them five tables group the filtered requests: **By day**, **By model**, **By type**, **By language**, **By employee**, with a small bar showing the share of tokens. A small italic number next to a call count is the number of errors.

The list at the bottom has the columns **ID**, **Status** (green **Success** or red **Error**), **Prompt** (first 180 characters), **Reply / Error**, **Provider** (service, model and duration), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp**, and a **View** button that opens the full prompt and reply with **Back to the list**. The list shows 50 rows per page.

The toolbar button **Clear list** deletes every History row at once, without asking. Do this only on purpose: the restore buttons on products, the monthly budget counter and the cron modes **pendingGemini** and **pendingField** all rely on History, so after clearing, cron treats every product as not yet written.

### 3.14 Images

Open **Images**. This screen only turns the product photo search on or off and stores its instruction. It downloads no pictures.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Field | On start | What it does |
|---|---|---|
| **AI Image Finder** | Enabled | Shows the **Photos** tab on the product page. Disabled hides it. |
| **AI Image Search Prompt** | Built-in English instruction | The instruction that asks Gemini for page addresses where photos of this product are likely to be. {product_name} and {product_description} are replaced for the current product. Keep the request for a plain list of addresses. |
| **Save** | – | Stores both fields. Message: **Settings saved.** |

The search finds web pages that already show your product; it does not create pictures. Check that you have the right to use any picture you import.

### 3.15 Updates

Open **Updates** (far right of the module bar). The page checks MyPresta.eu for a newer module file. It does not change your catalog and does not install anything.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Field | On start | What it does |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Asks once, immediately. You see **Module is up to date!** or **New version available!**. |
| **Automatic Notifications** | Enabled or Disabled switch | Enabled: about every three days the back office checks and shows a warning banner with a link when a newer version exists. This setting is shared with other MyPresta modules on the same shop. |
| **Product Page** | – | A link to the module page on MyPresta.eu, where you can read what changed and download the file. |
| **Save** | – | Stores the notification setting. Message: **Update settings saved.** |

### 3.16 Work on the product edit page

Open **Catalog**, **Products**, edit a product, and open **Modules**, then **My AI Gemini**. The product must already be saved once. The panel appears when **Product edit page Form** or **Product Edit History** (3.4) is enabled.

![Product edit page – My AI Gemini panel](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

The panel has up to four tabs: **Generate**, **Simulate**, **Photos** and **History**.

**Generate tab**

| Field | On start | What it does |
|---|---|---|
| **Language** buttons | The first language | Choose which language version is written. **Every language** writes all active languages, one after another. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** or **Skip if filled**. Skip sends nothing to Gemini for a filled field. |
| Field cards | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Press **Fill** on the card to write that one field and save it on the product at once. |
| **SEO pack** – **Fill all** | – | Writes the name, both descriptions and both meta fields in one request and saves them. |
| **Use your own instruction or a saved prompt** | Closed | Open it to filter saved templates by title or text, pick a tile (**Standard brief** or an enabled template) and edit the **Instruction** box. If the box is empty, **Fill** uses a standard instruction for the field. |

The reply is printed under the panel. The text is saved on the product straight away, but the fields of the open product form do not refresh by themselves: reload the product page before you edit and press save in the form, otherwise the old values in the form can overwrite the new text.

**Simulate tab.** Same language choice and field cards, but the buttons say **Try**. The reply stays on this page and the product is not changed. Use it to check wording first.

![Product edit page – Photos tab](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Photos tab.** Press **Find pages**. The module asks Gemini for up to 5 pages that probably show this product, reads up to 24 pictures from them and shows them as small thumbnails. Tick the ones you want and press **Add selected to this product**. The first ticked picture becomes the cover if you add several. Nothing is saved before you press the button. The line under the buttons tells you the progress: "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." After adding, reload the product page to see them. If the switch is off you see a note that tells you to enable **AI Image Finder** under **Settings**, **General**.

**History tab.** A table with **When**, **Type**, **Status** and a **Restore** button for each successful write that saved a previous value. Press **Restore**, confirm "Restore the previous value?" and the previous text returns. Rows that failed have no button. A restored SEO pack returns the name, both descriptions and both meta fields. Without any rows you see "No generations for this product yet."

**Generate with AI buttons next to fields.** On the product page the module also adds a **Generate with AI** button next to the description, short description, meta title and meta description fields. If the shop has more than one language, it asks "Generate this field for the current language, or for every active language?" with **Current language**, **All languages** and **Cancel**. The text goes only into the open form: "Text is in the field. Save the product to keep it." Other fields are not changed. For a product that was never saved you see "Save the product once before generating."

### 3.17 Work on the category edit page

Edit a category in **Catalog**, **Categories**. Next to the description, additional description, meta title and meta description fields the module adds the **Generate with AI** button. It works exactly like on products: choose the current language or all languages, the text is placed in the form, and you save the category to keep it ("Text is in the field. Save the category to keep it."). A category that was never saved shows "Save the category once before generating." The same top-bar prompt box (3.18) also works on category, CMS page and brand pages and records them in History.

### 3.18 Shortcuts: top bar, product list and Help

- **Top bar button.** With **Admin Top Bar CTA** enabled, a magic-wand icon sits in the top bar. It opens the box **My AI Gemini** with a **Template** list, a text area and **Generate**. The reply is shown below the button, with the number of tokens. It changes no field. Use the **×** to close.
- **Product list.** On the product list in **Catalog**, **Products**, the module adds a **My AI Gemini** link next to the bulk actions or in the toolbar. It opens **Generate**, **Products**.
- **Help.** The **Help** button on every module page opens the explanation of the page.

### 3.19 Placeholders you can use in prompts

In templates, the **Instruction** box, the mass prompt boxes and the Playground you can write placeholders in curly brackets. The module replaces them with real data for each item before sending the instruction.

| Placeholder | Works for | What it becomes |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Products | The product's own data in the chosen language. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Products | Main category name and description, all category names (comma separated), brand name. |
| {product_attributes}, {product_features}, {product_feature_values} | Products | Combination attributes, feature names, and feature name:value pairs. |
| {product_images} | Products | The product picture links, comma separated. |
| {category_name}, {category_description}, {category_parent_name} | Categories | The category's own data and the parent name. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | CMS pages, brands (top-bar box) | The page title or brand data. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Everything | Shop name, domain, language name, default country and default currency code. |

A placeholder that has no data becomes empty text. Placeholders for categories are not replaced in product prompts and the other way round.

## 4. Shop front

My AI Gemini has no customer interface. It adds nothing to product pages, category pages, the cart, the footer or the customer account, and there is nothing in the theme to switch on or off. The shop front does not receive any module template, so no screenshot is shown.

The module does own two web addresses that are not pages for customers:

| Address | Who uses it | What to know |
|---|---|---|
| Cron address (`…/module/myaigemini/cron?secret=…&action=…`) | Your server scheduler | Described in 3.12. Opened without the right secret it only answers "The token does not exist or it's wrong!". Keep it private: whoever knows it can start a batch. |
| Internal address used by the module screens | The module's own buttons in the back office | Do not open or share it. It rejects requests without the module's own secret ("Error! Invalid token!"). |

## 5. Problems

**Nothing is generated and I see the message "The Gemini API key is not set. Add it in the module settings."**
The key box on **Settings**, **Gemini** is empty. Paste the key from https://aistudio.google.com/apikey and press **Save**.

**An error from Google appears in a result, in History or in a cron answer (for example a message starting with "Google Gemini API Error").**
Google refused the call: wrong or disabled key, a model your key may not use, exhausted free limits, or a blocked region. Open **History**, press **View** on the red row to read the full text. Fix the key or choose another model on **Settings**, **Gemini**, then try again.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
The model needed longer than **API timeout (seconds)**. Raise the timeout on **Settings**, **General** (up to 600), shorten the text or choose a faster model such as gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" or "The model returned an empty response."**
The reply was cut or empty. Raise **Max Tokens** on **Settings**, **Gemini**. Some Gemini 2.5 models use part of the limit for thinking.

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google refused to answer the instruction. Rewrite the template or the product text it uses.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
The cap in **Settings**, **Studio**, **Monthly generation budget** is used up. Raise it or set 0 for no limit.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** is enabled and the reply contained a line from **Forbidden words**. The product stayed unchanged. Edit the list, change the prompt or disable the gate.

**"Error! Prompt is missing or too short!"**
The instruction has fewer than 4 characters. Type a full instruction or choose a template.

**A mass run row shows "skipped Product skipped."**
**Existing text** is **Skip if filled** and the field already had text. Choose **Replace**, **Add above** or **Add below** to write anyway.

**After I removed an added model, every request fails.**
Removing the active model resets the model name to gpt-4o, which Gemini does not know. Open **Settings**, **Gemini**, choose a Gemini name in **Model** (for example gemini-2.0-flash) and press **Save**.

**Screens still say "OpenAi" or "gpt".**
This version still has some wording from an older release: the confirmation **OpenAi Settings Updated**, the error **OpenAi Model field is invalid!**, the filter labels "Products that have not been updated with OpenAi content" and "Products that already have been updated with OpenAi content" on **Generate**, **Products**, the example "gpt-4.1" in the model box and in the message "Enter a model id such as gpt-4.1.", the service name "openai" in the **Provider** column of History, and the **Help** panel line "Paste the secret key from your OpenAI account". All of them are only wording. The module calls Google Gemini. Use a key from https://aistudio.google.com/apikey and Gemini model names.

**The button "Module settings" on Generate opens a different module's page or an error.**
That button points to the settings of an older sister module and not to this one. Use **Settings** in the module bar.

**The lower form "Generate category content" does nothing.**
It only reloads the category filter. Press **Run on the categories below** in the panel above it.

**The product cron does not do anything.**
Check, in this order: **Enable Cron Feature** is **Yes** and saved; the address contains `&action=generateProductContent`; the secret in the address matches the screen; a **Prompt Template** is chosen; **Enable Debug** is **No**; your server really calls the address (look at its scheduler log). A browser test with **Enable Debug** set to **Yes** prints what would run.

**The cron command on screen ends right after the secret and the "Generate Token" button does nothing.**
Known limitation of this version. The command line is not completed by the page, and the token button does not fill the field. Build the address yourself as shown in 3.12 and type a long secret if you want to change it.

**Cron keeps rewriting products in a ticked category.**
When **Product Categories** is ticked, products whose main category is ticked are selected on every call, even if they were already written. For scheduled runs leave the category tree empty and limit the run with **Product ID list**, or use **Enable Debug** to check which products are chosen before you schedule it.

**Cron processes the same products again after I cleared History.**
Cron modes **pendingGemini** and **pendingField** use History to know what is already written. After **Clear list** everything counts as not written. Use **emptyField** if you want filled fields to be left alone.

**Top P, Frequency Penalty and Presence Penalty change nothing.**
In this version only **Temperature** and **Max Tokens** are sent to Gemini. The other three are stored but not used.

**The menu entry "AI Content Generator" is missing.**
Open any back-office page once more; the module puts the entry back. If it is still missing, uninstall and install the module again (this clears History and settings).

**No "Modules → My AI Gemini" panel on the product page.**
Check that **Product edit page Form** (or **Product Edit History**) is enabled on **Settings**, **General**, that the product was saved once, and that you open the **Modules** tab of the product. The **Generate with AI** buttons next to the fields are added by the module separately and may stay visible even when the panel is switched off.

**The text I generated disappeared after I saved the product.**
The product form was open with the old values. Reload the product page after using **Fill** and edit only after that. Use **Restore** on the **History** tab to bring a previous text back.

**The Dashboard block on the main PrestaShop dashboard is empty.**
That block does not receive History figures. Open **AI Content Generator**, **Dashboard**.

**Photo search: "The search did not return photos. Reload the product page and try again." or "No photos were found on the suggested pages."**
Gemini suggested pages that could not be read or contained no suitable pictures. Press **Find pages** again, or improve **AI Image Search Prompt** on **Images**. Pages on private or local addresses are refused.

**New product shows "Failed to parse AI response. Please try again." or "Failed to create product".**
Gemini did not return a usable draft, or the shop refused the data (for example a language without a name in the default language). Press **Generate data** again, choose the shop default language and check the category number.

## 6. For the developer

### 6.1 Overview

| Item | Value | Where defined |
|---|---|---|
| Technical name | `myaigemini` | Module main file |
| Main class | `myaigemini` (extends `Module`) | Module main file |
| Version | **1.1.0** | Module main file |
| Display name | My AI Gemini - AI content generation | Module main file |
| Author | MyPresta.eu | Module main file |
| Tab | `front_office_features` | Module main file |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | Module main file |
| PHP | 7.0 or newer (`MIN_PHP_VERSION`, checked in `install()`) | Module main file |
| API | Google Gemini at `https://generativelanguage.googleapis.com/v1beta`, key as `key` query parameter | Module main file |
| Key source | https://aistudio.google.com/apikey | Module main file |
| Configuration prefix | `MYPRESTA_MYAIGEMINI_` | Module main file |
| CSS prefix | `.mag-` (plus `.myaigemini-ui`, `.myaigemini-stats`) | Module main file |

Data flow: a screen (product panel, mass run, top-bar box, Playground) posts to the module front controller `ajax` with the secret token; the controller builds the prompt (template, placeholders, `Studio::decorate`), calls `OpenAIService` (a Gemini client kept under its old class name), writes the result to the product or category, and inserts a row in `myaigemini_log`. Cron works the same way through the front controller `cron`. Generated text is saved by `Product::save()` or `Category::save()`.

URL parameters on the configure page: `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` is the **Gemini** tab; on **Generate** `products` and `categories`), dashboard range `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. On History: `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 Files

| File | Purpose | Area |
|---|---|---|
| `myaigemini.php` | Main class: install and uninstall, configuration forms (General, Gemini, Studio, templates), Dashboard, hooks, menu placement, model catalog. | Module code |
| `autoload.php` | Loads the module classes without Composer. | Module code |
| `src/OpenAIService.php` | Gemini client (`generateContent`, `models`); timeouts; remembers parameters a model refuses. | Module code |
| `src/Studio.php` | Prompt decoration, monthly budget, forbidden-word check, SEO pack and alt text prompts. | Module code |
| `controllers/admin/AdminMyAIGeminiMain.php` | Menu entry; redirects to the Dashboard. | Module code |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Hidden; redirects to Settings. | Module code |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (filters and mass panels). | Module code |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Module code |
| `controllers/admin/AdminMyAIGeminiCron.php` | **Cron** forms. | Module code |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Module code |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | **Images** form and photo search actions. | Module code |
| `controllers/front/ajax.php` | JSON actions used by the screens. | Module code |
| `controllers/front/cron.php` | Cron endpoint. | Module code |
| `lib/sectionHelp.php` | Text of the Help panel. | Module code |
| `lib/updateChecker.php` | Update check (`myaigeminiUpdate`). | Module code |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Compatibility helper and the module search tool. | Module code |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Screens. | Module code |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Behaviour of the screens. | Module code |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Styles. | Module code |
| `translations/*.php` | Language files (many languages). | Module code |

Assets referenced but not shipped: `views/js/admin.js`, `views/css/admin.css` (Main and Settings controllers), `views/js/product_creator.js` and `views/css/product_creator.css` (New product controller). They are skipped silently; the New product buttons are handled by `back.js`.

### 6.3 Controllers

| Controller | Class and menu parent | Notes |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (parent: Modules section) | Visible entry **AI Content Generator**. `initContent()` redirects to the configure page with `mag_tab=dashboard`. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (parent: AdminMyAIGeminiMain) | Hidden tab (`active = 0`). **Generate**. `mag_sub` `products` / `categories`; submit names `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (parent: AdminMyAIGeminiMain) | Hidden. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (placeholder reply "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (parent: AdminMyAIGeminiMain) | Hidden. Redirect only. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (parent: AdminMyAIGeminiMain) | Hidden. Submit `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (parent: AdminMyAIGeminiMain) | Hidden. `clear_log` empties the log table. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (parent: AdminMyAIGeminiMain) | Hidden. Actions `searchImages`, `extractImages` (private hosts refused), `saveImages`. Form submit `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (parent: –) | Requires `secret_token` equal to `MYPRESTA_MYAIGEMINI_TOKEN`, otherwise "Error! Invalid token!". Actions: `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (no button calls this one). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (parent: –) | Requires `MYPRESTA_MYAIGEMINI_ENABLE_CRON` and a `secret` equal to `_SECRET` or `_CAT_SECRET` (either secret opens either action). `action` = `generateProductContent` or `generateCategoryContent`. |

The Generate filter forms link "Module settings" to `configure=mychatgpt`. Products edit panel hook output is built in `renderProductModulesContent()`.

Cron selection SQL: the category filter and the product id list are appended to the WHERE clause; the category condition (`id_product IN (…) OR id_category_default IN (…)`) is not wrapped in brackets, so the OR widens the whole condition. `pendingGemini` and `pendingField` use `NOT EXISTS` on `myaigemini_log` rows whose status is empty or not `error`; `pendingField` also matches `type = product_<field>` / `category_<field>`. `emptyField` joins `product_lang` / `category_lang` for the chosen language. Product text lengths on save: name 128, short description 799 (cron) or 800 (ajax), meta title 69, meta description 159.

### 6.4 Hooks

Registered in `install()`: `displayAdminProductsMainStepLeftColumnMiddle` (returns an empty string), `displayAdminProductsMainStepLeftColumnBottom` (empty), `actionProductFormBuilderModifier` (no action), `displayAdminProductsExtra` (renders the panel in the product **Modules** tab), `displayBackOfficeHeader` (loads assets, runs `ensureLongSecrets()` and `placeModuleMenu()`, registers the image finder tab once, adds JS variables), `displayBackOfficeTop` (the top-bar box when `TOPCTA` is on, and JS variables for category, CMS and brand ids), `displayFooter` (empty), `displayHeader` (empty), `dashboardZoneTwo` (renders `dashboard.tpl` without its data). `actionProductGridDataModifier` exists as a method but is not registered. The module has no `enable()` and no `disable()` methods. The module exposes no custom hooks.

`hookDisplayBackOfficeHeader` loads `product-fields.js` on the product and category edit pages regardless of the `MYPRESTA_MYAIGEMINI_PRODUCT` switch (the switch only controls the Modules-tab panel).

### 6.5 Overrides

The module has no overrides. It does not replace any core file.

### 6.6 Database

| Table | Content | Notes |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 rows inserted on install. | Created on install, dropped on uninstall |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, `old_` / `new_` pairs for `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Indexes on `id_product` and `status`. | Created on install, dropped on uninstall |

Both tables use the shop database engine and are dropped on uninstall. The three token columns are also added at runtime by `ensureUsageColumns()` when the Dashboard, History or a cron/ajax log write needs them and they are missing. `ai_service` always stores the value `openai` (leftover). The mass generator `postProcess()` writes the submitted filter values into configuration keys such as `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS` each time **Generate** loads. Uninstall does not delete those keys.

### 6.7 Configuration keys and translations

Prefix `MYPRESTA_MYAIGEMINI_`. Values written by `install()`:

| Key | Default | Meaning |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Live and debug switches (`PrestaShopLogger` with object type `MyAIGemini`). |
| `TIMEOUT` | `120` | Seconds; clamped 10–600; browser timeout is this plus 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Restore list, top-bar box, product panel. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, built-in text | Photo search switch and instruction. `IMAGEFINDER_TAB_OK` marks the one-time tab repair. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | random 32 characters | Ajax token, product cron secret, category cron secret. Values shorter than 24 characters are regenerated on the next back-office page. |
| `API_KEY` | a single space | Stored trimmed; the form keeps the stored key if the box is empty. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, empty | Active model and added names (one per line). Removing the active added model sets `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Sent to Gemini as `temperature` and `maxOutputTokens`. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Stored; not included in the Gemini request. |
| `MODEL_CAPS` | empty | Learned per-model parameters. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | empty | Studio texts. |
| `BUDGET`, `QUALITY` | `0`, `1` | Monthly cap; quality gate. |
| `ENABLE_CRON` | `0` | Global cron switch. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Interval choice (6 = Every Hour). Stored only; used for display. |
| `updatedField`, `catupdatedField` | `description`, `description` | Cron field (the key names are written as `MYPRESTA_MYAIGEMINI_updatedField` etc.). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Cron selection mode. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Batch size. |
| `promptTemplateId`, `catpromptTemplateId` | empty | Cron template. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Cron language. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, empty | Cron debug and legacy selector. |
| `productIdsList`, `categories` | empty | Cron filters. |

Uninstall deletes the keys above plus `ACTIVE_SERVICE`, `GEMINI_API_KEY` and `GEMINI_MODEL` (old names), the tabs, and both tables. The back office also removes `GEMINI_API_KEY`, `GEMINI_MODEL` and `ACTIVE_SERVICE` on every configure-page load. The shared keys `mypresta_updates`, `update_myaigemini` and `updatev_myaigemini` belong to the update checker and are not removed.

Translations: add a language by creating `translations/{iso}.php` (the module ships many). Texts pass through `$this->l()` in the main class and `l s='…' mod='myaigemini'` in templates. Admin controllers translate through `trans()` on PrestaShop 8 and 9 and through the module `l()` on 1.6 and 1.7. Texts not translated: the column title **ID**, the label **Cron Job Secret Token** and **Generate Token**, JavaScript messages in `back.js`, `image-finder.js` and the photo picker page ("Write a prompt first.", "Looking for photos…", and similar), and the draft returned by New product. Field descriptions are `desc` entries built with `fieldHelp()` in the form definitions, in the form "What it does / How to configure / Effect"; the Help panel text is in `lib/sectionHelp.php`.

Placeholders are replaced in `controllers/front/ajax.php` (interactive runs) and `controllers/front/cron.php` (cron); the lists are the same except that cron has no CMS or brand placeholders.

### 6.8 Extending

There is no front template to override in a theme. To add prompt placeholders, extend the replacement blocks in `ajax.php` and `cron.php`. To change the AI service behaviour, edit `src/OpenAIService.php` (`createChatCompletion()` builds the Gemini payload). To add a model, use **Add a Gemini model** or extend `getPopularGeminiModels()`. Custom CSS can target `.mag-` classes on module screens. Changing the cron address format requires editing `AdminMyAIGeminiCron.php` and the templates `cron.tpl` and `cron-info.tpl`.

## 7. Help

Module page: https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

To ask for help:

1. Log in to your customer account on mypresta.eu.
2. Go to the contact page.
3. Choose the subject **Support for paid modules**. For paid modules the form states that you must be logged in; after logging in, choose this module from your purchase history.
4. Describe what you did, what you expected and what you saw. Add the red **History** row (open it with **View**) or the text of the message from the screen, and the model name you use.
