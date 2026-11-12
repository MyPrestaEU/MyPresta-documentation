---
title: MyFAQ - documentation and user manual
sidebar:
  label: MyFAQ - documentation and user manual
description: Configuration and troubleshooting manual for shops that already have MyFAQ.
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy MyFAQ: product FAQ with FAQPage schema Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Requirements

This PrestaShop FAQ module runs inside PrestaShop. It does not need another module.

- PrestaShop 1.7.0.0 through PrestaShop 9. The PrestaShop 8 FAQ module and the PrestaShop 9 FAQ module are this same package and use the same screens.
- PHP 7.0 or newer, and at least the PHP version required by that PrestaShop release. Installation and the scheduled address use `random_bytes`.
- cURL is required when you generate questions. Without cURL the generation stops and the progress line shows `curl_missing`. The update check uses cURL when PHP provides it, and reads the address directly when cURL is missing and the server allows remote reads.
- OpenSSL encrypts the AI key you save. Without OpenSSL the key is stored as you typed it.
- No other module is required. The product page of the theme must print the product footer, or the extra product tabs, for the customer to see the accordion.
- An account at OpenAI, Anthropic, Google, DeepSeek or Mistral is needed only for that provider. The compatible tile can point at your own server, such as Ollama, vLLM or LM Studio, and that server can run without an external account.
- An external system is needed only when you call the FAQ address from outside the shop. A scheduler is needed only when you want the server to finish a queue while the back office is closed.

A large catalogue is written one language at a time. Leave the bulk page open until the bar reaches 100%, or schedule the address from **Bulk generation**. Each scheduled call works for about 20 seconds and then stops, so the PHP time limit is not hit. One call writes at most 30 languages.

## 2. Installation

1. In the back office open **Modules**, then **Module Manager**.
2. Upload the module zip and click **Install**.
3. Open **Configure** on **MyFAQ**. The page opens on **Display**. The bar also has **Entries**, **AI**, **Bulk generation**, **API** and **Updates**.
4. MyFAQ does not add its own item to the left menu. The catalogue, the key list and the request history are hidden pages. The first opening of **Configure** creates them and gives the current employee profile the right to open them.
5. Installation does not run a separate cache clear. If the product page still shows the previous layout after an update, clear the cache in **Advanced Parameters**, **Performance**.

On a product, open the product and use the **MyFAQ** block. That block is where you set the placement for one product and write questions that belong only to it.

To turn the module off, use the switch in **Module Manager**. The product page no longer prints the accordion, and the product edit page no longer shows the MyFAQ block. The questions, the keys and the settings stay. Turn the module on again and they are used as before. The module has no separate enable or disable button of its own.

To remove it, click **Uninstall** and confirm. Uninstall removes the hidden pages, the questions and answers, the links, the per-product placement, the API keys, the request history, the generation queue and the display and AI settings. The two scheduled addresses stop working because the secret in them is removed. The module files stay on the server until you delete the module. Installing again starts with empty entries and the settings of a fresh installation. The old questions are not restored. The update-check switch is not cleared by uninstall.

## 3. Configuration and daily work

You write a question and an answer, then you link that entry to a product or to something the product already has: a category, a feature value, an attribute value, a tag, a brand or a supplier. One matching link is enough. The product page FAQ is the accordion the shop prints after it collects every active match in the customer's language and replaces the tokens. Entries linked directly to the product come first. After that, the order is the position you set.

The product footer FAQ sits under the product. The FAQ tab on product page is the same accordion in a tab. On one product you can force the footer, force the tab, or hide MyFAQ. Hide also removes the FAQ block that search engines read. The customer only opens the questions. There is no form for the customer to send a new question. The path ends when the product page shows the accordion, or when placement is **Hide** or no active entry matches, in which case that product shows no MyFAQ block.

Writing with a model is optional. Save the provider and the key on **AI**. Saving there does not generate anything. **Generate** on one product, or **Start generation** on **Bulk generation**, queues the work. Each language of a product is one request. **Append** keeps the current AI entries and adds new ones. **Replace unlocked AI entries linked only to the product** deletes unlocked AI entries that are linked only to that product, then writes new ones. An entry you edited is locked and is kept. An entry that is also linked to a category or another target is kept. The scheduled address does not read the filters on **Bulk generation**. It finishes a queue that already exists, or, with the second address, adds every active product in this shop that still has no AI entry.

An external system is optional. On **API** you generate a key, copy the base address, and paste both into that system.

Open **Modules**, **Module Manager**, **MyFAQ**, **Configure**. The line under the bar explains the open section.

### 3.1 Display

**Display** is the shop-wide presentation. A single product can still use a different placement.

| Field | At the start | What it does |
|---|---|---|
| **Placement** | Product footer | Shop default for every product that does not set its own placement. **Product footer** prints the accordion under the product. **Product tab** adds a tab on the product page. On a product you can still force the footer, the tab, or hide MyFAQ. Other modules on the same hook stay where **Design**, **Positions** put them. |
| **Tab title** | FAQ in every language | Label of the product tab. It is used only when placement is **Product tab**. Fill it in every language the shop sells in. If a language is empty, that language shows FAQ. |
| **Heading above the list** | FAQ in every language | Heading printed above the questions, both in the footer and in the tab. Fill it per language. Customers see this text. Leave FAQ if you do not need a custom heading. |
| **Include parent categories** | No | **Yes** also shows an entry linked to a parent of the product categories, so one link covers the child categories. The walk stops before Home, so a link to Home does not cover the whole catalogue. **No** matches only the categories the product is directly in. |
| **Open the first question** | No | **Yes** expands the first answer when the page loads. **No** leaves every answer closed until the customer clicks. Customers without JavaScript always see the answers. |
| **FAQ schema markup** | Yes | **Yes** adds one schema.org FAQPage block built from the questions actually shown on that product, after shortcodes are replaced. Search engines can use it for FAQ rich results. **No** prints the FAQ without that block. An empty list and a hidden product never output it. |

