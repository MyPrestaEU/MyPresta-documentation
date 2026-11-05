---
title: "My AI Mistral - AI content generation - documentation and user manual"
description: "Configuration, daily-use and troubleshooting instructions for merchants who already have My AI Mistral installed in their PrestaShop store."
sidebar:
  label: "My AI Mistral - AI content generation - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Meta and catalog descriptions with Mistral AI Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Requirements

### 1.1 Shop and server

| Item | Needed | Notes |
|---|---|---|
| PrestaShop | 1.6 up to 9.x | The module declares support for versions 1.6 to 9.99.99. The **My AI Mistral** tab on the product edit page and the small "Generate with AI" buttons are built for PrestaShop 1.7, 8 and 9. |
| PHP | 7.0 or newer | Installation stops with a message when the server runs an older PHP. |
| PHP extensions | cURL, JSON, mbstring, DOM | cURL is used for every call to Mistral AI. DOM and mbstring are used to read the web pages of the photo finder and to measure and cut the generated text. |
| Outgoing connection | HTTPS (port 443) to `api.mistral.ai` | The server must be allowed to call the Mistral AI API. Hosting plans that block outgoing connections do not work. |
| Shop front address | Reachable from the browser | The buttons in the back office send their requests to an address on your shop front. A password prompt, a firewall rule or a maintenance page that blocks that address makes the buttons fail. |

### 1.2 Mistral AI account

1. Create an account in the Mistral AI console and open the page for API keys: https://console.mistral.ai/api-keys/
2. Create a key and copy it. The console shows it once.
3. Make sure the account may use the API (a plan or billing that includes API access). Every generated text is one API request that is paid or counted against your quota.

The module needs no other module and adds no override. It shows nothing to your customers.

### 1.3 Costs and load

- One generated field in one language is one request. A batch of 40 products with descriptions and meta tags in two languages is 40 × 4 × 2 = 320 requests, because the descriptions option writes two fields and the meta option writes two fields.
- Each request waits for the answer for up to the time set in **API timeout (seconds)** (120 seconds by default). A large batch started from the browser is slow by nature; use cron for big catalogs.
- The module can stop generating after a monthly number of successful requests (**Monthly generation budget** in Studio).

## 2. Installation

### 2.1 Installing the module

1. Open **Modules > Module Manager** (**Modules and Services** in PrestaShop 1.6).
2. Click **Upload a module** (**Add a new module** in 1.6) and choose the module ZIP file.
3. Click **Install**, then **Configure**.

What the installation does for you:

- It adds the back-office menu entry **AI Content Generator** under **Modules**. It opens the module settings page, and all other screens are reached from the menu bar at the top of that page.
- It creates two database tables: one for the prompt templates and one for the history of requests.
- It saves 16 ready-made prompt templates (product names, descriptions, meta titles, meta descriptions and tags). All of them start enabled.
- It generates the secret codes for the back-office buttons and for cron, and selects the model **mistral-small-latest**.
- It does not clear the PrestaShop cache. If the menu entry does not appear, clear the cache in **Advanced Parameters > Performance**.

On the first visit you may see a green message "Mistral AI API Key has been automatically cleaned (whitespace removed)". It only means the empty placeholder key was tidied up. Nothing is wrong.

### 2.2 First steps after installation

1. Open **AI Content Generator > Settings > Mistral** and paste your API key.
2. Keep the default model for a first test and click **Save**.
3. Open **Settings > Playground**, write one short instruction and click **Generate**. A reply shows that the connection works.
4. Open an existing product, go to its **Modules** tab, choose **My AI Mistral**, open **Simulate** and click **Try** next to **Meta title**. The text is shown and nothing is saved.

### 2.3 Updating

Upload the new ZIP in the Module Manager in the same way as for the first installation. Settings, templates and history are kept. The **Updates** page of the module reports whether a newer version exists (section 3.15).

### 2.4 Uninstalling

Uninstalling removes the menu entries, the prompt templates, the whole history of requests and the module settings, including the API key and the cron secrets. A reinstall starts from scratch and creates new secrets, so every address you gave to a scheduler must be replaced.

Texts already written to products and categories, imported photos, products created with **New product** and tags stay in your shop. The update-check settings and a few leftover filter values are not removed.

## 3. Configuration and back-office work

### 3.1 How the work flows

1. **Connect** – paste the API key and choose the model (Settings – Mistral).
2. **Set the rules** – house rules, budget and quality check (Settings – Studio).
3. **Prepare prompts** – edit or add prompt templates (Settings – Prompt templates) and try them in the Playground.
4. **Generate** – choose one of three ways:
   - one product at a time, from the product edit page (section 3.16) or with the small "Generate with AI" buttons next to the fields (section 3.17);
   - many products or categories at once, from the Generate pages (sections 3.9 and 3.10);
   - automatically in small batches, with cron (section 3.12).
5. **Check** – every request is written to History (section 3.13). A wrong text can be restored from the product's own History tab.

Each settings page has its own **Save** button. Save a page before you leave it, because the pages do not share one form.

### 3.2 Opening the module and the menu bar

Open **Modules > AI Content Generator**, or click **Configure** in the Module Manager. Every screen shows the same menu bar at the top:

| Menu item | What it opens |
|---|---|
| Dashboard | Usage cards and charts (section 3.3). |
| Settings | A group with five sub-pages: General, Mistral, Studio, Prompt templates, Playground (sections 3.4 to 3.8). |
| Generate | Mass generation for products and for categories (sections 3.9 and 3.10). |
| New product | Create a product from a short brief (section 3.11). |
| Cron | Addresses for scheduled generation (section 3.12). |
| History | List of all requests with filters and token totals (section 3.13). |
| Images | Settings of the photo finder (section 3.14). |
| Updates | Update check (section 3.15). |

Every screen has a **Help** button. It opens a side panel with a short explanation of that screen. Hovering over a menu item shows a one-line hint. Under each field you find a description in three parts: what the field does, how to set it and what the effect is.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

The Dashboard counts what the module did in the selected period. The line at the top names the active service and the model.

