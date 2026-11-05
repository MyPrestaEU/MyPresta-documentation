---
title: "PrestaMind AI - documentation and user manual"
sidebar:
  label: "PrestaMind AI - documentation and user manual"
description: "Configuration and troubleshooting for a shop that already has PrestaMind AI installed."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy PrestaMind AI - AI assistant, live chat and chatbot Module on MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


## 1. Requirements

PrestaShop 1.7.6, 8 and 9. Use the PHP version required by that PrestaShop. The module calls the cURL extension, and either OpenSSL or libsodium, to store provider keys. It does not require another module.

You need an account and an API key at the provider you choose, unless you stay on the offline demo. A local OpenAI-compatible server (Ollama, vLLM, LM Studio) needs a base URL that the shop server can reach. DHL live tracking needs a free key from the DHL developer site. InPost live tracking does not need a key.

A large catalogue makes the first reindex longer. Embeddings send each product text to the embeddings provider once, so the first run spends tokens and time. Keyword search does not.

## 2. Installation

1. Upload the module in **Module Manager** and press **Install**.
2. Confirm the question **Delete this module and all its data (conversations, knowledge index, settings)?** only when you uninstall. Install itself does not ask that.
3. After install, the menu item **PrestaMind AI** appears under **Customer service**. If that menu is missing, the item is added under **Improve**. **Configure** on the module row opens the same page.
4. Installation does not clear the shop cache. The chat bubble stays hidden until you turn it on.

Uninstall removes the menu item, the module tables and the saved settings, including provider keys. Orders, products, CMS pages and cart rules already created in PrestaShop stay. The folder of the module stays on disk until you delete it. A new install starts with empty conversations and an empty knowledge index. It does not restore the previous ones.

## 3. Configuration and daily work

### 3.1 The full process

You start in the back office. The visitor starts on the shop.

1. Open **PrestaMind AI**. On **Settings**, then **Health**, fix every line that is not OK.
2. On **Model provider**, click one provider tile, paste the API key, choose the main model and the fast model, enter prices, and press **Save and test the connection**.
3. On **Knowledge** (the settings sub-page), choose what is indexed. Then open the **Knowledge** tab and press **Reindex now**.
4. On **Playground**, send a product question, a delivery question and an order question. Each send spends tokens on the real provider.
5. On **Settings**, then **Widget**, keep **Show the assistant to all visitors** off. Put your public IP in **Preview only for these IP addresses**, save, and open the shop. When the answers are right, switch the widget on for everyone and clear a full-page cache if the bubble does not appear.
6. A visitor opens the bubble, types a question and presses the arrow. The module reads price, stock, shipping or the order from the shop when the question needs it, and shows the reply in the same window.
7. A discount exists only when an offer you saved matches the cart. **Add to cart**, **Send the return request** and **Send the quote request** wait for the visitor's click.
8. If the visitor presses **Talk to a person**, the row appears on **Escalations** and, when the console is on, on the **Live chats** button. You press **Take over this conversation**, write the reply, press **Send**, then **Give back to the assistant**. Status **new**, **open** or **done** does not e-mail the visitor.

### 3.2 Where the screens are

The page has these tabs, in this order: **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** has its own row: **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Each sub-page saves only its own fields. **Save** shows **Settings saved.** Saving does not delete conversations or the index.

The shop dashboard (the page after you sign in) shows a block with the assistant numbers, customers waiting for a person, and the latest conversations.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

Read-only. Pick **today**, **7**, **30** or **90** days, or set **From** and **To**. You can limit the AI calls by model, provider, type (answers or embeddings) or status, then press **Filter**. **See full history** opens **History**.

The screen shows revenue from orders placed in the 7 days after a chat, conversations, how many were solved without a person, ratings, tokens sent and received, and an estimated cost. The cost uses the price stored on each call. It is not an invoice from the provider. Set a control group under **Settings**, then **Privacy**, if you want a comparison of order value. Use unanswered questions to add FAQ entries.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

Leave the page open. New lines appear at the top every few seconds. Chips hide customers, the assistant, the team, tools or escalations. Search the text, or type a chat number to follow one conversation. **thumbs down only** keeps answers visitors disliked. **Pause** freezes the view. **Compact** tightens the rows. **Reset filters** shows everything. **Clear** empties the view on this page. **Open chat** opens the conversation. **Take over** lets you answer.

The page only reads stored conversations. Filters stay in this browser. Masked card, IBAN and PESEL numbers stay masked.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

The full list of model calls, newest first: date, type, provider, model, tokens sent, tokens received, the price per 1M tokens that was valid then, the estimated cost, the time and the status, with a link to the conversation. The same filters as on **Dashboard** apply. The cards above the list use that filter.