Click **Save**. The page shows **Saved.**

### 3.2 Entries

**Entries** is a preview of the questions. The line under the bar says this is the 10 entries updated most recently, and that **New entry** and **Edit** open the catalogue.

| Field | At the start | What it does |
|---|---|---|
| **New entry** | a button | Opens the catalogue form for a new question. |
| **See full list** | a button | Opens the searchable catalogue, where you change the order and delete an entry. |
| **Question** | empty until you save one | The question in the current back-office language. **No question in this language** means that language has no question text. |
| **Linked to** | empty | Up to four links, then an ellipsis. |
| **Source** | Written by hand on an entry you typed | **AI** or **Written by hand**. **locked** means a later replace keeps this entry. |
| **Status** | Active on a new entry | **Active** is shown on matching product pages. **Inactive** stays in the back office and is hidden in the shop. |

The count on the right is the number of entries, not only the ten on this preview. **Edit** opens that entry in the catalogue.

When there are no entries the page says **No entries yet** and tells you the shop shows nothing until an active entry is linked to a product, category, feature, attribute, tag, brand or supplier.

### 3.3 Catalogue

Open **See full list**. The page title is **FAQ entries**. The note at the top says search matches the question, the product name or id, the language, and the other links. The question is the one in the current back-office language. The product name opens that product. **Edit** opens the form on this page. **Up** and **Down** move the entry. Drag the position column to set the same order. **Delete** asks for confirmation. **Active** shows or hides the entry. Locked entries are kept when AI replaces a product.

Columns: **ID**, **Question**, **Product**, **Also linked to**, **Languages**, **Shop**, **Source**, **Active**, **Locked**, **Position**, **Created**, **Updated**.

**Shop** shows **All shops** when the entry was saved while the shop context was all shops. Otherwise it shows that shop's name. The storefront of a shop shows entries for all shops and entries saved for that shop.

**Source** is **Written by hand** or **AI**. Filter that column with the dropdown. **Active** is a switch on the row: click it to show or hide the entry. **Locked** is a marker, not a switch. Editing an existing entry locks it. A new entry is not locked.

Row actions are **Edit**, **Up**, **Down** and **Delete**. **Delete** asks **Delete this entry? It disappears from every product that used it.** **Bulk actions** has **Delete selected**, which asks **Delete the selected entries? They disappear from every product that used them.** If a delete does not complete, the page shows **The entry could not be deleted.**

**New entry** in the toolbar opens a blank form. **Back to module** returns to **Entries**.

The form title is **New entry** or **Edit entry**.

| Field | At the start | What it does |
|---|---|---|
| **Question** | empty | The line the customer clicks to open the answer. This is the accordion header. Write one question per language. The help under the field says the default language is required. The question can contain shortcodes too. They are replaced on the product page and shown as plain text. If every language is empty, **Save** shows **Enter a question in at least one language.** |
| **Answer** | empty | The text revealed when the customer opens the question. Use the editor for paragraphs and lists. Shortcodes are replaced on the product page and the surrounding HTML stays. The shortcode list sits under this field: click a token to insert it at the caret. Fill every language you sell in. An empty language is not shown in that language. |
| **Shortcodes** | the token buttons | Click a token to insert it where the cursor is, in the question or in the answer. The shop replaces it on the product page with that product data, in the customer language and currency. The stored text keeps the token, so a price or name change updates every entry that uses it. In the question the result is plain text. |
| **Active** | Yes | **Yes** shows the entry on matching product pages and includes it in the schema. **No** keeps it in the back office and hides it from the shop. |
| **Products** | none | Type a product name in the search box and pick it. The entry is shown on these products even when no other link matches. One matching link is enough. Saving replaces the previous links of this entry. |
| **Categories** | none | Type a category name and pick it. The entry is shown on products placed in these categories. One link is one FAQ for a whole category. Parent categories count only if that option is on under **Display**. |
| **Feature values** | none | Type a feature value and pick it, for example Cotton. The entry is shown when the product has that value. |
| **Attribute values** | none | Type an attribute value and pick it, for example M. The entry is shown when any combination of the product uses that value. |
| **Tags** | none | Type a tag and pick it. The entry is shown when the product has this tag in the language of the page. |
| **Brands** | none | Type a brand name and pick it. The entry is shown on products of these brands. |
| **Suppliers** | none | Type a supplier name and pick it. The entry is shown on products of these suppliers, including the default supplier and suppliers added on combinations. |

**Save** with no link shows **Link the entry to at least one product, category, feature, attribute, tag, brand or supplier.** If the row cannot be stored, the page shows **The entry could not be saved.** A successful save stays on the form and PrestaShop confirms the update. **Back to the list** returns to the catalogue.

The token buttons, and the English hint on each button, are:

| Token | What the customer sees |
|---|---|
| `[product_name]` | Product name |
| `[product_reference]` | Reference |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | Condition |
| `[product_price]` | Price, tax included, in the customer currency |
| `[product_price_tax_excl]` | Price, tax excluded |
| `[product_price_before_discount]` | Price before reduction |
| `[product_discount_amount]` | Discount amount, empty when there is no reduction |
| `[product_discount_percent]` | Discount percent, empty when there is no reduction |
| `[product_quantity]` | Available quantity of the default combination |
| `[product_availability]` | The in-stock label, or the out-of-stock label when the quantity is zero |
| `[product_minimal_quantity]` | Minimum quantity |
| `[product_manufacturer]` | Brand |
| `[product_supplier]` | Supplier |
| `[product_category]` | Default category |
| `[product_categories]` | All categories |
| `[product_features]` | Feature list, as name and value |
| `[product_feature id=ID]` | One feature value. Replace ID with the feature number from **Catalog**, **Attributes & Features**. |
| `[product_tags]` | Tags in the current language |
| `[product_url]` | Product URL |
| `[product_weight]` | Weight with the shop weight unit |
| `[product_description_short]` | Short description, as plain text |
| `[shop_name]` | Shop name |
| `[shop_url]` | Shop URL |

