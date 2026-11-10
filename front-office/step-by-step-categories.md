---
title: Step by Step - documentation and user manual
sidebar:
  label: Step by Step - documentation and user manual
description: Configuration and troubleshooting manual for shops that already have the Step by Step category filter.
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Step by step - categories Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/step-by-step-categories/)
>
> ---


## 1. Requirements

The module runs inside PrestaShop. It does not need another module and it does not need an external account.

- PrestaShop 1.6.0.0 through PrestaShop 9, including later 8.x and 9.x releases. The module allows any PrestaShop version from 1.6.0.0 upward.
- PHP is the version required by that PrestaShop release. The update check uses cURL when PHP provides it, and `file_get_contents` when it does not. You do not install an extra PHP extension for the dropdowns.
- No other module is required.
- On a multistore, each block can belong to one shop or to all shops.

## 2. Installation

1. In the back office open **Modules**, then **Module Manager**.
2. Upload the module zip and click **Install**.
3. Open **Configure** on **Step By Step - categories tree**. The page shows **Blocks**, **Settings** and **Updates**. **Blocks** is the list of dropdown sets. The first visit creates the hidden page that holds that list. It does not appear as its own item in the left menu.
4. Installation does not run a separate cache clear. If the storefront still shows the previous layout after an update, clear the shop cache in **Advanced Parameters**, **Performance**.

Uninstall removes that hidden page. The blocks, their titles, their labels and the two global switches stay in the database. Install the module again and the same blocks are available. Open **Configure** once so the list page is registered again.

There is no separate enable or disable action beyond the normal module switch in **Module Manager**. Turning the module off stops the dropdowns on the storefront and leaves the saved blocks in place.

## 3. Configuration and daily work

You create a block, choose how deep the category tree goes, and choose where the shop shows it. The customer then picks a category. The next dropdown loads the children of that category. **ok** opens the selected category, or a product when the product list is on.

### 3.1 Module configuration page

Open **Modules**, **Module Manager**, **Step By Step - categories tree**, **Configure**.

The pictures in this chapter are the English back office.