| Element | Default | What it shows |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | filled by the period | A custom range. If From is later than To, the two dates are swapped. |
| Requests | – | Every stored call to Mistral AI in the period. |
| Success | – | Calls that returned a text. |
| Errors | – | Calls that failed. Open History to see why. |
| Tokens sent | – | Size of the instructions you sent. |
| Tokens received | – | Size of the answers. |
| Requests and errors | – | Line chart per day. |
| Tokens sent and received | – | Line chart per day. |
| Requests by model | – | Bar chart. |

The page only reports. Nothing in the catalog is generated or changed from here, and History is not deleted.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Open **Settings > General**. This page decides what employees see in the back office. Saving it does not change any product text.

| Field | Default | What it does |
|---|---|---|
| Live mode | Disabled | Marks the module as running on the real shop rather than a trial setup. Enable it on the production shop. |
| Debug mode | Disabled | Writes extra diagnostic detail to the PrestaShop log when a call to the provider fails. Turn it on only while you investigate an error. Customers never see it. This is not the same as **Enable Debug** on the Cron page. |
| API timeout (seconds) | 120 | How many seconds one call to Mistral may run before the module gives up. The value is kept between 10 and 600. An empty or non-numeric value is saved as 120. Raise it toward 600 for long texts and slow models. |
| Product Edit History | Enabled | Shows the **History** sub-tab on the product edit page, so you can put an old value back. Past rows stay in History either way. |
| Admin Top Bar CTA | Enabled | Shows the small wand icon in the back-office top bar. Disabling it removes only that button, not the module menu. |
| Product edit page Form | Enabled | Shows the **My AI Mistral** panel (Generate, Simulate, Photos) in the **Modules** tab of the product edit page. Disable it when only mass generation and cron should be used. The small "Generate with AI" buttons next to the fields (section 3.17) are not switched off by this setting in this version. |
| AI Image Finder | Enabled | Shows or hides the photo search on the product edit page. An image is imported only after you confirm it. |
| AI Image Search Prompt | Built-in instruction | The instruction sent when someone searches for photos. `{product_name}` and `{product_description}` are replaced with the current product. Keep the request for a list of page addresses in JSON form. The same two fields are repeated on the **Images** page. |

Click **Save**. The confirmation is "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Open **Settings > Mistral**. The page connects the shop to your Mistral AI account and sets how varied the wording is. The sampling fields do not change which products are updated.

| Field | Default | What it does |
|---|---|---|
| Mistral AI API KEY | empty | The key from https://console.mistral.ai/api-keys/. Spaces are removed when you save. Leave the field untouched to keep the stored key. A value shorter than 10 characters is refused while no key is stored. |
| Model | mistral-small-latest | The model that writes the text. The list holds the built-in models and the models you added. A model your key cannot use returns an API error instead of text. |
| Add a Mistral model | empty | Type the exact model name from your Mistral account and press **Add model**. The new name appears in the **Model** list and becomes the active model at once. Names may contain letters, digits and the characters `.`, `_`, `:` and `-`. Next to every added name there is a **Remove** link. Built-in models cannot be removed. |
| Max Tokens | 3200 | The longest answer in tokens. Use about 256 for a meta description and 1000 or more for a full HTML description. Too low a value cuts the text off. A high value costs more. |
| Temperature | 0.7 | How freely the model chooses words, from 0 to 1. About 0.2 suits meta texts, about 0.7 suits descriptions. Change either Temperature or Top P, not both. |
| Top P | 1 | Another way to limit how surprising the next word can be, from 0 to 1. Leave 1 if you set Temperature. |
| Frequency Penalty Value | 0 | From -2 to 2. A positive value such as 0.3 to 0.6 reduces repeated phrases inside one answer. |
| Presence Penalty Value | 0 | From -2 to 2. A positive value spreads the text over more points. Some models ignore it. |

The built-in models are: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest and open-mistral-nemo.

If Mistral refuses one of the numeric settings for a given model, the module remembers it, leaves that setting out for that model and retries. You do not need to do anything.

The model name field must hold at least 3 characters when you save, otherwise the page shows "OpenAi Model field is invalid!". The confirmation after saving is "OpenAi Settings Updated". The messages "Model added.", "Model removed." and "That model is already built in." belong to the add and remove buttons.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio is applied on top of every prompt, wherever the request starts: product page, Generate pages, cron, Playground or the top bar. Empty fields are skipped.

| Field | Default | What it does |
|---|---|---|
| Brand voice | empty | A short brief telling the model who is speaking, for example "specialist workshop, short sentences, no hype". |
| Audience | empty | The reader to write for, for example "professional installers". |
| Tone | empty | The mood of the wording. One or two words are enough. |
| Glossary | empty | Brand names, materials and spellings the model must copy exactly. One term per line. |
| Forbidden words | empty | Words and phrases that must not appear in a saved reply. One per line. Used only when Quality gate is Enabled. |
| Monthly generation budget | 0 | The most successful generations allowed in the current calendar month. 0 means no limit. The counter starts again on the first day of the month. When the number is reached, generation stops with a budget message. Failed calls are not counted. |
| Quality gate | Enabled | Checks every reply against Forbidden words before anything is saved. A reply that contains a listed word is rejected, is not written to the product and is stored in History as an error. When Disabled, the reply is saved anyway. |

Click **Save studio**. The confirmation is "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

A prompt template is a saved instruction. The page shows the list **Prompt Templates** with a button to create a new one.

#### The list

| Column | What it shows |
|---|---|
| ID | Number of the template. |
| Title | The name you see in the template lists. |
| Prompt | The text of the instruction. |
| Status | Click the icon to switch a template on or off. |
| Timestamp | Creation time. |

Each row has **Edit** and **Delete**. Tick several rows and use the bulk **Delete** to remove them. Newest templates are on top.

#### The form "Generate Prompt Template"

| Field | Default | What it does |
|---|---|---|
| Status | not set | Enabled templates are offered in the product panel, the Generate – Products page and the top bar. Disabled ones stay in the table but are not offered there. Choose **Enabled** before you save, because a new template starts without a choice. |
| Prompt title | empty | The name shown in the dropdowns. It is not sent to the model. Required. |
| Prompt content | empty | The instruction sent to the model. Placeholders in curly braces are replaced for each item before sending. Double quotes are replaced with single quotes when you save. Required. |