The line under the buttons says: click a shortcode to insert it at the caret. Prices and names are replaced on the product page, in the customer currency and language. `[product_price]` is the FAQ shortcode for price. It becomes the live price in an FAQ answer, in the customer currency.

### 3.4 AI

**AI** stores the connection the AI FAQ generator PrestaShop uses. The line under the bar says saving here does not generate anything. Use **Bulk generation** for many products, or the **Faq** section on a product for one product.

Click a tile. The tile in use shows **Active**. A tile shows **Key stored**, **No key**, or **Key optional** on the compatible tile.

| Tile | What it calls |
|---|---|
| **OpenAI** | GPT models on the official OpenAI API. The list starts with `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Claude models on the official Anthropic API. The list starts with `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Gemini models on the official Google API. The list starts with `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | DeepSeek models through an OpenAI-compatible API. The list starts with `deepseek-chat`. |
| **Mistral AI** | Mistral models on the official API. The list starts with `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Your own server: Ollama, vLLM, LM Studio. It can run fully local. The list is empty until you add a model id. |

| Field | At the start | What it does |
|---|---|---|
| **Provider** | OpenAI | Click a tile to choose the service that writes the questions. The model list switches at once. **Save** stores the provider, the key and the model. Official providers call their own host. The base URL appears only for the compatible tile. |
| **API key** | empty | Secret from the provider account of the tile you selected. Paste a new key to replace the stored one. Leave the field empty and save to keep the key already stored for that provider. The key is encrypted when the server has OpenSSL. Each tile shows whether a key is stored. A compatible local server, such as Ollama, can stay empty. |
| **Remove the saved key** | No | **Yes** deletes the stored key of the selected provider when you save. Use it when you rotate or revoke a key. **No** leaves the stored key in place. Generation without a key fails on official providers. |
| **Compatible base URL** | empty | Used only when the compatible tile is selected. Enter the API root that ends with `/v1`, for example `http://localhost:11434/v1` for Ollama. Official providers ignore this field. Leave it empty and a run does not start: the page shows **Set the compatible base URL on the AI tab before starting a run.** |
| **Model** | `gpt-4o-mini` for OpenAI | Model id sent with every generation for the selected provider. The list contains the built-in ids and the ids you added in the box under this form. A wrong id is rejected by the provider and that language is marked failed in the queue. The compatible tile shows **No model yet. Add one below.** until you add one. |
| **Temperature** | 0.4 | How freely the model writes, from 0 to 2. 0.4 keeps answers close to the product data. A higher value varies the wording and can drift from the facts. Values outside 0 to 2 are brought back inside that range. Some providers reject this setting. The module then retries once without it. |
| **Max tokens** | 2000 | Upper bound on the length of one reply. 2000 is enough for a handful of short answers. Raise it if answers are cut off. The provider may still stop earlier. Very high values cost more and can hit the provider limit. The saved value stays between 200 and 8000. |
| **Questions per product** | 5 | How many question and answer pairs to request for each product and each language. This number is the default on **Bulk generation** and on the product page. 5 is a practical start. A later run can use a different number. The saved value stays between 1 and 20. |
| **Extra instructions** | empty | Optional rules added to every prompt: tone, length, or topics to skip. The module already tells the model to write `[product_name]` and `[product_price]` instead of a fixed name or price, so a later price change stays correct. Leave empty to use only the built-in instructions. |

Click **Save**. The page shows **Saved.**

**Models you added** sits under the form. It is a separate box for ids that are not in the built-in list. Rename or remove only these. Built-in models stay in the **Model** list and have no delete button.

| Field | At the start | What it does |
|---|---|---|
| **New model id** | empty | Adds the id to the provider tile that is selected above and selects it for the next run. Letters, digits and `.` `_` `:` `/` `@` `-` only, up to 100 characters. A built-in id is refused. |
| **Add model** | a button | Stores that id. |
| **Save** on a row you added | the current id | Renames that id. If it was the selected model, the selection follows the new id. |
| **Delete** | a button on a row you added | Asks **Remove this model?** and removes that id. A built-in id cannot be removed. |

Until you add one, the box says **No model of your own for this provider yet. Built-in ids stay in the list above.**

Messages you can see here:

- **Choose a provider before adding a model.**
- **That id is already a built-in model. It stays in the list and cannot be added again.**
- **That model id is not valid. Use letters, digits and . _ : / @ -, up to 100 characters.**
- **Built-in models cannot be edited.**
- **That id is a built-in model. Type a different id.**
- **That model could not be renamed. Use a new id that is not already in the list.**
- **Built-in models cannot be removed.**
- **That model is not one you added, so it was left in place.**

### 3.5 Bulk generation

**Bulk generation** queues many products. The line under the bar says empty filters are ignored, **Start generation** writes one language per request, and this page shows a bar from 0% to 100%. The scheduled address does not read these filters.

**Active products in this shop** shows the count of active products before any filter. That number is the shop's catalogue, not a fixed value of the module.