The list does not store the message text. Editing a price later does not change old rows. The log stays after conversations are deleted by the retention period.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

Filter by **Waiting for a reply**, **Handled by a person**, escalated or negative sentiment. The eye icon opens the thread: messages, the model, the response time, thumbs up and down, and every tool call. The trash icon deletes that conversation, its messages and its tool calls. Deletion is permanent.

Press **Take over this conversation**. The assistant stays silent for that visitor. Your replies appear as **Shop team**. Press **Send** to post a reply. Press **Give back to the assistant** when you are done.

**Live chats** is a floating button at the bottom right of every back office page, if **Live chat console in the back office** is on and you may open **PrestaMind AI**. The badge counts customers who are waiting. You can keep several chat windows open. Switching the console off hides the button. This page still works.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

Press **Reindex now** after install, after you change exclusions, and after you change the embeddings provider or model. **Clear answer cache** drops stored replies to repeated policy questions. The cache is also cleared when you edit an FAQ entry or a product. A document that is still waiting is not used yet. A new FAQ entry is used from the next question.

Prices and stock are not stored in the index. They are read from the product at the moment of the question.

**Add FAQ entry** / **Edit FAQ entry**: write the question and the answer the way the assistant should say it, then save. Active CMS pages and active visible products are indexed when those switches are on.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

**Triggers & offers** has two sub-pages. Create the offer first, then attach it to a trigger. A visitor sees at most one proactive message per visit. The same trigger then stays silent for its cool-down.

The list columns are **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. Row actions are edit and delete. The status box explains why a bubble may not appear, and **Open the shop in test mode** ignores consent, cool-down and the one-per-visit limit.

| Field | On a new trigger | What it does |
|---|---|---|
| **Name** | empty | A label for you. Empty uses the message text. Visitors do not see it. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page**, or **Product viewed N times in a visit**. The message appears next to the chat button. A click opens the chat. |
| **Threshold** | 30 | Seconds, scroll percent, or number of views. Exit intent ignores it. Time and idle cart use at least 5 seconds. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout**, or **Home page**. Other pages ignore this trigger. |
| **Message shown to the visitor** | empty, required | One or two sentences per shop language, up to 300 characters. An empty language uses the default language. This text is also the first line when the visitor opens the chat from the bubble. |
| **Only for these categories** | none | On a product page the product must be in one of them. On a category page the category must match. Empty means all categories. |
| **Only for these products** | none | Limits the trigger to those products. Empty means all products. |
| **Offer the assistant may grant after this trigger** | **None** | Choose an offer you already saved, or **None**. The rules decide. The model does not invent a percent. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price**, or at once when the chat opens from the message. Both ways need a cart that matches the offer. If **apply_offer** is unticked under **Tools**, the code is handed out at once. |
| **Cool-down (days)** | 7 | 0 to 365. After the bubble is shown, this visitor does not see this trigger again until the cool-down ends. |

**Add trigger** or **Save trigger** stores the row. **Allow proactive messages** must be on under **Privacy**, or no trigger fires.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

List columns: **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. Edit and delete are on the row. With no offers, the assistant never gives a discount. One conversation gets at most one offer. The code is single-use, applied to the cart, and it does not stack on products that already have a discount. The visitor sees the cart-rule name **PrestaMind offer**.

| Field | On a new offer | What it does |
|---|---|---|
| **Name** | empty | Your label, for example a short name you recognise in the trigger form. |
| **Discount percent (1-50)** | 5 | Percent taken off products that are not already on sale. |
| **Minimum cart value (tax incl.)** | 0 | 0 means any cart. Below this amount the offer is refused. The amount is in the shop default currency. |
| **Valid for (hours)** | 24 | 1 to 720. The code expires after that many hours. |
| **Maximum codes per day** | 20 | 0 means no cap. When the cap is reached, this offer stops until the next day. |
| **No offer when the cart contains products from** | none | If any cart line is in these categories, the whole cart is refused. |

**Add offer** or **Save offer** stores the rule. Attach it to a trigger before the assistant can use it. Cart reminders can also attach one offer.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

Uses the real provider. It spends tokens and counts toward the daily budget. The thread is stored with the channel playground. Nothing is sent to visitors.

| Field | On start | What it does |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category**, or **Cart**. The assistant receives that page as context. |
| **Product id (optional)** | empty | Used only with **Product page**. The id from **Catalog**, then **Products**. The assistant sees the live price and stock of that product. |
| **Customer message** | empty | The question. **Send** shows the answer and the trace (sources, tools, tokens, cost). **New conversation** starts again. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

Add a question, words the answer must contain, and words it must not contain. Press **Run all tests**. Each run asks the real model, so it spends tokens. The list shows pass or fail, the reason and the answer. Test conversations are deleted after the run.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