Click **Save Prompt**. The confirmations are "Prompt template successfully added!", "Prompt template successfully updated!" and "Prompt template removed.". **Go Back to Module Settings** returns to the list.

#### Placeholders

| Placeholder | Replaced with | Works in |
|---|---|---|
| {product_name} | Product name | Product generation |
| {product_description} | Long description | Product generation |
| {product_description_short} | Short description | Product generation |
| {product_tags} | Current tags | Product generation |
| {product_reference} | Reference | Product generation |
| {product_ean13} | EAN-13 code | Product generation |
| {product_weight} | Weight | Product generation |
| {product_brand} | Brand name | Product generation |
| {product_default_category} | Default category name | Product generation |
| {product_category_description} | Description of the default category | Product generation |
| {product_categories} | Names of all categories of the product | Product generation |
| {product_attributes} | Combination attributes (group and value) | Product generation |
| {product_features} | Feature names | Product generation |
| {product_feature_values} | Features with their values | Product generation |
| {product_images} | Addresses of the product photos | Product generation |
| {category_name} | Category name | Category generation |
| {category_description} | Category description | Category generation |
| {category_parent_name} | Name of the parent category | Category generation |
| {shop_name} | Shop name | Product and category generation |
| {shop_url} | Shop domain | Product and category generation |
| {shop_language} | Language name | Product and category generation |
| {shop_country} | Default country | Product and category generation |
| {shop_currency} | Default currency code | Product and category generation |

"Product generation" means the product panel, Generate – Products and the product cron. "Category generation" means Generate – Categories and the category cron. Placeholders are not replaced in the Playground and in the top bar box, because no product or category is selected there. A placeholder with no data is replaced with an empty text.

#### The 16 templates that come with the module

| No. | Title | Purpose |
|---|---|---|
| 1 | Product name 1 | A short, better name based on the current name. |
| 2 | Product name 2 | A selling title that uses the brand and the default category. |
| 3 | Product description 1 | HTML description with three headings and the tags in bold. |
| 4 | Product description 2 | Description in three plain sections. |
| 5 | Product description 3 | A long SEO brief that also asks for heading ideas, keywords and meta texts. |
| 6 | Product description 4 | A short "captivating description" request. |
| 7 | Product description 5 | Description that uses the product tags as keywords. |
| 8 | Product description 6 | Description that uses the brand and the default category. |
| 9 | Product description 7 - using product images | Description that embeds the product photos through {product_images}. |
| 10 | Product meta title 1 | SEO meta title, up to 60 characters. |
| 11 | Product meta title 2 | A second meta title variant. |
| 12 | Product meta title 3 | Meta title that includes the brand. |
| 13 | Product meta description 1 | SEO meta description, up to 160 characters. |
| 14 | Product meta description 2 | A second variant; the example text mentions a smartwatch. |
| 15 | Product meta description 3 | The same text as number 14. |
| 16 | Product tags | Five tags on one line, separated by commas. |

Read and adjust the templates before you use them on real products:

- Template 3 asks the model to add a few spelling mistakes to the text. Delete that sentence.
- Template 5 returns more than a description (heading ideas, a keyword list and meta texts). Use it for inspiration, not for saving straight into the description field.
- Templates 5, 10, 13 and 16 ask for an answer in English. Change that line if your shop uses another language.
- Templates 14 and 15 are written for a smartwatch. Replace the example before you use them.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

The Playground sends one free prompt to the active model and prints the answer under the button. The reply stays on this page. No product or category is saved.

| Element | Default | What it does |
|---|---|---|
| Prompt box | empty | The instruction for this single call. Studio rules are added to it. |
| Generate | – | Sends the prompt. While waiting, the answer area shows "Working…". |
| Answer area | – | The reply from the model with the number of tokens used. |

Messages: "Write a prompt first." (the box is empty) and "The request timed out or the shop blocked it." (see section 5.2).

The request is recorded in History like every other request.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Open **Generate** and stay on **Products**. The work has two steps: build a list, then run the generation on it.

#### Step 1 – build the list ("Filter products to update")

Nothing is sent to the model in this step. The filters start with the values below every time you open the page.

| Field | Default | What it does |
|---|---|---|
| Product Categories | none ticked | Category tree. Only products that sit in a ticked category, or have it as the default category, are listed. Leave the tree empty to ignore category. |
| Brand | Select brand (all) | Only products of one brand. |
| Product status | Active | **Active**, **Disabled** or **Both**. |
| Product stock | All products | **All products** or **Only in stock products**. |
| Update only | Update all | Uses History: **Products that have not been updated with OpenAi content** lists products with no row in History, **Products that already have been updated with OpenAi content** lists products with a row, **Update all** ignores History. The word "OpenAi" in the first two choices is an old label; it means this module. A row of any status counts, also a failed one. |
| Product IDs | empty | Product IDs separated by commas, for example 12,45,103. Type only digits and commas. |
| Product Reference | empty | One or more references separated by commas. The reference must match exactly. |
| Product Add Date From | empty | Only products created after this date and time. |
| Product Add Date To | empty | Only products created before this date and time. |
| Minimum product ID | empty | The smallest product ID in the list. |
| Maximum product ID | empty | The largest product ID in the list. |
| Product Limit | empty | The most products to load. Use a small number such as 20 on a large catalog. |

Click **Go to next step**. The button **Module settings** next to it is an old shortcut and does not open this module's settings.

#### Step 2 – run the generation ("Mass product generation")

| Field | Default | What it does |
|---|---|---|
| Template | Choose a template | Copies an enabled template into the prompt box. The title itself is not sent. |
| Prompt box | empty | The instruction sent for every product, with placeholders replaced per product. If the box is empty, a standard brief for each field is used. |
| What to generate | Descriptions | **Descriptions** (long and short description), **Meta title and meta description**, or **Descriptions and meta together** (all four). Each field is its own request. |
| Existing text | Replace | **Replace** overwrites the text. **Skip if filled** leaves a filled field alone and does not call the model for it. **Add above** and **Add below** keep the old text and attach the new text. |
| Languages | your back-office language ticked | Tick every language to write. Each ticked language is one more request per field. |