| Field | At the start | What it does |
|---|---|---|
| **Categories** | none ticked | Tick every category to include. A child category is not included unless you tick it too. Leave the tree empty to ignore categories. A product in several ticked categories is queued once. |
| **Brands** | none selected | Hold Ctrl or Cmd and click one or more brands. Only products of those brands are queued. Leave the list untouched to ignore the brand. Combined with categories, the product must be in a ticked category and one of these brands. |
| **Suppliers** | none selected | Hold Ctrl or Cmd and click one or more suppliers. A product matches when that supplier is the default supplier or an extra supplier. Leave the list untouched to ignore the supplier. |
| **Skip products that already have an AI entry** | No | **Yes** leaves out products that already have an AI entry linked directly to them. Entries you wrote by hand do not count, so those products are still queued. **No** queues matching products again. |
| **Skip products that already have any FAQ** | No | **Yes** leaves out products that already have any entry linked directly to them, including entries you wrote by hand. **No** only applies the AI switch above. |
| **Only products in stock** | No | **Yes** keeps products with a quantity above zero, including a combination that is in stock. **No** ignores stock. |
| **Only products with a cover image** | No | **Yes** skips products that have no cover image in this shop. **No** ignores images. |
| **Only products with a description** | No | **Yes** keeps products whose short or full description is filled in the shop default language. **No** ignores the text. |
| **Base price from** | empty | Tax excluded catalogue price, before specific prices. Leave empty for no minimum. A product below this price is left out. |
| **Base price to** | empty | Tax excluded catalogue price, before specific prices. Leave empty for no maximum. A product above this price is left out. |
| **Added since** | empty | Queue only products created on this date or later. Leave empty to ignore the creation date. |
| **Maximum products** | empty | Stop after this many products, lowest id first. 0 or empty means no cap. Use a small number to try the filters before a full run. |
| **Languages** | none selected | Hold Ctrl or Cmd and click the languages to write. Each language is one request per product. Leave the list empty to write every active language of this shop. The names are the languages of this shop. |
| **Questions** | 5, the number from **AI** | How many pairs to write for each product in this run. It overrides the default from the **AI** tab for this queue only. Use the same number in every language of the product. |
| **Existing AI entries of the product** | Append | **Append** keeps the current AI entries and adds new ones. **Replace unlocked AI entries linked only to the product** deletes unlocked AI entries that are linked only to that product, once per product, then writes new ones. Entries you edited by hand are locked and are kept. Entries also linked to a category or another target are kept. |
| **Send to the model** | see the cards | Choose the product data the model may read. A card that is off is not sent. Saving a run also stores these cards for the next time. |

The cards under **Send to the model** use these titles. The sentence under each title is the hint on the card.

| Card | At the start | Hint on the card |
|---|---|---|
| **Name and reference** | on | Title and reference of the product. |
| **Short description** | on | The summary shown under the title. |
| **Full description** | on | The long description from the product page. |
| **Price summary** | on | Current price and the price before a discount. |
| **Categories** | on | Default category and the other categories. |
| **Features** | on | Feature names and their values. |
| **Brand** | on | Brand name. |
| **Attributes and combinations** | off | Attributes of each combination. |
| **Tags** | off | Tags in the language being written. |
| **Supplier** | off | Default supplier name. |
| **Stock and availability** | off | Quantity and the availability label. |
| **Weight and dimensions** | off | Weight, width, height and depth. |
| **EAN, ISBN and condition** | off | EAN, ISBN, UPC, MPN and condition. |
| **Attachment titles** | off | Titles of files attached to the product. |
| **Existing questions (avoid duplicates)** | off | Questions already published, so the model does not repeat them. |

**Run** has two cards.

**Start in this browser.** **Start generation** queues the products that match the fields above, one row per language. This page stays open and shows the status here, then sends each language to the model. Leave the tab open until the bar finishes. Closing the tab stops this page. The queue itself stays and the scheduled address can finish it.

The bar starts at **Starting…** and 0%. While it runs, the line is the number done, a slash, and the total. At the end it reads `Finished.` plus that count. A failed language adds `failed` and the last error text from the provider. When nothing matched, the page shows **No products matched this selection.** When the queue cannot be stored, it shows **The queue could not be created.** When the run cannot start, the status line shows **The run did not start.** A reply the page cannot read shows **That request could not be read.** A failed step shows **The generation request failed.** or the error text from the provider. These progress sentences stay in that wording.

**Continue on the server.** This is not a second start button. It does not read the categories, the question count or append or replace from this form. Schedule one URL every few minutes. Each call works for about 20 seconds and then stops.

Copy **Finish a queue that already exists** after **Start generation** when you will close the tab, or when a run stopped before the bar reached the end. It only writes rows that are already queued.

Copy **Fill products that still have no AI entry** when you want new products filled without opening this page. That address adds every active product in this shop that has no AI entry, using the question count and the data choices saved on **AI**. It always appends, then drains the queue.

Keep both addresses private. They contain the secret that authorises the call. **Save** on this form is not what starts the run. **Start generation** does.

Before a run, the page refuses to start and shows one of these:

- **Choose a provider on the AI tab before starting a run.**
- **Choose a model on the AI tab before starting a run.**
- **Set the compatible base URL on the AI tab before starting a run.** Fill **Compatible base URL** on the compatible tile. An empty address does not start the run.
- **Save an API key for the selected provider on the AI tab before starting a run.**

### 3.6 API

**API** is for a system outside the shop. The line under the bar says you generate a key here, give it a label, and copy the base URL. **See full list** opens the key catalogue. **Request history** lists every call, with the parameters and the response. **API documentation** lists every action.

| Field | At the start | What it does |
|---|---|---|
| **Base URL** | the address of this shop | Address an external system calls. Send `action` and `api_key` as query parameters or as POST fields. The header `X-Api-Key` is also accepted. Open **API documentation** for the parameter list of each action. A missing or revoked key is rejected. |
| **Key label** | empty | A name so you can tell keys apart, for example ERP or staging. It is not the secret. **Generate key** creates a new secret and shows it in the table. **Revoke** stops a key and leaves it in the list. **Delete** removes that row and the secret. Other keys keep working. You can create more than one key. |

**Generate key** adds the key and returns to this page. The preview **Keys already issued** lists the five newest keys. The count is the full number of keys. The secret in this preview is shortened. **See full list** shows the whole secret so you can copy it into the other system.

| Column | What you use it for |
|---|---|
| **Label** | The name you typed. |
| **Key** | The start of the secret on this preview. The full secret is on the key list. |
| **Status** | **Active** or **Revoked**. |
| **Created** | When the key was generated. |
| **Last used** | The last successful call, or **Not used yet**. |
| **History** | Opens **Request history** filtered to this key. |
| **Revoke** | Asks **Revoke this key? It stops working immediately and stays in this list.** Hidden when the key is already revoked. |
| **Delete** | Asks **Delete this key? The row and the secret are removed. Past requests stay in the history.** |

