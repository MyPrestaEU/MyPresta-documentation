---
title: MyFAQ Free - documentation and user manual
sidebar:
  label: MyFAQ Free - documentation and user manual
description: Configuration and troubleshooting manual for shops that already have MyFAQ Free.
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Free Product FAQ Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/free-product-faq/)
>
> ---


## 1. Requirements

MyFAQ Free runs inside PrestaShop. It does not need another module.

- PrestaShop 1.7.0.0 through PrestaShop 9.
- The PHP version required by that PrestaShop release. The module does not add its own PHP version check.
- No extra PHP extension is required. The update check uses cURL when the server has it. When cURL is missing, the check reads the address only if the server allows remote reads.
- No other module is required. The product page of the theme must print the product footer, or the extra product tabs, for the customer to see the questions.
- No account in an external service is required to write and show the three questions. A PayPal donation on the configuration page is optional. The update check only needs the shop to reach MyPresta.eu.

Each product stores three questions. There is no import, so a large catalogue does not start a batch or raise the memory the module asks for.

## 2. Installation

1. In the back office open **Modules**, then **Module Manager**.
2. Upload the module zip and click **Install**.
3. Open **Configure** on **MyFAQ Free**. The page opens on **Unlock Pro**. The bar also has **Settings** and **Updates**.
4. MyFAQ Free does not add an item to the left menu. The questions are written on each product.

Installation does not clear the PrestaShop cache. If the product page still shows the previous layout after an update, clear the cache in **Advanced Parameters**, **Performance**.

To turn the module off, use the switch in **Module Manager**. The product page no longer prints the questions, and the product edit page no longer shows the FAQ block. The questions and the placement settings stay. Turn the module on again and they are used as before. The module has no separate enable or disable button of its own.

To remove it, click **Uninstall** and confirm. Uninstall removes the questions, the placement, the tab title and the heading. The hidden page that saves the questions is removed. The module files stay on the server until you delete the module. Installing again starts with empty questions, **Product footer**, the tab title FAQ and an empty heading. The old questions are not restored. The update notification switch is shared with other MyPresta modules and stays as you left it.

## 3. Configuration and daily work

You write the questions on the product, not on the module page. Open **Catalog**, **Products**, and edit the product. On a shop with several stores, the product page asks you to pick one store in the multistore header. Open the **Modules** tab, and in **Module to configure** choose **MyFAQ Free**. Fill in up to three questions, tick **Show on the product page**, and click **Save these questions**. A slot whose question is empty stays off the product page.

On the module page you only choose where that block is printed and what it is called. **Product footer** prints the accordion under the product. **Product tab** adds one product tab and leaves the footer empty. A product with no question shows nothing in either place.

The customer opens the product, clicks a question, and reads the answer. There is no form for the customer to send a new question. The path ends when the product page shows the accordion, or when the product has no question to show.

Open **Modules**, **Module Manager**, **MyFAQ Free**, **Configure**. Above the bar, the page says **I am developing this module for free - if you want** and offers **send me a donation**. Under that line is a strip of other modules. The note under the bar says the questions are set on each product.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

The screen is the **Unlock Pro** section, with the donation line above the bar.

**Unlock Pro** does not save a setting and does not write questions. The line under the bar is **MyFAQ without the three-question limit**. It says MyFAQ keeps every question you already wrote and adds the catalogue, the AI writer and the API, and that the questions on a product stay in the free module until you move them.

The box **The full FAQ for the catalogue** lists what the paid module adds and ends with **See MyFAQ**. That button opens the paid module page in a new tab. Nothing on this tab is stored for the free module.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

The screen is the **Settings** section. The picture shows a shop that already saved **Product tab** and a heading. A fresh installation uses the values in the table.

The line under the bar is **Where the three questions are shown**. It says the free module writes the FAQ on each product, three questions at most, and that here you only choose the product footer or a product tab, and the names of that block.

The form title is **Placement**.

