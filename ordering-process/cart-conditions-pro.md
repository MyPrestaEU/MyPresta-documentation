---
title: "Cart Conditions - documentation and user manual"
sidebar:
  label: "Cart Conditions - documentation and user manual"
description: "Configuration and troubleshooting manual for shops that already use Cart Conditions."
---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy Cart conditions pro Module on MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Requirements

Cart Conditions runs inside the shop. It does not need another module and it does not need an account in an outside service.

- PrestaShop 1.7, 8 and 9. This manual was checked on PrestaShop 9.2.0.
- PHP version required by that PrestaShop. The module does not ask for an extra PHP extension.
- No other module is required.
- The rules read the current cart. The size of the catalog does not change the check.

## 2. Installation

1. Open **Modules**, then **Module Manager**.
2. Upload the module zip and install it. The module turns on as part of that install.
3. Open **Catalog**. Five entries appear, in this order, with these English names on every back-office language:

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

Installation does not clear the shop cache.

Uninstall removes those five menu entries and unhooks the module. It leaves the saved rules, the exclusion list, the availability setting and the update setting in the shop. Install the module again and the menu returns, and the old rules are still there.

## 3. Configuration and daily work

A customer fills the cart. On the cart page the shop lists every broken rule in a red alert. If the customer continues toward payment, the shop sends them back to the cart until every active rule is met. A customer listed under **Exclude customers from conditions** skips every rule and can check out.

You prepare the shop in this order:

1. Open **Configure** and decide who and which products the rules ignore.
2. Decide whether future availability dates may be mixed.
3. Open each list under **Catalog**, click **Add new**, fill the form, set **Active** to **On**, and click **Save**.
4. Place a test order with a normal customer and with an excluded customer.

A new rule form opens with **Active** set to **Off**. **Save** stores that row, and the cart ignores it until you set **Active** to **On**. The configuration page answers **Saved**. The rule lists use the usual back-office confirmation after **Save**.

The blue note on **Configure** says: "Management of this module is located under Price Rules menu." The five links in that note, and the entries under **Catalog**, are the screens that open the lists. There is no Price Rules entry for this module.