Click **Run on the list below**. The table lists the products by ID and reference. The run goes through every product, field and language one by one. The line above the button shows the progress, for example "3 / 120 – description", and the **Result** column shows the answer for each step. "skipped" means the field already had text and you chose **Skip if filled**. When it ends, the line says "Finished N products.".

You cannot untick single products in the table. Change the filter in step 1 to change the list. Names and tags are not part of this run; use the product edit page or cron for them. Text is saved as each answer arrives. Closing the page stops the run, and the products already done keep their new text.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Open **Generate** and switch to **Categories**.

#### Step 1 – build the list ("Filter categories to update")

| Field | Default | What it does |
|---|---|---|
| Categories | none ticked | Tick the categories to list. With nothing ticked, the list contains every category that matches the status, including Root and Home. Tick specific categories to avoid that. |
| Category status | Active | **Active**, **Disabled** or **Both**. |

Click **Go to next step**.

#### Step 2 – run the generation ("Mass category generation")

| Field | Default | What it does |
|---|---|---|
| Prompt box | empty | The instruction sent for every category. Use {category_name}, {category_description}, {category_parent_name} and the shop placeholders. There is no template list on this page. |
| Field | Description | The field to write: **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. Only that field is saved. |
| Existing text | Replace | **Replace** or **Skip if filled**. |
| Language | your back-office language | One language. Run again for another language. |

Click **Run on the categories below**. The table lists the category IDs and shows a result for each.

If the prompt box is empty, a standard brief is used for description, meta title and meta description. For **Name** and **Additional description** the description brief would be used, so always type your own prompt for those two fields.

Below the list the page also shows the older form **Generate category content** with its button **Generate content**. It does not generate anything. Use the run button above it.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** asks the model for a full product draft and can insert it into the catalog.

| Field | Default | What it does |
|---|---|---|
| What is the product? | empty | A few sentences: what the product is, materials, audience, names to keep. A richer brief gives a closer draft. An empty box is refused. |
| Optional source URL | empty | A full http or https address of a public page. Its readable text is added to the brief. A page the shop cannot read is ignored. |
| Language | shop default language | The language in which name, descriptions, meta and tags are saved. Other languages are not filled. |
| Default category ID | 2 | The number of the category from **Catalog > Categories**. 2 is usually Home. The product is placed there. |

Buttons:

- **Generate data** shows the draft as plain text in the box below the buttons. It does not save anything. The draft contains the name, descriptions, meta texts, tags, reference, a suggested price and features.
- **Create product** inserts the last generated draft. The new product is **active**, has stock **100**, uses the first tax rules group of the shop and is placed in the category you typed. After success the box shows "Product #" and the new product number.

The draft cannot be edited on this page. Check the price, tax, photos and category in the product afterwards; the price is the one the model suggested and can be 0. The page shows "Add an API key in the module settings first." when no key is saved.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Cron lets your server update a few products or categories each time a scheduler opens an address. The page shows: the panel **Category cron**, the form **CRON JOB Settings - Generate product content using Mistral AI**, the form **CRON JOB Settings - Generate category content using Mistral AI** and the panel **Cron parameters**. The forms only build and store settings; nothing runs until your server calls the address.

#### The cron address

The product address looks like this:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

The category address looks like this:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Replace `YOUR-SHOP.EXAMPLE` with your shop address.
- Replace the secret with the **Cron Job Secret Token** of the matching form. Never publish it.
- The part `&action=generateProductContent` or `&action=generateCategoryContent` is required. Without it the address answers "Invalid action!".
- The panels on the page show the address only up to the secret. The category panel adds `&entity=category`, which the shop does not use. Add the `action` part yourself as shown above.
- The line "Command:" inside each form shows only the plain address without the secret and the action. Build the full address yourself.

#### Product form

| Field | Default | What it does |
|---|---|---|
| Enable Cron Feature | No | The master switch for both the product and the category cron. When No, every cron address answers that the feature is disabled. |
| Cron Job Secret Token | random, 32 characters | The password in the product address. It must have at least 24 characters. A shorter secret is replaced with a random one when the module page loads. |
| Update Field | description | One field per scheduler entry: name, description, description_short, meta_title, meta_description or tags. To fill several fields, create several entries. |
| Selected Products | pendingMistral | Which products still wait. **pendingMistral** takes products that have no successful row in History for any field. **pendingField** takes products with no successful row for the chosen field, so several entries can fill different fields of the same products. **emptyField** takes products where the chosen field is empty in the chosen language. |
| Product Categories | none ticked | Limits the run to products in the ticked categories. See the warning below. |
| Product ID list | empty | A fixed list of product IDs separated by commas. Letters are dropped when you save. |
| Language | shop default language | The language to write. Other languages need their own entry. |
| Product to update | 5 products | How many products to process per call: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 or 1000. Start with 5 or 10 so a slow model does not hit the server time limit. |
| Prompt Template | first template in the list | The saved instruction used for every product. See the note below. |
| Enable Debug | No | When Yes, the address prints what it would do and saves nothing. |
| CRON JOB interval | Every Hour | A reminder of how often you plan to call the address (from every minute to every 6 hours). The module does not start anything by itself. |

Click **Save**. The list for **Prompt Template** has no empty choice and shows every saved template, also disabled ones, newest first. Until you saved one, the form displays the newest template (Product tags). Always choose the template you want and save, otherwise the shown template is stored.

Warning: when **Product Categories** has ticked categories, the shop also picks products whose default category is ticked even if they were already processed. The cron may then rewrite the same first products on every call. Leave the category tree empty and use **Product ID list** instead.

#### Category form

| Field | Default | What it does |
|---|---|---|
| Cron Job Secret Token | random, 32 characters | The password in the category address. At least 24 characters. |
| Update Field | description | name, description, meta_title or meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** or **emptyField**, with the same meaning as for products. |
| Language | shop default language | The language to write. |
| Categories to update | 5 categories | How many categories per call (same choices as for products). |
| Prompt Template | first template in the list | The saved instruction. Write it for a category, not for a product. |
| Enable Debug | No | When Yes, the address prints the plan and saves nothing. |
| CRON JOB interval | Every Hour | A reminder only. |

