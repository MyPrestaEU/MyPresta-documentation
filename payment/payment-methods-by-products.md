---
title: "Payment options by products - documentation and user manual"
description: "Use this manual to set payment methods per product, combine them in the cart, and fix a checkout list that still shows the wrong methods."
sidebar:
  label: "Payment options by products - documentation and user manual"
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Payment methods by products Module on MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/payment/payment-methods-by-products/)
>
> ---


## 1. Requirements

Check these points before you install the module.

- Use PrestaShop 1.7.0.0 or newer, including PrestaShop 8 and 9. The module accepts shop versions up to 9.99.99.
- Keep the PHP version required by that PrestaShop release. The installer does not add a separate PHP version check.
- Enable PHP cURL if you want the update check to call MyPresta.eu. When cURL is missing, the check tries to open the address with the server setting that allows remote reads. The payment rules themselves do not need cURL.
- No other PrestaShop module is required. The method list is built from the payment modules already installed in the shop. With none installed, the checkboxes are empty.
- Have at least one payment module installed and enabled if you want a method to appear at checkout.
- The module does not ask for an external account.

## 2. Installation

1. Open **Modules**, then **Module Manager**.
2. Click **Upload a module** and upload the ZIP file.
3. Click **Install** on **Payment options by products**.

Installation does the following:

- Adds **Payment - Product associations** under **Improve**, then **Payment**. If that Payment menu is missing, the entry is placed under **Improve**.
- Creates the table that stores one row per product, payment module, shop and country.
- Registers the checkout filter and the product-page tab.
- Copies the checkout override. PrestaShop must allow overrides. If they are off, the product tab and the checkout hook still run. The yellow warning on the configuration page says so.
- Does not clear the shop cache. Clear it under **Advanced Parameters**, then **Performance**, only if an old screen stays visible.
- Does not create any product rule. Checkout stays unchanged until you save a rule.

**Configure** in **Module Manager** opens the module settings. The menu entry **Payment - Product associations** opens the list of rules.

Uninstall:

- Removes the menu entry **Payment - Product associations**.
- Removes the checkout override and the registered hooks.
- Removes the stored module version used by the upgrade.
- Does not delete the saved product rules. A later install reads those rows again.
- Does not turn off the shop-wide update notices used by other MyPresta modules.
- Leaves the module folder in place until you delete it from **Module Manager** or from the server.

Turning the module off under **Module Manager** stops the checkout filter. The saved rules stay in the database.

## 3. Configuration and back-office work

A rule is a list of payment methods for one product, in the shop you are editing, for one delivery country or for every country.

Follow this process:

1. Open **Configure** and choose how several restricted products in one cart combine. Click **Save**. This step is optional. Until you save, the shop keeps every method allowed by at least one restricted product.
2. Open a product and use the **Payment methods** tab, or open **Improve**, **Payment**, **Payment - Product associations** and add a row.
3. Tick the methods that must stay available when that product is in the cart. Choose **All countries** or one country. Save.
4. At checkout, the shop reads the delivery address and hides the methods the rules do not allow.

A product with no saved rule does not remove payment methods. **Free order** stays available when it is the only method on a zero-total cart.

There is no order status in this module. The result is the payment list on the checkout page.

### 3.1 Module configuration

Open **Modules**, **Module Manager**, **Payment options by products**, **Configure**.

Two notes sit at the top. The first link opens **Payment - Product associations**. The second tells you to use the **Payment methods** tab on the product. Neither note saves a rule.

If overrides are disabled, a yellow warning says: “Overrides are disabled. Checkout filtering still runs through the payment options hook.” Leave overrides off if you only need PrestaShop 8 or 9. Turn them on under **Advanced Parameters**, **Performance**, only if you also need the older checkout override.

The **Settings** panel explains the country rule and the combine mode. The text above the select is the description of the module. It does not save anything by itself.