Rows are customers who asked for a person, return requests and quote requests, with a summary and the contact they left. Set the destination under **Settings**, then **Escalation**. On this list, set the status to **new**, **open** or **done**. The status does not e-mail the visitor. Reply with the contact on the row, or open the chat link.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

A checklist. **OK** means the line is ready. **!** means it is not. **Repair hooks** registers missing hooks and then shows **All hooks are registered.** or **Could not register:** followed by the hook names. **Test streaming** checks that the server does not buffer the live reply. Looking at the page changes nothing else. The widget line is OK only when the bubble is visible to you.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

| Field | After install | What it does |
|---|---|---|
| **Show the assistant to all visitors** | No | On: every visitor sees the bubble, except the control group. Off: nobody sees it, except the preview IPs. Clear a full-page cache after you change it. |
| **Preview only for these IP addresses** | empty | Comma-separated public IPs. The page shows the IP the shop sees now. Behind a proxy that address can differ from the one you know. |
| **Assistant name** | PrestaMind | Name in the chat header, per language, up to 60 characters. An empty language uses the default language. |
| **Greeting** | empty | First message in an empty chat, per language, up to 300 characters. Empty uses a built-in sentence. |
| **AI disclosure line** | empty | Line under the header, per language, up to 300 characters. Empty uses a built-in sentence that also says answers may contain mistakes. |
| **Color** | #2563eb | Main colour of the button, the header, the buttons and the visitor bubbles. |
| **Position** | **Bottom right** | **Bottom right** or **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square**, or **Square with sharp corners**. The window is unchanged. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)**, or **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)**, or **Very round**. |
| **Button icon** | built-in speech bubble | **Choose icon** opens Font Awesome and Material Icons. **Use the built-in bubble** restores the default. The icon is stored in the shop. Save the form to apply it. |
| **Button color** | empty (uses **Color**) | Background of the chat button. |
| **Icon color** | #ffffff | Colour of the icon on the button. |
| **Header color** | empty (uses **Color**) | Background of the top bar. |
| **Header text color** | #ffffff | Name and buttons in the top bar. |
| **Customer bubble color** | empty (uses **Color**) | Visitor messages, and also the buttons and the send arrow. |
| **Customer bubble text color** | #ffffff | Text inside visitor messages and primary buttons. |
| **Preview** | sample | Updates as you change the fields. Nothing is saved until **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual**, or **Expert**. Applies to new messages. |
| **Your instructions to the assistant** | empty | Up to 1500 characters, added to every conversation. They do not override live prices, the ban on invented discounts, or the ban on other customers' data. Long text costs tokens on every message. |

### 3.15 Model provider and every built-in model