Click **Save** under the form. Root and Home are never processed by the category cron. The switch **Enable Cron Feature** is in the product form and also controls the category cron.

#### Secrets and "Generate Token"

If you want a new secret, type it into the field by hand, at least 24 characters, letters and digits. The **Generate Token** button may not fill the field in this version, so do not rely on it. After you save a new secret, change it in your scheduler too, because the old address stops working. Either secret opens either action, so keep both private.

#### Setting up the scheduler

On a Linux server add a line like this to the crontab (every hour):

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Keep the address in quotes, because it contains the `&` sign. On Windows use the Task Scheduler with `curl.exe` and the same address. Hosting panels with a "cron job" screen take the same command.

#### Testing safely

1. Save the form with **Enable Cron Feature** set to Yes and **Enable Debug** set to Yes.
2. Open the full address in a browser. You see the settings that were read, the query and the final prompt, and nothing is saved.
3. Set **Enable Debug** to No, save, and open the address again. The page now answers with a short text such as "5 products have been updated.".

If **Enable Debug** stays on, scheduled calls save nothing. This is the most common reason why a cron "does nothing".

The saved text is cut to the length PrestaShop allows: name 128, short description 799, meta title 69 and meta description 159 characters. The old text is kept in History, so you can restore it from the product page.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Every request to Mistral AI is written to History with its instruction, its answer or error, the model, the token counts and the time it took.

#### Filters and totals

| Element | Default | What it does |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | filled by the period | A custom range. |
| Model | Any | Only one model. |
| Type | Any | Only one kind of request, for example product_description or category_meta_title. |
| Status | Any | Success or Error. |
| Language | Any | Only one language. |
| Employee | Any | Only requests made by one employee. |
| Product / category ID | empty | Only requests for that record. |
| Prompt or reply contains | empty | A word searched in the instruction and in the answer. |
| Filter | – | Applies the filters. |

The cards show Requests, Success, Errors, Tokens sent, Tokens received, Tokens total and Average time. A dash means Mistral did not return a token count for that call. Under the cards there are tables **By day**, **By model**, **By type**, **By language** and **By employee** with the columns Group, Calls, Sent, Received and Total. A small number next to Calls is the number of errors in that group.

#### The list "Prompt history"

The list follows the filters and shows 50 rows per page.

| Column | What it shows |
|---|---|
| ID | Number of the log row. |
| Status | Success or Error. |
| Prompt | The first part of the instruction. |
| Reply / Error | The first part of the answer, or the error text. |
| Provider | The provider name, the model, the HTTP code and the time in seconds, separated by dots. The provider name still reads "openai". |
| Sent / Received / Total | Tokens. |
| Entity ID | The product or category the request was for. |
| Type | The kind of request. |
| Timestamp | When the request was made. |

Click **View** on a row to read the full prompt and reply. **Back to the list** returns to the list.

**Clear list** (toolbar) deletes all rows, not only the filtered ones, and shows "Log list successfully deleted.". It also resets the information the cron uses to know which items were already updated (the "pending" targets start again from the beginning), resets the monthly budget counter and removes the previous texts needed for **Restore**. There is no undo.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

The page **AI Image Finder** holds the same two settings as the end of Settings – General. Saving them does not download any image and does not change any text.

| Field | Default | What it does |
|---|---|---|
| AI Image Finder | Enabled | Shows or hides the photo search on the product edit page. |
| AI Image Search Prompt | Built-in instruction | The instruction sent when someone searches for photos. `{product_name}` and `{product_description}` are replaced with the current product. The built-in text asks for exactly 5 page addresses as a JSON list. Change the wording if you prefer manufacturer sites. A vague prompt returns unrelated links. |

Click **Save**. The confirmation is "Settings saved.".

How it works: the model suggests web pages that probably show the product, the module opens those pages and lists the photos it finds, and you tick the photos to import. The module does not check who owns the photos. Use only photos you have the right to use.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Element | Default | What it does |
|---|---|---|
| Manual Check – Check Now | – | Asks the update server for the latest version once. The answer is "Module is up to date!" or "New version available!". |
| Automatic Notifications | Enabled | About every three days the module checks in the background. When a newer version exists, employees see a warning banner in the back office. Choose Disabled to manage updates by hand. |
| Product Page | – | A link to the module page. |

Click **Save**. The confirmation is "Update settings saved.". The check sends the module name, its version and your shop address to MyPresta.eu.

### 3.16 Product edit page

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Open **Catalog > Products**, edit an existing product and open the **Modules** tab. Choose **My AI Mistral**. The tab has the sub-tabs **Generate**, **Simulate**, **Photos** and **History**. The first three appear when **Product edit page Form** is Enabled; **History** appears when **Product Edit History** is Enabled.

#### Controls shared by Generate and Simulate

| Element | Default | What it does |
|---|---|---|
| Language | first language | Click a language, or **Every language** to write all of them one after another. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** or **Skip if filled**. Shown on the Generate sub-tab only. |
| Use your own instruction or a saved prompt | closed | Opens a filter box and tiles: **Standard brief** and every enabled template. Click a tile to use it. |
| Instruction | empty | Your own text. When empty, the standard brief of the field you press is used. Placeholders are replaced for this product. |

The Instruction box keeps the text of the last run. After you press one button the box shows the brief that was used, and the next button reuses it. Clear the box before you press the button of another field.

#### Generate

Each card has a **Fill** button: **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** and **Tags**. The text is **saved on the product at once** and shown below the cards with the number of tokens. The card **SEO pack** has the button **Fill all**; it fills the name, both descriptions and both meta fields in one request and answers "SEO pack saved. Refresh the product to see it.".

Important: the product form that is open in your browser still holds the old texts. Reload the product page before you click **Save** in PrestaShop, otherwise the old texts overwrite the new ones.

#### Simulate