![Settings](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

The top bar has **Blocks**, **Settings** and **Updates**. **Blocks** leaves this page and opens the block list. **Settings** is the default tab. The line under the bar says that these options apply to every block and that blocks are edited from **Blocks**.

| Field | At the start | What it does |
|---|---|---|
| **Reset search fields** | No | Yes clears the dropdowns after a search. No keeps the categories the visitor selected. The visitor's browser stores that choice for 30 minutes. |
| **Include Select2 library** | No | Yes loads the extra script and stylesheet used by **Search inside dropdown** on a block. No leaves the lists as normal dropdowns. |

Click **Save**. The page shows **Settings saved.**

![Updates](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** is the **MyPresta updates** form.

| Field | At the start | What it does |
|---|---|---|
| **Manual check** | a **Check now** button | Asks MyPresta whether a newer release exists. **New version available!** links to the changelog. **Module is up to date!** means this install matches the published release. The button does not upload a zip. |
| **Automatic notifications** | Enabled | Enabled repeats that check about every 3 days while you work in the back office. Disabled skips it. |
| **Product page** | the module page link | Opens the Step by Step page on mypresta.eu. |

**Save** shows **Update settings saved.** Upload a new zip from **Module Manager** when a newer release is listed.

### 3.2 Blocks list

Open **Blocks**. The line under the bar says that each block is one set of dropdowns.

![Blocks](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

Columns:

| Field | At the start | What it does |
|---|---|---|
| **ID** | assigned on save | The number of the block. You use it only to tell rows apart. |
| **Title** | Block and the ID, until you type a title | The heading for the current back-office language. |
| **Depth** | 3 on a new block | How many dropdowns the block renders. |
| **Root category** | the shop home category on a new block | The parent of the first dropdown, shown as the category ID and name. |
| **Hook** | Top on a new block | Where the storefront renders the block. |
| **Active** | Yes | The icon turns the block on or off. Off keeps the row and hides the dropdowns. |
| **Position** | next free position | Drag the row to change the order of blocks that share a hook. |

Row actions are **Edit** and **Delete**. **Bulk actions** has **Enable selection**, **Disable selection** and **Delete selected**. The delete confirmation asks **Delete selected blocks?**

**Add new** opens an empty form. A new block is active, depth 3, root set to the home category, sort by ID ascending, product counter off, submit button after the last select box, products off, auto submit off, search inside dropdown off, label inside the select box, hook Top, and the current shop. Save it. The form opens again so you can fill the labels. The labels are not on the form until the block exists.

The list shows blocks for the shop you are in, plus blocks set to **All shops**.

### 3.3 Block form

Open a row with **Edit**, or use **Add new** and then the edit screen that follows the first save.

![Block form, top](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Block form, labels and position](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Field | At the start | What it does |
|---|---|---|
| **Block title** | empty | Heading shown above the dropdowns. One field per shop language. |
| **Depth** | 3 | How many dropdowns the block renders. Save the block, then edit it again to fill a label for each level. The form shows at most 30 label fields. |
| **Root category** | home category | The first dropdown lists the children of this category. |
| **Sort method** | By ID | By ID, By name, or By position. Position is the order set on the category in the catalog. |
| **Sort direction** | Ascending | Ascending or Descending. |
| **Products counter** | No | Yes displays the number of products in a category in brackets after its name. |
| **Submit button** | After last select box | After each select box shows **ok** for the step the customer is on. After last select box shows one **ok** for the whole set. |
| **Include products** | No | Yes displays a list of products from the last category selected in the dropdowns. |
| **Auto submit** | No | Yes submits the form once the last available category is selected. The shop opens that category. This runs when **Include products** is off. If the chosen category has no children, the shop also opens that category. |
| **Search inside dropdown** | No | Yes enables search inside the dropdowns. **Include Select2 library** must also be on in **Settings**. |
| **Exclude categories** | empty | Category IDs that should not appear in the dropdowns. Separate them with commas, for example 1,2,3,4,5,6. The search control next to the field finds a category and appends its ID. |
| **Show on category pages** | empty | Empty shows this block on every page where its hook is displayed. Category IDs, separated by commas, show it only on those category pages. |
| **Label position** | Inside select box | Inside select box uses the label as the first option. Outside select box prints the label above the field. |
| **Label 1**, **Label 2**, and so on | empty | One field per step, per language. They appear only after the block has been saved. Change **Depth** and save if you need more or fewer of them. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home, or displaySbs. |
| **Position top settings** | Blocks | Blocks stacks the dropdowns. Wide horizontal bar lays them in a row. The wide bar is used on Top and displaySearch. The other positions stay stacked. On the wide bar, **ok** sits after the last dropdown and wraps under the row when there is no room. |
| **Shop** | the shop you are editing | One shop, or **All shops**. **All shops** keeps the block available in every shop. |
| **Active** | Yes | No hides the block on the storefront. |

Click **Save**. PrestaShop shows its standard confirmation. Deleting a block also deletes its title, its wide-bar choice and its step labels.

To show a block in a theme file that has no built-in hook, put the displaySbs hook in that template and set **Module position** to displaySbs. Transplant the other positions under **Design**, **Positions**, if the theme does not already display them.

## 4. Storefront

The customer sees the block title and the dropdowns.

1. The first dropdown lists the children of the root category. Later dropdowns stay disabled until the previous step has a category.
2. The customer picks a category. A spinner covers the block. The next dropdown fills with the child categories. The spinner disappears when the list is ready, and also when the request fails.
3. Excluded category IDs are missing from those lists.
4. With **Submit button** set to after each select box, **ok** is shown for the current step. With after last select box, one **ok** is shown for the set.
5. **ok** opens the selected category.
6. With **Include products** on, the last step adds a product dropdown. The first option is **- Select Product -**. **ok** then uses the chosen product.
7. With **Auto submit** on and **Include products** off, choosing the last category opens that category without **ok**. The same redirect happens when the chosen category has no children.
8. With **Reset search fields** off, a later visit can show the same categories selected. The browser keeps them for 30 minutes. With the option on, the lists start empty.
9. With **Search inside dropdown** and **Include Select2 library** both on, the customer can type inside the list.

On the left and right column the steps are stacked and the title is uppercase, in the Classic column style. On the wide bar the steps sit in a row. On a narrow screen the wide bar stacks. Colors, borders and the **ok** button follow the theme, including Hummingbird and Classic on PrestaShop 9.

A block with **Show on category pages** filled in is absent on other pages. An inactive block is absent. A block for another shop is absent.

## 5. Problems

**The block is missing on the storefront.** Open the block and check **Active**, **Module position** and **Shop**. Empty **Show on category pages** shows it on every page of that hook. A filled list shows it only on those category pages. In **Design**, **Positions**, confirm the hook is on the pages you expect. For a custom spot, the template must call displaySbs and the block must use that position.

**The next dropdown never fills, or the spinner stays.** Clear the shop cache so the storefront uses the current stylesheet and script. The spinner is supposed to disappear when the request finishes, including when the reply cannot be applied. If the shop still shows an old gif loader, the previous CSS is cached.

**Search inside the dropdown does nothing.** Turn on **Include Select2 library** in **Settings** and **Search inside dropdown** on the block. Save both. Clear the cache.

**Labels are missing on a new block.** Save the block once. Open it again. **Label 1** and the rest appear only after the block exists, and only up to the saved **Depth**.

**A category you wanted is not in the list.** Remove its ID from **Exclude categories**. Check that it is a child of the selected parent and that it is active in the catalog.

**The wide bar still stacks the fields.** **Wide horizontal bar** applies on Top and displaySearch. Left, right, home, TopColumn and displaySbs stay stacked. On a phone the wide bar stacks on purpose.

**After an update the Blocks page is missing.** Open **Configure** once. That visit registers the page. Do not uninstall if you want to keep using the existing rows without a gap. Uninstall removes the page and leaves the rows.

**The old configure screen has no delete icon.** That screen is a previous release. Install the current zip from your customer account. In the current release you delete a block from the **Blocks** list, with **Delete** on the row or **Delete selected**.

## 6. For developers

### 6.1 Overview

Technical name `stepbystep`, class `Stepbystep`, version 1.9.0, author MyPresta.eu, tab `front_office_features`. The back-office name is **Step By Step - categories tree**.

`AdminStepbystepBlocksController` writes rows in `sbs_block` and writes titles, labels and the wide-bar flag to `Configuration`. Storefront hooks read active rows for the current shop or `id_shop = 0`. `controllers/front/tree.php` returns the script that fills the next dropdown.

### 6.2 Files

| File | Role |
|---|---|
| `stepbystep.php` | Install, hooks, settings form, dropdown HTML, storefront script. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Block list and block form. |
| `models/SbsBlock.php` | Object model for `sbs_block`. |
| `controllers/front/tree.php` | Front controller that returns the next-level script. |
| `views/templates/hook/front.tpl` | Storefront markup for every hook. |
| `views/templates/hook/header.tpl` | Prints the inline script. |
| `views/templates/admin/configure.tpl` | Blocks, Settings, Updates bar. |
| `css/sbs-front.css` | Storefront layout, theme variables, spinner. |
| `js/advajax.js` | Request used by the dropdowns. |
| `lib/updatesChecker.php` | Update check. Class `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Category ID search on the block form. Class `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Class `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Back-office bar. |

`tree.php` in the module root is the older copy of the front controller. The shop link uses `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` and `displaySearch.tpl` are not rendered. `css/sbs-block.css` and `css/sbs-top.css` are not enqueued.

### 6.3 Controllers

`AdminStepbystepBlocksController` extends `ModuleAdminController`. `class_name` is `AdminStepbystepBlocks`. `id_parent` is `-1`, so it is hidden from the menu. The list identifier is `id`. Position drag calls `ajaxProcessUpdatePositions`. The list filter is `id_shop` of the context shop or `0`.

`stepbysteptreeModuleFrontController` is the module front controller `tree`. `initContent` sets `ajax` and does not call `parent::initContent`. It reads `sbs_block`, `sbs_pid`, `sbs_lvl`, and on confirm `sbs_blockid` and `sbs_cidlink`. The body is JavaScript. A missing block ends the response.

### 6.4 Hooks

Registered hooks: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. On PrestaShop 1.6 and newer, also `displaytopColumn`.

| Hook | Block position value | Layout |
|---|---|---|
| `displayTop` | 1 | top, wide bar when `sbs_top_type{id}` is 1 |
| `displayLeftColumn` | 2 | stacked |
| `displayRightColumn` | 3 | stacked |
| `displayHome` | 4 | stacked |
| `displaytopColumn` | 5 | stacked |
| `displaySearch` | 6 | top, wide bar when `sbs_top_type{id}` is 1 |
| `displaySbs` | 7 | stacked |

`displayHeader` loads `js/advajax.js` and `css/sbs-front.css`. When `SBS_SELECT2` is 1 it also loads Select2. There is no `enable()` or `disable()` override.

### 6.5 Overrides

The module does not override a PrestaShop class or controller.

### 6.6 Database

| Table | Contents |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

The prefix follows the shop. Uninstall does not drop the table. `inconsistency()` adds any missing column from that list when the module configuration or the block list is opened. `on_cat_only` is kept and is not shown on the form. The storefront uses `id_categories` instead.

### 6.7 Configuration keys and translations

| Key | When missing |
|---|---|
| `SBS_RESET` | Treated as 0. Choices are remembered for 30 minutes in cookies `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Treated as 0. Select2 is not loaded. |
| `sbs_title{id}` | Multilingual block title. |
| `{id}sbs_lbl_{n}` | Multilingual label for step `n`, from 1 to the depth, capped at 30. |
| `sbs_top_type{id}` | 0 stacked, 1 wide bar. |

Install also writes `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` and `sbs_root`. The block form does not read those keys. New blocks use the defaults in `prepareObjectDefaults()`.

Translations live in `translations/{iso}.php`. Strings in the block controller use the source `AdminStepbystepBlocksController`. The confirm button text is the module string `ok`. The product placeholder is `- Select Product -`.

### 6.8 Extending

Override `views/templates/hook/front.tpl` in the theme under `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Override `css/sbs-front.css` the same way if the theme should replace the layout. The wide-bar button position is the flex order in that stylesheet: the visible `.sbs__actions` is ordered after the dropdowns and wraps with the row.

## 7. Help

Module page: [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

To write about this module, sign in to your customer account on [mypresta.eu](https://mypresta.eu), open the contact form, and choose **Support for paid modules**. That topic says that login is required. After you sign in, choose this module from the purchase history.