![Model provider and every built-in model](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

Click a tile. Only the active provider is called, plus the fallback if you set one and the active one fails before the first word is sent. Models and prices are kept for every provider, so you can switch back.

After install the active provider is **Demo (offline)**. It needs no key and costs nothing. It returns canned answers so you can test the installation. It is not a shop assistant.

| Field | After install | What it does |
|---|---|---|
| **Fallback provider** | **None** | A second provider used when the active one times out, is rate-limited, or returns a server error. Choose one whose key is stored. Its usage is billed by that second provider. Demo cannot be the fallback. |
| **API key** | empty | Paste the key and save. Leave the field empty to keep the stored key. The key is stored encrypted and is not shown again, only the first and last characters. **Remove the stored key** set to Yes, then save, deletes it. The compatible server can stay without a key. |
| **Base URL** | http://localhost:11434/v1 | Only for **OpenAI-compatible / Ollama**. The URL must end in /v1. Requests go there instead of a cloud provider. |
| **Main model** | see the table of that provider | Used for product advice, order questions and any reply that needs tools. |
| **Fast model** | see the table of that provider | Used for shop-policy questions and small talk. Set it equal to the main model if you want one model for everything. |
| **Your own model id** | empty | Letters, digits and . _ - : / @ only, up to 100 characters. **Add model** saves it at once with the rest of the page. **Model added. Choose it as the main or fast model and enter its price.** If it is already listed: **That model is already on the list.** A bad id: **Enter a model id: letters, digits and . _ - : / @ only.** |
| Price columns | built-in list price | **USD / 1M input tokens** and **USD / 1M output tokens**. Use a dot as the decimal separator. A model marked **set price** has no known default. A model without a price counts as free, so the daily money budget does not protect you. |
| **Reset prices to defaults** | - | Puts the built-in prices back. **Prices set back to the built-in defaults.** Prices you typed are lost. |
| **Remove** | - | Only on a custom chat model. **Model removed.** A built-in model shows a lock and **Built-in models cannot be removed.** |

**Save and test the connection** saves and calls the active provider with the main model. **No API key stored for the selected provider.** means you still need a key.

Prices below are USD per 1 million tokens, input then output. They are the list prices stored in the module on 2026-10-31. The provider can change them. Edit the two price columns when your invoice differs. DeepSeek has peak and off-peak prices. The module stores the peak price so the estimate is not too low.

**OpenAI.** Streaming, tools and embeddings. Default main model **gpt-6.1-sol**. Default fast model **gpt-6-luna**.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| gpt-6.1-sol | chat | 2 / 10 | main model |
| gpt-6.1-terra | chat | 1 / 5 | no |
| gpt-6-luna | chat | 0.10 / 0.50 | fast model |
| gpt-5.5 | chat | 5 / 30 | no |
| gpt-5-mini | chat | 0.25 / 2 | no |
| gpt-4.1 | chat | 2 / 8 | no |
| gpt-4.1-mini | chat | 0.40 / 1.60 | no |
| gpt-4o-mini | chat | 0.15 / 0.60 | no |
| text-embedding-3-small | embeddings | 0.02 / 0 | default embeddings model |
| text-embedding-3-large | embeddings | 0.13 / 0 | no |

**Anthropic Claude.** Streaming and tools. No embeddings. Default main model **claude-sonnet-5-5**. Default fast model **claude-haiku-5-5**.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| claude-fable-5-1 | chat | 10 / 50 | no |
| claude-opus-5-5 | chat | 4 / 20 | no |
| claude-opus-5 | chat | 5 / 25 | no |
| claude-sonnet-5-5 | chat | 2 / 10 | main model |
| claude-sonnet-4-6 | chat | 3 / 15 | no |
| claude-haiku-5-5 | chat | 0.10 / 0.50 | fast model |
| claude-haiku-4-5 | chat | 1 / 5 | no |

**Google Gemini.** Streaming, tools and embeddings. Default main model **gemini-2.5-flash**. Default fast model **gemini-2.5-flash-lite**.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| gemini-2.5-pro | chat | 1.25 / 10 | no |
| gemini-2.5-flash | chat | 0.30 / 2.50 | main model |
| gemini-2.5-flash-lite | chat | 0.10 / 0.40 | fast model |
| gemini-embedding-001 | embeddings | 0.15 / 0 | default embeddings model |

**DeepSeek.** OpenAI-compatible API. No embeddings. Default main model and default fast model are both **deepseek-flash**.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| deepseek-flash | chat | 0.30 / 1.20 | main model and fast model |
| deepseek-v4-pro | chat | 1.32 / 3.96 | no |

**Mistral AI.** Streaming, tools and embeddings. Default main model **mistral-large-latest**. Default fast model **mistral-small-latest**. A blank price means the module has no list price: the row is marked **set price** until you type one.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| mistral-large-latest | chat | 0.50 / 1.50 | main model |
| mistral-medium-latest | chat | no built-in price | no |
| mistral-small-latest | chat | no built-in price | fast model |
| open-mistral-nemo | chat | no built-in price | no |
| mistral-embed | embeddings | no built-in price | default embeddings model |

**OpenAI-compatible / Ollama.** Your server. Built-in prices are 0 / 0, including local models. Default main model and default fast model are both **llama3.1**. Default embeddings model is **nomic-embed-text**.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| llama3.1 | chat | 0 / 0 | main model and fast model |
| llama3.2 | chat | 0 / 0 | no |
| mistral | chat | 0 / 0 | no |
| qwen2.5 | chat | 0 / 0 | no |
| nomic-embed-text | embeddings | 0 / 0 | default embeddings model |
| mxbai-embed-large | embeddings | 0 / 0 | no |
| bge-m3 | embeddings | 0 / 0 | no |
| snowflake-arctic-embed | embeddings | 0 / 0 | no |

**Demo (offline).** No key. Prices 0 / 0.

| Model | Kind | Input / output USD per 1M | Selected after install |
|---|---|---|---|
| mock | chat | 0 / 0 | main model and fast model, and this provider is the active one |
| mock-64 | embeddings | 0 / 0 | used when the embeddings provider is demo |

Some newer OpenAI models ignore **Temperature**. A model id the provider does not know shows up as a provider error on **Dashboard**.

### 3.16 Knowledge settings

![Knowledge settings](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

The cron address is on this page. Call it every 10 to 15 minutes. Each call indexes new and changed pages, builds embeddings, sends cart reminders if you turned them on, deletes conversations older than the retention, and clears the answer cache and rate-limit rows older than two days. Without cron, the index still updates when visitors chat or when product and CMS hooks run. Retention deletion and embeddings then run only from the buttons.

| Field | After install | What it does |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible**, or **demo**. Anthropic and DeepSeek are not in this list. Changing it requires **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | A model of the provider above. Vectors from two models cannot be compared. A model of another provider is ignored and the default is used. Reindex after a change. |
| **Other embeddings model** | empty | Exact id of a model that is not on the list, for example one you installed in Ollama. When filled, it replaces the choice above. |
| **Index products** | Yes | Indexes name, brand, categories, features and descriptions of active visible products. No means product questions get no catalogue text. |
| **Index CMS pages** | Yes | Indexes active CMS pages. Do not index pages that contain internal notes. |
| **Never use these categories** | none | Products in these categories are not indexed and cannot be shown, compared or offered for the cart. Reindex after a change. |
| **Never use these products** | none | The same, for single products. |
| **Cache answers to repeated policy questions** | Yes | Guests, first question only, and never a reply that contains a price or an order. **Clear answer cache** on the Knowledge tab after you edit a policy page. |
| **Cache lifetime (hours)** | 24 | 1 to 720. After that, the model answers again. |

### 3.17 Limits and cost

![Limits and cost](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

The top line shows today's requests, tokens and estimated cost. When a daily budget is reached, the assistant sends a short notice and offers to pass the question to your team until the next day.

| Field | After install | What it does |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 means no cap. Works only when the models you use have prices. When today's cost reaches it, model calls stop until midnight. |
| **Daily token budget** | 0 | 0 means no cap. Counts tokens even when prices are 0. 1000000 tokens is about several hundred conversations. |
| **Messages per minute per visitor IP** | 8 | 1 to 60. Faster senders get a please-wait reply and no model call. |
| **Messages per conversation per day** | 60 | 1 to 500. After that, the conversation is blocked for the day. |
| **Max reply tokens** | 700 | 150 to 3000. About 450 words at 700. A short limit cuts the answer off. |
| **Max tool steps per message** | 5 | 1 to 8. How many live lookups (search, product, shipping) one message may run. 1 stops multi-step research. |
| **Max characters per customer message** | 800 | 100 to 2000. Longer text is cut. |
| **Messages of history sent to the model** | 12 | 2 to 30. 12 is the last six exchanges. More history sends more tokens. |
| **Temperature (0-1)** | 0.3 | 0.2 to 0.4 stays closer to the shop data. Higher varies the wording. Some newer OpenAI models ignore it. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

| Field | After install | What it does |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Yes | Replaces them with [card], [iban] and [id] before the text is stored and before it is sent to the provider. |
| **Delete conversations after (days)** | 90 | 0 keeps them. The cron URL deletes older conversations. Order statistics stay. |
| **Order status without signing in, for registered customers** | Yes | A visitor may ask with the order reference and the checkout e-mail. No: that pair works only for guest orders, and a registered customer must sign in. At most 10 attempts in 10 minutes. |
| **Allow proactive messages** | Yes | No switches every trigger off. |
| **Proactive triggers wait for consent** | Yes | No bubble until the cookie banner calls the consent function. The chat itself still works. No: triggers fire for everybody. |
| **Control group (% of visitors)** | 0 | 0 to 50. Those visitors never see the assistant. **Dashboard** can compare order value. |

**Delete old conversations** is a separate form. **Older than (days)** starts at 30 on that form. **Delete** removes those conversations now. The message is **Deleted N conversations.** This cannot be undone.

### 3.19 Escalation settings

![Escalation settings](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

| Field | After install | What it does |
|---|---|---|
| **Live chat console in the back office** | Yes | Shows the **Live chats** button. Only employees who may open **PrestaMind AI** see it. Off hides the button. **Conversations** still works. |
| **E-mail for hand-offs** | empty | Each escalation sends a summary and the contact the visitor left. Empty means no e-mail. The shop mail must work. |
| **Webhook type** | **Slack** | **Slack**, **Telegram**, or **Generic JSON**. |
| **Webhook URL** | empty | Slack incoming-webhook URL, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage`, or any https URL. Empty means no webhook. The result is on the **Escalations** list. |
| **Telegram chat id** | empty | Numeric id of the chat or group. Ignored for Slack and generic JSON. |
| **Offer a person when sentiment falls below** | -0.5 | From -1 to 0. Closer to 0 reacts sooner. The assistant apologizes and offers to pass the case to the team. |

### 3.20 Cart reminders

![Cart reminders](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

Nothing is sent until **Send cart reminders** is Yes and the cron URL runs. One e-mail per abandoned cart, only to a registered customer. Guests are not mailed.

| Field | After install | What it does |
|---|---|---|
| **Send cart reminders** | No | On: the next cron run sends reminders that match the rules below. Off: nothing new is sent. Rows already sent stay in the list. |
| **Only customers who subscribed to the newsletter** | Yes | Yes: customers without the newsletter tick get nothing. |
| **Send after (hours of inactivity)** | 3 | At least 1. The cart must stay untouched for this long. |
| **Stop after (hours since the last change)** | 72 | Must be larger than the value above. Older carts are skipped. |
| **Minimum cart value (tax incl.)** | 0 | 0 means any cart. The amount is in the shop currency. |
| **Discount code in the e-mail** | **No discount code** | One of your offers, or none. The offer rules still apply. If the daily cap is reached, the e-mail goes out without a code. |
| **E-mail subject** | empty | Per language. Empty uses a built-in subject. The customer receives the subject of their account language. |

**Send a test e-mail** uses **Send the test to** (your back-office e-mail at first) and **Send test**. One sample is sent at once. It is not recorded and it does not create a code. **Test e-mail sent.** or **The e-mail could not be sent. Check the e-mail settings of the shop.** A bad address shows **Enter a valid e-mail address.**

**Latest reminders** lists date, cart, customer, code and status.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

The page lists the shipping methods of this shop. If the shop has none, you see **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

For each method, **tracking link** is one address per language. Put `{n}` where the tracking number goes. An address without `{n}`, or one that does not start with http or https, is ignored. An empty language uses the default language. If the carrier already has a tracking URL in **Shipping**, then **Carriers**, that URL is used first. Without any link, the assistant quotes the tracking number only.

**live status** appears only when the method name contains InPost or DHL, or you chose it earlier. **No live status (tracking link only)** keeps the link. InPost does not need a key. DHL shows **DHL API key**: register at the DHL developer site, create an app with Shipment Tracking - Unified, and paste the key. The free key is about 250 calls a day. The key is stored encrypted. Without it, DHL live status is skipped and the link is used. Live answers are cached for 10 minutes.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

Untick a tool to stop offering it to the model. A disabled tool cannot run. In catalogue mode the cart, offer and cart-contents tools stay off. A policy question or small talk can only call **create_ticket**.

| Tool | Risk on the screen | Needs | What the visitor gets |
|---|---|---|---|
| search_products | read | - | Up to six product cards. Optional maximum price and in-stock only. The visitor presses **Add to cart**. |
| popular_products | read | - | Bestsellers from real orders, default 90 days, from 7 to 365, up to six cards. No exact sales numbers. |
| get_product_live | read | - | Live price, stock, features and variants of one product. |
| compare_products | read | - | Two or three products side by side. |
| suggest_substitute | read | - | In-stock alternatives. |
| get_cart | read | a cart | Contents and total. |
| add_to_cart | the screen marks the confirmation | customer confirmation | A product card. Quantity 1 to 20. The module does not add the line. The visitor presses **Add to cart**. |
| check_shipping | read | - | Methods, times and the free-shipping threshold. Optional country ISO code. |
| get_order_status | read | session, or reference plus checkout e-mail | Status of that order. |
| track_parcel | read | same identity as the order status | Carrier, number and link. InPost live without a key. DHL live with the DHL key. |
| start_return | confirmation | signed-in customer | Nothing is sent until **Send the return request**. |
| request_quote | confirmation | the form | Items, company and contact. Nothing is sent until **Send the quote request**. |
| create_ticket | handoff | a guest is asked for e-mail or phone | **Talk to a person** opens an escalation. |
| apply_offer | the rules decide | a cart | A code only when a saved offer matches. No matching rule means no code. |

**Save** stores the ticks.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

**Check now** compares the installed version with the version on the MyPresta.eu servers. Keep automatic notifications on to see a notice in the back office. The module is never updated by itself. You install the new package yourself.

## 4. Storefront

The bubble is hidden until **Show the assistant to all visitors** is on, except for IPs on the preview list. Visitors in the control group do not see it.

The visitor presses the button in the corner you chose. The window shows the assistant name, the disclosure line and the greeting. The visitor types and presses the arrow. There is no button labelled Send on the shop. The reply streams into the window when the server does not buffer it.

Product cards show **Add to cart**. A return stays pending until **Send the return request**. A quote stays pending until **Send the quote request**. **Talk to a person** hands the chat to the team. While you have taken over, new visitor messages are stored and your replies show as **Shop team**.

A proactive bubble appears only when triggers are allowed, the visitor matches the rule, and consent is given if you require it. One bubble per visit. The test link from **Triggers** is for you, not for customers.

The cron address is not a page for visitors. Open it only from the server scheduler. A wrong token returns a refusal and does no work.

## 5. Problems

**The bubble is missing.** **Show the assistant to all visitors** is off, or this visitor is in the control group, or a full-page cache still has the old page. Turn the switch on, or add your IP to the preview list, save, and clear the full-page cache.

**Could not create the module tables.** Install stopped before the menu item was added. Read the database message on the screen, fix the database user rights, and install again.

**Could not register hook** followed by a hook name, or **Could not register:** on **Health**. Press **Repair hooks**. If the line stays, the shop user cannot write hooks. Fix the database rights and press the button again.

**Could not add the menu tab.** Install did not finish the menu. Open **Module Manager**, uninstall if the module is half-installed, and install again. **Configure** also tries to recreate the menu item.

**No API key stored for the selected provider.** Paste the key on **Model provider** and press **Save and test the connection**. An empty password field does not delete a key. **Remove the stored key** does.

**That model is already on the list.** Choose it as **Main model** or **Fast model** instead of adding it again.

**Enter a model id: letters, digits and . _ - : / @ only.** Retype the id from the provider's model list. Spaces are not allowed.

**Built-in models cannot be removed.** Leave the row. Add a custom id if you need another model.

**Provider errors on Dashboard.** The key is wrong, the model id is unknown to that provider, or the provider is down. If a fallback is set and the failure happens before the first word, the fallback answers. Fix the key or the model, then use **Playground**.

**The reply appears in one block, not word by word.** Press **Test streaming** on **Health**. If it fails, the proxy or the host is buffering the response. Ask the host to disable buffering on the shop's chat address.

**I cannot answer right now.** The daily budget or the token budget is reached, or the provider failed and there is no fallback. Raise the budget, wait until the next day, or fix the provider. The assistant offers to pass the question to the team.

**Please wait, or the conversation is blocked.** The visitor sent more than **Messages per minute per visitor IP** or more than **Messages per conversation per day**. Wait, or raise the limit.

**A trigger never appears.** Read the box on **Triggers**. **Allow proactive messages** is off, the trigger is inactive, **apply_offer** is off while the trigger waits until the visitor asks, or triggers wait for consent and the banner never calls the consent function. Use **Open the shop in test mode** to ignore consent, cool-down and the one-per-visit limit. After a real test, the cool-down hides that trigger for that browser.

**The discount never appears.** There is no offer, the offer is not attached to the trigger, the cart is under the minimum, the daily cap is reached, a product is in an excluded category, or the product is already discounted. The assistant does not invent a percent.

**Add to cart does nothing by itself.** The card is only a card. The visitor presses **Add to cart**. In catalogue mode the cart tools stay off.

**Test e-mail sent.** is success. **The e-mail could not be sent. Check the e-mail settings of the shop.** means the shop mail failed. **Enter a valid e-mail address.** means the test address is empty or invalid. Reminders to customers also need **Send cart reminders** on Yes and a working cron URL.

**Deleted N conversations.** You pressed **Delete** under **Privacy**. Those threads are gone.

## 6. For developers

### 6.1 Overview

Technical name `prestamindai`, class `prestamindai`, version in the file `1.8.9`, display name **PrestaMind AI**, author MyPresta.eu, tab `front_office_features`. Compliance from 1.7.6.0 with max `99.99.99`. There is no `enable()` and no `disable()` of its own. PrestaShop's disable stops the registered hooks. Enable registers them again through the core.

`PmaiConfig` reads and writes `Configuration` keys with the prefix `PMAI_`. `PmaiProviderRouter` picks `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` or `PmaiMockProvider`. DeepSeek and the compatible URL use the OpenAI-compatible client. `PmaiOrchestrator` builds the prompt, calls the model, and runs tools from `PmaiToolRegistry`. Prices used for a call are copied onto the usage row.

### 6.2 Files

| File | Role |
|---|---|
| `prestamindai.php` | Install, uninstall, hooks, menu tab, redirect from **Configure**. |
| `sql/install.php` | Creates the 16 tables. |
| `sql/uninstall.php` | Drops those tables. |
| `controllers/admin/AdminPrestamindaiController.php` | Back-office tabs and POST actions. |
| `controllers/front/chat.php` | Storefront chat endpoint. |
| `controllers/front/cron.php` | Single cron URL. |
| `src/Service/PmaiConfig.php` | Defaults, model lists, built-in prices, custom models. |
| `src/Admin/PmaiForms.php` | Every back-office form and the field descriptions. |
| `src/Admin/PmaiSectionHelp.php` | The help text of each tab. |
| `src/Agent/PmaiToolRegistry.php` | The 14 tools and the catalogue-mode filter. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek and the compatible URL. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Offline demo. |
| `src/Knowledge/PmaiIndexer.php` | Discover and reindex. |
| `src/Safety/PmaiGuardrails.php` | Replaces card, IBAN and PESEL. |
| `upgrade/` | Version upgrades call `upgradeDb()`. |
| `translations/{iso}.php` | Back-office strings. |
| `views/` | Admin and storefront templates, CSS and JS. |

### 6.3 Controllers

`AdminPrestamindai` is the menu class. Parent is the first existing class among `AdminParentCustomerThreads`, `AdminCustomerThreads` and `IMPROVE`. The tab label is **PrestaMind AI**. `getContent()` redirects to this controller.

Query `pmai_tab` is one of `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Settings also read `pmai_sub`: `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` accepts the storefront operations init, message, feedback, confirm, add_to_cart, escalate, poll, event and open_trigger. `controllers/front/cron.php` requires the cron token. A bad token returns JSON `ok: false` and `error: token`.

### 6.4 Hooks

Registered on install: `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` prints the widget, with `displayFooter` as a fallback. Product and CMS hooks mark documents to reindex. `actionValidateOrder` links the order for the revenue figure. GDPR hooks export or delete the customer's module rows. **Repair hooks** calls `ensureHooks()` for any missing name. The module does not register hooks of its own for other modules.

### 6.5 Overrides

The module does not override a PrestaShop class or controller.

### 6.6 Database

Uninstall runs `DROP TABLE` on every table below. Install uses `CREATE TABLE IF NOT EXISTS`, so a failed uninstall that left tables would keep old rows. A normal uninstall drops them, and the next install is empty.

| Table | Contents |
|---|---|
| `PREFIX_pmai_thread` | One conversation: shop, customer, guest, channel, status, page. |
| `PREFIX_pmai_message` | Messages on that thread, including payload for cards. |
| `PREFIX_pmai_tool_call` | Tool name, arguments and result for a message. |
| `PREFIX_pmai_doc` | Indexed product, CMS or FAQ document. |
| `PREFIX_pmai_chunk` | Chunks of a document, including the embedding when present. |
| `PREFIX_pmai_cache` | Cached policy answers. |
| `PREFIX_pmai_trigger` | Proactive trigger rules. |
| `PREFIX_pmai_offer` | Discount rules. |
| `PREFIX_pmai_event` | Storefront events used by triggers and analytics. |
| `PREFIX_pmai_usage` | One model call: provider, model, tokens, price snapshot, cost, status. No message text. |
| `PREFIX_pmai_request` | Request rate-limit rows. |
| `PREFIX_pmai_cart_reminder` | One sent cart reminder. |
| `PREFIX_pmai_escalation` | Handoff, return or quote, plus notification result. |
| `PREFIX_pmai_ratelimit` | Short-window counters. |
| `PREFIX_pmai_eval_case` | A quality-test question and the required words. |
| `PREFIX_pmai_eval_run` | One run of those tests. |

`PmaiConfig::PRICES_CHECKED` is `2026-10-31`. Built-in chat and embedding ids and prices live in `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` and `builtinPrices()`. Custom ids are JSON in `PMAI_CUSTOM_MODELS`. Edited prices are JSON in `PMAI_MODEL_PRICES` and win over the built-in price.

### 6.7 Keys and translations

Every key is `PMAI_` plus the name in `PmaiConfig::defaults()`. Provider secrets are `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK`, plus `PMAI_KEY_DHLTRACK`. They are encrypted with libsodium when `sodium_crypto_secretbox` exists, otherwise with OpenSSL. `PMAI_CRON_TOKEN` is a random hex string created on install when it is empty.

Model selection keys are `PMAI_MODEL_MAIN_{PROVIDER}` and `PMAI_MODEL_FAST_{PROVIDER}`. After install: OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` is `mock`. `PMAI_EMBED_PROVIDER` is `none`. `PMAI_EMBED_MODEL` is empty, so the first built-in embedding model of the chosen provider is used.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` and `PMAI_REMINDER_SUBJECT` are multilingual. Field help is the `desc` HTML built in `PmaiForms`. Add a language by translating `translations/{iso}.php`. Strings that never go through `$this->l()` stay as written in the PHP arrays (provider tile names, model ids, tool ids).

### 6.8 Extending

The storefront widget template and CSS can be overridden by a theme in the usual PrestaShop way, under `modules/prestamindai/views/`. The back office is not a theme override. Do not edit model ids in a theme. Add a model on **Model provider**. A cookie banner can call `window.PrestaMindAI.setConsent(true)` after the visitor accepts. The module does not ship a banner.

## 7. Help

Module page: [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

To write about this module, sign in to your customer account on mypresta.eu, open the contact form and choose the topic **Support for paid modules**. The form says that signing in is required for paid modules. After you sign in, choose this module from the purchase history.