![Links on the configuration page](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Configuration page

Open **Modules**, **Module Manager**, find **Cart Conditions**, and click **Configure**.

#### Exclude customers and products

![Exclusion form](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Search a customer, click the result, and that person is added to the exclusion list. Remove a person from the same list before you save. Excluded customers skip every cart rule, including the availability check.

| Field | Starting value | What it does |
|---|---|---|
| **Exclude customers from conditions** | empty | Customers in this list can check out with no cart rule. **Save** stores the list. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** makes the rules skip the products and categories you select. **Do not exclude products** counts every product. |
| **Categories** | none checked | Checked categories are skipped when the switch above is **Exclude selected products**. |
| **Save** | - | Stores the customers, the switch, the products and the categories. The page shows **Saved**. |

The product search and the category tree sit on this same form. Select the products the same way you select a customer: search, then click the result.

#### Global conditions

![Availability comparison](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

This check looks only at products that are out of stock and whose **Availability date** is still in the future. Products that are in stock, products with an empty or past availability date, and excluded products are left out. One future date in the cart does not block the order. Two or more different values do.

| Field | Starting value | What it does |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** blocks the cart when those future dates do not match the comparison below. **Off** skips this check. PrestaShop can already allow an order for a product that will be available later. This switch decides whether different dates may sit in one cart. |
| **How to compare availability dates** | **Exact date** | **Exact date** blocks the order when the future dates are not the same day. **Same calendar month** allows different days in the same month and year, and blocks the order when the month or the year differs. 5 November 2026 and 20 November 2026 pass. 2 December 2026 does not. 5 November 2027 does not. |
| **Save** | - | Stores the switch and the comparison. The page shows **Saved**. This button does not create a Catalog rule. |

The cart message for **Exact date** is: "Availability dates of products in your cart are different. You cant place an order." The message for **Same calendar month** is: "Availability months of products in your cart are different. You cant place an order."

#### MyPresta updates

![Update check](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Check updates** / **Check now** | - | Asks MyPresta whether a newer file exists. **Module is up to date!** means this file is current. **New version available!** means a newer file is published. The button does not install it. |
| **Updates notifications** | **Disable** | **Enable** shows a back-office warning when a newer version is published. **Disable** stays quiet. **Save** stores the choice. |
| **Module page** | link | Opens the module page, where the change list is published. |
| **Save** | - | Stores the notification choice. |

### 3.2 Cart Conditions

Open **Catalog**, then **Cart Conditions**. These rules apply to every customer who is not excluded. There is no customer-group field on this list.

![Cart Conditions list](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

The list columns are **ID**, **Cart condition**, **Target type**, **Target item** and **Active**. An empty shop shows **No records found**. Use the filters above the columns to search. The row actions are edit, delete, and the **Active** icon. The bulk action is delete. **Add new** opens the form.

![New Cart Conditions rule](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Condition** | **Must have** | **Must have** demands the target. **Can't have** blocks the target. |
| **Target type** | **Category** | **Category** uses a category id. **Product** uses a product id. **More than defined number of products** uses a piece count of the whole cart. |
| **Target item** | empty | Category id, product id, or the piece count. The hint on the field says to enter an id or a number of products. |
| **Active** | **Off** | **On** makes the cart check this row. **Off** keeps the row and skips it. |
| **Save** | - | Stores the rule. |

What the customer sees:

- **Must have** and **Category**: "To place an order you must order product from category: ...".
- **Can't have** and **Category**: "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** and **Product**: "To place an order you must order product: ...".
- **Can't have** and **Product**: "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** and a piece count: "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** and a piece count: "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

The piece count is the sum of quantities in the cart, after excluded products are removed. **Must have** requires the cart to reach that number. **Can't have** blocks a cart above that number.

### 3.3 Cart Value Conditions

Open **Catalog**, then **Cart Value Conditions**. Each row is one customer group, one category and one minimum amount.

![Value conditions list](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Columns are **ID**, **Customer group**, **Cart condition**, **Target**, **Value** and **Active**. Empty list: **No records found**. Row actions: edit, delete, **Active** icon. Bulk action: delete. **Add new** opens the form.

![New value condition](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Customer Group** | first group in the shop (Visitor on a default shop) | Only shoppers in this group are checked. A logged-in customer is checked for every group they belong to. |
| **Condition** | **Must order from selected category** | This is the only choice. The rule runs when the cart already contains that category. |
| **Target item** | empty | Category id. |
| **Value** | empty | Minimum tax-included total of the products from that category. Type it in the shop default currency. The currency sign on the form is the shop currency. |
| **Active** | **Off** | **On** applies the row. **Off** stores it unused. |
| **Save** | - | Stores the rule. |

If the category is missing from the cart, this rule stays silent. If the category is present and its tax-included total is below **Value**, the cart shows: "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Open **Catalog**, then **Cart Quantity Conditions**.

![Quantity conditions list](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Columns are **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity** and **Active**. Empty list: **No records found**. Row actions: edit, delete, **Active** icon. Bulk action: delete.

![New quantity condition](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Customer Group** | first group in the shop | Only that group is checked. |
| **Condition** | **Must order at least X products from selected category** | Pick the limit. The full list is below. |
| **Target country** | first country in the shop | Used only for the two rules that say "from Y category". For every other condition the page hides this list. |
| **Target item** | empty | Category id, product id, manufacturer id, or attribute value, depending on **Condition**. The hint asks for the id of the target. For whole-cart conditions the page replaces this field with the word Cart and locks it. |
| **Quantity** | empty | The number X in the chosen condition. |
| **Accept only multiplied qty** | **Off** | **On** accepts only multiples of **Quantity**, for example 6, 12, 18, 24 when **Quantity** is 6. **Off** accepts any count that meets the rule. |
| **Active** | **Off** | **On** applies the row. |
| **Save** | - | Stores the rule. |

**Condition** choices, in the order on the form:

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

For the last two, set **Target country** and put the category id in **Target item**. For the two country rules that do not mention a category, the page hides **Target country**, so you cannot pick a country for them on this form. Use **Cart value by country conditions** when the limit is a money total, or the last two quantity rules when the limit is a piece count from one category.

**Search for attribute value** appears only for **Can't order more than X products with the same attribute value**. Search, click a value, and that value becomes **Target item**.

The cart text follows the choice. Category and manufacturer rules say "at least" or "can't order more than" and name the category or manufacturer. A product rule quotes the current quantity. A whole-cart rule says "you must order more than" or "you can't order more than" and quotes the current quantity. With **Accept only multiplied qty** on, the cart adds: "We accept only multiplied quantity...".

The product page can also show "You must order at least: ... quantity of this product" for **Must order at least X quantity of selected product**, when that product is the target and the visitor matches the group. That line is a notice. The block still happens in the cart.

### 3.5 Cart Associations Conditions

Open **Catalog**, then **Cart Associations Conditions**. A row links one item with another for one customer group. The rule starts only when the first item is already in the cart.

![Associations list](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Columns are **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)** and **Active**. Empty list: **No records found**. Row actions: edit, delete, **Active** icon. Bulk action: delete.

![New association](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Active** | **Off** | **On** applies the row. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** or **Associations between category and category** change what the two ids mean. |
| **For what customer group** | first group in the shop | Only that group is checked. |
| **Target item (1)** | empty | Product id or category id. The rule runs when the customer puts this object in the cart. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | See the choices below. |
| **Associated item (2)** | empty | The required or forbidden product id or category id. |
| **Save** | - | Stores the pair. |

**Condition** choices:

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Cart text: "If your cart has a product: ... you must order also product: ..." or the category equivalent.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Shown only for product and product. The cart check does not raise a message for this choice. Use another choice when the cart must block.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Cart text: "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. The page hides **Associated item (2)**. Cart text: "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Shown only for category and category. The page hides **Associated item (2)**.

The form also contains **Include subcategories of Target item (1)** and **Include subcategories of Associated item (2)**. The page hides both switches for every type. The rule uses the ids you type.

### 3.6 Cart value by country conditions

Open **Catalog**, then **Cart value by country conditions**. The rule uses the delivery address country.

![Country totals list](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Columns are **ID**, **Customer group**, **Condition**, **Country**, **Value** and **Active**. Empty list: **No records found**. Row actions: edit, delete, **Active** icon. Bulk action: delete.

![New country total](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Field | Starting value | What it does |
|---|---|---|
| **Customer Group** | first group in the shop | Only that group is checked. |
| **Target country** | first country in the shop | The rule runs when the delivery address is this country. The list is the shop country list. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** is the maximum. |
| **Condition tax** | **Tax included** | **Tax excluded** compares the total without tax. The cart message repeats the tax label you picked. |
| **Cart value type** | **Products + shipping** | **Products** leaves shipping out of the compared total. |
| **Value** | empty | The amount, in the shop default currency. |
| **Active** | **Off** | **On** applies the row. |
| **Save** | - | Stores the rule. |

Below the minimum, the cart shows: "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Above the maximum: "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Storefront

The customer does not open a separate page. The module speaks on the product page and on the cart.

On the product page, and only for an active **Must order at least X quantity of selected product** rule aimed at that product, the theme can show: "You must order at least: ... quantity of this product". The theme has to print the product-actions area. This manual does not include a storefront picture, because that line was not confirmed on the test theme.

On the cart, every broken rule is a line in one red alert. Names of required or forbidden products and categories are links. If the customer opens payment while a rule is broken, the shop returns them to the cart and shows the same alert.

A customer on the exclusion list sees none of these messages and is not sent back.

There is no front-office address to copy. There is no form for the customer to accept or reject a rule.

## 5. Problems

**The five entries are missing under Catalog.** The module is not installed, or it was uninstalled. Install it again from **Module Manager**. Old rules come back with it.

**The blue note says Price Rules, and Price Rules has no Cart Conditions entry.** Use the five links in the note, or **Catalog**. The menu parent is Catalog.

**A saved rule does nothing.** **Active** is **Off**, the customer is on the exclusion list, or the customer is not in the selected group. A visitor who is not logged in is checked as the Visitor group. Open the row, set **Active** to **On**, and test with a customer in that group.

**A value rule stays silent.** The category is not in the cart. Add a product from that category. The compared total is tax included.

**Two country quantity rules ignore the country.** **Target country** is hidden unless **Condition** is one of the two "from Y category" lines. Pick one of those, or use **Cart value by country conditions** for a money limit.

**Same calendar month still blocks November and November.** The years differ. 5 November 2026 and 5 November 2027 are different. The product must also be out of stock with a future **Availability date**. In-stock products are not compared.

**Check now shows nothing, or the warning never appears.** The shop server cannot open the remote MyPresta address. **Check now** only reports a version. It does not download or install the file. Open **Module page** and take the new file from there.

**The cart alert is missing, and payment still returns to the cart.** The theme does not print the cart block. The return to the cart still runs. Override the cart template in the theme, or confirm the theme prints the shopping-cart hook.

**Uninstall removed the menu and a later install shows the old rules.** That is the uninstall behaviour. Delete the rows in the lists before you uninstall if you want an empty module afterwards.

## 6. For developers

### 6.1 Overview

Main class `cartcon`, version 2.1.9, list name **Cart Conditions**, author MyPresta.eu, tab `advertising_marketing`. `cartconPrestashopNewCompatibility` extends `cartcon` for price formatting and is not the instantiated module class. `psversion()` maps a major version of 8 or higher onto the 1.7 branch for a few back-office markup choices. There is no `enable()` or `disable()` override.

`getRestrictions()` reads active rows for the current shop, skips customers listed in `CARTCON_CUSTOMERS`, and fills `errors_cartcon`. `hookDisplayShoppingCart` prints that list. `hookDisplayPaymentTop` redirects to the cart with `cartcon=show` when the list is not empty. `hookDisplayProductActions` prints a minimum quantity only for `cartcon_quantity.c_type = 2` on that product id.

### 6.2 Files

- `cartcon.php` - install, configuration forms, restriction checks, hooks.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - must-have and can't-have rules.
- `controllers/admin/AdminCartValueConditionController.php` - category minimum amount.
- `controllers/admin/AdminCartQuantityConditionController.php` - quantity rules.
- `controllers/admin/AdminCartAssociationsConditionController.php` - pairs.
- `controllers/admin/AdminCartCountryConditionController.php` - country totals.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - object models.
- `views/templates/front/displayShoppingCart.tpl` - red alert.
- `views/templates/front/productActions.tpl` - product-page minimum.
- `views/templates/admin/script.tpl` - quantity form behaviour.
- `views/templates/admin/search-attribute-value.tpl` - attribute search, shown for quantity type 7.
- `lib/searchTool/searchTool.php` - `initTool()` injects scripts only. It does not render a panel.

### 6.3 Controllers

All five admin controllers extend `ModuleAdminController`. `createMenu()` inserts a tab per language with the English name, parent `AdminCatalog` (`Sell > Catalog` on PrestaShop 9). Class names: `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. There is no front controller. The only front query flag read by the module is `cartcon=show`, added by the payment redirect.

`script.tpl` disables **Target item** and sets its value to the word `Cart` for quantity types 4, 5, 8, 9, 15 and 16. The country select is shown for types 8 and 9 and then hidden by the next block unless the type is 10 or 11, so the visible result is a country field only for types 10 and 11. Type 7 shows `.searchAttributeValue`.

Associations script hides `.subcatt` and `.subcata` for every type. Condition id 4 is enabled only for category-category (type 3). Condition id 5 is shown only for product-product (type 1). Condition ids 3, 4 and 5 hide **Associated item (2)**. `getRestrictions()` compares association `c_value` 1, 2, 3 and 4. It does not compare `c_value` 5.

### 6.4 Hooks

- `displayHeader` - front CSS and JS, and the ajax call `getCartConditions`.
- `displayShoppingCart` - alert list.
- `displayProductActions` - minimum quantity notice.
- `displayPaymentTop` - redirect to the cart when any error exists.
- `actionAdminControllerSetMedia` - admin assets.

The module does not register its own hooks.

### 6.5 Overrides

None. No class or controller override.

### 6.6 Database

Prefix tables. `inconsistency()` / `maybeUpdateDatabase()` add missing columns during `installdb()` and from the updates button. They do not run on every configuration page load. Uninstall does not drop tables.

| Table | Contents |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` default 1, `id_shop` added later. No customer group. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` default 0, `c_group`, `id_shop`. `c_only_if_in_cart` is not on the form. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` default 0, `c_group`, `id_shop`, `multiply` default 0, `c_country` default 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` default 0, `subcata` default 0. Category matching reads `subcatt` and `subcata` when they are 1. The form hides both switches. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` default 1, `c_cartValueType` default 1. |

New HelperForm screens submit **Active** as 0 because the Off radio is checked. The column default 1 applies only when the column is omitted.

### 6.7 Keys and translations

| Key | When missing |
|---|---|
| `CARTCON_CUSTOMERS` | empty. Comma-separated customer ids. Those customers return from `getRestrictions()` immediately. |
| `ccon_visibility_rule` | `0` means do not exclude. `1` means skip selected products and categories. |
| `ccon_visibility_products` | empty product id list. |
| `ccon_visibility_cat` | empty category id list. |
| `CARTCON_FUTURE` | not set, treated as off. `1` runs the availability comparison. |
| `CARTCON_FUTURE_MODE` | missing casts to `0` (**Exact date**). `1` groups by `date('Y-m')`. Compared products need `stock_quantity <= 0` and `available_date` strictly in the future. More than one distinct key blocks checkout. |
| `mypresta_updates` | `0` disables the automatic warning. `1` enables it. |
| `update_cartcon` | last check timestamp. |
| `updatev_cartcon` | version string from the last check. |

The check uses `allow_url_fopen` and `file_get_contents` against `dev.mypresta.eu`. Shop translation files are `translations/{iso}.php`. Menu labels are written in English for every language inside `createMenu()` and do not go through a translation file. Field descriptions live in the controller `l()` calls and in `cartcon.php` HelperForm `desc` strings. `getCustomerGroups()` maps cart `id_customer` 0 to group id 1. The guest branch runs only when `id_customer` is not set.

### 6.8 Extending

Override `views/templates/front/displayShoppingCart.tpl` and `views/templates/front/productActions.tpl` from the theme. If the theme never calls `displayShoppingCart` or `displayProductActions`, there is nothing to override and the customer will not see the alert. The payment redirect still runs.

## 7. Help

Module page: [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

To write about this module, log in to the customer account on mypresta.eu, open the contact form and choose **Support for paid modules**. The form says that login is required for paid modules. After login, pick this module from the purchase history.
