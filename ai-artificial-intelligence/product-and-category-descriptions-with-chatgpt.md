---
title: "My ChatGPT - AI content generation - documentation and user manual"
description: "Use this manual to configure OpenAI, generate catalog text with the module you already own, and fix problems when a generation fails."
sidebar:
  label: "My ChatGPT - AI content generation - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Product and Category Descriptions with ChatGPT Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Requirements

Check these points before you connect the module to OpenAI.

- Use PrestaShop 1.6, 1.7, 8 or 9 (up to 9.99.99).
- Use PHP 7.0 or newer. The installer refuses to continue on an older PHP version.
- Enable the PHP cURL and JSON extensions. Every call to OpenAI and the update check use cURL. Enable mbstring as well, because text clean-up in the image search and in the new-product screen uses it.
- Use the optional **Optional source URL** field on **New product** only when PHP can read web pages (the `allow_url_fopen` setting) and the DOM extension is available. Without them the field is ignored and only your brief is used.
- Have your own OpenAI account and an API key from platform.openai.com. The key must be allowed to call the model you choose. You pay OpenAI for every request. The module does not include credit.
- Let the server reach the internet on port 443. The shop contacts OpenAI for every generation and the MyPresta.eu update server for update checks.
- Add a scheduled task (CRON) on the server only if you want generation to run without anyone clicking. The cron addresses do nothing until the server calls them.
- No other PrestaShop module is required.
- Plan time for large catalogs. Every field in every language is one separate request to OpenAI. A mass run on 500 products with four fields and two languages sends 4000 requests, one after another, and keeps your browser tab busy. Use small test batches first, or use cron batches for big catalogs.

## 2. Installation

1. Open **Modules**, then **Module Manager**.
2. Click **Upload a module** and upload the ZIP file.
3. Click **Install** on **My ChatGPT - AI content generation**.
4. Open **Modules** in the left menu. A new entry **AI Content Generator** appears there. Click it to open the module **Dashboard**. **Configure** in **Module Manager** opens the same place.

Installation does the following:

- Adds the **AI Content Generator** menu entry under **Modules**. All other screens of the module are reached from the module’s own top menu and have no separate menu entries.
- Creates two tables: one for prompt templates and one for the history of every generation.
- Adds 16 ready-made prompt templates (product names, descriptions, meta titles, meta descriptions and tags). All of them are enabled.
- Creates long secret values for the module’s internal calls and for the two cron addresses.
- Turns off the shop-wide HTML filter (HTMLPurifier). Descriptions and category texts then keep their HTML tags, but the same switch is off for every other text in the shop. Turn it on again in the shop settings if you do not want that.
- Does not clear the PrestaShop cache. Clear it under **Advanced Parameters**, then **Performance**, only if old styles or an old screen stay visible.

If the installer shows “This module requires PHP 7.0.0 or newer”, upgrade PHP first. If it shows “Could not create the module database tables.”, check that the database user may create tables, then install again.

Uninstall:

- Removes the menu entries, both tables (all prompt templates and the full History are lost) and nearly all module settings, including the API key and the cron secrets.
- Does not turn the HTML filter back on. Switch it on yourself if you want it.
- Does not delete any product text, category text or product photos that the module created. Those stay in the catalog.
- Leaves a few harmless leftovers in the shop configuration (the saved cron category choice, the last filter values from **Generate** and the update-check values).
- A new install creates new secrets, empty History and the 16 default templates again. Old cron addresses stop working, so copy them again.

## 3. Configuration and back-office work

Open **Modules**, then **AI Content Generator**. The top menu of the module has these entries: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** and, on the right, **Updates**. A round **Help** button at the bottom of every module screen opens a short explanation of the screen you are on.

The figures show the whole back-office window. The left menu is left out so the module screen stays readable.

Follow this process:

1. Open **Settings**, then **ChatGPT**. Paste the OpenAI API key and choose a model. Click **Save**.
2. Optionally open **Studio** and set voice, audience, tone, glossary, forbidden words, monthly budget and the quality gate.
3. Open **Prompt templates**. Review the 16 templates, edit them or add your own, and keep enabled only the ones your team should use.
4. Generate text in the way that fits the job:
   - One product: open the product, tab **Modules**, and use **Generate**, **Simulate** or **Photos**. The small **Generate with AI** buttons next to the description and meta fields also work.
   - Many products or categories at once: open **Generate**, build a list with filters and press **Run**.
   - A new product from a short brief: open **New product**.
   - Scheduled batches without clicking: open **Cron** and add the address to the server scheduler.
5. Check **History** to see every prompt, reply, error and token count. Check **Dashboard** for totals and charts.

The module has no order-style statuses. A prompt template is **Enabled** or **Disabled**. Every call in **History** is **Success** or **Error**. A mass or cron run ends when the last item has been written, and the text is saved on the product or category as soon as each reply arrives.

If **Admin Top Bar CTA** is on, a small magic-wand button **My ChatGPT** sits in the top bar of every back-office page. It opens a small box with a template list, a text field and **Generate**. It works like the **Playground** (section 3.6): the reply is shown in the box and nothing is saved in the catalog.

On the product list of **Catalog**, **Products**, the module also adds a **My ChatGPT** button that opens **Generate**.

### 3.1 Dashboard

Open **AI Content Generator**, **Dashboard**. This page is a report. It never writes product or category text.