When there are no keys the page says **No keys yet**.

**API documentation** opens a window. **Copy** copies the base URL and then shows **OK**. Each action has **Copy URL** and **Copy cURL**. Replace `YOUR_API_KEY` in the example with the secret from the key list. The window also lists **Parameter**, **Required** and **Description**. **Close** leaves the window.

| Action | What to send | What it does |
|---|---|---|
| `list` | `action=list`. Optional `id_product`, `resolved=1`, `page`, `id_shop`. | Returns entries. With `id_product`, only entries linked directly to that product. With `resolved=1`, the set the product page would show. Without a product, `page` walks the catalogue, 50 entries per page. |
| `get` | `action=get` and `id`. | Returns one entry with every translation and association. |
| `create` | `action=create`, plus a question and at least one link. Optional `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Creates one entry. `id_product` attaches it to that product. `translations` is a JSON object keyed by the language id. Shortcodes such as `[product_name]` are stored as-is. `active` defaults to on. A missing question or a missing link is rejected. |
| `update` | `action=update` and `id`, plus only the fields you want to change. | Updates only the fields you send. `replace_assoc=1` replaces associations. Otherwise `id_product` and `assoc` are added. This call does not lock the entry. |
| `activate` | `action=activate` and `id`. | Shows the entry again without changing the text. |
| `deactivate` | `action=deactivate` and `id`. | Hides the entry. It stays in the back office and disappears from the product page. |
| `delete` | `action=delete` and `id`. | Deletes the entry, its translations and its links. |

`assoc` is a JSON list of objects with `type` and `id`. The type is `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` or `supplier`. Optional `id_shop` selects the shop. Without it, the shop of the called URL is used. GET is enough for a short call. POST the same fields when a question or answer is long HTML.

**Request history** is a read-only list titled **API request history**. The note says each row is one call. Search from the boxes under the column titles. **View** opens the parameters and the response. The secret in the stored call is masked. Rows stay as they were recorded. You cannot add, edit or delete a row. If a write is attempted, the page shows **Request history is a record of calls. Open View to read one row.**

Columns: **ID**, **Date**, **Action**, **HTTP**, **Key ID**, **Key**, **Details**, **IP**. **API keys** in the toolbar opens the key catalogue. **Back to module** returns to **API**. Opening history from the module uses a reset link, so a previous filter is cleared. **History** on one key keeps that key's filter.

The key catalogue is titled **API keys**. The note says the secret is listed so you can copy it into the other system. **Revoke** stops that key and leaves the row. **Delete** removes the row and the secret. Past requests stay in **Request history**. **Generate a key** returns to the **API** tab. There is no **New** button on this list. Columns: **ID**, **Label**, **Key**, **Status**, **Created**, **Last used**. **Status** reads **Active** or **Revoked**. **Last used** reads **Not used yet** until the first accepted call. Row actions are **Revoke**, **History** and **Delete**. **Revoke** is hidden on a revoked key and asks **Revoke this key? It stops working immediately and stays in this list.** **Delete** asks **Delete this key? The row and the secret are removed. Past requests stay in the history.** **Bulk actions** has **Revoke selected** and **Delete selected**, with the same effect on every ticked row. If the employee cannot edit, the page shows **You do not have permission to edit this.**

### 3.7 Updates

**Updates** checks MyPresta.eu for a newer release. The check only reports a version. Installing the package stays a manual download from the module page. The form title is **MyPresta Updates**.

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | a **Check now** button | Manually check if a new version of this module is available on MyPresta.eu servers. **New version available!** means a newer release is listed. **Module is up to date!** means this install matches the published release. The button does not upload a zip. |
| **Updates notifications** | Enable | **Enable** repeats that check about every three days while you work in the back office. **Disable** skips it. **Enable** and **Disable** are the two choices. |
| **Module page** | a link named **MyFAQ** | Direct link to the official addon page, where you can read about changes in the module. |

Click **Save**. The page shows **Update settings saved.**

When a newer release is known, the back office can show **New version available, check http://MyPresta.eu for more informations** and a link **More details in changelog**. Upload the new zip from **Module Manager**.

### 3.8 One product

Open **Catalog**, **Products**, the product, then the **MyFAQ** block. The heading is **FAQ on this product**. The text under it says: choose where this product shows its questions, review what it inherits from the catalogue, and write entries that belong only here. If no entry is active, or placement is **Hide**, the shop renders no MyFAQ block on this product.

The tabs are **FAQ entries**, **Question & Answer** and **Generate with AI**.

**FAQ entries** starts with **Placement**.

| Field | At the start | What it does |
|---|---|---|
| **Placement** | Use the shop default | **Use the shop default** follows **Display**. **Product footer** or **Product tab** forces that place for this product only. **Hide** removes MyFAQ from this product, including the schema block. Other modules on the hook are not moved. Their order stays under **Design**, **Positions**. |

**Save** shows **Saved.**

**FAQs on this product** has two lists. The first is read-only and comes from a category, feature, attribute, tag, brand or supplier. The second is stored for this product. Drag a row to change the order, use the switch to show or hide a question, and delete to remove it.

**From the catalogue** lists entries shown because another product with the same link would show them too. Change the text in the module catalogue. Columns are **Question**, **Status** and **Actions**. **Status** is **Active** or **Inactive**. **Edit in the catalogue** opens that entry. An AI entry can show **AI** and **locked**. A typed entry shows **Written by hand**. When nothing matches, the card says **Nothing inherited**.

**Only this product** lists questions tied to this product. Drag the handle (**Drag to reorder**) to set their order on the product page. The switch shows **Active** or **Inactive**. **Edit** opens **Question & Answer**. **Delete** asks **Delete this entry?** When the list is empty the card says **No FAQ for this product yet** and offers **Add an entry**. **No question in this language** means the current back-office language has no question text; another language may still have one.

**Question & Answer** is **Add an entry** or **Edit entry**. The note says it is saved for this product only. Category, feature and other links stay on the **Entries** screen. The question is plain text on the shop. The answer keeps the editor formatting. Shortcodes sit under the answer. The language button on the right switches the question and the answer together.

| Field | At the start | What it does |
|---|---|---|
| **Question** | empty | Same role as in the catalogue. The help says the default language is required. If every language is empty, the block shows **Enter a question in at least one language.** |
| **Answer** | empty | Same role as in the catalogue. An empty language is not shown in that language. |
| **Shortcodes** | the token buttons | Same tokens as in the catalogue. Click one to insert it at the caret. |
| **Active** | Yes | **Yes** shows the entry. **No** hides it from the shop. |

**Save** links the entry only to this product. Editing an existing row locks it, so a later replace keeps it. A new row is not locked. **New entry** clears the form. **Delete entry** removes it after **Delete this entry?** If you open an entry that is also linked to something else, the block shows **This entry is not exclusive to the product.** and does not save over it. Change that entry from **Edit in the catalogue**.

If the save cannot reach the shop, the block shows **The save could not reach the shop. Reload the product and try again.**

**Generate with AI** writes questions for this product from its catalogue data, in every shop language. The run continues in the background. A progress bar appears here after you start it.

| Field | At the start | What it does |
|---|---|---|
| **Questions** | 5, the number from **AI** | How many pairs to write for this product, in every shop language. It overrides the default from the **AI** tab for this run only. |
| **Existing AI entries of the product** | Append | **Append** keeps the current AI entries and adds new ones. **Replace unlocked AI entries linked only to the product** deletes unlocked AI entries linked only to this product, then writes new ones. Entries you edited by hand are locked and are kept. |
| **Send to the model** | the same cards as **Bulk generation** | The same cards. A card that is off is not sent. This run stores the cards for the next time. |

**Generate** starts the run. The same four messages as on **Bulk generation** appear when the provider, the model, the compatible address or the key is missing. The bar uses the same wording: **Starting…**, then the counts, then `Finished.` Leave this product page open until the bar finishes, or finish the queue with the address on **Bulk generation**.

## 4. Storefront

The customer sees the block only on a product page.

When **Placement** is **Product footer**, the accordion is under the product. The heading is **Heading above the list** for the customer's language. Each question is a button. The answer opens under it. **Open the first question** set to **Yes** opens the first answer on load. Without JavaScript every answer is visible.

When **Placement** is **Product tab**, the theme adds a product tab. The tab label is **Tab title** for that language, or FAQ when that language is empty. The tab content is the same accordion and the same heading.

Entries linked directly to the product come first. Then the order is the position from the catalogue and from **Drag to reorder** on the product. A question or an answer that is empty in the customer's language is skipped. After the tokens are replaced, a question that is empty, or an answer that has no text left, is skipped too. Inactive entries are skipped. **Hide** on that product prints nothing, including the schema block.

**FAQ schema markup** set to **Yes** is the FAQ schema PrestaShop writes into the page source: one FAQPage block, built from the questions the customer can open, in the language of the page, and pointing at the product URL. The customer does not see a separate schema box. **No**, an empty list, or **Hide** prints no such block.

The customer cannot add, edit or send a question. There is no account page for these entries.

If the theme does not print the product footer and does not print extra product tabs, the customer sees nothing even when entries exist. Move **MyFAQ** under **Design**, **Positions**, on **displayFooterProduct** or **displayProductExtraContent**. Other modules on that hook stay in the order you set there.

Two footer positions can exist on the same theme. The accordion is printed once.

## 5. Problems

**The product page has no accordion.** The product has no active entry in the customer's language, the question or the answer is empty after the tokens are replaced, or **Placement** for that product is **Hide**. Open the product, set **Placement** to **Use the shop default** or **Product footer** or **Product tab**, and confirm an **Active** entry. If the theme has no footer and no extra tabs, move the module under **Design**, **Positions**.

**An entry linked to a parent category does not show.** **Include parent categories** is **No**, or the link is Home. Set **Include parent categories** to **Yes**. A link to Home does not cover the catalogue. Tick the parent you actually want, under Home.

**The shop shows the entry in one language and not in another.** That language has an empty question or an empty answer. Edit the entry and fill both. The page skips an empty language.

**Save shows "Enter a question in at least one language."** Type a question in at least one language and click **Save** again.

**Save shows "Link the entry to at least one product, category, feature, attribute, tag, brand or supplier."** Pick at least one result in **Products**, **Categories**, **Feature values**, **Attribute values**, **Tags**, **Brands** or **Suppliers**.

**The product block shows "This entry is not exclusive to the product."** That question is also linked to a category or another target. Click **Edit in the catalogue** and change it there.

**The product block shows "The save could not reach the shop. Reload the product and try again."** Reload the product and save again.

**Generate does nothing and shows a message about the AI tab.** Open **AI**, choose the tile, save a model, and save a key for an official provider. For the compatible tile, fill **Compatible base URL**, for example `http://localhost:11434/v1` for Ollama. Then start the run again.