The same cards with the button **Try**. The text is shown on the page and the product is not changed. Use it to compare prompts and models before the module writes.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Click **Find pages**. The model suggests pages that probably show the product, and the module lists the photos found on them.
2. Tick the photos you want. The message says "Tick the photos you want, then add them to this product.".
3. Click **Add selected to this product**. The photos are downloaded and attached to the product. The message says "Done. Reload the product to see the new photos." or the number added.

When the finder is off the tab says so and points to Settings – General. Other messages: "No photos were found on the suggested pages.", "The search failed." and "The photos could not be added.".

#### History

A table with **When**, **Type**, **Status** and a **Restore** button for the last 50 requests of the product. **Restore** asks "Restore the previous value?", puts the previous text back and answers "Content successfully restored. Refresh this page to see changes.". The button is shown only for successful changes that kept a previous text. If there is none, the page says "No generations for this product yet.".

### 3.17 "Generate with AI" buttons next to fields

On the product edit page a small button with the Mistral logo sits next to the editors of **Description**, **Short description**, **Meta title** and **Meta description**. On the category edit page it sits next to **Description**, **Additional description**, **Meta title** and **Meta description**.

1. Click the button. If the shop has more than one language, choose **Current language**, **All languages** or **Cancel**.
2. Wait. The button shows a busy state while the request runs.
3. The text appears in the field. **Save** the product or category to keep it. Nothing is saved before you do.

The record must exist already. On a new product the button answers "Save the product once before generating." and on a new category "Save the category once before generating.". Errors appear in a message box, for example "Generation failed.".

These buttons always use the standard brief of the field, not your templates. House rules, the budget and the quality check from Studio and the model from Settings still apply.

### 3.18 Other shortcuts

| Place | What it does |
|---|---|
| Wand icon in the top bar | Opens a small box: optional **Template**, a text box and **Generate**. The reply is shown in the box; copy it where you need it. Nothing is saved and placeholders are not replaced. Hide the icon with **Admin Top Bar CTA** in Settings – General. |
| Products list | A **My AI Mistral** button next to the bulk actions or the toolbar of **Catalog > Products** opens the Generate page. |
| PrestaShop Dashboard | A small panel with shortcuts **Mass content**, **Log** and **Cron** and the link to MyPresta.eu support. |

## 4. Shop front

My AI Mistral has no customer-facing part. It adds no blocks, pages, scripts or styles to your shop pages, and customers cannot see that the module exists. Its two front addresses are used only by the back office and by your scheduler.

### 4.1 Addresses

| Address | Used by | What to do |
|---|---|---|
| /module/myaimistral/cron | Your scheduler (section 3.12) | Call it with the secret and the action as shown in section 3.12. |
| /module/myaimistral/ajax | The buttons in the back office | Do not call it by hand and do not put it in a scheduler. |

### 4.2 What the cron address answers

The address answers with plain text. A run stops at the first error; items already finished stay saved.

| Answer | Meaning | What to do |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** is No. | Set it to Yes and save. |
| The token does not exist or it's wrong! | The secret is missing, wrong or an old one. | Copy the current secret of the form. |
| Invalid action! | The `action` part is missing or misspelled. | Add `&action=generateProductContent` or `&action=generateCategoryContent`. |
| updatedField parameter is wrong! | The field is not one of the allowed ones. | Choose the field again and save the form. |
| All must include all mandatory parameters! | A saved setting is empty. | Save the form again, with a language and a template chosen. |
| productTarget parameter is wrong! Allowed values: … | The target value is unknown. | Choose **Selected Products** again. The same for the category form. |
| No valid product IDs provided. | **Product ID list** holds text but no valid number. | Fix or empty the list. |
| No products to update. / No categories to update. | Nothing matches the settings. | Change the filters or the target, or accept that the work is done. |
| 5 products have been updated. / 5 categories have been updated. | The run finished. The number is the count. | Check History for details. |
| 5 pending products. | Debug is on; nothing was saved. | Set **Enable Debug** to No. |
| Error! followed by a text | The provider returned an error. | Read the text, see section 5.2. |
| Error! The model returned an empty response. | Mistral sent no text. | Raise **Max Tokens** or change the template. |
| Error! Could not save product 12: … | PrestaShop refused the text for that product. | Read the reason that follows; the run stopped there. |

## 5. Problems

### 5.1 Installation and menu

| Symptom | Cause | What to do |
|---|---|---|
| The installer says the module requires PHP 7.0 or newer | The server runs an older PHP. | Switch the PHP version in your hosting panel and install again. |
| "Could not create the module database tables." | The database user cannot create tables. | Give the user that right or ask your host. |
| The menu entry AI Content Generator is missing | Old cache, the module is disabled, or the employee's profile has no permission. | Clear the cache, enable the module and check **Administration > Permissions** for the profile. |
| The product page has no My AI Mistral panel in the Modules tab | **Product edit page Form** and **Product Edit History** are both Disabled, or the page is cached. | Enable the setting in Settings – General and reload the product page. |

### 5.2 Connection to Mistral AI

| Symptom | Cause | What to do |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | No key is saved. | Paste the key in Settings – Mistral. |
| "Mistral AI API KEY field is invalid!" | Fewer than 10 characters and no stored key. | Copy the whole key from the console. |
| "Mistral AI API Error (401): …" | The key is wrong, revoked or from another account. | Create a new key and paste it again. |
| "Mistral AI API Error (429): …" | A Mistral limit was reached. | Wait a minute and try again, use smaller batches or raise your plan. |
| "Mistral request timed out after N seconds…" | The model is slow or the text is long. | Raise **API timeout (seconds)** in Settings – General or use a faster model. |
| "The request timed out or the shop blocked it." | The server, a firewall or the shop front blocked the request. | Allow outgoing HTTPS to the Mistral API and make the shop front address reachable. |
| The model is not found | A model name that your Mistral account cannot use. | Choose another model from the list. |
| The Model list switched to gpt-4o after you removed a model | The module falls back to an old default name. | Choose a Mistral model again and save. |
| "Error! Invalid token!" | The secret held by the open back-office page no longer matches the one in the shop, for example after a reinstall. | Reload the page. |

### 5.3 Generation