| Field | At the start | What it does |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** prints the accordion under the product. **Product tab** adds one product tab and leaves the footer empty. A product with no question shows nothing in either place. |
| **Tab title** | FAQ in every language | The name of the product tab when **Show the FAQ** is **Product tab**. Use the language button to fill each language. Leave a language empty to use FAQ. |
| **Heading** | empty | A title above the questions, in the footer and in the tab. Use the language button to fill each language. Leave it empty to show the questions only. |

Click **Save**. The page shows **Settings saved.**

The language button shows the languages of this shop. On the shop in the picture they are English, French and Polish.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

The screen is the **Updates** section.

The line under the bar is **Newer versions of MyFAQ Free**. It says the check reports a version and that installing the package stays a manual download.

The form title is **MyPresta Updates**.

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | **Check now** | Manually checks if a new version of this module is available on MyPresta.eu servers. The button does not download or install the package. After the check, **New version available!** or **Module is up to date!** appears beside the button. |
| **Updates notifications** | Enable | Turn this option on if you want to check MyPresta.eu for module updates automatically. This option displays a notification about new versions of this addon. **Disable** stops that automatic check. The switch is shared: other MyPresta modules on this shop use the same switch. The automatic check runs about every three days while the back office is in use. |
| **Module page** | a link named **MyFAQ Free** | This is the direct link to the official addon page, where you can read about changes in the module (changelog). The link opens [https://mypresta.eu/](https://mypresta.eu/). |

Click **Save**. The page shows **Update settings saved.**

When a newer version has been reported and notifications are on, the back office shows **New version available, check http://MyPresta.eu for more informations** and the link **More details in changelog**. That link opens the same address as **Module page**.

### 3.4 Questions on the product

![FAQ on the product](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

The screen is the **MyFAQ Free** block on the product, on the **Modules** tab. The picture is a product that already has three questions. A new product starts with empty boxes. The languages EN, FR and PL are the languages of this shop.

Open **Catalog**, **Products**, edit the product, open **Modules**, and in **Module to configure** choose **MyFAQ Free**.

On a product that has not been saved yet, the block says **Save the product first** and **The three FAQ slots appear after the product has an id.** Save the product, then come back to this block.

The box **Three questions on this product** repeats the paid-module note and ends with **See MyFAQ**. It does not store the free questions.

Under it, **FAQ for this product** says: three questions, an empty question is left off the page, and **Save these questions** keeps you on this product. The language buttons switch the question and the answer. They appear when the shop has more than one language.

| Field | At the start | What it does |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | three empty slots, **Show on the product page** ticked | The three slots on this product, in this shop. The customer sees them in this order. |
| **Show on the product page** | ticked | Ticked shows this slot when its question is filled in. Untick it to keep the text and hide the slot. |
| **Question** | empty | The line the customer clicks. The box accepts 512 characters. An empty question is left off the page. Fill the question in each language you sell in. A language with an empty question is not shown in that language. |
| **Answer** | empty | The text under the question. A line break in the box becomes a new line on the product page. Text you type is shown as text. |
| **Save these questions** | a button | Saves the three slots and stays on this product. While it saves, the line under the button says **Saving the three questions…** After a successful save it says **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

There is no list of questions outside the product, and no bulk action. Deleting the product deletes its three questions. Questions written in one store are not shown in another store until you write them there.

## 4. Shop front

![Questions on the product page](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

The customer sees the block only on a product page, and only when that product has at least one question that is filled in, ticked **Show on the product page**, and written in the customer's language.

With **Show the FAQ** set to **Product footer**, the accordion sits under the product. With **Product tab**, the same accordion is inside one product tab and the footer stays empty. The tab name is **Tab title**. An empty tab title is shown as FAQ. The picture is the tab on this shop: the tab is named FAQ and the heading is **Questions before you buy**.

The heading, when you filled one in, is printed above the questions. The first question is open when the page loads. The customer clicks a question to open or close its answer. A customer without JavaScript sees every answer. Under the list, the line **Powered by MyFAQ for PrestaShop** links to the paid module.

There is no separate page, no address to copy, and no form for the customer. A product with nothing to show prints no block.

## 5. Problems

**The product shows no questions.** The question for that language is empty, **Show on the product page** is unticked, the module is switched off, or the theme does not print the place you chose. Open the product, check the slot, then on **Settings** confirm **Show the FAQ**. **Product footer** needs the theme to print the product footer. **Product tab** needs the theme to print extra product tabs. A product with no filled question shows nothing in either place.

**The block on a new product says Save the product first.** The product has no id yet. Save the product, open it again, and the three slots appear. If you click **Save these questions** before that, the line says **Save the product first, then add the FAQ.**

**Save these questions ends with The FAQ could not be saved.** Click **Save these questions** again. If it still fails, confirm the module is installed and that your employee profile can edit products.

**The line says The FAQ could not reach the shop.** The browser did not reach the back office. Check the connection and click **Save these questions** again. While the request runs, the line says **Saving the three questions…**

**The question on the shop is shorter than the one you typed.** The question box stops at 512 characters.

**The answer shows the tags you typed.** The answer is plain text. A line break is kept. Tags are shown as characters, not as formatting.

**The footer is empty after you chose Product tab.** That is the setting. **Product tab** leaves the footer empty and puts the accordion in the product tab. Choose **Product footer** on **Settings** and click **Save** when you want the accordion under the product.

**Another store does not show the questions.** The three slots belong to the store you edited. Switch the multistore header to that store, open the product, and write the questions there.

**The product page in the back office asks you to select a store.** The product edit page works in one store at a time. Pick the store in the multistore header, then open **Modules**.

**Check now says Module is up to date! and you expected a newer version.** The check could not read a version from MyPresta.eu, or this package is the one the server reported. Confirm the shop can reach MyPresta.eu and click **Check now** again. The button never installs the package.

**A warning says New version available, check http://MyPresta.eu for more informations.** Notifications are on and a newer version was reported. Open **Updates**, read **Module page**, and install the package yourself when you want it. **Disable** under **Updates notifications** stops the warning. That switch is shared with other MyPresta modules.

**The donation strip stays empty.** The rest of the configuration page still works. Write the questions on the product and set the placement on **Settings**.

## 6. For the developer

### 6.1 Overview

Main class `myfaqfree`, version `1.0.0`, display name **MyFAQ Free**, author mypresta.eu, tab `front_office_features`. Compatibility is declared from `1.7.0.0` to `9.99.99`.

Placement is read from `MYFAQFREE_DISPLAY` (`footer` unless the value is `tab`). The tab title and the heading are read per language from `MYFAQFREE_TAB_TITLE` and `MYFAQFREE_HEADING`. The product page loads at most three active slots for the current shop and language from `MyfaqfreeRepository::frontItems()` and renders `views/templates/hook/product.tpl`. The first item is given `is-open` in the template. The answer is escaped and passed through `nl2br`.

### 6.2 Files

- `myfaqfree.php` — install, configuration, product panel, front render.
- `lib/MyfaqfreeRepository.php` — three slots, tables, save and delete.
- `lib/updatesChecker.php` — class `myfaqfreeUpdate`, update check.
- `lib/prestashop9compatibility.php` — HelperForm template directories and `curl_close` on PHP before 8.
- `controllers/admin/AdminMyfaqfreeController.php` — ajax save. The controller is a hidden tab.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — paid-module box.
- `views/templates/admin/product.tpl` — three slots on the product.
- `views/templates/hook/product.tpl` — accordion. Assigned variables: `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — language switch and save on the product.
- `views/js/front.js` — open and close a question.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — present and empty. The English strings are the source strings.

### 6.3 Controllers

`AdminMyfaqfree` extends `ModuleAdminController`. The tab is created with `id_parent = -1`, so it is not in the left menu. The class name on the tab is `AdminMyfaqfree` and the label is MyFAQ Free. `ajaxProcessSave` forwards to `myfaqfree::ajaxProcessSave()`. The product block posts `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` and `mff_a_{position}_{id_lang}` to `AdminMyfaqfree` with `ajax=1` and `action=Save`.

There is no front controller. The accordion is rendered from hooks.

`getContent()` is the configuration page. `mff_tab` accepts `unlock`, `settings` and `updates`. Any other value opens `unlock`.

### 6.4 Hooks

Registered in `install()`:

| Hook | Role |
|---|---|
| `displayHeader` | CSS and JS on the product page only. |
| `displayFooterProduct` | Accordion when placement is footer. |
| `displayProductFooter` | Same accordion. A static flag prints it once per request. |
| `displayProductExtraContent` | One product tab when placement is tab. Empty array otherwise. |
| `displayAdminProductsExtra` | The three slots on the product edit page. |
| `actionAdminControllerSetMedia` | Admin CSS and JS on the product page and on the module configuration page. |
| `actionProductDelete` | Deletes the slots of that product. |

The class does not define `enable()` or `disable()`. Turning the module off in Module Manager uses the core module switch. The class does not register a hook of its own.

`ensureHiddenTab()` and `grantHiddenTabAccess()` run from the constructor when the object is `myfaqfree`, from `getContent()`, and from the product hook. Access grants `view`, `add`, `edit` and `delete` to profile 1 and to the current employee profile.

### 6.5 Overrides

The module does not override a class or a controller.

### 6.6 Database

| Table | Contents |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Unique key on product, shop and position. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` drops both tables after `parent::uninstall()` returns true. If `parent::uninstall()` returns false, the tables stay. The tab and the three configuration keys are deleted before that return. Deleting a product deletes its rows in both tables. A slot whose every language has an empty question is deleted on save. A language with an empty question is not inserted.

The tables are created at install. Opening the configuration page does not add a column.

### 6.7 Keys and translations

| Key | When missing or at install |
|---|---|
| `MYFAQFREE_DISPLAY` | Install writes `footer`. Any value other than `tab` is treated as footer. |
| `MYFAQFREE_TAB_TITLE` | Install writes `FAQ` for every language. An empty language falls back to the source string FAQ at render time. |
| `MYFAQFREE_HEADING` | Install writes an empty string for every language. An empty heading is not printed. |
| `mypresta_updates` | Not created by this module. Missing is treated as enabled. **Disable** writes `0`. Uninstall does not delete it. |
| `update_myfaqfree` | Unix time of the last check. Uninstall does not delete it. |
| `updatev_myfaqfree` | Version string returned by the check. Uninstall does not delete it. |

The check URL is `https://dev.mypresta.eu/update/get.php`. The interval is 259200 seconds. cURL is used when `curl_init` exists, with a 3 second timeout. Otherwise `file_get_contents` is used when `allow_url_fopen` is on. The returned body is stripped of tags and stored as the available version.

Back-office strings go through `$this->l()`. The update form uses the source `updatesChecker`. Add a language by placing `translations/{iso}.php`. Strings that do not go through `$this->l()`: **Saving the three questions…**, **The FAQ could not reach the shop.**, and the JavaScript fallbacks **The FAQ could not be saved.** and **Saved.** in `views/js/admin.js`. The storefront credit **Powered by MyFAQ for PrestaShop** is fixed in `product.tpl`.

Field descriptions are the `desc` strings in `renderSettingsForm()` and in `renderUpdateForm()`.

### 6.8 Extending

Override `views/templates/hook/product.tpl` from the theme at `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. Override `views/css/front.css` and `views/js/front.js` the same way. The template is not rendered when the product has no visible slot, so a theme override has nothing to print in that case.

## 7. Help

Module page: [https://mypresta.eu/](https://mypresta.eu/)

To ask about this module, sign in to the customer account on [mypresta.eu](https://mypresta.eu), open the contact form and choose the topic **Support for paid modules**. The form says that login is required for that topic. After you sign in, choose this module from the purchase history. This module is free, so name **MyFAQ Free** in the message when it is not in that history.