**Start generation shows "No products matched this selection."** Clear a filter or tick a category that contains active products. Empty filters are ignored, so a filter you did set is what removed the products.

**The bar stops before 100%.** Leave the tab open, or copy **Finish a queue that already exists** and open it on a schedule. Closing the tab does not delete the queue. A line with `failed` and a provider message means that language was rejected. Read the message, fix the key or the model id, and run again. **Append** adds another set. **Replace unlocked AI entries linked only to the product** removes the unlocked AI set first.

**The progress line shows `curl_missing`.** The server has no cURL. Ask the host to enable it. Generation does not run without it.

**A newer version notice appears.** The text is **New version available, check http://MyPresta.eu for more informations**. Open **Updates** and click **Check now**. Download the zip from the module page and upload it in **Module Manager**. **Disable** under **Updates notifications** stops the automatic notice.

**MyFAQ is not in the left menu.** That is expected. Open **Modules**, **Module Manager**, **MyFAQ**, **Configure**. The catalogue, the keys and the history are opened from that page. If **Configure** cannot open the catalogue, open **Configure** once while you are logged in as an employee who can install modules. That visit creates the hidden pages and grants the current profile access.

**A key is rejected.** The key was revoked, deleted, or copied without the full secret. Open **API keys**, copy the full **Key** of an **Active** row, or click **Generate a key**.