| Symptom | Cause | What to do |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | The API returned an error. The details name it. | Read the details and the row in History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | The Studio limit is used up. | Raise the budget or wait for the next month. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate found a word from your list. | Edit the list or the prompt and run again. |
| "The model returned an empty response." or "The model hit the token limit before returning any text…" | **Max Tokens** is too low or the model spent it thinking. | Raise **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral refused the content. | Reword the prompt. |
| "Error! Prompt is missing or too short!" | The prompt has fewer than 4 characters. | Write a longer instruction or leave the box empty. |
| A meta title or meta description ends abruptly in a cron run | The cron cuts meta titles at 69 and meta descriptions at 159 characters. | Ask the prompt for a shorter text. |
| The product shows the old text after generation | The product form open in the browser was saved over it. | Reload the product page before you click Save. |
| A row says "skipped" | The field had text and you chose Skip if filled. | Choose Replace to overwrite. |
| The same brief is used for two fields | The Instruction box still holds the previous brief. | Clear the box before pressing another field. |
| Name or Additional description gets a description-like text in Generate – Categories | The empty prompt uses the description brief for those two fields. | Type your own prompt. |
| "Error! This log entry has no previous value to restore." | The row kept no old text, or the list was cleared. | The old text cannot be recovered by the module. |
| "Error! This PrestaShop version does not support the category Additional Description field." | Older PrestaShop. | Skip that field. |

### 5.4 Photos and New product

| Symptom | Cause | What to do |
|---|---|---|
| The Photos tab says the finder is off | **AI Image Finder** is Disabled. | Enable it in Settings – General or Images and reload the product page. |
| "No photos were found on the suggested pages." | The suggested pages have no usable photos. | Click **Find pages** again or add the photos by hand. |
| "The photos could not be added." | The server could not download them. | Choose other photos. |
| "Failed to parse AI response. Please try again." | The model returned data the module cannot read. | Click **Generate data** again or raise **Max Tokens**. |
| "Generate the product first." | **Create product** was clicked before **Generate data**. | Generate first. |
| "Prompt is required" | **What is the product?** is empty. | Describe the product. |

### 5.5 Cron

| Symptom | Cause | What to do |
|---|---|---|
| The address answers but nothing changes | **Enable Debug** is Yes. | Set it to No and save. |
| The address says the feature is disabled | **Enable Cron Feature** is No. | Set it to Yes. |
| The secret changed by itself | A secret shorter than 24 characters was replaced. | Copy the new secret from the form and update the scheduler. |
| The same products are rewritten each time | **Product Categories** is ticked (see section 3.12). | Leave the category tree empty and use **Product ID list**. |
| The cron uses the wrong template | The form displayed the newest template and that choice was saved. | Choose the right **Prompt Template** and save. |
| "Generate Token" does nothing | The script of the button is not shipped in this version. | Type the new secret yourself. |
| "Command:" in the form shows no secret | It shows the plain address only. | Build the address as in section 3.12. |
| The address ends in a time-out | Too many items per call. | Lower **Product to update**. |
| Everything is processed again after a while | **Clear list** in History removed the log that marks finished items. | Do not clear History while a cron is running, or use **Product ID list**. |

### 5.6 Texts that mention OpenAI or ChatGPT

The module was built from an earlier module for another AI provider. A few texts still show the old name. They do not change how the module works.

| Where | What you see | Meaning |
|---|---|---|
| Settings – Mistral | The model name example in the add field is a GPT name; the messages "OpenAi Settings Updated" and "OpenAi Model field is invalid!". | Only examples and wording. Type a Mistral model name. |
| Generate – Products | "OpenAi content" in **Update only**. | It means content from this module. |
| Generate pages | **Module settings** button. | An old shortcut that does not open this module. Use the menu bar. |
| History | The provider shows "openai". | Only a label. |

## 6. For the developer

### 6.1 Overview

| Item | Value |
|---|---|
| Module name | `myaimistral` |
| Display name | My AI Mistral - AI content generation |
| Version | 1.0.0 |
| Main class | `myaimistral` (`myaimistral.php`) |
| PrestaShop | 1.6 to 9.99.99 |
| PHP | 7.0.0 or newer (checked at install, constant `MIN_PHP_VERSION`) |
| API base | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Config prefix | `MYPRESTA_MYAIMISTRAL_` |
| Tables | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| CSS prefix | `.mam-` |
| URL parameters | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to`, and `stats_*` on History |

Folders: `controllers/admin`, `controllers/front`, `src` (autoloaded classes `OpenAIService` and `Studio` in the namespace `MyAIMistral`), `lib` (update checker, section help, PrestaShop 9 compatibility), `views/templates`, `views/js`, `views/css`, `translations`.

The module has no overrides and no front templates. Field help is written with the helper `fieldHelp($does,$how,$effect)`, which builds the "What it does / How to configure / Effect" text of each HelperForm `desc`.

### 6.2 Admin controllers, hooks and routing

| Controller class | Tab name | Purpose |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Redirects to `AdminModules&configure=myaimistral`. |
| `AdminMyAIMistral` | Mass Content Creator | Generate pages (products and categories). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Settings entry. |
| `AdminMyAIMistralCron` | Cron Job Settings | Cron forms. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Images page and the photo actions `searchImages`, `extractImages`, `saveImages`. |

Admin controllers redirect to `AdminHome` when the module is inactive.

Hooks registered at install: `displayBackOfficeHeader` (assets and `Media::addJsDef` values such as `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (top bar icon and dropdown), `displayAdminProductsExtra` and `actionProductFormBuilderModifier` (product tab), `actionProductGridDataModifier` (product list), `dashboardZoneTwo` (PrestaShop Dashboard panel), `displayAdminProductsMainStepLeftColumnMiddle` and `displayAdminProductsMainStepLeftColumnBottom` (empty), `displayHeader` and `displayFooter` (empty).

Navigation inside the module page uses URL parameters:

| Parameter | Values | Meaning |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (module page); the other tabs are controllers | The main tab on the module configuration page. |
| `mam_sub` | general, openai, studio, templates, playground (settings); products, categories (Generate) | The sub-tab. `openai` is the Mistral tab. |
| `mcg_preset` | today, 7, 30, 90, month, all | Period preset of the Dashboard. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Custom Dashboard range. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | see History | History filters. `clear_log` deletes the log. |