![Settings](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Configure**, panel **Settings**. The blue text explains countries. The select is **How to get available payment methods?**.

| Field | On a new install | What it does |
|---|---|---|
| **How to get available payment methods?** | **Show all payment methods from products**, until you save another choice | **Show the same payment methods available for all products in cart** keeps a method only when every restricted product in the cart allows it. **Show all payment methods from products** keeps a method when at least one restricted product allows it. A product without a saved restriction does not remove methods. |
| **Save** | — | Writes that choice only. It does not edit a product rule. The page reloads with the selected value. |

### 3.2 Payment - Product associations

Open **Improve**, **Payment**, **Payment - Product associations**. A note at the top repeats that the same rule is on the product, in the **Payment methods** tab.

The list shows one line per product in the current shop.

![Payment - Product associations](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Payment - Product associations** with no rows. The columns are **ID**, **Product**, **Payment** and **Country**. The plus icon is **Add new**.

| Column | What you see |
|---|---|
| **ID** | The row number. It is not the product ID. |
| **Product** | Product number and name. |
| **Payment** | Every method saved for that product, one under another. |
| **Country** | **All countries**, or the delivery country stored on the row. The column note says a selected country applies only when the delivery address is in that country, and **All countries** applies the rule to every delivery address. |

**Add new** opens a blank form. **Edit** opens the form for that product. **Delete** removes that one database row, not every method listed in the **Payment** column. **Delete selected** does the same for the ticked lines. To remove the whole rule, open **Edit**, untick every method is not allowed here: this form rejects an empty selection. Delete the remaining rows, or clear the rule from the product tab, where an empty selection is allowed.

Search and filters on the list are the standard back-office filters for these columns.

### 3.3 Association form

On **Add new** or **Edit**:

![Association form](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Add new**, filled for this picture and not saved. **ID Product** is 1. **Payment methods** and **Country** (**All countries**) are on this form.

| Field | On a new install | What it does |
|---|---|---|
| **ID Product** | Empty on a new row. Filled on edit. | Type the product number, or use **Search** to fill it. The help says to search by name, ID or reference. **Save** without a product shows “Product is required.” and does not write a rule. |
| **Payment methods** | Unticked on a new row. On edit, the methods already saved for this product are ticked. | Tick the methods that stay available at checkout when the cart contains this product and the delivery country matches the country below. The label shows the payment module name. |
| **Country** | **All countries** | If you select a country, the ticked methods apply only when the customer delivery address is in that country. **All countries** applies them to every delivery address. |
| **Save** | — | Replaces every method stored for this product in the current shop with the ticks and the country on this form. If no method is ticked, the page shows “There was a problem with form. No payment method selected” and the previous rows stay. |

One product has one country. Saving again replaces the previous methods for that product in this shop. Rules in another shop are left as they are. Switch the shop context before you edit that shop.

### 3.4 Product page

Open **Catalog**, **Products**, edit the product, then the **Payment methods** tab.

![Payment methods on the product](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Product Hummingbird printed t-shirt, tab **Payment methods**. **Country** and **Available payment methods** are here. The ticks are only on this picture. The product was not saved.

| Field | On a new install | What it does |
|---|---|---|
| **Country** | **All countries** when the product has no rule. Otherwise the country already saved. | If you select a country, the checked payment methods apply only when the customer delivery address is in that country. **All countries** applies them to every delivery address. |
| **Available payment methods** | Unticked when the product has no rule. Otherwise the methods already saved are ticked. | Checked methods stay available at checkout when the cart contains this product and the delivery country matches the country above. Leave all unchecked to remove the restriction for this product. |

Click **Save** on the product. PrestaShop confirms the product save. The payment rule is stored with that save, for the shop you are editing. An empty set of ticks deletes the rule for this product in this shop. That is different from the association form, which refuses to save when nothing is ticked.

The same data is what **Payment - Product associations** lists.

### 3.5 MyPresta updates

On **Configure**, under the settings, the **MyPresta Updates** panel checks for a newer file. It does not install it.

![MyPresta Updates](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**MyPresta Updates**, under the settings on **Configure**.

| Field | On a new install | What it does |
|---|---|---|
| **Check updates** | — | **Check now** asks MyPresta.eu whether a newer file exists. The line above the button shows that a new version is available, or that the module is up to date. It does not download or install the file. |
| **Updates notifications** | Enabled, until you save **Disable** | **Enable** shows a back-office warning when a newer version is published. **Disable** stops that automatic check. **Save** stores the choice and shows “Update settings saved.” |
| **Module page** | — | Opens the module page on MyPresta.eu, where the changelog is published. It does not save a setting. |
| **Save** | — | Stores **Updates notifications** only. |

## 4. Shop front

The module does not add a block, a page or a message on the product, the cart or the customer account. There is nothing to theme on those pages.

The customer sees the effect on the checkout payment step. Methods that the rules do not allow are missing from the list. Methods with no rule, and **Free order** when it is the only choice, stay.

The country is the country of the delivery address. Before a delivery address exists, only rules set to **All countries** apply. A rule for one country waits until the delivery address is in that country.

## 5. Problems

**The payment list did not change.** The product has no saved rule, or every product in the cart has no rule. Open the product, **Payment methods**, tick the methods, and save the product. A product with nothing ticked does not limit checkout.

**A method disappeared for one country only.** The rule country is not **All countries**, and the delivery address is in the selected country. Set **All countries** if the rule must apply to every delivery address.

**A method is still offered.** Another product in the cart allows it, and **How to get available payment methods?** is **Show all payment methods from products**. Switch to **Show the same payment methods available for all products in cart** if the method must be allowed by every restricted product. A product with no rule does not block it.

**Checkout shows “Overrides are disabled…” on the configuration page, and you are not sure filtering runs.** On PrestaShop 8 and 9 the filter still runs. The yellow text says the checkout hook does the filtering. Turn overrides on only if you also rely on the older override file.

**Save on Payment - Product associations shows “Product is required.”** The product field is empty. Search for the product or type its number, then click **Save** again.

**Save on Payment - Product associations shows “There was a problem with form. No payment method selected”.** No method is ticked. Tick at least one. The previous rule was not replaced. To remove a rule completely, use the product **Payment methods** tab and save with nothing ticked.

**Delete on the list removed only one method.** **Delete** removes the single row behind that line, while the **Payment** column prints every method. Open **Edit** and **Save** to rewrite the full set, or delete until the product disappears from the list.

**Free order is the only method and the rule does not list it.** A zero-total cart keeps **Free order**. The module does not remove that single method.

**The rule saved in one shop is missing in another.** Rules are stored per shop. Switch the shop in the multistore header and save the rule there.

## 6. For the developer

### 6.1 Overview

Main class `pobp`, version `1.4.0`, display name **Payment options by products**, author MyPresta.eu, tab `administration`. Compliancy `1.7.0.0` to `9.99.99`.

A row in `ps_pobp` is one allowed payment module for one product, one shop and one country (`id_country` `0` means every country). Checkout reads the cart products and the delivery address in `pobp::filterPaymentOptions()`. The hook `actionPresentPaymentOptions` unsets module keys that the filter removed. The override `PaymentOptionsFinder::find()` returns the same filter when the module is enabled, so older checkouts that call `find()` and not the hook get the same list. `pobp_innerjoin` truthy means the intersection of restricted products. Any other value, including a missing key, means the union. Products with no matching rows are ignored. The key `free_order` is never removed, and a payment list that contains only `free_order` is returned unchanged.

### 6.2 Files

| File | Role |
|---|---|
| `pobp.php` | Install, settings form, checkout filter, product-form tab. |
| `lib/updatesChecker.php` | Class `pobpUpdate`. Update check and the MyPresta Updates form. |
| `lib/searchTool/searchTool.php` | Product search on the association form. |
| `models/pob.php` | ObjectModel `pob` and `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Association list and form. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` delegates to `filterPaymentOptions()`. |
| `upgrade/upgrade-1.4.0.php` | Calls `ensureModuleComplements()` and stores `POBP_VERSION`. |
| `translations/pl.php` | Polish strings. |

There is no front controller and no front template.

### 6.3 Controllers

`AdminPobpController` extends `ModuleAdminController`. Tab class `AdminPobp`, parent `AdminParentPayment`, or `IMPROVE` when that parent is missing. Icon `credit_card`. Visible name **Payment - Product associations**.

The list groups with a subquery on `MIN(id_pobp)` per product and shop, so one line is shown. `processAdd()` and `processUpdate()` call `pob::replaceForProduct()`. An empty payment set or a missing product returns false and does not replace rows. Strings use `$this->module->l(..., 'AdminPobpController')`.

The module configuration is `getContent()` on `pobp`, not a separate controller.

### 6.4 Hooks

Registered in `registerHooks()`:

| Hook | Role |
|---|---|
| `actionPresentPaymentOptions` | Unsets payment modules removed by the filter. The array is edited in place. |
| `actionProductFormBuilderModifier` | Adds the `pobp` tab (country and payments) on the product form. |
| `actionAfterUpdateProductFormHandler` | Writes `form_data['pobp']` for the saved product. |
| `actionAfterCreateProductFormHandler` | Same write after a product is created. |

There is no custom `enable()` or `disable()`. Disabling the module unregisters the hooks. The override still loads and returns the parent list when `Module::isEnabled('pobp')` is false.

The first back-office load after an upload calls `ensureModuleComplements()` when `POBP_VERSION` differs from the file version. That refreshes the table, the hooks, the menu and the override.

### 6.5 Overrides

`override/classes/checkout/PaymentOptionsFinder.php` replaces `find()` only. It does not override `present()` or `findFree()`.

### 6.6 Database

| Table | Contents |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (module id), `id_shop`, `id_country`. `id_country` is added by `inconsistency()` when the column is missing. `0` means every country. |

Uninstall does not drop `ps_pobp`. Install uses `CREATE TABLE IF NOT EXISTS`, so a new install keeps old rows.

### 6.7 Keys and translations

| Key | When missing |
|---|---|
| `pobp_innerjoin` | Treated as off. Checkout uses the union of restricted products. |
| `POBP_VERSION` | The next back-office request runs `ensureModuleComplements()` and then stores the file version. |
| `mypresta_updates` | Treated as on. Set to `0` to stop the automatic update check. Shared with other MyPresta modules. |
| `update_pobp` | Last check timestamp. |
| `updatev_pobp` | Version string returned by the update server. |

Shop strings go through `$this->l()`. The updates panel uses the source `updatesChecker`. The association controller uses the source `AdminPobpController`. Polish is `translations/pl.php`. Add another language as `translations/{iso}.php` with the same key shape.

`key.php` in the module folder may set `$this->mkey`. If the file is missing, the update check sends `nlc`.

### 6.8 Extending

The front office does not render a module template, so the theme has nothing to override for this module. To change the checkout list, keep using the payment-option hook or the `PaymentOptionsFinder` override. To change the product tab, extend `hookActionProductFormBuilderModifier` and keep the `pobp` form keys, or the save hook will ignore the post.

## 7. Help

Module page: [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

To write about this module, log in to your customer account on mypresta.eu, open the contact form and choose **Support for paid modules**. The form says that login is required for that topic. After you log in, choose this module from your purchase history.