**You cannot delete a row in request history.** The page shows **Request history is a record of calls. Open View to read one row.** Use **View**.

**You do not have permission to edit this.** The employee profile cannot edit the key list. Open **Configure** as an administrator, or grant the profile access to the module pages.

**The first answer is closed even though Open the first question is Yes.** The customer has JavaScript off. In that case every answer is visible. With JavaScript on, only the first item starts open.

**The same question appears twice.** It is linked twice only if you saved two entries. One entry is shown once. Check **Only this product** and **From the catalogue** for two different rows with the same text.

**Replace left an old AI question in place.** That entry is locked, or it is also linked to a category or another target. Locked is the marker on the row. Edit it and delete it if you want it gone.

## 6. For the developer

### 6.1 Overview

Main class `myfaq` in `myfaq.php`. Version `1.3.1`. List label **MyFAQ**. Author `mypresta.eu`. Tab `front_office_features`. `ps_versions_compliancy` is `1.7.0.0` to `9.99.99`. `need_instance` is 0. `bootstrap` is true. `config.xml` still says version `1.0.0`; the class version is the one the shop runs.

`getContent()` renders `MyfaqAdminBo`. Display settings are `Configuration` keys. Entries, links, per-product placement, API keys, the request log and the AI queue are database tables. The storefront reads matches through `MyfaqMatcher`, replaces tokens with `MyfaqShortcode`, and optionally prints `MyfaqSchema`. AI calls go out through `MyfaqAi` and `MyfaqQueue`. The public address is the front controller `api`.

There is no `enable()` and no `disable()`.

### 6.2 Files

- `myfaq.php` — install, uninstall, hooks, config defaults, ajax entry points.
- `config.xml` — package metadata. Version there is `1.0.0`.
- `lib/MyfaqAdminBo.php` — back-office forms, `desc` texts, product panel.
- `lib/MyfaqConfig.php` — providers, models, flags, encryption, cron token.
- `lib/MyfaqRepository.php` — tables and CRUD.
- `lib/MyfaqMatcher.php` — which entries a product shows.
- `lib/MyfaqShortcode.php` — token catalogue and replacement.
- `lib/MyfaqSchema.php` — publishes the JSON-LD FAQ on product page.
- `lib/MyfaqAi.php` — provider HTTP calls. Requires cURL.
- `lib/MyfaqQueue.php` — batch and queue.
- `lib/MyfaqApi.php` — public API.
- `lib/MyfaqApiDocumentation.php` — modal copy.
- `lib/updatesChecker.php` — class `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — helper templates, price display, id lists.
- `lib/searchTool/searchTool.php` — autocomplete used by the association fields.
- `controllers/admin/AdminMyfaqController.php` — ajax only: search, product panel, bulk start, bulk step, reorder.
- `controllers/admin/AdminMyfaqEntriesController.php` — catalogue.
- `controllers/admin/AdminMyfaqKeysController.php` — keys.
- `controllers/admin/AdminMyfaqLogsController.php` — request history.
- `controllers/front/api.php` — public JSON API.
- `controllers/front/cron.php` — queue worker.
- `views/templates/admin/tabs.tpl` — section bar.
- `views/templates/admin/entries.tpl` — latest-ten preview.
- `views/templates/admin/product.tpl` — product edit block.
- `views/templates/admin/api.tpl` — key preview.
- `views/templates/admin/_shortcodes.tpl` — token buttons.
- `views/templates/admin/_api_documentation_modal.tpl` — action window.
- `views/templates/admin/_api_log_modal.tpl` — one stored call.
- `views/templates/hook/product.tpl` — storefront accordion.
- `views/css/myfaq.css`, `views/js/myfaq.js` — storefront.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — back office. Several progress strings in `admin.js` are fixed English.
- `upgrade/upgrade-1.0.0.php` — calls `installDb()`.
- `key.php` — optional. When present, the update check sends its license value. When absent, the check sends `nlc`.

### 6.3 Controllers

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` and `AdminMyfaqLogs` are tabs with `id_parent` `-1`. They do not appear in the menu. `ensureSearchTab()` creates a missing tab. `grantHiddenTabAccess()` grants view, add, edit and delete to the super-admin profile and to the current employee profile.