### 6.3 Cron contract

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Rule | Behaviour |
|---|---|
| Switch | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` must not be 0. |
| Authentication | `secret` must equal `SECRET` or `CAT_SECRET`. Either works for either action. |
| Optional overrides (products) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. They replace the saved values for that call only. |
| Optional overrides (categories) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Allowed fields | Products: name, description, description_short, meta_title, meta_description, tags. Categories: name, description, meta_title, meta_description, additional_description. |
| Targets | `pendingMistral`: no successful log row for the item. `pendingField`: no successful log row of type `product_FIELD` or `category_FIELD`. `emptyField`: the field is empty in the language. Rows with status `error` do not count. |
| Order and limit | `ORDER BY id ASC LIMIT n`. Category queries start after `PS_HOME_CATEGORY`. |
| Debug | When `debug` is 1, the SQL, the selected items and the final prompts are printed and nothing is saved. A saved debug value of 1 also stops scheduled saving. |
| Truncation | name 128, short description 799, meta title 69, meta description 159. Tags go through `Tag::addTags`. |
| Secrets | `ensureLongSecrets()` replaces secrets shorter than 24 characters. |
| Log | Every saved item writes a row with `method` `cron` and the old and new value. |

The category filter of the product cron is built as `... AND p.id_product IN (...) OR p.id_category_default IN (...)` without parentheses, so products with a ticked default category bypass the other conditions. The Generate – Products filter uses parentheses and is not affected.

### 6.4 AJAX controller

`/module/myaimistral/ajax` is a front module controller. Every call carries `secret_token` (the `TOKEN` value) and answers JSON `{status, msg, date}`.

| Action | Purpose |
|---|---|
| `initiatePrompt` | Playground and top bar. May carry `id_category`, `id_cms` or `id_manufacturer` to replace `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}`. |
| `updateProduct` | Generate one product field. Behaviours: `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (no save). `keep` answers status `skipped`. |
| `updateCategory` | The same for categories (`single_category` saves nothing). |
| `generateSeoPack` | Writes name, descriptions and meta fields in one request. |
| `generateAltTexts` | Writes image alt texts. No button in the interface. |
| `initiateProductRestore` | Restores a previous value from a log row. |
| `updateSettings` | Saves Max Tokens, Temperature, Top P and the penalties. |

The token is printed into back-office pages and the controller does not check an employee session. Treat the token as a secret.

`Studio::gate()` applies house rules, the monthly budget (counts rows that are not errors) and the forbidden-word check. `OpenAIService` calls Mistral with cURL, keeps the timeout between 10 and 600 seconds, retries up to six times without parameters the API rejects (remembered in `MODEL_CAPS`) and relaxes SSL verification only on localhost. The ajax controller extends PHP `max_execution_time` to match the timeout.

### 6.5 Configuration keys

All keys start with `MYPRESTA_MYAIMISTRAL_`.

| Key suffix | Default | Purpose |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | random | AJAX secret. |
| `SECRET` | random | Product cron secret. |
| `CAT_SECRET` | random | Category cron secret. |
| `API_KEY` | single space | Mistral key. |
| `MODEL` | mistral-small-latest | Active model. |
| `EXTRA_MODELS` | empty | Models added by the merchant, one per line. |
| `MODEL_CAPS` | empty | Parameters rejected per model. |
| `TEMPERATURE` | 0.7 | Sampling temperature. |
| `MAX_TOKENS` | 3200 | Answer limit. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Penalties. |
| `TIMEOUT` | 120 | Seconds, 10 to 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | empty | Studio texts. |
| `BUDGET` | 0 | Monthly request limit. |
| `QUALITY` | 1 | Forbidden-word check. |
| `IMAGEFINDER_ENABLE` | 1 | Photo finder switch. |
| `IMAGEFINDER_PROMPT` | built-in text | Photo finder instruction. |
| `ENABLE_CRON` | 0 | Cron switch. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Interval reminder (6 is Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, shop default language, empty, 0, empty, empty | Product cron form. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, shop default language, empty, 0 | Category cron form. |

The Generate page filters use the same prefix: `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, plus `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` and `EXISTING` of the old category form. They are written on every request of the Generate controller and are not removed at uninstall. The Product IDs value is inserted into the query as typed with spaces removed, so keep that page for trusted employees only.

### 6.6 Database

| Table | Columns | Notes |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 rows at install. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `old_*` and `new_*` field values, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Token columns are added on demand by `ensureUsageColumns()`. Both tables are dropped at uninstall. |

Values of `type` are for example `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` and `error`. Values of `method` are `initiatePrompt`, `updateProduct`, `updateCategory` and `cron`.

### 6.7 Front-end building blocks

| Item | Notes |
|---|---|
| Classes | Admin styles start with `.mam-` (navigation, dashboard, cards, chips, tiles, help drawer). The product panel uses `.myaimistral-ui` and the field buttons use `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, product panel buttons, mass runner, New product, restore, tabs, top bar dropdown. Product panel data attributes: `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | The field buttons on product and category pages. Reads `window.myaimistralField`. |
| `views/js/image-finder.js` | Photo search and import. |
| `views/js/admin-products-bulk.js` | The button in the products list. Reads `myaimistralAdminLink`. |
| Styles | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Extending

- New prompt templates: insert a row into `myaimistral_prompt` with `status` 1.
- New placeholders: extend the product and category prompt builders in `controllers/front/ajax.php` and in `controllers/front/cron.php`. Shop placeholders are handled in `applyShopShortcodes()`.
- New models: add them in Settings – Mistral, or append the name to the built-in list in `myaimistral.php`.
- Another provider: change the base URL and request body in `src/OpenAIService.php`. Everything else talks only to that class.
- Translations: use `$this->l()` in the module and `trans()` in controllers on PrestaShop 8 and 9. Strings live in `translations/`.

## 7. Help

Product page: https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

For help with the module, log in to mypresta.eu, open **contact** and choose **Support for paid modules**. Describe the problem, your PrestaShop and PHP versions and the text of the message you see. Never send the API key or a cron secret.
