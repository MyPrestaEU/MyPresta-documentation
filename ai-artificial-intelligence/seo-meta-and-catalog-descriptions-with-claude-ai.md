---
title: My AI Claude - AI content generation - documentation and user manual
description: Configuration, daily use and troubleshooting guide for shop owners who already have My AI Claude installed and want it connected to their Anthropic Claude account and working on their catalog.
sidebar:
  label: My AI Claude - AI content generation - documentation and user manual
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy SEO meta and catalog descriptions with Claude AI Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai/)
>
> ---


## 1. Requirements

My AI Claude runs inside the PrestaShop back office and sends your prompts to Anthropic Claude. It needs the following.

| Item | Requirement | Notes |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 and 9 (1.6 up to 9.99.99) | Works in the classic and in the new product page. |
| PHP | 7.0 or newer | On a lower version the installation stops and shows a message with the PHP version of your server. |
| PHP extensions | cURL, JSON, mbstring, DOM, fileinfo, GD | Standard on most hosting. cURL talks to Claude, DOM reads the source page in **New product**, GD resizes imported photos. |
| PHP setting | `allow_url_fopen` enabled | Needed only by **New product** (reading the source page address). |
| Other modules | None | No other module has to be installed. |
| Database | No extra requirement | The module uses the MySQL or MariaDB version that PrestaShop already runs on. |
| Account outside the shop | An Anthropic account with API access and credit | Create the key at https://console.anthropic.com/settings/keys. Every generation is billed by Anthropic according to the tokens used. |
| Network | The server can open HTTPS connections | The shop contacts `api.anthropic.com` for every generation. Update checks contact the MyPresta.eu server. The Images feature opens public web pages. |
| Browser | JavaScript enabled | All buttons in the module are scripts running in the back office. |

**Time and memory.** One generation is one request to Claude and takes from a few seconds to about a minute. The wait limit is set in **Settings, General** under **API timeout (seconds)** (120 seconds at the start, any value from 10 to 600). Set the PHP time limit of your server higher than that value. A mass run sends one request per product, per field and per language, one after another, and works only while its page stays open in the browser. The module starts no background process and needs no extra memory beyond a normal back office page.

## 2. Installation

### 2.1 Upload and install

1. Open **Modules → Module Manager** (PrestaShop 1.6: **Modules and Services**).
2. Click **Upload a module** (PrestaShop 1.6: **Add a new module**).
3. Select the module ZIP file and wait for the upload to finish.
4. Click **Install** when PrestaShop offers it.
5. Wait for the confirmation. The installation creates the menu entry, two database tables and the ready-made prompt templates (see 3.6).

The installer does not clear the cache. If the menu entry does not appear, open **Advanced Parameters → Performance**, click **Clear cache** and reload the page.

After the installation the module does nothing until you enter your Anthropic key. Go to chapter 3, section 3.1.

### 2.2 Where the module appears

The module adds one menu entry named **AI Content Generator** under **Modules**. Click it to open the module on its **Dashboard**. Every other screen is reached from the horizontal menu at the top of the module page:

**Dashboard**, **Settings** (with the sub-pages **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

The module also adds a **Modules → My AI Claude** panel to every product page, small **Generate with AI** buttons next to text fields in product and category forms, a shortcut in the top bar of the back office and a **My AI Claude** button above the product list. Section 3.16 and 3.17 describe each.

If an employee who is not a super administrator cannot open the menu entry, give that employee's profile access to the module screens under **Advanced Parameters → Team → Permissions**.

### 2.3 Disabling and uninstalling

- **Disable** the module in the Module Manager to hide its screens. While it is disabled, any module address sends you back to the PrestaShop home dashboard. All data stays.
- **Uninstall** removes the menu entries, the table with prompt templates, the table with the generation history and every module setting (API key, model, Studio rules, cron settings and cron secrets). The History disappears with its restore points, and so do the Dashboard figures.
- Uninstall leaves everything the module already wrote into your shop: product and category texts, imported photos and products created with **New product**.
- Uninstall also leaves a few saved screen choices from the **Generate** filters and the settings of the MyPresta update check.
- **Reinstall** starts from zero: the API key is empty, the secrets are new (the cron addresses change, so update your server scheduler), the History is empty and the ready-made templates are back in their original wording.

## 3. Configuration and daily work in the back office

### 3.1 The whole process, step by step

1. Create an Anthropic API key at https://console.anthropic.com/settings/keys and make sure the account has credit.
2. Open **AI Content Generator → Settings → Claude**. Paste the key into **Anthropic Claude API KEY**, choose a **Model** and click **Save**.
3. Open **Settings → Playground**, type a short question and click **Generate**. A reply on the page confirms that the key works.
4. Optional: open **Settings → Studio** and describe your brand voice, audience, tone, preferred terms and forbidden words. These rules are added to every generation.
5. Open **Settings → Prompt templates** and read the ready-made templates. Edit the ones you want to keep, disable the others.
6. Open one product, go to **Modules → My AI Claude**, press **Try** on the description card to read a result without changing the product, then press **Fill** to write it into the product.
7. Open **History** and check the entry. Press **Restore** in the product panel if you want the old text back.
8. For many products, open **Generate → Products**, filter the list, write or choose a prompt, and click **Run on the list below**. Test on a small list first.
9. For automatic runs by the server, set up **Cron** (section 3.12).
10. Watch cost and volume on **Dashboard** and **History**. Set a **Monthly generation budget** in **Studio** to cap the usage.

### 3.2 Opening the module and moving around

Click **AI Content Generator** under **Modules**. The top menu of the module contains **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** and **Updates**. Some pages have a second row: **Settings** has **General**, **Claude**, **Studio**, **Prompt templates** and **Playground**; **Generate** has **Products** and **Categories**.

Every module page has a round **Help** button in the lower right corner. It opens a side panel with a short explanation of the page you are on.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

The Dashboard shows how much the module has been used. The first line tells you the active service and model.

Pick the period with one of the buttons **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**, or type your own dates in **From** and **To** and click **Apply**. The page opens with **30 days**.

| Element | Meaning | Notes |
|---|---|---|
| Requests | Number of calls made to Claude in the period | Counts every row of the History: mass runs, product panel, Playground, top bar, cron. |
| Success | Calls that returned text | |
| Errors | Calls that failed | The reason is stored in the History row. |
| Tokens sent | Tokens in your prompts | Tokens are the unit Anthropic bills by. |
| Tokens received | Tokens in the replies | |
| Requests and errors | Chart per day | Long periods are grouped per week. |
| Tokens sent and received | Chart per day | |
| Requests by model | Chart | Shows which models did the work. |

The module also adds a block to the PrestaShop home dashboard. The full figures and charts are on this page.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Open **Settings → General**, change the fields and click **Save**. The message **Settings Updated** confirms it.

| Field | At start | What it does |
|---|---|---|
| Live mode | No | A label for yourself that marks the shop as running live. It does not switch any feature on or off. |
| Debug mode | No | Writes technical lines about failed calls to the PrestaShop log (**Advanced Parameters → Logs**). Enable it when support asks for details, then disable it. |
| API timeout (seconds) | 120 | How long the shop waits for Claude before it gives up. Values below 10 become 10, values above 600 become 600, an empty or invalid value becomes 120. Raise it for long descriptions. |
| Product Edit History | Yes | Shows the **History** tab in the product panel and lets you restore earlier text there. When it is off, the tab disappears. Generations are still stored in the main History. |
| Admin Top Bar CTA | Yes | Shows the small My AI Claude icon in the top bar of the back office (section 3.17). |
| Product edit page Form | Yes | Shows the **Modules → My AI Claude** panel on the product page. When both this switch and **Product Edit History** are off, the panel is empty. |
| AI Image Finder | Yes | Allows the **Photos** tab on the product page. The same switch is on the **Images** page. |
| AI Image Search Prompt | Ready-made text | The instruction used to find pages with photos of a product. The same field is on the **Images** page (section 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

This page connects the shop to your Claude account. The first time you open it, the module may show a notice that blank spaces were removed from the key field. This is normal.

| Field | At start | What it does |
|---|---|---|
| Anthropic Claude API KEY | Empty | The secret that lets the shop call your Claude account. Paste the key from https://console.anthropic.com/settings/keys. Spaces are removed when you save. Leave the field untouched to keep the stored key. A missing key makes every call fail, and the error appears in **History**. |
| Model | claude-sonnet-4-5 | The Claude model that writes the text. Built-in names: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest, plus the names you added. A model your key cannot use returns an error instead of text. |
| Add a Claude model | Empty | Type the exact model name from your Claude account and click **Add model**. The name appears in the **Model** list. Next to each added name there is a **Remove** link. Built-in names cannot be removed. |
| Max Tokens | 3200 | Upper limit on the length of the reply, counted in tokens. Use about 256 for a meta description and 1000 or more for a full description. A low value cuts the reply off. An empty value is replaced by 256. |
| Temperature | 0.7 | How varied the wording is, from 0 to 1. Lower is steadier, higher is more creative. Enter 0.1 for the steadiest style, because a plain 0 is read as the starting value 0.7. |
| Top P | 1 | Saved with the other fields, but My AI Claude does not send it to Claude. Changing it has no effect. |
| Frequency Penalty Value | 0 | Saved, but not sent to Claude. Changing it has no effect. |
| Presence Penalty Value | 0 | Saved, but not sent to Claude. Changing it has no effect. |

Click **Save** at the bottom of the form. A confirmation appears when the values are valid. The message **Anthropic Claude API KEY field is invalid!** means the key field is empty and no key is stored yet.

If a model refuses one of the settings (for example the temperature), the module removes that setting, tries again and remembers it for that model. You do not have to do anything.

The sampling values (Max Tokens, Temperature) are used by the mass runs, the product panel, the Playground, the top bar and the cron. **Images** uses its own fixed values.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

A template is a saved instruction that you can pick in the mass runs, the product panel, the top bar and the cron. The installation creates 16 templates, all enabled.

| Template | Purpose | Notes |
|---|---|---|
| Product name 1, Product name 2 | Shorter or better product names | Name 2 uses brand and default category. |
| Product description 1 to 6 | Product descriptions | Description 1 builds an HTML layout with headings and asks for deliberate spelling mistakes. Delete that sentence before you use it. Description 3 also asks for H1 ideas, keywords, a meta title and a meta description, which all end up in the description field. |
| Product description 7 - using product images | Description with embedded photos | Uses the product image links. |
| Product meta title 1 to 3 | Meta titles | Meta title 1 asks for the English language and 60 characters. |
| Product meta description 1 to 3 | Meta descriptions | Meta description 1 asks for the English language and 160 characters. Meta descriptions 2 and 3 are identical and mention a smartwatch, so rewrite them for your own products. |
| Product tags | Five tags in one line | Asks for the English language. |

Several templates ask for English in the text itself. If you sell in another language, edit those templates and remove the line.

The list shows **ID**, **Title**, **Prompt**, **Status** (click the switch to enable or disable), **Timestamp** and the row actions to edit or delete. Select several rows and use the bulk action **Delete** (the question **Are you sure you want to delete the selected prompts?** asks for confirmation). The newest templates are on top and the list shows 50 rows per page.

To create a template, click the **new** button in the toolbar. To change one, click the edit action in its row.

| Field | At start | What it does |
|---|---|---|
| Status | Enabled for a new template | Only enabled templates appear in the pickers of the module. |
| Prompt title | Empty (required) | The name you see in the pickers and in the list. |
| Prompt content | Empty (required) | The instruction sent to Claude. You can use placeholders such as `{product_name}` (section 3.18). Double quotes are replaced by single quotes when you save. |

Click **Save Prompt** to store the template. The messages are **Prompt template successfully added!** and **Prompt template successfully updated!**. A deleted template shows **Prompt template removed.**. Click **Go Back to Module Settings** to leave the form without saving.

A template tells Claude what to write. The module also adds the rules from **Studio** and the language of the run (section 3.8 describes the Studio rules).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

The Playground is a free text box for trying a prompt. Type your prompt and click **Generate**. The reply appears on the page. Nothing is written to any product or category.

The call is stored in the History as a general generation, so it counts for the Dashboard and for the monthly budget. Use the Playground to check the API key, the model and the effect of the Studio rules.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio holds the rules that are added to every generation: mass runs, product panel, categories, cron, Playground and top bar. Even with all Studio fields empty, the module tells Claude which language to write in (the language of that run).

| Field | At start | What it does |
|---|---|---|
| Brand voice | Empty | Describes how your shop sounds. Claude follows it in every text. |
| Audience | Empty | Describes the customer you write for. |
| Tone | Empty | The mood of the text, for example warm, technical or neutral. |
| Glossary | Empty | Terms Claude must keep exactly as you write them. One per line. |
| Forbidden words | Empty | Words Claude must not use. One per line. Claude is told not to use them, and when the quality gate is on, a reply that still contains one is rejected. |
| Monthly generation budget | 0 | Maximum number of successful generations in the current calendar month. 0 means no limit. When the number is reached, new calls stop with the message **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Failed calls are not counted. |
| Quality gate | Yes | Checks every reply for forbidden words before it is saved. A rejected reply is not written and shows **The reply was rejected because it contains a forbidden word from the studio settings.** |

Click **Save studio**. The message **Studio settings saved.** confirms it.

The budget counts all successful rows of the History in the month: mass runs, product panel (**Try** included), Playground, top bar and cron. **New product** is not counted.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Open **Generate → Products**. The page works in two steps: first a filter picks the products, then a panel runs Claude on that list.

**Step 1 – the filter.** Fill the fields and click **Go to next step**. The form always opens with the values shown below.

| Field | At start | What it does |
|---|---|---|
| Product Categories | Nothing ticked | Tick categories to limit the list to products in them. Empty means all categories. |
| Brand | All | Limits the list to one brand. |
| Product status | Active | Active, Disabled or Both. |
| Product stock | All products | **Only in stock products** keeps products with quantity above zero. |
| Update only | Update all | Three options: only products that have no History entry yet, only products that already have one, or all products. Any entry counts, including failed calls and **Try** runs. |
| Product IDs | Empty | A list of product IDs. |
| Product Reference | Empty | Limits the list to products with this reference. |
| Product Add Date From, Product Add Date To | Empty | Limits the list by the date the product was created. |
| Minimum product ID, Maximum product ID | Empty | Limits the list to a range of IDs. |
| Product Limit | Empty | The maximum number of products in the list. |

**Step 2 – the Mass product generation panel.** The matching products appear in a table with **ID**, **Reference** and **Result**. Above the table you set the run.

| Field | At start | What it does |
|---|---|---|
| Template | Nothing chosen | Picks an enabled template and copies its text into the prompt box. You can edit the text afterwards. |
| Prompt | Empty | The instruction for Claude, with placeholders such as `{product_name}`. When the box is empty, the module uses a built-in brief for each field: an HTML description with intro and feature list, a short plain summary under 400 characters, a meta title of about 70 characters and a meta description of about 160 characters. |
| What to generate | Descriptions | **Descriptions** (long and short description), **Meta title and meta description**, or **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** or **Add below**. |
| Languages | The current language ticked | Tick every language you want written. |

Click **Run on the list below**. A status line shows progress (for example `3 / 40` with the field name) and ends with **Finished N products.** Each row shows the field, the result and the message, for example **Content successfully generated and updated to product.** or **Product skipped.**

Rules of a run:

- The run sends one request per product, per field and per language, one after another. Count the requests before you start, because each one is billed.
- Keep the page open. Closing or reloading it stops the run. Products already written stay written.
- A failure in one row does not stop the others. The reason is in the row and in **History**.
- Limits when saving: product name 128 characters, short description 800, meta title 69, meta description 159. Longer text is cut.
- Text is saved straight to the product. Use the product panel (section 3.16) to restore an earlier text.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Open **Generate → Categories**. The first form has **Categories** (a tree, empty means all) and **Category status** (Active, Disabled or Both, Active at start). Click **Go to next step**. The list can include the Root and Home categories, so tick the categories you want.

Below the filter the panel **Run on the categories below** appears with a table of **ID** and **Result**.

| Field | At start | What it does |
|---|---|---|
| Prompt | Empty | The instruction for Claude. Use category placeholders such as `{category_name}`, `{category_description}` and `{category_parent_name}`. Product placeholders are not filled here. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** or **Additional description**. |
| Existing text | Replace | **Replace** or **Skip if filled**. |
| Language | The current language | One language per run. |

Click **Run on the categories below**. Each row shows the result, for example **Content successfully generated and updated to category.** or **Category skipped.**

Below the panel the page shows a second form named **Generate category content**. Its button does not start a run. Use **Run on the categories below** and ignore the second form. The button **Go Back to Category Filter** returns to the filter.

Limits when saving are the same as for products: name 128 characters, meta title 69, meta description 159. The field **Additional description** exists only in PrestaShop versions that have it. Otherwise the row shows an error.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** creates a complete product from a short description. Claude writes a draft, you read it, and then the module creates the product in your catalog.

| Field | At start | What it does |
|---|---|---|
| What is the product? | Empty | Describe the product in a few sentences: what it is, who it is for, the main features. This is the only required field. The text is cut at 8000 characters. |
| Optional source URL | Empty | The address of a page about the product. The module reads its title, meta description and price and gives them to Claude. |
| Language | The shop default language | The language of the draft. |
| Default category ID | 2 | The ID of the category the product is placed in. 2 is the Home category of a standard shop. |

1. Fill the fields and click **Generate data**. The draft appears on the page as a block of data (name, descriptions, meta fields, tags, features, price). Nothing is saved yet.
2. Read the draft. If it is not right, change the description and click **Generate data** again.
3. Click **Create product** only when you accept the draft. The page then shows **Product #** followed by the new product number. Find the product in **Catalog → Products**.

The new product is created with these settings: active, available for order, price shown, visible in catalog and search, condition new, the first tax rule of the shop, a stock of 100 pieces and the price from the draft (0 when the draft has none). Claude also fills the name, descriptions, meta fields, tags, features and the reference (maximum 32 characters). Open the product afterwards, check the price, the tax, the stock and the photos, and add photos with the **Photos** tab of the product panel.

If no key is stored, the page shows **Add an API key in the module settings first.** This page does not apply the Studio rules or the monthly budget, and its calls do not appear in **History** or on the **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Cron lets your server generate text on a schedule without anyone clicking. The page builds the address that the server has to open. It does not start any scheduler. You create the scheduled task on your hosting or server, and each call processes one batch and stops.

The page has two forms: the product cron and the category cron. The product form is described below. The category form has the same logic, with its own secret and its own settings.

Under each form's introduction the page shows the address of the cron. The product address looks like `https://your-shop/module/myaiclaude/cron?secret=...`. The category address ends with `&entity=category`.

**Complete the address before you use it.** Add `&action=generateProductContent` at the end of the product address and `&action=generateCategoryContent` at the end of the category address. Without it the address answers **Invalid action!** and does nothing.

Example for products:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

The address uses the choices you saved in the form: field, target, number of products, language and template. You can override them in the address (section 6.3 lists the parameters).

**Product cron form**

| Field | At start | What it does |
|---|---|---|
| Enable Cron Feature | No | Master switch for both cron addresses (product and category). When it is off the address answers **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Random text | The long password in the address. Without the right one the address answers **The token does not exist or it's wrong!** The **Generate Token** button does not work in this version (section 5.5). Type your own secret of at least 24 letters and digits, save, and copy the new address into your scheduler. |
| Update Field | description | The one field written by this address: name, description, description_short, meta_title, meta_description or tags. For several fields create several tasks. |
| Selected Products | pendingClaude | **pendingClaude** takes products that have no successful My AI Claude generation yet (any field). **pendingField** takes products with no successful generation for this field yet, which lets you run one task for the description and another for the name over the same products. **emptyField** takes products whose chosen field is empty. |
| Product Categories | Nothing ticked | Limits the run to products in the ticked categories. |
| Product ID list | Empty | Only these product IDs, separated by commas. Letters are dropped when you save. |
| Language | The shop default language | The language version that is written. Other languages need their own task. |
| Product to update | 5 | How many products one call processes. Start with 5 or 10 so a slow reply does not hit the server time limit. The next call continues with products that still match. |
| Prompt Template | Nothing saved | The saved instruction used for every product of the run. Pick one and click **Save**. Without a saved template the address answers **All must include all mandatory parameters!** |
| Enable Debug | No | When you open the address in a browser, shows the plan, the database query and the final prompt and saves nothing. Disable it before the scheduler uses the address. |
| CRON JOB interval | Every Hour | A note for yourself about the rhythm of your scheduler (from every minute to every 6 hours). It does not schedule anything and does not change the address. |
| Product Cron Job command | The address | The address of the cron. Add the `&action=` part as described above. |

Click **Save** under the form. The category form has the fields **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** and the secret, and its own **Save** button.

What every call does:

- It replaces the chosen field. The cron has no option to keep or add text.
- It applies the Studio rules and the monthly budget. When the budget is reached the call answers **Error!Monthly generation budget reached.**
- It writes a History row for each text, so you can restore or review it.
- Both secrets open both actions. The cron stays off until **Enable Cron Feature** is **Yes**.

Test with **Enable Debug** set to **Yes** and the address opened in a browser. When the plan looks right, set it to **No**, save and create the task.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

History is the log of everything that was sent to Claude. The page opens on **This month**.

**Filters.** Quick buttons: **Today**, **7 days**, **30 days**, **This month**, **All time**. Fields: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Click **Filter**.

**Cards.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Breakdown panels.** **By day**, **By model**, **By type**, **By language**, **By employee**. Each shows calls, tokens sent, tokens received and total. Rows without an employee (all cron calls) appear as Unknown.

**Prompt history list.**

| Column | Meaning | Notes |
|---|---|---|
| ID | Row number | |
| Status | **Success** or **Error** badge | |
| Prompt | The text sent | Cut at 180 characters in the list. |
| Reply / Error | The reply or the error message | Cut at 180 characters in the list. |
| Provider | The service, the model, the error status number when Claude returned one, and the time in seconds | |
| Sent, Received, Total | Tokens | |
| Entity ID | The product or category | Empty for Playground and top bar calls. |
| Type | What was generated | See the next table. |
| Timestamp | Date and time | |

Click the view action in a row to see the full prompt and reply and the link **Back to the list**. The list shows 50 rows per page.

| Type | Meaning | Notes |
|---|---|---|
| general | Playground and top bar | No product or category. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | One product field | Written by mass runs, the product panel, the logo buttons and cron. |
| product_seo_pack | The SEO pack of the product panel | Name, descriptions and meta fields in one request. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | One category field | |
| error | A failed call | The reason is in **Reply / Error**. |

**Clear list** in the toolbar deletes **all** rows after confirmation and shows **Log list successfully deleted.** This cannot be undone. It also removes the restore points of every product, empties the Dashboard, resets the monthly budget counter, and changes which products count as already processed in **Update only** and in the cron targets. Export or note what you need first.

When there are no rows in the chosen period, the page shows **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

This page controls the **Photos** tab of the product page. The form is named **AI Image Finder**.

| Field | At start | What it does |
|---|---|---|
| AI Image Finder | Yes | Enables the **Photos** tab on the product page. When it is off, the tab tells you to enable it under **Settings → General**. |
| AI Image Search Prompt | Ready-made text | The instruction sent to Claude to find web pages that show the product. Use `{product_name}` and `{product_description}` as placeholders. Keep the request for exactly five page addresses returned as a list, because the module reads that list. |

The ready-made prompt asks for exactly five page addresses of pages that show the product, as a JSON list, using the product name and description.

Click **Save**. The message **Settings saved.** confirms it. The page and the tab in **Settings → General** share the same switch and prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

The **Updates** page checks whether a newer version of My AI Claude exists. The check sends the module name, its version and the shop address to the MyPresta.eu server.

| Field | At start | What it does |
|---|---|---|
| Manual Check | Button **Check Now** | Runs the check now. The answer is **Module is up to date!** or **New version available!** |
| Automatic Notifications | Enabled | When enabled, the module checks about every three days and shows a notice in the back office when a new version exists. |
| Product Page | A link | Opens the module page on MyPresta.eu. |

Click **Save**. The message **Update settings saved.** confirms it.

### 3.16 Product page – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Open any product, go to the **Modules** tab and find **My AI Claude**. The panel has the tabs **Generate**, **Simulate**, **Photos** and **History**. Save a new product once before you use the panel, because the panel works on a saved product.

**Generate and Simulate.**

1. Pick the language chip, or **Every language**. The first language of the shop is selected at start.
2. Under **If the field already has text** pick **Replace**, **Add above**, **Add below** or **Skip if filled**. **Replace** is selected at start.
3. Press **Fill** on a card: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** or **Tags**. The text is written straight into the product.
4. The **SEO pack** card has **Fill all**. One request returns the name, both descriptions and both meta fields. It overwrites those fields, including the name. The message **SEO pack saved. Refresh the product to see it.** confirms it. If Claude does not return a usable pack, the panel says **The model did not return a usable SEO pack.**
5. Open **Use your own instruction or a saved prompt** to filter and pick **Standard brief** or an enabled template, or type your own text into the **Instruction** box. With an empty box, the standard brief for the card is used.
6. The reply and the token count appear under the cards.

On the **Simulate** tab the same cards have **Try**. **Try** shows the reply and leaves the product unchanged. It is still stored in the History and counted for the budget, and it makes the product count as already processed for **Update only** and for cron.

**After Fill, reload the product page.** The open form still holds the old text. If you press **Save** in PrestaShop without reloading, PrestaShop writes the old text over the new one.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Open the **Photos** tab and click **Find pages**. Messages: **Looking for photos…** and **Reading photos…**.
2. Tick the photos you want. The page shows **Tick the photos you want, then add them to this product.**
3. Click **Add selected to this product**. The message **Adding the photos to this product…** appears, then the number of imported images.
4. Reload the product page to see the photos.

The finder reads up to 5 pages and offers up to 24 photos. The first ticked photo becomes the cover of the product. The photos are downloaded to your shop and resized to all image sizes of your shop. Check that you have the right to use them. When the finder is disabled, the tab asks you to enable it in **Settings → General**.

**History.** The tab shows **When**, **Type**, **Status** and a **Restore** button for the last 50 entries of this product. The intro line reads **Earlier writes for this product. Restore puts the previous text back…** With no entries it says **No generations for this product yet.** Click **Restore** and confirm. The message **Content successfully restored. Refresh this page to see changes.** appears. A row without a previous value shows **Error! This log entry has no previous value to restore.** The tab appears only when **Product Edit History** is on.

### 3.17 Other places where the module appears

**Generate with AI buttons next to fields.** A small logo button appears next to these fields.

| Place | Fields | What happens |
|---|---|---|
| Product form | Description, Short description, Meta title, Meta description | Claude writes into the field of the open form. |
| Category form | Description, Additional description, Meta title, Meta description | Claude writes into the field of the open form. |

If the shop has more than one language, the button asks whether to write the current language or all languages. The text appears in the field but is not saved. The note **Text is in the field. Save the product to keep it.** (for categories: **Save the category**) reminds you. On a new, unsaved item the button says **Save the product once before generating.** (for categories: **Save the category once…**). Each use is stored in the History and makes the product count as already processed.

**Top bar shortcut.** The magic icon in the top bar of the back office opens a small window named **My AI Claude** with a **Template** list, a text box, **Generate** and a close button. It works like the Playground and saves nothing. The switch is **Admin Top Bar CTA** in **Settings → General**.

**Product list.** A **My AI Claude** button in the toolbar above the product list opens **Generate → Products**.

### 3.18 Placeholders for prompts

Placeholders are words in curly brackets that the module replaces with real data before it sends the prompt. They work in templates, in the prompt box of mass runs, in the product panel and in cron.

| Placeholder | Works for | Replaced with |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Products | The current name, description, short description and tags in the language of the run. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Products | Reference, EAN-13 code and weight. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Products | Brand, default category with its description, and all categories. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Products | Combinations, feature names and feature values. |
| `{product_images}` | Products | Links to the product photos. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Categories | Name, description and parent category name. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Everywhere | Shop name, address, language, country and currency. |

A placeholder that has no data is replaced with an empty text.

## 4. Storefront

My AI Claude adds nothing that your customers can see or use. It has no front office page, no block, no widget and no customer setting. The texts it writes become visible only because they are saved in your products and categories, and you see them through your normal theme.

The module has two addresses that belong to the shop domain but are not meant for customers.

| Address | Who uses it | What it returns |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Your server scheduler | A plain text answer such as **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** or one of the messages in the next table. |
| `…/module/myaiclaude/ajax` | The module's own back office screens | Nothing useful when opened by hand. It answers only requests that carry the secret of the screens. |

| Message from the cron address | Meaning | What to do |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** is **No**. | Set it to **Yes** and save. |
| The token does not exist or it's wrong! | The secret in the address does not match a saved secret. | Copy the address again from the **Cron** page. |
| Invalid action! | The `&action=` part is missing or misspelled. | Add `&action=generateProductContent` or `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | A required choice is missing, most often the prompt template. | Pick a template in the form and click **Save**. |
| updatedField parameter is wrong! | The field is not one of the allowed fields. | Pick the field in the form and save. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | The target in the address is misspelled. | Use one of the three values. |
| No valid product IDs provided. | The **Product ID list** has no numbers. | Fix the list or empty it. |
| Error!… | Claude or the shop returned an error. The text after the word Error explains it. | Read the text, see chapter 5. |

The module's storefront hooks are empty, so it adds no output to your shop pages.

## 5. Troubleshooting

### 5.1 Menu and screens

| Symptom | Cause | What to click |
|---|---|---|
| **AI Content Generator** is not in the menu. | The cache was not cleared, the module is disabled, or the employee has no access. | **Advanced Parameters → Performance → Clear cache**. Check **Modules → Module Manager**. Check **Advanced Parameters → Team → Permissions**. |
| Every module address returns to the home dashboard. | The module is disabled. | Enable it in **Module Manager**. |
| The **Modules → My AI Claude** panel on the product page is empty. | **Product edit page Form** and **Product Edit History** are both off. | Enable at least one in **Settings → General**. |
| The product panel does not work on a new product. | The product is not saved yet. | Save the product once, then use the panel. |
| The **History** tab is missing in the product panel. | **Product Edit History** is off. | Enable it in **Settings → General**. |
| The My AI Claude block on the PrestaShop home dashboard shows empty or zero figures. | The home block does not hold the report data. | Open **AI Content Generator → Dashboard** for the real figures. |

### 5.2 Connection to Claude

| Symptom | Cause | What to click |
|---|---|---|
| The message says the Anthropic Claude API key is not set (**The Anthropic Claude API key is not set. Add it in the module settings.**). | No key is stored. | **Settings → Claude**, paste the key in **Anthropic Claude API KEY**, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | The key field is empty and no key is stored. | Paste the key and save. |
| The message begins with **Anthropic Claude API Error** followed by a text from Anthropic. | Claude refused the call. Typical reasons are a wrong key, a model your account cannot use, no credit, or too many requests. | Read the text after the colon. Check the key, the credit and the model in your Anthropic account. Choose another **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude answered too slowly. | Raise **API timeout (seconds)** in **Settings → General** (maximum 600) or lower **Max Tokens**. Try again later. |
| A message that starts with **cURL Error** | The server cannot reach Claude, or a firewall blocks it. | Ask your hosting to allow outgoing HTTPS to `api.anthropic.com`. |
| A new Claude model is missing in the **Model** list. | The list holds only the built-in names and the ones you added. | Type the exact name in **Add a Claude model** and click **Add model**. |
| After **Remove**, the **Model** list shows a model that does not belong to Claude. | Removing the active added model switches the shop to a fallback name that Claude does not know. | Choose a Claude model in **Model** and click **Save**. |
| The module says **OpenAi Settings Updated** or **OpenAi Model field is invalid!**, the **Provider** column in History shows `openai`, the page help speaks about an OpenAI account, and the example in **Add a Claude model** mentions a GPT name. | These are leftover texts from the older version of the module. | Nothing. The module talks to Claude only. Read the texts as Claude. |
| The button **Module settings** on the **Generate** filter forms opens a wrong page. | The button points to the settings of another module (My ChatGPT), not to My AI Claude. | Open **Settings** in the top menu of the module. |
| The log of PrestaShop fills with lines about the model list. | **Debug mode** is on. | Disable **Debug mode** in **Settings → General**. |

### 5.3 Generation problems

| Symptom | Cause | What to click |
|---|---|---|
| **Error! Prompt is missing or too short!** | The prompt has fewer than 4 characters. | Write a longer prompt or pick a template. |
| **Error! Product not found!** | The product no longer exists. | Reload the list. |
| **The model hit the token limit … Increase "Max Tokens" …** | The reply used all tokens before any text. | Raise **Max Tokens** in **Settings → Claude**. |
| **The model returned an empty response.** | Claude returned no text. | Try again, or reword the prompt, or raise **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude refused the subject. | Reword the prompt. |
| The text stops in the middle of a sentence. | **Max Tokens** is too low. | Raise **Max Tokens**. Use 1000 or more for a full description. |
| The description contains spelling mistakes, headings you did not want, H1 ideas or keyword lists. | The ready-made template asks for that. | Edit the template in **Settings → Prompt templates** (section 3.6). |
| The text is in English although the shop is in another language. | A ready-made template asks for English, or the wrong language was selected. | Edit the template and tick the right language in the run. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | The **Quality gate** found a word from **Forbidden words**. | Run again, or remove the word from **Studio**, or switch off **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | The number of generations in this month reached **Monthly generation budget**. | Raise the value in **Settings → Studio**, or set it to 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop refused the text, for example a product name with characters not allowed. | Read the details in the row and in **History**. Edit the prompt and run again. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Your PrestaShop version has no such field. | Pick another field. |
| A row says **Product skipped.** or **Category skipped.** | **Skip if filled** is selected and the field already has text. | Choose **Replace** to overwrite. |
| After **Fill**, the old text is back. | The form was saved without reloading the page. | Reload the product page after every **Fill**, then continue. |
| A mass run stopped. | The page was closed or reloaded. | Start again with **Update only** set to the option for products not yet updated. Failed calls count as updated there. |
| The category page has a second form with **Generate content** that does nothing. | That form is not connected. | Use **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | The History row has no earlier text. | Edit the field by hand. |
| The **Try** result does not appear in the product, but a History row exists. | **Try** never writes to the product. | Press **Fill** to write it. |

### 5.4 Photos and new products

| Symptom | Cause | What to click |
|---|---|---|
| The **Photos** tab asks you to enable the finder. | **AI Image Finder** is off. | Enable it in **Settings → General** or on **Images**. |
| **Claude API key is not configured. Please check module settings.** | No key is stored. | **Settings → Claude**. |
| **The search failed.** | Claude or the network did not answer. | Click **Find pages** again, check the key and the timeout. |
| **No photos were found on the suggested pages.** | The pages had no usable photos. | Change the product name or description, or edit **AI Image Search Prompt**. |
| **URL not allowed (private network).** | The address points to a private or local network. | Use public web pages only. |
| **No images selected** | Nothing was ticked. | Tick at least one photo. |
| **No images could be imported. Details: …** | The photos could not be downloaded or were not valid images. | Read the details. Try other photos. |
| The cover photo changed. | The first ticked photo becomes the cover. | Reorder the photos in the product page. |
| **Add an API key in the module settings first.** (**New product**) | No key is stored. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude returned text that is not a valid draft. | Click **Generate data** again. Describe the product in more detail. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | The description is empty, the draft is incomplete, or PrestaShop could not save the product. | Fill **What is the product?**, generate again, check the category ID. |

### 5.5 Cron problems

| Symptom | Cause | What to click |
|---|---|---|
| The address answers **Invalid action!** | The cron address copied from the page has no `&action=` part. | Add `&action=generateProductContent` (products) or `&action=generateCategoryContent` (categories). |
| The address answers **Cron Job feature is disabled…** | **Enable Cron Feature** is off. | Set **Yes** and **Save**. |
| **Generate Token** does nothing. | The button is not connected in this version. | Type a secret of at least 24 letters and digits in **Cron Job Secret Token** and **Save**. A shorter secret is replaced by a random one the next time an admin page opens. |
| The address answers **All must include all mandatory parameters!** | The form was never saved, so no template is stored. | Choose a **Prompt Template**, then **Save**. |
| The address answers **No products to update.** while products need text. | **Selected Products** excludes them. **pendingClaude** skips every product that has a successful generation, including **Try** runs. | Use **emptyField** or **pendingField**, or set the **Product ID list**. |
| The text of a product was rewritten again. | The cron always replaces the field. | Use **emptyField** to touch only empty fields. |
| **Error!Monthly generation budget reached.** | The monthly budget is used up. | Raise it in **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop refused the text for product N. | Fix that product or exclude it, run again. |
| The command on the page does not change when you change the form. | The command shows the base address only. | Add `&action=` yourself. The form values are read from the saved settings. |
| The interval in the form has no effect. | It is a note for you. | Create the schedule in your hosting panel. |

### 5.6 History and data

| Symptom | Cause | What to click |
|---|---|---|
| The Dashboard and History are empty after **Clear list**. | **Clear list** deletes all rows. | Nothing to restore. Plan exports before you clear. |
| **This log entry no longer exists.** | The row was deleted. | Go back to the list. |
| **Update only** shows no products. | The filter uses History entries, and every product already has one. | Choose **Update all**. |
| Some products are left out of **Update only**. | Failed calls and **Try** runs also count as entries. | Choose **Update all**. |

## 6. For developers

### 6.1 Overview

My AI Claude (`myaiclaude`, version 1.1.0, author MyPresta.eu) is a PrestaShop module for the tab `front_office_features`. It supports PrestaShop 1.6 to 9.99.99 and PHP 7.0 and newer. It calls the Anthropic Claude Messages API at `https://api.anthropic.com/v1` (endpoint `/messages`) and writes the results into products and categories.

- Class `myaiclaude` in `myaiclaude.php` holds install, uninstall, configuration pages and hooks.
- Class `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) is the client. It sends `model`, `max_tokens`, `messages`, an optional `system` and an optional `temperature`, with the headers `x-api-key` and `anthropic-version: 2023-06-01`. Top P and the two penalties are stored but not sent. It maps `input_tokens` and `output_tokens` to sent and received tokens. `listModels()` always answers that the model list is provided by the module catalogue, so the model list is the built-in set plus the names kept in `EXTRA_MODELS`. The timeout is clamped to 10–600 seconds. When the API answers 400 and names a parameter, the client drops that parameter, retries and remembers the decision per model in `MODEL_CAPS`.
- Class `MyAIClaude\Studio` (`src/Studio.php`) wraps prompts with the language line, voice, audience, tone, glossary and forbidden terms, applies the monthly budget and the forbidden-word gate, and builds the SEO pack prompt.
- Configuration page tabs use the URL parameters `mac_tab` (`dashboard`, `settings`, `updates`) and `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). The value `openai` of `mac_sub` opens the Claude tab. The Dashboard uses `mcg_preset` and the dates `mac_from` and `mac_to`.
- Admin CSS classes use the prefix `.mac-`.
- Mass jobs run one item per AJAX request from `back.js`.

### 6.2 Files

| Path | Purpose | Notes |
|---|---|---|
| `myaiclaude.php` | Module class | Install, uninstall, forms, hooks, tab placement. |
| `autoload.php` | Loader for the namespace `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | API client and Studio rules | |
| `controllers/admin/AdminMyAIClaude*.php` | Back office controllers | See 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Front controllers | AJAX and cron. |
| `lib/updateChecker.php` | MyPresta update check | Contacts `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Texts of the **Help** drawer | |
| `lib/prestashop9compatibility.php` | Compatibility helpers | |
| `lib/searchTool` | Autocomplete helper for admin forms | |
| `views/templates/` | Smarty templates | Hooks, admin pages, mass panels. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Styles with the prefix `.mac-` | |
| `translations/` | 34 language files | |
| `upgrade/index.php` | Placeholder | The module has no upgrade scripts. |

### 6.3 Controllers

| Controller | Menu or route | Role |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** under **Modules** | Redirects to the Dashboard. Parent of the hidden tabs. |
| AdminMyAIClaude | Hidden tab **Mass Content Creator** | Generate: products and categories. |
| AdminMyAIClaudeProductCreator | Hidden tab **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Hidden tab **Module Settings** | Redirects to the Settings tab. |
| AdminMyAIClaudeCron | Hidden tab **Cron Job Settings** | The two cron forms. |
| AdminMyAIClaudeUsage | Hidden tab **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Hidden tab **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Actions `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Requires `secret_token` equal to `TOKEN`. It is not tied to an employee session. No screen of this version calls `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Requires `secret` equal to `SECRET` or `CAT_SECRET` and `ENABLE_CRON=1`. Parameters: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Missing parameters are read from the saved settings. |

The child tabs are created with `active=0` under `AdminMyAIClaudeMain`. On `displayBackOfficeHeader` the module places the main tab under the Modules parent tab, renames it and regenerates secrets shorter than 24 characters. The icon class is `icon-openai`. The Image Finder tab is registered on demand and marked by `IMAGEFINDER_TAB_OK`.

The product cron accepts the targets `pendingClaude`, `pendingField` and `emptyField` and counts only log rows whose status is not `error`. The Generate filter **Update only** counts every log row. Cron log rows use the method `cron`.

### 6.4 Hooks

| Hook | Behavior | Notes |
|---|---|---|
| `displayAdminProductsExtra` | Renders the **Modules → My AI Claude** panel | Tabs Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Loads assets, places the menu, regenerates short secrets | Runs on every admin page. |
| `displayBackOfficeTop` | Renders the top bar shortcut | |
| `dashboardZoneTwo` | Renders `dashboard.tpl` on the PrestaShop dashboard | The template is rendered without its report variables. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Registered, return an empty string | |
| `actionProductFormBuilderModifier` | Registered, does nothing | |
| `displayHeader`, `displayFooter` | Registered, empty | The storefront gets no output. |

The module has no `enable()` or `disable()` method. `displayCustomTop` and `top.tpl` exist but are not called.

### 6.5 Overrides

The module has no `override` directory and changes no core file. Product photos are written with the PrestaShop image classes and the module writes products and categories with the PrestaShop objects (`Product`, `Category`, `Tag::addTags`).

### 6.6 Database

Tables (prefix as in your shop, engine as PrestaShop):

| Table | Columns | Notes |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (primary key), `status`, `title`, `prompt`, `date_generated` | Holds the 16 installed templates and your own. |
| `myaiclaude_log` | Prompt, reply, status, type, model, product or category ID, language, employee, token counts, duration, date | One row per call. Token columns are added on demand for older installs. |

The product and category writes touch the core tables of the edited data (`product`, `product_lang`, `category_lang`, `tag`, `image` and the related tables). Uninstall drops both module tables.

### 6.7 Keys and translations

Configuration keys use the prefix `MYPRESTA_MYAICLAUDE_`.

| Key (after the prefix) | At start | Meaning |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Label and debug logging. |
| `TIMEOUT` | 120 | API timeout. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Switches of the General page. |
| `IMAGEFINDER_PROMPT` | Ready-made text | Uses `{product_name}` and `{product_description}`. |
| `API_KEY` | A single space | Anthropic key. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, empty, empty | Active model, added models, learned parameter support. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Sampling fields. The last three are not sent. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Empty | Studio text fields. |
| `BUDGET`, `QUALITY` | 0, 1 | Monthly budget and quality gate. |
| `TOKEN` | Random 32 characters | AJAX secret. |
| `SECRET`, `CAT_SECRET` | Random 32 characters | Product and category cron secrets. |
| `ENABLE_CRON` | 0 | Cron switch. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Interval notes. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, empty, default language, empty, 0, empty | Saved product cron form. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, empty, default language, 0, empty | Saved category cron form. |

The Generate screens also store their last filter choices in keys such as `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` and several `PROD_*` keys. Uninstall does not delete them, nor `mypresta_updates`, `update_myaiclaude` and `updatev_myaiclaude` of the update check. Uninstall removes the other keys, and the older keys of the former provider.

Field help texts of the forms are built with `fieldHelp()` into the three parts **What it does**, **How to configure** and **Effect**. Strings go through the PrestaShop translation system (module and controller translation domains). Add a language by placing a file `translations/<iso>.php`. The texts of the Help drawer come from `lib/sectionHelp.php`. Cron answers, Studio prompts and the default prompt texts are plain English strings in code.

### 6.8 Extending

- Add models with the field **Add a Claude model**, or by adding the id to `EXTRA_MODELS`.
- Add prompts as templates, or send your own text through the `ajax` actions with the secret.
- Placeholders are replaced in `controllers/front/ajax.php`. The placeholders `{cms_title}`, `{brand_name}`, `{brand_description}` and `{brand_short_description}` are recognised when the request carries a CMS page or brand ID. No screen of this version sends those IDs.
- Build your own schedule with the cron address and its parameters (section 6.3).
- The module renders no storefront template, so a theme has nothing to override.

## 7. Help

Module page: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

To get support:

1. Log in to mypresta.eu.
2. Go to **contact**.
3. Choose **Support for paid modules**.
4. Write the module name (My AI Claude), its version (1.1.0), your PrestaShop and PHP versions, and what you did before the problem appeared. Add the text of the message you see.