`AdminMyfaq` only serves ajax: `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. The same actions exist on the module object because the product panel and the bulk page post there.

`AdminMyfaqEntries` parent list is the catalogue. Toolbar **New entry** is `addmyfaq_item`. Save posts `submitMyfaqItem` and redirects with `conf=4`. Position uses the helper position links.

`AdminMyfaqKeys` has no add form. **Generate a key** links back to `configure=myfaq&mfq_tab=api`. `processRevoke` and bulk revoke call `MyfaqRepository::revokeApiKey`. Delete calls `deleteApiKey`.

`AdminMyfaqLogs` refuses add, update and delete with **Request history is a record of calls. Open View to read one row.** `action=View` returns the stored request and response as JSON for the modal. `id_api_key` in the query pre-fills the key filter unless the list is reset.

Front controller `api` (`module/myfaq/api`) calls `MyfaqApi::handle()` and returns JSON. It sets the HTTP status from the result. Front controller `cron` (`module/myfaq/cron`) requires `token` equal to `MYFAQ_CRON_TOKEN`. A wrong token returns `403` and `{"error":"forbidden"}`. `fill_missing=1` calls `MyfaqQueue::enqueueMissing` for the current shop, then the action drains pending rows for about 20 seconds, at most 30 rows. The JSON is `ok`, `enqueued_batch`, `processed`, `finished`.

API results: missing or revoked key `401` `unauthorized`. Unknown `action` `400` `unknown_action`. Missing or unknown id `400` `missing_id` or `not_found`. Create without a question `422` `question_required`. Create without a link `422` `association_required`. Create success `201`. Update, activate, deactivate and delete success `200`. A failed write `500`.

`list` with `id_product` and `resolved=1` uses `MyfaqMatcher::forProductAllLangs`. `list` with `id_product` and no `resolved` returns entries linked directly to that product. `list` without a product pages `MyfaqRepository::listItems` at 50 per page. Update uses `lock_on_update` false, so an API update does not lock the row.

### 6.4 Hooks

Registered in `install()`:

| Hook | Role |
|---|---|
| `displayHeader` | On a product controller, adds `views/css/myfaq.css` and `views/js/myfaq.js`. |
| `displayFooterProduct` | Renders the accordion when the resolved placement is `footer`. |
| `displayProductFooter` | Same render. A static flag prints the footer block only once per request. |
| `displayProductExtraContent` | When placement is `tab`, returns one `ProductExtraContent`. The title is `MYFAQ_TAB_TITLE` for the current language, or the source string FAQ when that value is empty. |
| `displayAdminProductsExtra` | Product edit block plus CSS and JS. |
| `actionAdminControllerSetMedia` | Admin CSS and JS on the product page, on `configure=myfaq`, and on the entries, keys and logs controllers. |

The module registers no hooks of its own and does not call `Hook::exec` for a custom hook. `displayProductExtraContent` returns an empty array when the placement is not `tab`, when the HTML is empty, or when `ProductExtraContent` does not exist.

### 6.5 Overrides

The module overrides no PrestaShop class and no controller.

### 6.6 Database

`MyfaqRepository::installDb()` creates the tables with `_MYSQL_ENGINE_` and `utf8mb4`, and retries with `utf8` if that fails. `uninstall()` drops them in this order: `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. Uninstall does drop the tables. Reinstall does not restore the rows.

| Table | Contents |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` means all shops), `active`, `position`, `source` (`manual` or `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Unique on item, type and target. Types: `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. The stored key is masked. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. A `running` row older than five minutes is set back to `pending`. |

`ensureApiSchema()` runs when the API tab, the key list, the history or a public API call is opened. It adds `last_used` when that column is missing and creates `myfaq_api_log` when that table is missing.

Catalogue save sets `lock_on_update`, so an update sets `locked` to 1. `source` on update stays the current value unless `force_source` is set. A new catalogue row is `manual` and unlocked. A product-page update also locks. A product-page insert links only that product and does not lock. AI replace deletes rows with `source` `ai`, `locked` 0, and no association other than that product.

`MyfaqMatcher::categoryIds()` adds parents only when `MYFAQ_INCLUDE_PARENT_CAT` is 1. The walk stops when `id_parent` is less than or equal to 2, or after 25 steps.

### 6.7 Configuration keys and translations

Installed by `installConfig()`. Removed by `deleteConfig()` on uninstall.

| Key | When missing or at install |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` per language |
| `MYFAQ_HEADING` | `FAQ` per language |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | empty until a model is saved. `MyfaqConfig::model()` then returns the first built-in id, or an empty string for `compatible` |
| `MYFAQ_AI_KEY_` plus the provider in upper case | empty. Stored with `MyfaqConfig::encrypt` (`enc:` and AES-256-CBC, key `sha256` of `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | empty. `baseUrl('compatible')` then uses `http://localhost:11434/v1`. `aiBlockReason()` refuses a run while this value is empty, so the back-office buttons do not reach that fallback |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. Read path clamps 0 to 2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. Read path uses 2000 when the stored value is under 200, and caps at 8000 |
| `MYFAQ_AI_COUNT` | `5`. Read path uses 5 when the stored value is under 1, and caps at 20 |
| `MYFAQ_AI_PROMPT` | empty |
| `MYFAQ_AI_CONTEXT` | JSON of `MyfaqConfig::defaultFlags()`. On: `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Off: `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` creates one when the value is empty |
| `MYFAQ_BO_TAB` | not set at install. The open section is stored on each render. Unknown values fall back to `display` |

`deleteConfig()` also deletes every `MYFAQ_AI_KEY_*` and `MYFAQ_AI_MODEL_*` for `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

Uninstall does not delete `mypresta_updates`, `update_myfaq` or `updatev_myfaq`. Those belong to the update check. `mypresta_updates` defaults to enabled when the key is missing. The automatic check interval is 259200 seconds.

Field descriptions live in `MyfaqAdminBo` (`desc` and the `sectionBrief` texts) and in `MyfaqApiDocumentation`. Back-office strings go through `$this->l()`. Add a language by placing `translations/{iso}.php`. Strings that do not go through `$this->l()`: the shortcode hints in `MyfaqShortcode::catalogue()`, the provider tile names, the flag card titles in `MyfaqConfig::contextFlagDefs()`, and the progress sentences fixed in `views/js/admin.js`. The flag card hints are translated. The flag card titles are the English source strings.

`MyfaqConfig::shopScope()` returns `0` when the multistore context is all shops, and the current shop id otherwise. Catalogue saves use that value. Product-page saves use the current shop id only.

### 6.8 Extending

Override `views/templates/hook/product.tpl` from the theme at `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. The assigned variables are `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` and `mfq_schema`. Override `views/css/myfaq.css` and `views/js/myfaq.js` the same way. The accordion is not rendered when the matcher returns no visible rows, so a theme override has nothing to print in that case. Do not edit the module templates in place if the theme can carry the override.

## 7. Help

Module page: [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

To ask about this module, sign in to the customer account on [mypresta.eu](https://mypresta.eu), open the contact form and choose the topic **Support for paid modules**. The form says that login is required for that topic. After you sign in, choose this module from the purchase history.