![Dashboard](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Click a period button: **Today**, **7 days**, **30 days** (opened by default), **90 days**, **This month** or **All time**. Or type **From** and **To** and click **Apply**.
- The line **Active service** shows ChatGPT and the model saved in **Settings**, **ChatGPT**.
- Read the cards **Requests**, **Success**, **Errors**, **Tokens sent** and **Tokens received** for the chosen period. **Requests** counts every call stored in **History**. **Errors** counts the failed ones. Tokens sent is the size of your instruction, tokens received is the size of the reply.
- Read the charts **Requests and errors**, **Tokens sent and received** and **Requests by model**.
- Empty charts mean nothing was generated in that period. Changing the dates only redraws the page. Nothing is deleted.

### 3.2 Settings – General

Open **Settings**, then **General**. Click **Save** after changing anything. You see “Settings Updated”.

![General settings](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Field | Default | What it does |
|---|---|---|
| **Live mode** | No | Marks the module as running on the real shop rather than a trial setup. Turn it on in production. Off keeps the same tools but signals that this is not the production setup. |
| **Debug mode** | No | Writes extra technical detail when a call to OpenAI fails. Turn it on only while you investigate a problem. Details appear under **Advanced Parameters**, **Logs**. Customers never see them. |
| **API timeout (seconds)** | 120 | How long one call to OpenAI may take before the module gives up. 120 suits normal descriptions. Raise it up to 600 for long texts or slow models. Values below 10 are raised to 10, values above 600 are lowered to 600, and an empty or non-numeric value becomes 120. A short timeout fails fast and writes an error to History. |
| **Product Edit History** | Yes | Adds a **History** list with a **Restore** button on the product page so editors can put an older text back. Off hides that list. The rows stay in **History** either way. |
| **Admin Top Bar CTA** | Yes | Adds the **My ChatGPT** shortcut button to the back-office top bar on every page. Off removes only that button. The **AI Content Generator** menu entry stays. |
| **Product edit page Form** | Yes | Shows the generator panel (**Generate**, **Simulate**, **Photos**) in the **Modules** tab of the product and the **Generate with AI** buttons next to the description and meta fields. Off hides them. Use Off when only mass generation and cron should be used. |
| **AI Image Finder** | Yes | Lets an editor ask the model for web pages that probably show photos of the current product. On shows the **Photos** tab on the product. Off hides it. Nothing is downloaded until someone confirms photos. The same switch is on **Images** (section 3.12). |
| **AI Image Search Prompt** | Long default text | The instruction sent when someone searches for photos. The default asks for exactly five page addresses as a plain list, preferring manufacturer pages, big retailers and catalogs. The words `{product_name}` and `{product_description}` are replaced with the current product. Keep the request for a plain list of addresses. A tight prompt returns relevant pages. A vague prompt returns unrelated links. The same text is on **Images**. |

### 3.3 Settings – ChatGPT

Open **Settings**, then **ChatGPT**. The form is titled **OpenAI Settings**. Every generation, including the product buttons, mass runs and cron, uses these values. Click **Save**. You see “OpenAi Settings Updated”.

![ChatGPT settings](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Field | Default | What it does |
|---|---|---|
| **OpenAI API KEY** | Empty | The secret that lets this shop call your OpenAI account. Paste the key created at platform.openai.com in your OpenAI account. Spaces around it are removed on save. Leave the box untouched to keep the key already stored. An empty or wrong key makes every generation fail, and the error is written to History. If you save a new key shorter than 10 characters while no key is stored, you see “OpenAI API KEY field is invalid!”. |
| **Model** | gpt-3.5-turbo | The ChatGPT model that writes the text. The list holds the built-in models (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini and others) and the models you added. Pick one and click **Save**. A model your key cannot use returns an OpenAI error instead of text. An empty model gives “OpenAi Model field is invalid!”. |
| **Add a ChatGPT model** | Empty | Adds a model name that is not in the built-in list. Type the exact name from your OpenAI account (for example `gpt-4.1`) and click **Add model**. The name appears in **Model** and becomes the active model. **Remove** next to an added name deletes it. Built-in names cannot be removed. If you remove the active added model, the module switches to gpt-4o. Messages: “Model added.”, “That model is already built in.”, “Model removed.”, “Built-in models cannot be removed.”, “Enter a model id such as gpt-4.1.”. |
| **Max Tokens** | 3200 | The upper limit for the length of a reply, counted in tokens, not words. Use about 256 for a meta description and 1000 or more for a full HTML description. Too low cuts the reply off. Too high allows long text and costs more on your OpenAI bill. A value of 0 is treated as empty and replaced by 256. |
| **Temperature** | 0.7 | How freely the model chooses words. Stay between 0 and 1. Use about 0.2 for specifications and meta text and about 0.7 for descriptions. Change this or **Top P**, not both. Low values repeat a similar structure. High values vary more and may drift from the brief. A value of 0 is treated as empty and replaced by 0.7. |
| **Top P** | 1 | Another way to limit how surprising the next word can be. 1 considers the full range. Leave 1 if you already set **Temperature**. A lower value such as 0.9 gives a tighter vocabulary. A value of 0 is replaced by 1. |
| **Frequency Penalty Value** | 0 | Reduces phrases that repeat inside one reply. Use 0 unless descriptions keep copying the same sentence, then try 0.3–0.6. Allowed range -2 to 2. It does not compare products with each other. |
| **Presence Penalty Value** | 0 | Pushes the reply toward new topics. Use 0 by default. Try a small positive number if every paragraph says the same thing. Allowed range -2 to 2. Some newer models ignore this field. |

The module learns by itself which settings a model refuses (some reasoning models reject temperature or penalties) and then stops sending them to that model.

### 3.4 Settings – Studio

Open **Settings**, then **Studio**. Studio adds house rules on top of every prompt: product buttons, mass runs, cron and the playground. Empty boxes are skipped. Click **Save studio**. You see “Studio settings saved.”. Text already in the catalog is not rewritten.

![Studio settings](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Field | Default | What it does |
|---|---|---|
| **Brand voice** | Empty | Tells the model who is speaking, so the text matches your shop and not a generic assistant. Write a short brief, for example “specialist workshop, short sentences, no hype”. Every later generation starts from this voice. |
| **Audience** | Empty | Names the reader to write for, for example “professional installers” or “first-time buyers”. Replies use vocabulary and examples aimed at that reader. |
| **Tone** | Empty | The mood of the wording: formal, warm, technical. One or two words are enough. It does not change the model or the temperature. |
| **Glossary** | Empty | Brand names, materials and spellings the model must copy exactly. Put one term per line. New text prefers those spellings. Terms not listed can still be reworded. |
| **Forbidden words** | Empty | Words and phrases that must not appear in a saved reply. One per line. The list works only when **Quality gate** is on. A reply that contains one of the lines (also inside a longer word) is rejected, is not written to the product and is stored in History as an error. |
| **Monthly generation budget** | 0 | The most successful generations the shop may run in the current calendar month. Enter a whole number. 0 means no limit. The counter starts again on the first day of the month. When the cap is reached, new generations stop with a budget message. Failed calls are not counted. Playground, product buttons, mass runs and cron all count. |
| **Quality gate** | Yes | Checks every reply against **Forbidden words** before anything is saved. On blocks a matching reply. Off saves the reply even when it contains a listed word. |

### 3.5 Settings – Prompt templates

Open **Settings**, then **Prompt templates**. A template is a saved instruction that editors pick by title instead of typing the same brief again. The title is only a label for the dropdown. The model receives the prompt text. Enabled templates appear in the product panel, in the mass generator and in the cron form. Disabled ones stay in the list but are not offered (the cron form still lists them, so choose an enabled one).

![Prompt templates](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

The list **Prompt Templates** shows **ID**, **Title**, **Prompt**, **Status** and **Timestamp**, newest first, 50 per page.

- Click the green **+** button to create a template.
- Click the status mark in a row to switch a template between enabled and disabled.
- Use **Edit** or **Delete** in a row. Tick several rows and use the bulk action **Delete** (you must confirm “Are you sure you want to delete the selected prompts?”).

The form **Generate Prompt Template**:

| Field | Default | What it does |
|---|---|---|
| **Status** | Disabled for a new template | Shows or hides this template in the dropdowns on the product page, in mass generation and in cron. Enable templates your staff should use. Disable a draft instead of deleting it. |
| **Prompt title** | Empty (required) | The name editors see in the dropdown, for example “HTML description with features”. It is not sent to the model. |
| **Prompt content** | Empty (required) | The instruction sent to the model. Write it the way you would brief a copywriter: length, HTML, language. Placeholders are filled from the item being written. Double quotation marks are changed to single ones on save. |

Click **Save Prompt**. You see “Prompt template successfully added!” or “Prompt template successfully updated!”. **Go Back to Module Settings** returns to the list. Deleting shows “Prompt template removed.”.

Placeholders you can use in a template:

| For | Placeholders | Replaced with |
|---|---|---|
| Products | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | The value of that product in the language being written. |
| Products | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | The brand and category data of the product. |
| Products | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Comma-separated attributes, feature names, feature name:value pairs and photo addresses of the product. |
| Categories | `{category_name}`, `{category_description}`, `{category_parent_name}` | The category and its parent. |
| Products and categories | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Your shop data. |

The 16 default templates are **Product name 1–2**, **Product description 1–7**, **Product meta title 1–3**, **Product meta description 1–3** and **Product tags**. Some of them contain sample wording (for example a smartwatch). Review them before the first mass run.

### 3.6 Settings – Playground

Open **Settings**, then **Playground**. The playground is a scratch pad that calls the active model and shows the reply on the page. Use it to try a prompt before you save it as a template, or to check that your API key works.

![Playground](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Type an instruction in the box. The grey hint reads “Ask the model anything about your catalog”.
2. Click **Generate**.
3. Read the reply and the token count under the button.

The call uses the model, the sampling values and the Studio rules you saved. The reply is stored in History. No product, category or meta field is changed. Write real names and details: placeholders in curly braces are not filled in the playground.

### 3.7 Generate – Products

Open **Generate**, then the sub-tab **Products**. Work in two steps. Step 1 only builds a list. Nothing is sent to OpenAI and nothing is saved as a shop setting.

![Generate products](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Step 1 – the form **Filter products to update**. All filters are combined. A filter you leave empty is ignored.

| Field | Default | What it does |
|---|---|---|
| **Product Categories** | Nothing ticked | Keeps products from the ticked categories (including products whose default category is one of them). An empty tree leaves this filter off. |
| **Brand** | Select brand | Keeps products of one manufacturer. The empty option includes every brand. |
| **Product status** | Active | **Active** keeps products on sale, **Disabled** keeps drafts, **Both** keeps all. |
| **Product stock** | All products | **Only in stock products** removes products with no available quantity. **All products** ignores stock. |
| **Update only** | Update all | **Products that have not been updated with OpenAi content** is for a first pass (products with no row in History). **Products that already have been updated with OpenAi content** is for rewriting. **Update all** ignores History. |
| **Product IDs** | Empty | Only these product numbers, separated by commas, for example 12,45,103. |
| **Product Reference** | Empty | Only products with these reference codes, separated by commas. |
| **Product Add Date From** | Empty | Leaves out products created before this date and time. |
| **Product Add Date To** | Empty | Leaves out products created after this date and time. |
| **Minimum product ID** | Empty | Skips products with a smaller number. |
| **Maximum product ID** | Empty | Skips products with a larger number. |
| **Product Limit** | Empty | The most products loaded into the list, for example 20. The list never shows more than this, so one run cannot walk the whole catalog by accident. |

Click **Go to next step**. **Module settings** opens the module configuration.

Step 2 – the panel **Mass product generation** and the table of products (**ID**, **Reference**, **Result**):

| Field | Default | What it does |
|---|---|---|
| **Template** | Choose a template | Fills the prompt box from an enabled template. You can also type your own prompt. The title is not sent. If the box stays empty, the module uses a standard brief for each field. |
| Prompt box | Empty | The instruction for every product in the table. If you type one text, the same text is used for every field you chose, so run one field at a time when the fields need different wording. |
| **What to generate** | Descriptions | **Descriptions** writes the long and the short description. **Meta title and meta description** writes both meta fields. **Descriptions and meta together** writes all four. Each field is its own request. Names and tags are written from the product page, not from here. |
| **Existing text** | Replace | **Replace** overwrites. **Skip if filled** leaves a filled field alone and does not call the model for it. **Add above** and **Add below** keep the old text and attach the new text. |
| **Languages** | Your current language ticked | Tick every language to write. Each ticked language is generated separately. Unticked languages keep their text. |

Click **Run on the list below**. The status line shows progress such as “3 / 40 – description”. Every row shows its own results as soon as that product finishes, for example “description: success Content successfully generated and updated to product.”, “description_short: skipped Product skipped.” or “meta_title: error …” with the reason. At the end you see “Finished N products.”. Without any ticked language you see “Select at least one language.”.

Keep the browser tab open until the run ends. Closing it stops the run, and the products already written stay saved. To continue, build the list again with **Update only** set to products that have not been updated. A failure on one field does not undo the ones already saved. Start with a small **Product Limit**, such as 20, and check the wording first.

### 3.8 Generate – Categories

Open **Generate**, then the sub-tab **Categories**. The two steps work like the product screen.

![Generate categories](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Step 1 – the form **Filter categories to update**:

| Field | Default | What it does |
|---|---|---|
| **Categories** | Nothing ticked | Picks the categories for the next step. An empty tree does not narrow the list by category, so the list then holds every category with the chosen status, including **Home** and the root category. Tick the categories you want. |
| **Category status** | Active | **Active**, **Disabled** or **Both**. |

Click **Go to next step**.

Step 2 – the panel **Mass category generation** and the table of categories (**ID**, **Result**):

| Field | Default | What it does |
|---|---|---|
| Prompt box (first box) | Empty | The instruction sent for every category. Describe tone, length and HTML. Name the subject in the text. This box does not insert product placeholders. This panel has no template picker. |
| Field list | Description | The field to write: **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. Only that field is saved. |
| Existing text list | Replace | **Replace** overwrites. **Skip if filled** leaves a filled field alone and does not call the model for that category. |
| Language list | Your current language | One language. Run again for another language. |

Click **Run on the categories below**. Results appear per row as in the product screen. A category with no **Additional description** field in your PrestaShop version shows “Error! This PrestaShop version does not support the category Additional Description field.”.

Below the table the screen also shows the form **Generate category content**. Its introduction says “This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives.” In this release that form does not start a run. Use **Run on the categories below** above it. The form has these fields:

| Field | Default | What it does |
|---|---|---|
| **Field to update** | Description | The category field this form would rewrite: **Category name**, **Description**, **Meta Title**, **Meta Description** or **Additional Description**. Only that field is sent to the model and saved. The other fields stay as they are. Description and meta are separate runs. |
| **Existing data** | Keep existing data and add new generated content at the top | What happens when the chosen field already has text: **Keep existing data and add new generated content at the top**, **Keep existing data and add new generated content at the end**, **Keep existing data and skip category** or **Remove data and add new generated content**. Replace changes the stored text. Skip does not call the model for a category that already has that field. Add keeps both versions in one field. |
| **Language** | First language in the list | The language version that is written. Only that language changes. |
| **Content Prompt** | Empty (required) | The instruction for every category in the list. Describe the tone, length and HTML. Name the category subject in the text, because product placeholders are not inserted. |
| **API call delay** | Empty | A pause in seconds between one category and the next, so the OpenAI rate limit is not hit. Use 1 or 2 on a low-tier key. Set 0 to send the next request at once. The **Run** panel above does not use this pause. |

The buttons **Generate content** and **Go Back to Category Filter** do not generate text. **Generate content** only stores the values you typed and shows the filter again. **Module settings** opens the module configuration.

### 3.9 New product

Open **New product**. The panel **Create a product from a brief** asks the model for a product draft and can insert that draft as a new product. It is for products that are not in the catalog yet. To fill an existing product, use **Generate** or the product page.

![New product](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

If no key is saved you see “Add an API key in the module settings first.”.

| Field | Default | What it does |
|---|---|---|
| **What is the product?** | Empty (required) | The brief the model expands into name, descriptions, meta, tags, features, reference and price. Write a few sentences with material, audience and names that must stay. An empty box is refused with “Prompt is required”. |
| **Optional source URL** | Empty | A full web address of a public page about the product. A readable page adds its title, description and price text to the brief. A page that cannot be read is ignored. |
| **Language** | Shop default language | The language the text is saved in. Other languages are not filled. Choose your default shop language, because PrestaShop needs a name in the default language to create a product. |
| **Default category ID** | 2 | The category number from **Catalog**, **Categories**. 2 is usually **Home**. The product is placed in that category and it becomes the default category. |

1. Click **Generate data**. The draft appears as text in the box below (name, description, short description, meta title, meta description, keywords, tags, reference, price, features). Nothing is saved yet. Click again for a new draft. You cannot edit the draft in this screen.
2. Check the draft, especially the suggested price and reference.
3. Click **Create product**. The result line shows “Product #” and the new product number.

The new product is active, available for order, visible in catalog and search, new condition, with the tax rule group number 1, a stock of 100 pieces and the suggested price. Name, descriptions, meta, tags and features are saved in the chosen language only. This screen adds no photos. Open the new product, tab **Modules**, **Photos**, to add them. Check price, tax, quantity and category before you publish. Generation here is not recorded in History and does not count toward the monthly budget.

### 3.10 Cron

Open **Cron**. Cron is for the server, not for a person clicking **Run**. This screen stores your choices and shows the secret addresses that your server calls on a schedule. Each real call writes one small batch and stops. The shop does nothing until the server requests the address.

![Cron](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

The top panel **Category cron** and the panel **Cron parameters** show the addresses of your shop with the secrets. Treat the secrets like passwords: never publish a full address. This manual shows them as `YOUR_SECURE_KEY`, for example `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. Each address needs the settings from the form added to it (field, language, template, batch size and so on). Section 6.3 lists them. Ask your developer or host to add them when you set up the scheduler.

Product form **CRON JOB Settings – Generate product content using OpenAI**. Click **Save** after changing it.

| Field | Default | What it does |
|---|---|---|
| **Enable Cron Feature** | No | Allows the server to generate product and category text on a schedule. Turn it on only after the secret, field, language and template are saved. While it is off, every cron address answers that the feature is disabled. This one switch is also required for the category cron. |
| **Cron Job Secret Token** | Long random value | A long password that must be part of the product cron address. Without it the shop refuses the call. Keep the generated value. Changing it immediately invalidates the old address. The **Generate Token** button does not create a new value in this release, so keep the value created at install. |
| **Update Field** | description | The single product field this cron writes: name, description, description_short, meta_title, meta_description or tags. To fill several fields, make several cron commands. |
| **Selected Products** | pendingOpenAI | Decides which products still wait. **pendingOpenAI**: products the module has not written yet (any field). **pendingField**: products not yet written for this specific field, so several commands (for example description and name) can work on the same products. **emptyField**: only products where the chosen field is empty. Each run skips products that no longer match, so a finished catalog stops changing. |
| **Product Categories** | Nothing ticked | Limits the run to the ticked categories. An empty tree means category is not a filter. |
| **Product ID list** | Empty | Limits the run to these product numbers, separated by commas. Letters and other characters are removed on save. |
| **Language** | Shop default language | The language version that is written. Other languages need their own command. |
| **Product to update** | 5 products | How many matching products one call processes (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 or 1000). Start with 5 or 10 so a slow model does not hit the server time limit. |
| **Prompt Template** | First template in the list | The saved instruction used for every product in the run. Placeholders are filled per product. Pick an enabled template. |
| **Enable Debug** | No | When the address is opened with debug on, it prints the plan (settings, selected products, final prompts) and does not write anything. Check a command with it once. Turn it off before the scheduler uses the address. |
| **CRON JOB interval** | Every Hour | The rhythm you plan to use (every 1, 2, 5, 10 or 30 minutes, every hour, every 2 or every 6 hours). It documents your plan. The module does not start the scheduler. |
| **Product Cron Job command** | – | Shows the command line to copy into the scheduler. Save the form first. |

Category form **CRON JOB Settings – Generate category content using OpenAI**. It has its own secret and **Save** button, and it does not need its own enable switch:

| Field | Default | What it does |
|---|---|---|
| **Cron Job Secret Token** | Long random value | The password of the category address. It is separate from the product secret. Changing it invalidates the old category address. |
| **Update Field** | description | The single category field written: name, description, meta_title or meta_description. |
| **Selected categories** | pendingOpenAI | Same three rules as for products, applied to categories. **pendingField** lets several commands share the same categories. |
| **Language** | Shop default language | The language version that is written. |
| **Categories to update** | 5 categories | How many categories one call processes (2 up to 1000). |
| **Prompt Template** | First template in the list | Write the template for a category, not a product, for example with `{category_name}`. |
| **Enable Debug** | No | Prints the plan and does not save categories. |
| **CRON JOB interval** | Every Hour | The rhythm you plan to use. |
| **Category Cron Job command** | – | The command line to copy after you save. |

The category cron never touches **Home** and the root category.

### 3.11 History

Open **History**. History is the log of what was asked and what came back. Opening or filtering the page deletes nothing and changes no product.

![History](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

The filter bar opens on **This month**. Use the period buttons **Today**, **7 days**, **30 days**, **This month** and **All time**, or **From** and **To**. You can also narrow by **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee**, **Product / category ID** and **Prompt or reply contains**. Click **Filter**.

- The cards show **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** and **Average time** for the filter. A dash means OpenAI returned no token count for that call.
- The panels **By day**, **By model**, **By type**, **By language** and **By employee** group the same rows by **Group**, **Calls**, **Sent**, **Received** and **Total**. A small italic number next to the calls is the number of errors.
- The list **Prompt history** has the columns **ID**, **Status**, **Prompt**, **Reply / Error**, **Provider** (model, error code, seconds), **Sent**, **Received**, **Total**, **Entity ID**, **Type** and **Timestamp**. Prompt and reply are shortened. Click **View** in a row to read the full prompt and the full reply with the tokens, then **Back to the list**. An error row shows the error text instead of a reply. **Type** shows what was written, for example product_description or category_meta_title. Simulations and the playground also create rows.
- The button **Clear list** deletes every row at once, without a question, also rows outside your filter. After that the **Dashboard** counters, the **Update only** filter, the **pendingOpenAI** rule and the monthly budget counter start from zero, and **Restore** is no longer possible for old texts.

### 3.12 Images

Open **Images**. This page does not download pictures. It turns the product-page image search on or off and stores the instruction used for that search.

![Images](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Field | Default | What it does |
|---|---|---|
| **AI Image Finder** | Enabled | **Enabled** shows the **Photos** tab on the product edit page. **Disabled** removes it. An image is imported only after someone confirms it. |
| **AI Image Search Prompt** | Same long default as in **General** | The instruction sent when someone searches. `{product_name}` and `{product_description}` are replaced with the current product. Keep the request for a plain list of page addresses. |

Click **Save**. You see “Settings saved.”. Searching for pages and importing photos is described in section 3.13.

### 3.13 Product edit (Modules tab)

Open **Catalog**, **Products**, edit a product and open the tab **Modules**. The panel **My ChatGPT** has the tabs **Generate**, **Simulate**, **Photos** and **History**. If **Product edit page Form** is off, only **History** remains. If **Product Edit History** is off too, nothing appears. Save a new product once before you generate, so that it has a number.

![Product edit](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Generate** writes one field and saves it on the product right away.

1. Choose a **Language** chip, or **Every language**.
2. Under **If the field already has text** choose **Replace**, **Add above**, **Add below** or **Skip if filled**.
3. Click **Fill** on a field card: **Description** (long text with a short introduction and a feature list), **Short description** (plain summary under about 400 characters), **Name**, **Meta title** (about 70 characters), **Meta description** (about 160 characters) or **Tags** (comma-separated words).
4. **SEO pack** with **Fill all** writes the name, both descriptions and both meta fields in one go. It replaces those fields whatever you chose under **If the field already has text**.
5. Optional: open **Use your own instruction or a saved prompt**. Type in **Filter by title or text**, pick **Standard brief** (a ready-made brief for the field you press) or an enabled template, or type your own **Instruction**.

You see the sent instruction and the reply under the buttons, and “Content successfully generated and updated to product.”. The product form on the screen is not refreshed. Reload the product page before you edit again. If you press **Save** on the old form, PrestaShop writes the old text back. The module shortens long replies to the field size: name 128 characters, short description 800, meta title 69, meta description 159.

**Simulate** has the same choices and the buttons **Try**. It shows the reply on the page and does not change the product. The attempt is written to History.

**Photos** (needs **AI Image Finder** on):

1. Click **Find pages**. The model suggests pages likely to show this product.
2. Click a page address. The shop reads the page (addresses of private or local networks are refused) and lists up to 24 pictures. Small icons and tracking pixels are skipped.
3. Tick the photos you want. The first photo you tick becomes the cover image of the product and replaces the current cover. The others are added after the existing photos.
4. Click **Add selected to this product**. Nothing is saved before this click. Reload the product to see the photos.

Photo searches are not written to History and do not count toward the budget. Respect the copyright of the photos you import.

**History** lists earlier writes for this product with **When**, **Type** and **Status**. **Restore** puts the previous text back after you confirm “Restore the previous value?”. You see “Content successfully restored. Refresh this page to see changes.”. The shop-wide History is not deleted.

Next to the description, short description, meta title and meta description fields (any product form) you also see a small round OpenAI-logo button **Generate with AI**. Click it. If the shop has more than one language, choose **Current language**, **All languages** or **Cancel**. The field receives a ready-made brief for that field, and the text goes into the form field only, with “Text is in the field. Save the product to keep it.”. Click **Save** on the product to keep it. This button does not use templates or the **Instruction** box.

### 3.14 Updates

Open **Updates** (right side of the top menu). The form **MyPresta Updates** checks MyPresta.eu for a newer module file. It does not change your catalog and does not install anything.

![Updates](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Field | Default | What it does |
|---|---|---|
| **Manual Check** | – | Click **Check Now**. The shop asks the MyPresta.eu update server once and shows “Module is up to date!” or “New version available!” next to the button. |
| **Automatic Notifications** | Enabled | **Enabled** lets the back office check about every three days and show a warning with a link when a newer version exists. **Disabled** stops that. |
| **Product Page** | – | A link to the module page on MyPresta.eu. |

Click **Save** to store the notifications choice. You see “Update settings saved.”. The version number next to the module name in the menu is the version installed on your shop, not the newest one.

## 4. Storefront

The module shows nothing to your customers. It adds no block, no page, no script and no style to the shop front. The theme has nothing to override. Everything you see is in the back office: the **My ChatGPT** top-bar button, the module screens and the product page panel.

The module has two web addresses that exist only for servers and for the back office:

- The **cron address**. Copy it from **Cron** (section 3.10) and put it only in your server scheduler. Anyone who knows the full address with the secret can start a batch, so never publish it, and do not paste it into chats or tickets.
- A technical address that the back-office buttons use for every generation. Do not open or share it.

Opening the cron address in a browser shows plain text. These are the messages you can read:

| What you see | What to do |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Open **Cron**, set **Enable Cron Feature** to **Yes** and click **Save**. |
| The token does not exist or it’s wrong! | The secret is missing or does not match. Copy the address again from **Cron** after saving. |
| Invalid action! | The address has no job part. Add the settings listed in section 6.3. |
| updatedField parameter is wrong! | The field name in the address is not one of the allowed fields. Use a field listed in **Update Field**. |
| All must include all mandatory parameters! | The address lacks field, selection rule, batch size, language or template. Add them (section 6.3). |
| productTarget parameter is wrong! Allowed values: … (or categoryTarget) | Use pendingOpenAI, pendingField or emptyField. |
| No valid product IDs provided. | The **Product ID list** holds no usable numbers. Fix or clear the list. |
| No products to update. / No categories to update. | Nothing matches the rule any more. The job is finished, or change **Selected Products** or the filters. |
| N products have been updated. / N categories have been updated. | One batch was written. The next call continues with the next items. |
| N pending products. | Debug is on. Nothing was written. Turn debug off for real runs. |
| Error!Monthly generation budget reached. | Raise **Monthly generation budget** or wait until next month. |
| Error!Reply rejected by the studio quality gate. | The reply contained a forbidden word. Edit **Forbidden words** or turn **Quality gate** off. |
| Error! The model returned an empty response. | Increase **Max Tokens**, try another model or template. |
| Error! followed by an OpenAI message | Read the message. Typical causes are a wrong key, no credit or an unknown model. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop refused the text for that item. Check the product, then run again. |

## 5. Problems
### 5.1 Connection and settings

| Symptom | Cause | What to do |
|---|---|---|
| “The OpenAI API key is not set. Add it in the module settings.” or “The ChatGPT API key is not set. Add it in the module settings.” | No key is stored. | Open **Settings**, **ChatGPT**, paste the key into **OpenAI API KEY** and click **Save**. |
| “OpenAI API KEY field is invalid!” | You saved a new key shorter than 10 characters while no key was stored. | Paste the full key. |
| “OpenAi Model field is invalid!” | **Model** has fewer than 3 characters. | Pick a model from the list and save again. |
| Message from OpenAI about an incorrect key, quota or a model that does not exist | OpenAI refused the call. The module shows OpenAI’s own text. | Check the key, your OpenAI billing and the model name in **Settings**, **ChatGPT**. A model you added must be available to your account. |
| “Error! Invalid token!” | The page was opened before the module renewed its internal secret, or it was open for a very long time. | Reload the page and try again. |
| “OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.” | OpenAI answered too slowly. | Raise **API timeout (seconds)** in **Settings**, **General** (up to 600), use a faster model or ask for shorter text. |
| “The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking.” | **Max Tokens** is too low for this model. | Raise **Max Tokens** in **Settings**, **ChatGPT**. |
| “The response was blocked by the provider content filter. Try rewording the prompt.” | OpenAI’s filter stopped the reply. | Reword the prompt or the product data it uses. |
| “The model returned an empty response.” | The model gave no text. | Try again, another model or a less strict prompt. |
| “Monthly generation budget reached. Raise it in the studio settings or wait until next month.” | The count of successful generations reached **Monthly generation budget**. | Raise the number in **Settings**, **Studio**, set it to 0, or wait for the next month. Clearing **History** also resets the counter. |
| “The reply was rejected because it contains a forbidden word from the studio settings.” | A line of **Forbidden words** appears in the reply, also inside a longer word. | Shorten or edit the list, or set **Quality gate** to **No**. Nothing was written to the product. |

### 5.2 Product page and generation results

| Symptom | Cause | What to do |
|---|---|---|
| The panel **My ChatGPT** is missing on the product page. | **Product edit page Form** and **Product Edit History** are both off, or you are not on the tab **Modules**. | Turn the switches on in **Settings**, **General**, then open the tab **Modules**. |
| “Save the product once before generating.” | The product has no number yet. | Save the product, then generate. |
| The new text vanished after I saved the product. | The product form on screen still held the old text. | After **Fill**, reload the product page before you edit and save. |
| “Product skipped.” or “Category skipped.” | **Skip if filled** found text in the field. This is not an error. | Choose **Replace**, **Add above** or **Add below** if you want to write anyway. |
| “Error! Content retrieve has failed! Details: …” | OpenAI or the server returned an error. | Read the details after “Details:”. Open **History**, filter **Status** by **Error**, and open the row. |
| “Error! The generated content could not be saved to the product.” or “… to the category.” | PrestaShop rejected the text, for example because of a forbidden character. | Read the reason after the sentence. Try another prompt or a shorter field. |
| “Error! Prompt is missing or too short!” | The instruction has fewer than 4 characters. | Write a longer instruction or leave the box empty to use the standard brief. |
| “Error! Product not found!” / “Error! Category not found!” | The item was deleted or the number is wrong. | Rebuild the list and run again. |
| “Error! This log entry has no previous value to restore.” or “Error! Nothing to restore for this entry.” | That History row has no old text. | Use another row. Rows written by **Simulate** or errors cannot restore anything useful. |
| “The model did not return a usable SEO pack.” | The reply was not in the expected format. | Click **Fill all** again, or fill the fields one by one. |
| “Generation failed.” on a **Generate with AI** button | The call failed. | Try again. See **History** for the reason. |
| “Error! This PrestaShop version does not support the category Additional Description field.” | Your shop has no such category field. | Choose another category field. |

### 5.3 Mass generation

| Symptom | Cause | What to do |
|---|---|---|
| The table after **Go to next step** is empty. | The filters match nothing. | Loosen the filters. Check **Product status**, **Product stock** and **Update only**. |
| “Select at least one language.” | No language is ticked. | Tick at least one language. |
| The run stopped in the middle. | The tab was closed, the connection dropped or the server stopped. | Build the list again with **Update only** set to products that have not been updated and run again. |
| Many rows show errors. | A budget, key or timeout problem. | Open **History** and read the first error, fix it and run again. |
| Home and the root category are in the category list. | **Categories** was left empty. | Tick the categories you want before **Go to next step**. |

### 5.4 Cron

| Symptom | Cause | What to do |
|---|---|---|
| Nothing changes in the catalog. | **Enable Cron Feature** is off, the scheduler does not call the address, or no item matches the rule. | Check the switch, the scheduler log and **Selected Products**. Open the address once with debug on to see the plan. |
| The address answers with a message from the table in section 4. | See that table. | Do what the table says. |
| The same products are written again and again. | **Selected Products** is **emptyField** and the field stays empty, or **pendingOpenAI** is used and History was cleared. | Use **pendingField**, or fix the prompt so that text is written. |
| An old address stopped working. | The module replaces secrets shorter than 24 characters, or the secret was changed or the module was reinstalled. | Copy the address again from **Cron** and update the scheduler. |
| **Generate Token** does nothing. | The button has no function in this release. | Keep the secret created at install. |

### 5.5 Images, new product and menu

| Symptom | Cause | What to do |
|---|---|---|
| The tab **Photos** is missing. | **AI Image Finder** is off. | Turn it on in **Settings**, **General** or **Images**, then reload the product. |
| “No pages were suggested.” or “The search failed.” | The model returned no usable addresses, or the key has a problem. | Click **Find pages** again, or check **AI Image Search Prompt**. |
| “That page could not be read.”, “URL not allowed (private network)” or an error starting with HTTP | The page blocks the shop, needs a login or is in a private network. | Choose another page. |
| “No photos were found on that page.” | The page has no usable pictures. | Choose another page. |
| “No images could be imported. Details: …” | The pictures could not be downloaded or are not real images. | Read the details. Choose other photos. |
| “Failed to parse AI response. Please try again.” on **New product** | The reply was not in the expected format. | Click **Generate data** again. |
| “Error creating product: …” or “Failed to create product” | PrestaShop refused the product, often because the chosen **Language** is not the shop default language. | Choose the default language and check the category number. |
| “Generate the product first.” | You clicked **Create product** before **Generate data**. | Click **Generate data** first. |
| The menu entry **AI Content Generator** is missing. | The module is disabled, or the entry was moved. | Enable the module in **Module Manager** and open any back-office page once. The module puts the entry back under **Modules**. If it is still missing, check that your employee profile may open **Modules**. |
| Dashboard and History are empty. | Nothing was generated in the chosen period, or **Clear list** was used. | Choose **All time**. |

## 6. Developer reference
### 6.1 Overview

| Item | Value |
|---|---|
| Technical name | mychatgpt |
| Version | 1.1.0 |
| Name in the module list | My ChatGPT - AI content generation |
| Author | MyPresta.eu |
| Module tab | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| Minimum PHP | 7.0.0 (checked in `install()`) |
| Main class | `mychatgpt extends Module`, with helper classes `mychatgptUpdate` and `searchToolmychatgpt` that extend it |

Data flow: back-office JavaScript calls the front controller `ajax` with `secret_token` (read from `MYPRESTA_MYCHATGPT_TOKEN`) or an admin controller. The controller reads the model and sampling keys, applies Studio (`MyChatGPT\Studio`), calls OpenAI through `MyChatGPT\OpenAIService` (cURL to the chat completions endpoint of the OpenAI API), writes the text with the PrestaShop object model and inserts a row into `mychatgpt_log`. `cron` does the same without a browser. `getServiceName()` always returns `openai`. Leftover code for other providers was removed. The settings keys of an earlier second provider (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) are deleted every time the settings screen opens.

### 6.2 Files

| Path | Purpose |
|---|---|
| `mychatgpt.php` | Main class: install and uninstall, tabs, settings forms, prompt templates, dashboard, hooks, product tab, model catalogue. |
| `autoload.php` | Small class loader for the `MyChatGPT\` namespace (no Composer). |
| `src/OpenAIService.php` | cURL client for chat completions and model listing. Timeout 10–600 s, drops parameters a model rejects (up to 6 retries), disables certificate checks only on localhost. |
| `src/Studio.php` | Budget check, prompt decoration (language, voice, audience, tone, glossary, forbidden), reply inspection, SEO pack and alt-text prompts. |
| `controllers/admin/*.php` | Seven admin controllers (section 6.3). |
| `controllers/front/ajax.php` | JSON endpoint for all browser-triggered generation. |
| `controllers/front/cron.php` | Plain-text cron endpoint. |
| `lib/updateChecker.php` | Update check against dev.mypresta.eu every 3 days and the Updates form. |
| `lib/sectionHelp.php` | Texts of the Help drawer. |
| `lib/searchTool/` | Helper class `searchToolmychatgpt` (autocomplete tool in the module screens). |
| `lib/prestashop9compatibility.php` | Wrappers for price display, hashing and redirects on PrestaShop 9. |
| `views/templates/hook/*.tpl` | Module screens and panels (dashboard, nav, subnav, mass generators, product tab, history, cron info, top-bar box). |
| `views/templates/admin/product_creator.tpl` | New product screen. |
| `views/js/back.js` | Mass runs, product panel, playground, top-bar box, new product, restore. |
| `views/js/product-fields.js` | **Generate with AI** buttons next to product fields. |
| `views/js/image-finder.js` | **Photos** tab. |
| `views/js/admin-products-bulk.js` | Adds the **My ChatGPT** button to the product list. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Charts and Help drawer. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Styles. |
| `translations/*.php` | 34 language files. |
| `upgrade/index.php` | Only a redirect file. There are no upgrade scripts. |

The classes `AdminMyChatGPTMain` and `AdminMyChatGPTSettings` call `addJS`/`addCSS` for `views/js/admin.js` and `views/css/admin.css`, and the new-product controller for `product_creator.js` and `product_creator.css`. None of these files is shipped. The cron form expects JavaScript functions `generateTokenAndFill()` and `generateCategoryTokenAndFill()` and fills `.cron-parameters` spans. That script is not shipped either.

### 6.3 Controllers

| Controller | Parent and route | Purpose |
|---|---|---|
| `AdminMyChatGPTMain` | Under **Modules**, visible. Redirects to the module configuration, Dashboard. | The **AI Content Generator** menu entry. |
| `AdminMyChatGPTSettings` | Hidden tab (`active = 0`). Redirects to configuration, Settings. | Compatibility entry. |
| `AdminMyChatGPT` (file `AdminMyChatGPT.php`, class `AdminMyChatGPTController`) | Hidden tab. `mcg_sub=products` or `categories`. | Filters and mass generators. `renderProductUpdateForm()` and the category update form have no handler. The `generateProductContent` and `generateCategoryContent` submits only save the form values. Generation runs from `back.js`. |
| `AdminMyChatGPTProductCreator` | Hidden tab. Ajax actions `generateProductData`, `createProduct`, `extractImages`, `generateImages` (stub). | New product. |
| `AdminMyChatGPTCron` | Hidden tab. Forms `submitCronUpdate`, `submitCatCronUpdate`. | Cron settings. |
| `AdminMyChatGPTUsage` | Hidden tab. Parameters `stats_*`, `view` and `clear_log`. | History. `clear_log` runs `DELETE` on the whole log table. |
| `AdminMyChatGPTImageFinder` | Hidden tab. Ajax actions `searchImages`, `extractImages`, `saveImages`. | **Images** form and photo search. |

All admin controllers redirect to the home screen if the module is inactive. The module configuration page (`getContent`) renders Dashboard, Settings (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) and Updates (`mcg_tab=updates`).

Front controller `ajax` (`secret_token` must equal `_TOKEN`; there is no employee check). Actions: `initiatePrompt`, `updateSettings` (writes max tokens, temperature, top p and both penalties), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (no button uses it; 8 images at most), `generateSeoPack`. `updateProduct` and `updateCategory` take `target` (field), `behavior` (`replace`, `keep`, `keep_top`, `keep_end`, or `single_product` for a preview that is not saved), `prompt`, language and the item number. Answers are JSON with `status` (`success`, `error`, `skipped`), `msg` and `date`.

Front controller `cron`: refuses with the “disabled” message when `_ENABLE_CRON` is 0. The `secret` parameter must equal `_SECRET` or `_CAT_SECRET` (either secret opens either job). Parameters:

| Parameter | Used by | Meaning |
|---|---|---|
| `secret` | both | Product or category secret. |
| `action` | both | `generateProductContent` or `generateCategoryContent`. |
| `updatedField` | both | Products: name, description, description_short, meta_title, meta_description, tags. Categories: name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | each | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | each | Batch size (`LIMIT`). |
| `languageId` | both | Language number. |
| `promptTemplateId` | both | Template number from `mychatgpt_prompt`. |
| `debug` | both | Any value except 0 prints the plan and writes nothing. |
| `categories` | products | Comma-separated category numbers. |
| `productIds` | products | Comma-separated product numbers. |

Example (use `YOUR_SECURE_KEY` only as a placeholder):

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` and `pendingField` look at successful rows of `mychatgpt_log` (rows with status error are ignored, so failed items are retried). The category job excludes categories with a number up to the home category.

### 6.4 Hooks

Registered in `install()`:

| Hook | Behavior |
|---|---|
| `displayAdminProductsExtra` | Renders the **Modules** tab panel (`product-tab-wrapper.tpl`) when `_PRODUCT` or `_PRODUCT_LOG` is 1. |
| `displayBackOfficeHeader` | Loads assets; runs `ensureLongSecrets()` (replaces `_TOKEN`, `_SECRET`, `_CAT_SECRET` shorter than 24 characters) and `placeModuleMenu()`; registers the **AI Image Finder** tab once (`_IMAGEFINDER_TAB_OK`); queues `product-fields.js`, `admin-products-bulk.js` and `image-finder.js` on `AdminProducts`; re-registers `dashboardZoneTwo` if missing. `product-fields.js` is queued on every product page, whatever `_PRODUCT` says. |
| `displayBackOfficeTop` | Defines JavaScript values (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) and renders the top-bar box when `_TOPCTA` is 1. |
| `dashboardZoneTwo` | Renders `dashboard.tpl`, which reads `mcg_*` variables that this hook does not assign. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Empty stub, returns an empty string. |
| `displayAdminProductsMainStepLeftColumnBottom` | Empty stub, returns an empty string. |
| `actionProductFormBuilderModifier` | No-op, returns nothing. |
| `displayHeader` | Empty stub. |
| `displayFooter` | Empty stub. |

The method `hookActionProductGridDataModifier` exists but is not registered. The module has no `enable()` or `disable()` override and exposes no hooks of its own.

### 6.5 Overrides

The module has no overrides.

### 6.6 Database

| Table | Contents |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Seeded with 16 rows. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, `old_*` and `new_*` pairs for name, description, description_short, meta_title, meta_description and tags, `date_updated`. Keys on `id_product` and `status`. |

Uninstall drops both tables. `ensureUsageColumns()` adds the three token columns when a screen opens, if an older table lacks them. Product, category and image rows written by the module are standard PrestaShop data and are not touched on uninstall.

### 6.7 Keys and translations

Keys use the prefix `MYPRESTA_MYCHATGPT_`. Values set at install:

| Key | Default |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | Random 32 characters |
| `_API_KEY` | One space |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Empty (the second one is filled at run time with rejected parameters per model) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Empty |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, long default prompt |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, empty, default language, empty, 0, empty |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, empty, default language, 0 |
| `PS_USE_HTMLPURIFIER` | Set to 0 (shop-wide) |

The cron keys without a prefix (`updatedField`, `debug` and the others above) are global names and can collide with other modules.

Created later: `_IMAGEFINDER_TAB_OK`, `categories` (cron category choice), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` also writes every filter field (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) to the configuration on each request of that controller, but nothing reads them back.

Uninstall deletes the keys listed in `uninstall()`. It does not restore `PS_USE_HTMLPURIFIER`. It leaves `categories`, the filter keys above and the update keys.

The generators, the cron and the usual validation use `Tools::getValue` with whitelists. The API key is stored as plain text in the configuration table. `randomString()` uses `rand()`.

Translations: add `translations/{iso}.php` in the standard PrestaShop module format (34 languages are shipped). Texts pass through `$this->l()` in the main class, the update checker and the help drawer. On PrestaShop 8 and 9 the admin controllers use `trans()` with the domains `Admin.MyChatGPT`, `Admin.MyChatGPTCron` and `Admin.MyChatGPTUsage`. Not translated: the messages inside `back.js`, `image-finder.js`, the default instructions used by **Fill** and **Generate with AI**, the output of `cron` and the error texts of `AdminMyChatGPTProductCreator` and `AdminMyChatGPTImageFinder`. The long help texts (“What it does / How to configure / Effect”) are built by `fieldHelp()` and live in the form definitions of `mychatgpt.php` and of the admin controllers (method `help()`), in the templates and in `lib/sectionHelp.php`. The names of the default templates and the menu names are written to the database in the shop languages at install.

### 6.8 Extending

- Add or edit prompt templates in the module screen or in `mychatgpt_prompt`.
- Add placeholders in the prompt builders of `ajax.php` (`updateProduct`, `updateCategory`) and of `cron.php`.
- Add models in **Settings**, **ChatGPT** with no code change. The module learns unsupported parameters by itself.
- Change the standard instructions for **Fill**, **Generate with AI** and mass runs in `back.js` and `product-fields.js`.
- The front office has no template, so the theme has nothing to override. The back-office templates in `views/templates` are changed in the module folder.

## 7. Help

Product page: https://mypresta.eu/modules/administration-tools/my-chatgpt.html

To write about the module:

1. Log in to your customer account on mypresta.eu.
2. Open the contact page.
3. Choose **Support for paid modules**.
4. Describe the problem. Give the exact message from the screen and the steps that lead to it. Never paste your OpenAI API key or a full cron address with the secret.
