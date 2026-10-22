---

title: "HTML Box Pro - merchant manual"

sidebar:

  label: "HTML Box Pro - merchant manual"

description: "Configuration of HTML boxes, hook positions and visibility rules for a shop that already has the module."

---

> ⚠️ **Notice:** This is the official documentation for the PrestaShop module.
> - 🛒 **You can find the full commercial specification, changelog, and purchase options on the official product page at MyPresta.eu:** [Buy HTML Box Pro Module on MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Official online documentation hub:** [Read interactive documentation on MyPresta.eu](https://mypresta.eu/docs/front-office/html-box-pro/)
>
> ---




The module technical name is `htmlboxpro`, version 4.0.5. In this language the module list shows **HTML Box Pro**.



## 1. Where the screens are



Modules, then Module Manager, then the module **HTML Box Pro**, then Configure. The page is the module configuration (`configure=htmlboxpro`).



The bar under the title has two buttons: **Settings** and **Boxes**. **Settings** writes `hbp_lasttab` = 1. **Boxes** writes `hbp_lasttab` = 2. When the key is missing, opening the page writes 1, so the first view is **Settings**.



The same bar has **Support**, which opens `https://mypresta.eu/contact.html` in a new tab, and **Updates**, which opens the module page at MyPresta in a new tab. The update check itself is the panel at the bottom of **Settings**, not that button.



There is no import screen and no block on the product edit page. A box appears on the storefront only after its hook is switched on and the block is **Active** and passes the filters below.



The first time `firsttime_hbp` is not 1, the page shows an information alert with the address `https://www.youtube.com/watch?v=uxzhSr5TrF4`. The close control posts `firsttime_hbp` = 1 and the alert is not shown again.



## 2. What install writes



Install runs the parent install, creates the tables, writes `hbp_notinyjs` = 1, and registers `actionAdminControllerSetMedia` plus every hook in the list further down.



It does not turn those hooks on. A hook prints boxes only when the configuration key `hbp_` plus the hook name equals 1. Until the checkbox on **Boxes** is saved, that key is missing and the hook returns nothing.



Opening configuration always runs the column check and adds any missing columns on `hbp_block`. Existing rows stay.



## 3. Settings



![Settings. Global module settings, with the update panel under the switches. The back office language on this screen is English.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)



The legend is **Global module settings**. The submit button is **Save**. Each switch is **On** (1) or **Off** (0).



| Label on the screen | Key | After install |

| --- | --- | --- |

| Use internal module's  rich text editor | `hbp_tiny` | key missing; the form matches **Off** |

| Prevent removing URLs from images | `hbp_forceurls` | key missing; the form matches **Off** |

| Don't load (duplicate) boxes with product page  ajax queries | `hbp_noajax` | key missing; the form matches **Off** |

| Do not load tinyMCE libraries | `hbp_notinyjs` | 1, so **On** |



The English source of the first label contains two spaces between "module's" and "rich". The third label contains two spaces between "page" and "ajax".



**Save** posts the four switch names. The module writes each posted value. `hbp_tiny` = 1 loads `views/js/tinymce16.inc.js` on this page. The same switch together with `hbp_forceurls` = 1 loads `views/js/tinymce16-force-urls.inc.js` instead. `hbp_tiny` = 0 loads the shop file `js/admin/tinymce.inc.js` and calls `tinySetup()`. `hbp_notinyjs` = 1 skips `js/tiny_mce/tinymce.min.js`. The page still includes `js/tiny_mce/tiny_mce.js`, `views/js/script.js` and `views/css/styles.css`.



`hbp_noajax` = 1 makes `generateHookContents` return nothing when the request has `ajax` = 1 and `action` = refresh. Other requests still print the boxes.



Under the switches the page appends the update panel from `checkforupdates`. The select **Updates notifications** has `-- select --`, **Enable** (1) and **Disable** (0). **Check now** is the button `submit_settings_updates_now`. **Save** in that panel is `submit_settings_updates` and writes only `mypresta_updates`.



The module constructor asks the remote server when `mypresta_updates` is not 0, or when the key is missing (`Configuration::get` is false), and `update_htmlboxpro` is older than 259200 seconds. The request runs when `allow_url_fopen` is enabled. The license value sent by this package is `nlc`. A warning is shown when the returned version is higher than 4.0.5 and the request is not ajax. **Disable** (0) still enters the timed branch; the warning condition is the one in that branch.



## 4. Boxes



![Boxes. Default positions on the left, empty state on the right. The back office language on this screen is English.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)



**Boxes** is two columns. The left column title is **Default positions**. Above the rows is a search field with the placeholder **Search hooks**. **Custom positions** is the panel under that list, in the same left column. The right column is the selected hook's blocks, or the empty state. The main column starts with the heading **No box selected** and the sentence **Please select blocks from list available on the left hand side. Or create new block.** Those two strings are not in the translation files, so every language shows this English source. An expanded hook with no blocks shows **No boxes in this position yet**. That string is not in the translation files either.



Each default hook is one row: a checkbox, the hook name, and **Add a new box**. The hook name links to `https://mypresta.eu/prestashop/hook/` plus the name in lower case. The checkbox posts `togglehook`. Checked writes `hbp_{hook}` = 1 and calls `registerHook` again. Unchecked posts no `status`, so the key becomes 0. Turning the hook off does not unregister it. The success text is **Visibility of hook changed properly**.



A block row has the internal name, or **no internal block name** when the name is empty. The buttons are **Edit this block**, **Duplicate this block** and **Remove this block**. The active switch success text is **Visibility of block changed properly**. Dragging a row posts `action=updateSlidesPosition` and `elements{hook}[]` and writes `hbp_block.position`. The page loads jQuery UI sortable for that tab. An empty hook shows **no blocks defined**. In a multishop context the row can show **for this shop**.



**Duplicate this block** copies the block and prefixes the name with `[duplicate] `. The success text is **Block duplicated properly**. **Remove this block** deletes that row through the object model. The success text is **Block removed properly**. The active switch on the list runs `smart_clean` on every language body and saves the block again, then sets `active` with an SQL update.



## 5. Add and edit a block



![Create new block, opened from displayHeader. The button Smarty templates manager sits under the editor. The back office language on this screen is English.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)



**Add a new box** opens the form **Create new block**. Edit opens **Edit existing block**. The button is **Save**. Add posts `submitAddNewHbox`. Edit posts `submitEditHbox`. Success texts are **Block added properly** and **Block saved properly**.



The body of each shop language is stored in `hbp_block_lang.body`. Before save the module runs `addslashes(smart_clean(...))` on that text. `smart_clean` collapses a repeated whitespace character to a single space and trims the string. The last replacement inside `prepare()` rewrites `\'`, `\\` and `\"`. Earlier lines in `prepare()` assign from the original string and do not change the returned value. The function does not remove HTML tags. The same clean runs again when the list switch changes **Active**.



The form is six sections. **Create new block** or **Edit existing block** holds the content fields. The products section title is **Products**. **Placement**, **Pages**, **Cart**, **Customers** and **Schedule** have no entry in the translation files, so the screen shows that English source.



| Section | What the fields do |

| --- | --- |

| Content | **Contents** (`hbp_body`, one value per language) and **Name** (`hbp_name`, 150 characters). The editor switch in `views/js/script.js` calls `tinyMCE.execCommand('mceToggleEditor')` for that language field. Under the editor the form shows **Smarty templates manager**. That button opens the template manager from `lib/smartyTemplatesManager/`. |

| Placement | **Shop** (`hbp_shop`). **Position** (`hbp_hook`, the hook chosen from the list). **Active** (`hbp_active`, default 0 in the table until saved as 1). **Only on secured (SSL) pages** (`hbp_bssl`). **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices** (`hbp_onmobile`, `hbp_ontablet`, `hbp_onpc`). A missing device value is saved as 1. |

| Pages | **Only on homepage** (`hbp_homeonly`). **Only on "Specials" page** (`hbp_specialsonly`). **Only on order confirmation page** (`hbp_oconfirmation`). Category, category plus subcategories, excluded categories, CMS category, CMS page, manufacturer page, exact URL, and search keywords. ID fields are comma-separated. The search box next to an ID field is the module search tool (`ajax=1` and `searchType`). |

| Products | Include or exclude product IDs, all product pages, specific price, out of stock, available to purchase, not available to purchase, in stock, min and max product value, product category, manufacturer, supplier, and feature value. |

| Cart | Show only when the cart contains, or does not contain, the listed category IDs or product IDs. |

| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) in `hbp_logged`. **Show for all groups** and the group checkboxes go to `hbp_cgroup` as a comma-separated list. **Hide for (users' groups)** is `hbp_hcgroup`. Geolocation and delivery-address country are in this section. |

| Schedule | Currency, date from / date to, weekdays, and time from / time to. |



Weekday checkboxes call the translation with the domain `forms` (`Sunday` through `Saturday`). The files `translations/*.php` store those words under the `htmlboxpro` domain, not `forms`. The screen shows the English source: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.



Geolocation text on the form points to `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` and the directory `/app/Resources/geoip/`. The same text says geolocation does not work on localhost. Selected countries are stored in `selected_geoip`, separated by semicolons. Delivery-address countries are stored in `delivery_address_selected`, separated by semicolons. That switch is a different control from geolocation.



## 6. When the storefront hides a block



`generateHookContents` loads blocks with `active` = 1 for the current language and the current hook, ordered by `position`. When multishop is on, the row `shop` must be the current shop id or 0. The template `html.tpl` then hides the body when any rule below fails. A switch left **Off** does not apply that rule.



| Switch on | The body is hidden when |

| --- | --- |

| Only on homepage | the controller is not `index` |

| Date range | today is before **date from** or after **date to** (`Y-m-d`) |

| Search keywords | the search query is not one of the comma-separated words |

| Only on secured (SSL) pages | `$_SERVER['HTTPS']` is not `on` |

| Logged only | the customer is not logged |

| Unlogged only | the customer is logged |

| Only on selected product pages | the current product id is not in the list. An empty first list entry keeps the block when a product id is present |

| Only if viewed product is out of stock | the stock value used by the template is greater than 0 |

| Only if viewed product is in stock | that stock value is not greater than 0 |

| Only if viewed product is NOT available to purchase | the product `oos` value does not match the deny rule in `html.tpl` |

| Only if viewed product is available to purchase | the product `oos` value does not match the allow rule in `html.tpl` |

| Specific price / no specific price | `hook_params.product` has no matching specific price |

| Only on selected Category pages | the controller is not the category controller or the category id is not selected |

| Category pages + subcategories | the category is not selected and is not a child according to `htmlboxpro::checkIfChildren` |

| CMS category / CMS page / manufacturer page | the current id is not in the selected list, or the controller is a different page |

| Only on selected url | `htmlboxpro::currentPageURL()` is not in the saved URL list. The comparison strips a `rand=` parameter |

| Only if viewed product is associated with category | the product categories do not intersect the list |

| Associated feature | no selected feature value is on the product |

| Only on order confirmation page | the controller is not `orderconfirmation` |

| Associated manufacturer or supplier | the product manufacturer or supplier is not selected |

| Cart category or cart product, include or exclude | the cart does not match the list. The PHP in `get_blocks` removes the block before the template for these four filters |

| Hide for (users' groups) | the customer group matches `hbp_hcgroup`. Groups 1 and 2 are compared with the default group. Any other group hides the block when that group is among the customer's groups |

| Device | `Context::getDevice()` is 1 and **Active on PC devices** is off; 2 and **Active on tablet devices** is off; 4 and **Active on mobile devices** is off |

| Min / max product value | the converted price is outside the saved amount, or the hook has no product |

| Weekdays | `hbp_daytype_on` is 1 and today's `%w` is not in the saved list |

| Currency | `hbp_currency_on` is 1 and the current currency id is not `hbp_currency` |

| Delivery address | the delivery country is not in `delivery_address_selected` |

| Geolocation | `hbp_geoip` is 1 and the resolved country is not in `selected_geoip` |

| Exclude selected products / all product pages / excluded categories | the current product or category is excluded |



The time filter runs in PHP, before the template. When `hbp_tim` is 1, `timfrom` and `timto` are compared with `date("H:i:s")` after the colons are removed. `timto` is passed through `ltrim` with `0` as the character mask, so leading zeros are stripped from that bound. A block outside the window is removed from the list.



## 7. Tokens in the box body



Replacement runs when the request has a `controller` and that controller is not `AdminModules`. A token that is not filled is replaced with an empty string at the end, except `{current_url}`.



| Token | Filled when |

| --- | --- |

| `{currency_iso}` | a currency is loaded; the value is the ISO code |

| `{id_lang}` | always in that branch; the value is the language ISO code, not the numeric id |

| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | the customer is logged |

| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | the controller is `product` or the hook receives `product` |

| `{product_price_tax_incl}`, `{product_price_tax_excl}` | product page; formatted with the module price helper |

| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | the same prices without the currency sign |

| `{id_category}`, `{name_category}`, `{path_array_category}` | a category id is in the request |

| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | a cart exists |

| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | the order-confirmation branch has an order id |

| `{current_url}` | every request, after the branch above. Scheme, host and request URI |

| `{HOOK:HookName}` | replaced with `Hook::exec` of that name, except when the name is the hook that is rendering this box, in which case the token becomes empty |

| `{HOOK:HookName:moduleName}` | replaced with `Hook::exec` limited to that module id |

| `{smartyTemplate:name}` | replaced with the template loaded by `loadSmartyTemplateFromManager` |



`{shop_name}` is set to the shop name and the cleanup pass then replaces `{shop_name}` with an empty string. The token does not remain as the shop name. `{id_product_attribute}` is empty when the attribute id is 0.



## 8. Custom positions



![Custom positions. Add support of new hook, Add new hook, and regenerate now. The back office language on this screen is English.](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)



**Custom positions** lists rows from `hbp_customhook`. The heading above the field is **Add support of new hook**. **Add new hook** reads **Hook name**. The saved name keeps only letters and digits (`preg_replace("/[^\da-z]/i", '')`). When the shop has no hook with that name, the module creates a `Hook` row with `live_edit` 1, `position` 1, the title equal to the name, and the description `Custom hook created with usage of HTML BOX PRO module`. It inserts `hbp_customhook` when the row is missing, rewrites `htmlboxpro.php`, and registers the hook.



When the hook already exists and the method `hook{Name}` is already in `htmlboxpro.php`, the page shows **Hook already exist in shop database** and does not add another row. When the hook exists and the method is missing, the module still rewrites the file and registers the hook.



**regenerate now!** posts `hbp_rh_submit`. The warning on the button is **use this option to rebuild module file if custom hooks doesnt want to work**. The rewrite replaces the part of `htmlboxpro.php` between the markers `//~~explode~~//` with one method per hook: `hook{Name}` returns `generateHookContents("{Name}", $params)`. The file must be writable. Failure text: **Main module file is not writable. Please check permissions (CHMOD) to /modules/htmlboxpro/htmlboxpro.php file**. Success text: **Main module file rebuilded properly. Module should support custom hooks now.**



**Remove hook** asks **Remove this custom hook?** It deletes the `hbp_customhook` row and, when the shop hook id exists, deletes that `Hook`, then rewrites the file.



The link **How to use custom hooks?** opens `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. On the add/edit form, a block attached to a custom hook shows **This block uses custom hook** and two snippets:



`{hook::exec('HookName') nofilter}`



`{hook h='HookName' product=$product}`



The second snippet is the one described for a product list.



## 9. Hooks registered at install



`actionAdminControllerSetMedia` adds the jQuery autocomplete plugin only when `configure` is `htmlboxpro`. It does not print a box.



These hooks each call `generateHookContents` with the hook name. Output still depends on `hbp_{hook}` = 1 and on an active block:



`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.



`displayHeader` does not attach a CSS or JS file on the storefront. It prints the boxes of that hook. The storefront has no module stylesheet of its own. The HTML, CSS and JavaScript are the body the merchant saved.



`registerHook` uses the parent method when `hook{Name}` already exists. Otherwise it inserts the `Hook` row if needed and inserts `hook_module`.



## 10. Tables and files



Install creates three tables if they are missing, engine InnoDB, charset `utf8_general_ci`. The shop prefix is in front of each name.



| Table | Columns created by the CREATE statement |

| --- | --- |

| `hbp_block` | `id` (auto increment, primary key), `position` default 1, `hook` varchar(50), `active` default 0, `logged` default 0, `name` varchar(150), index `indek1` |

| `hbp_customhook` | `id`, `hook` varchar(70) |

| `hbp_block_lang` | `id`, `id_lang`, `body` text. The CREATE statement has no primary key |



The model `models/hbox.php` maps `hbp_block`, with `body` as a multilingual field. The next configuration page adds the columns used by the filters: `bssl`, `shop` (default 1), the page and product flags, the selected-id text columns, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (altered to varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (default 1), price fields, `daytype`, `currency`, `geoip`, and the cart and delivery columns. `inconsistency()` also widens `hook` to varchar(255).



Other files used by the back office: `views/templates/hook/html.tpl` is the storefront body, `views/templates/admin/_configure/helpers/form/form.tpl` replaces the helper form for this module, `lib/searchTool/` is the ID search, `lib/smartyTemplatesManager/` serves `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` is the price display helper. `key.php` is optional and is not in this package. The update license inside `checkforupdates` is the literal `nlc`.



Configuration keys that are not columns: `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.



## 11. Disable, enable, uninstall



The class has no `disable()` and no `enable()`. Disabling uses the PrestaShop parent: the module stays installed, the tables and configuration stay, and the hooks are not executed. Enabling uses the parent enable.



The class has no `uninstall()`. Uninstall uses the parent method: the module is unregistered and the hook registrations PrestaShop stored for it are removed. The parent method does not drop `hbp_block`, `hbp_block_lang` or `hbp_customhook`. It does not delete the configuration keys listed above. It does not delete custom `Hook` rows created with **Add new hook**, and it does not restore `htmlboxpro.php` after **regenerate now!** or after adding a custom hook. A later install uses `CREATE TABLE IF NOT EXISTS`, so rows left in those tables remain.



## 12. Empty page under the tabs



The code accepts `selecttab` = 3 and can store `hbp_lasttab` = 3. The bar has no third button, and the form renderer has no page for 3. With that value the area under the bar is empty. **Settings** or **Boxes** writes 1 or 2 again.



## 13. Support



Module page: [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).

