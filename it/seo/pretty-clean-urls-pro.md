---
title: "URL Amichevoli e Pulite - istruzioni per il venditore"
description: "Istruzioni di configurazione e risoluzione dei problemi per chi ha già questo modulo."
sidebar:
  label: "URL Amichevoli e Pulite - istruzioni per il venditore"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Pretty / Clean URLs PRO su MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/pretty-clean-urls-pro/)
>
> ---


Nome tecnico `purls`, versione 3.0.0, nome nel pannello: URL Amichevoli e Pulite.

## Dove sono le schermate

Apri **Moduli > Gestione moduli** e configura **URL Amichevoli e Pulite**. La pagina è il modulo **Impostazioni**, sotto il pannello **Possibili collisioni**, sotto il pannello **Aggiornamenti MyPresta**. Il modulo non aggiunge una voce di menu propria, una schermata di importazione né un blocco sulla scheda prodotto.

Le etichette vengono da `translations/it.php`. La frase «on documentation page of this module» non è nei file di traduzione, quindi la schermata mostra il testo sorgente inglese.

## Cosa scrive l'apertura della configurazione

`install()` non scrive questi valori. All'apertura della configurazione, `getContent()` scrive una rotta quando il valore corrente manca o è vuoto:

| Chiave | Valore scritto |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` e `PS_ROUTE_category_rule` sono chiavi di PrestaShop. Se sono vuote, aprire questa pagina le sostituisce con i valori della tabella. Con più di una lingua, le quattro chiavi `PURLS_ROUTE_*` sono salvate per lingua. Con una lingua, come stringa singola.

## Impostazioni

![La schermata è in inglese. In queste istruzioni: Impostazioni.](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Schermata in inglese, dopo il salvataggio. ID prodotto: ID of product + ID of attribute. Hash disattivato. Categorie, produttori, fornitori e CMS attivati. 301 attivato. In queste istruzioni: Impostazioni.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

La legenda è **Impostazioni**. La descrizione è **Seleziona da quali tipi di URL vuoi rimuovere l'ID**. Il pulsante è **Salva** (`submitCategoryFeatured`).

`install()` non crea queste chiavi. Fino al primo salvataggio, `Configuration::get` restituisce false. La rimozione gira solo per i valori sotto, quindi una chiave assente lascia l'ID nell'URL. Nel modulo, false coincide con l'opzione `0` (**Non rimuovere i numeri ID** / **Disabilitato**).

| Etichetta | Chiave | Valori |
| --- | --- | --- |
| ID Prodotto | `purls_products` | `0` Non rimuovere i numeri ID. `1` ID del prodotto + ID dell'attributo. `2` Solo ID dell'attributo. `3` Solo ID del prodotto. |
| Hashcode con attributi | `purls_product_hash` | `1` Abilitato, `0` Disabilitato. |
| Categorie | `purls_categories` | `1` Abilitato toglie l'ID dai link delle categorie. `0` Disabilitato. |
| Produttori | `purls_manufacturers` | `1` Abilitato toglie l'ID dai link dei produttori. `0` Disabilitato. |
| Fornitori | `purls_suppliers` | `1` Abilitato toglie l'ID dai link dei fornitori. `0` Disabilitato. |
| CMS | `purls_cms` | `1` Abilitato toglie l'ID dai link CMS. `0` Disabilitato. |
| Reindirizzamento 301 da vecchi URL | `purls_301` | Radio. `1` Abilitato, `0` Disabilitato. Testo: Attiva il reindirizzamento automatico da vecchi URL (con ID) a nuovi URL (senza ID). |

L'aiuto di **ID Prodotto** chiede di modificare lo schema, nel file chiamato «Percorso ai prodotti»:

- **ID del prodotto + ID dell'attributo**: togli `{id}` e `{id_product_attribute}`.
- **Solo ID dell'attributo**: togli `{id_product_attribute}`.
- **Solo ID del prodotto**: togli `{id}` e come ID dell'attributo usa `{id_product_attribute:-}`.

Lo stesso aiuto apre `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. Il testo del link è la sorgente inglese «on documentation page of this module». La frase prima del link nel file italiano è **I dettagli sulla configurazione dello "schema degli URL" li puoi trovare**.

**Hashcode con attributi**: Abilitato taglia l'URL del prodotto su `#`. Disabilitato, e solo se ID Prodotto è `1` o `2`, tiene un hash come `#/size-s/color-white`. Il testo dice che l'opzione funziona quando l'ID dell'attributo del prodotto viene rimosso dall'URL. Nel codice, `Link::getProductLink()` tiene l'hash solo se `purls_product_hash` è `0` e `purls_products` è `1` o `2`. Con il valore `3` lo stesso metodo taglia sempre l'URL su `#`. Il valore `0` di ID Prodotto chiama il metodo padre di PrestaShop.

| Etichetta | Chiave | Campo lingua | Parole nel modulo |
| --- | --- | --- | --- |
| Regola prodotto | `PS_ROUTE_product_rule` | No | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Regola categoria | `PS_ROUTE_category_rule` | No | `{id}`, `{rewrite}`, `{parent_categories}` |
| Regola fornitore | `PURLS_ROUTE_supplier_rule` | Sì | `{id}`, `{rewrite}` |
| Regola marchio | `PURLS_ROUTE_manufacturer_rule` | Sì | `{id}`, `{rewrite}` |
| Regola pagina CMS | `PURLS_ROUTE_cms_rule` | Sì | `{categories:/}`, `{id}`, `{rewrite}` |
| Regola pagina categoria CMS | `PURLS_ROUTE_cms_category_rule` | Sì | `{id}`, `{rewrite}` |

Su regola prodotto e categoria compare: Questo campo è anche configurabile nella sezione "schema degli URL" in: Parametri negozio > Traffico & SEO.

Su fornitore, marchio, pagina CMS e categoria CMS, con l'interruttore a `0`, compare **Per modificare questo campo è necessario attivare l'opzione per rimuovere l'ID da questo tipo di URL**. Il campo resta modificabile. Dispatcher e `Link` usano la rotta del modulo solo con l'interruttore a `1`.

### Schemi dei campi rotta

Sono i modelli della pagina degli schemi. In **Regola prodotto** va una riga del gruppo che corrisponde a **ID prodotto**. `{category}` è il rewrite della categoria predefinita. `{categories}` sono i rewrite delle categorie padre uniti da `/` (`Link::getProductLink()`). `{rewrite}` è `link_rewrite`. `{id}` è l'id del prodotto. `{id_product_attribute:-}` è l'id della combinazione, con `-` davanti quando quell'id è presente. Un campo prodotto vuoto riceve `{category:/}{rewrite}.html` anche se l'ID prodotto è `2` o `3`, quindi per quelle due opzioni nel campo va una riga del loro gruppo.

| Campo | ID prodotto | Schema |
| --- | --- | --- |
| Regola prodotto | `1` | `{rewrite}.html` |
| Regola prodotto | `1` | `{category:/}{rewrite}.html` |
| Regola prodotto | `1` | `{categories}{rewrite}.html` |
| Regola prodotto | `1` | `{categories}{rewrite}` |
| Regola prodotto | `2` | `{id}-{rewrite}.html` |
| Regola prodotto | `2` | `{category:/}{id}-{rewrite}.html` |
| Regola prodotto | `2` | `{categories}{id}-{rewrite}.html` |
| Regola prodotto | `2` | `{categories}{id}-{rewrite}` |
| Regola prodotto | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Regola prodotto | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Regola prodotto | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Regola prodotto | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Campo | Schema |
| --- | --- |
| Regola categoria | `{parent_categories:/}{rewrite}/` |
| Regola categoria | `{rewrite}/` |
| Regola fornitore | `supplier/{rewrite}/` |
| Regola fornitore | `any-text/{rewrite}/` |
| Regola marchio | `manufacturer/{rewrite}/` |
| Regola marchio | `any-text/{rewrite}/` |
| Regola pagina CMS | `info/{rewrite}.html` |
| Regola pagina categoria CMS | `info/{rewrite}` |

Un campo categoria vuoto riceve `{parent_categories:/}{rewrite}/`. L'altra riga categoria è l'alternativa. `{parent_categories}` sono i rewrite delle categorie padre uniti da `/`, senza gli id 1, 2 e la categoria stessa. Un campo fornitore vuoto riceve `supplier/{rewrite}/`, un campo marchio vuoto `manufacturer/{rewrite}/`. `any-text` non è una parola della rotta. È un prefisso fisso da scrivere al posto di quelle parole, per esempio `marca/{rewrite}/`. La pagina degli schemi non indica un'alternativa per le due regole CMS. I campi CMS vuoti ricevono `info/{rewrite}.html` e `info/{rewrite}`.

`parent::loadRoutes()` legge `PS_ROUTE_` più l'id della rotta. Se quel valore non è vuoto, quella stringa è la regola compilata, quindi uno schema prodotto o categoria salvato sostituisce la regola assegnata da `loadRoutes()`. Questo modulo non scrive `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}` né `PS_ROUTE_cms_category_rule_{id_lang}`. Quelle rotte di lingua restano i valori `PURLS_ROUTE_*`. Le rotte base `supplier_rule` e `manufacturer_rule` restano `supplier/{rewrite}/` e `manufacturer/{rewrite}/`.

## Cosa fa Salva

**Salva** fa, in quest'ordine:

1. Cancella i nomi di configurazione `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule` e `PURLS_ROUTE_manufacturer_rule`. I valori di queste quattro chiavi, in tutte le lingue, spariscono prima della scrittura dei nuovi.
2. Riscrive queste quattro chiavi dai campi inviati. Con più lingue i campi si chiamano `PURLS_ROUTE_..._{id_lang}`. Con una lingua il campo usa l'id della lingua di contesto. Un campo vuoto viene salvato come stringa vuota.
3. Scrive `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms` e `purls_301`.

Il salvataggio sostituisce lo schema prodotto e categoria di PrestaShop. Il modulo non scrive `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule` né `PS_ROUTE_cms_category_rule`. Il testo di conferma è **Le tue impostazioni sono state aggiornate.**

## Avvisi sul modulo

L'avviso compare quando l'interruttore è spento (`0` o assente) e `strpos` della parola nella rotta PrestaShop è `== false`. In PHP quel confronto è vero anche quando la parola è in posizione 0, quindi uno schema che inizia con `{id}` mostra comunque l'avviso.

Il controllo legge chiavi PrestaShop, non i campi `PURLS_ROUTE_*`:

- ID Prodotto è `0` e `PS_ROUTE_product_rule` non ha `{id}`: «L'URL di riscrittura del tuo prodotto non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine prodotto».
- ID Prodotto è `0` e manca `{-:id_product_attribute}`: «L'URL di riscrittura del tuo prodotto non contiene la variabile {-:id_product_attribute}. È richiesta quando non vuoi rimuovere l'ID dell'attributo prodotto dall'URL delle pagine prodotto».
- Categorie è `0` e `PS_ROUTE_category_rule` non ha `{id}`: «L'URL di riscrittura della tua categoria non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine categoria».
- Produttori è `0` e `PS_ROUTE_manufacturer_rule` non ha `{id}`: «L'URL di riscrittura del tuo produttore non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine produttore».
- Fornitori è `0` e `PS_ROUTE_supplier_rule` non ha `{id}`: «L'URL di riscrittura del tuo fornitore non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine fornitore».
- CMS è `0` e `PS_ROUTE_cms_category_rule` non ha `{id}`: «L'URL di riscrittura della tua categoria CMS non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine fornitore».
- CMS è `0` e `PS_ROUTE_cms_rule` non ha `{id}`: «L'URL di riscrittura del tuo CMS non contiene la variabile {id}. È richiesta quando non vuoi rimuovere l'ID dall'URL delle pagine fornitore».

Gli ultimi due testi parlano di pagine fornitore. Così è scritto in `translations/it.php`.

## Possibili collisioni

![La schermata è in inglese. In queste istruzioni: Possibili collisioni.](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

Il pannello **Possibili collisioni** è `views/purls.tpl`, sotto il modulo. Elenca i `link_rewrite` duplicati per ogni lingua attiva del negozio corrente.

Il testo **Aggiungi questo URL alla tua tabella dei processi cron per correggere automaticamente le collisioni** stampa un link di vetrina al controller `cron` del modulo, con `key` uguale a `Tools::hash('purls')`. Questo pacchetto non contiene `controllers/front/cron.php`. Il metodo `cronJob()` chiama la stessa routine per prodotti e categorie in ogni lingua attiva, e nessun file di questo pacchetto chiama `cronJob()`.

**URL Prodotti**. Colonne: **ID**, **Nome**, **Riscrivi Link**, **Occorrenza**, **Azione**. Per lingua, il menu **Correggi tutte le collisioni** ha **Correggi tutto in una volta** e **Correggi parzialmente**. **Mostra prodotti** ricarica la pagina con `product_rewrite` e `id_lang`. Lista vuota: **Nessuna collisione trovata**.

**URL Categorie** ha le stesse colonne. Il pulsante è **Rendi unici i campi di riscrittura**. **Mostra categorie** aggiunge `category_rewrite`. `getAllCategoryCollisionsRewrite()` riceve un argomento `id_lang` ed esegue l'SQL con l'id lingua del contesto, non con quell'argomento.

**Correggi tutto in una volta**, **Rendi unici i campi di riscrittura** e **Correggi parzialmente** chiamano `makeUnique()`. Per ogni rewrite duplicato, la prima riga tiene `link_rewrite`. Ogni riga successiva viene salvata con quel rewrite più `-1`, `-2`, e così via, nella lingua del pulsante. `save()` gira per ogni riga del gruppo, compresa la prima. Questo cambia `product_lang.link_rewrite` o `category_lang.link_rewrite`. La disinstallazione non rimette il rewrite precedente.

**Correggi parzialmente** invia una richiesta AJAX per riga prodotto (`AjaxCollisions`, `id_lang`, `id_product`) e nasconde la riga dopo la risposta.

La query prodotti raggruppa `link_rewrite` in `product_lang` per negozio e lingua correnti e tiene i gruppi con conteggio di almeno 2. Non filtra per categoria. Le categorie fanno lo stesso su `category_lang`.

## Rotte, reindirizzamenti e hash del prodotto

L'abbinamento proprio di `Dispatcher::getController()` gira quando PrestaShop usa gli URL semplificati (`use_routes`), il controller non è già scelto e la richiesta non è del back office. L'override copia le rotte originali e le registra di nuovo con il suffisso `_original`.

Queste schermate del negozio sono dopo il salvataggio in Impostazioni. La lingua del negozio è l'inglese. Nei percorsi non c'è un id numerico.

![Negozio in inglese. Percorso: men/hummingbird-printed-t-shirt.html#/color-white/size-s. Selezionati Size S e Color White.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Negozio in inglese. Percorso: clothes/men/. Titolo: Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Negozio in inglese. Percorso: manufacturer/studio-design/. Titolo: List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![Negozio in inglese. Percorso: info/delivery.html. Titolo: Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

Con l'interruttore a `1`, `Dispatcher::loadRoutes()` assegna queste `default_routes` e poi chiama `parent::loadRoutes()`:

| Interruttore | Id rotta | Regola assegnata |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` e `supplier_rule_{id_lang}` | base `supplier/{rewrite}/`, rotta lingua da `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` e `manufacturer_rule_{id_lang}` | base `manufacturer/{rewrite}/`, rotta lingua da `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule` e le stesse con `_{id_lang}` | base `info/{rewrite}.html` e `info/{rewrite}` |

Gli altri schemi di questi campi sono in Impostazioni, in **Schemi dei campi rotta**. Uno schema prodotto o categoria salvato sostituisce la regola di questa tabella.

`Link` costruisce l'indirizzo solo con l'interruttore acceso. Altrimenti chiama il metodo padre di PrestaShop.

- Prodotti (`purls_products` `1`, `2` o `3`): `getProductLink()` usa `product_rule`. I parametri che non sono parole di quella rotta vengono omessi. Gli `extraParams` che non sono parole della rotta restano.
- Categorie (`purls_categories` = `1`): `getCategoryLink()` usa `category_rule`. Se la rotta ha la parola `parent_categories`, il percorso nasce dalle categorie padre, senza gli id 1, 2 e la categoria stessa.
- Fornitori, produttori, pagine CMS e categorie CMS usano `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}` e `cms_category_rule_{id_lang}`.

Ricerca quando l'id non è nell'URL:

- Prodotti nei modi `1` e `3`: l'ultimo segmento, senza `.html`, è confrontato con `product_lang.link_rewrite`. Se il percorso ha un segmento categoria, viene confrontato anche il `link_rewrite` della categoria predefinita. Se non trova nulla, una seconda query usa solo `link_rewrite`. Il risultato va in `$_GET['id_product']`.
- Categorie: il percorso è confrontato con `category_lang.link_rewrite`, con i segmenti padre se ci sono più parti.
- Pagine CMS: `cms_lang.link_rewrite`, senza `.html`.
- Categorie CMS: `cms_category_lang.link_rewrite`.
- Produttori e fornitori: `Tools::str2url()` del **nome**, non della colonna `link_rewrite`. Il primo segmento `supplier` è rifiutato dal controllo produttore. Se più nomi danno lo stesso slug, resta l'ultima riga del ciclo.

`purls_301` = `1` invia `HTTP/1.1 301 Moved Permanently` solo in questi casi:

- La rotta fornitore contiene `id_supplier` e la rimozione fornitori è accesa: reindirizzamento a `getSupplierLink()`.
- La rotta produttore contiene `id_manufacturer` e la rimozione produttori è accesa: reindirizzamento a `getManufacturerLink()`.
- La rotta CMS contiene `id_cms`: reindirizzamento a `getCmsLink()`. Contiene `id_cms_category`: reindirizzamento a `getCmsCategoryLink()`. La rimozione CMS deve essere accesa.
- Modo prodotto `1`: la rotta contiene `id_product` e `isProductLink()` ha restituito false: reindirizzamento a `getProductLink()`. I modi `2` e `3` non chiamano quel reindirizzamento.
- La rimozione categorie è accesa, la rotta contiene `id_category` e `isCategoryLink()` ha restituito false: reindirizzamento a `getCategoryLink()`.

Il modo prodotto `3`, se l'abbinamento ha `id_product_attribute` non vuoto, chiama `isProductLinkAttribute()`. Quel metodo scrive `$_GET['id_product']` e `$_GET['id_product_attriubte']` (la chiave è scritta così nel file). Non scrive `id_product_attribute`.

Sulla pagina prodotto, `displayHeader` aggiunge `views/js/purls.js` solo se il controller è `product`, la richiesta non è AJAX, c'è un id prodotto, `purls_product_hash` è `0`, `purls_products` è `1` o `2` e il prodotto ha combinazioni. Il separatore è `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, oppure `-` se quel valore manca o è vuoto. Lo script legge l'hash, imposta `select` o `radio` `group[groupId]` ed emette `prestashop.updateProduct` se un controllo è cambiato.

`CartController::displayAjaxProductRefresh()` ricostruisce l'URL prodotto e aggiunge `idpa` con l'id combinazione. `ProductController::init()` copia `idpa` in `id_product_attribute` quando `id_product_attribute` manca. `getIdProductAttributeByRequest()` legge prima `idpa`.

Se `pm_advancedsearch4` è installato, `hookModuleRoutes()` aggiunge tre rotte con `/filter-{id}/s-{id_search}/{as4_sq}` alle regole di categoria, fornitore e produttore. Se non è installato, l'hook non restituisce nulla.

## Hook

`install()` registra solo questi hook:

| Hook | Metodo | Effetto |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | Sulla pagina prodotto, alle condizioni sopra, aggiunge `views/js/purls.js` e la mappa `purls_attributes`. |
| `ModuleRoutes` | `hookModuleRoutes` | Restituisce le rotte di Advanced Search 4 se quel modulo è installato. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Metodo vuoto. |

## Classi e file sostituiti

PrestaShop copia questi file in `override/` del negozio durante l'installazione:

| File | Classe | Cosa cambia |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` estende `DispatcherCore` | `loadRoutes()`, `getController()` e `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` estende `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Omette i parametri che non sono parole della rotta compilata. |
| `override/controllers/front/ProductController.php` | `ProductController` | Legge `idpa` in `init()`, `getIdProductAttributeByRequest()` e `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` aggiunge `idpa`. |
| `override/controllers/front/CmsController.php` | `CmsController` | Con `purls_cms` a `1`, ricava `id_cms` / `id_cms_category` da `link_rewrite`. Legge anche i vecchi percorsi `content/{id}-{rewrite}` e `content/category/{id}-{rewrite}`. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | Con `purls_categories` a `1`, ricava `id_category` da `category_rewrite` e dal percorso. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | Con `purls_manufacturers` a `1`, ricava `id_manufacturer` con `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | Con `purls_suppliers` a `1`, ricava `id_supplier` con `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | Solo `getPreviewUrl()`. Costruisce il link prodotto nella lingua predefinita del negozio, id combinazione `0` e `force_routes` uguale a `PS_REWRITING_SETTINGS`. Un prodotto inattivo riceve `adtoken`, `ad` e `id_employee`. |

Non c'è un pannello sulla scheda prodotto. Non c'è un file CSS. La configurazione è `views/purls.tpl` più l'helper form di PrestaShop. Lo script di vetrina è `views/js/purls.js`. `purls.tpl` contiene anche la funzione `FixProductsCollisions`.

`Link::psversion()` e `ProductController::psversion()` spezzano `_PS_VERSION_`. `getCategoryLink()` usa un ramo per il meta title quando la versione minore è 6 o 7, o la maggiore è 8 o più, e un altro ramo negli altri casi. I commenti in `Dispatcher.php` e `ProductController.php` nominano PrestaShop 9 e, per un metodo privato, PrestaShop 1.7.

Il modulo non crea tabelle SQL. Legge e scrive `configuration`, e legge `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier` e le tabelle attributi per costruire l'hash. La riparazione collisioni scrive `link_rewrite` tramite `Product::save()` e `Category::save()`.

Nel back office il costruttore crea `override/controllers/front/listing` con modo `0777` se esiste `override/controllers/front/` e non esiste `listing`.

## Aggiornamenti MyPresta

![La schermata è in inglese. In queste istruzioni: Aggiornamenti MyPresta.](https://mypresta.eu/docs/images/docs/purls-updates.webp)

Il pannello **Aggiornamenti MyPresta** sta tra il modulo impostazioni e il pannello collisioni.

| Etichetta | Controllo |
| --- | --- |
| Controlla aggiornamenti | Pulsante **Controlla ora** (`submit_settings_updates_now`). Mostra **Nuova versione disponibile!** o **Il modulo è aggiornato!** |
| Notifiche aggiornamenti | Elenco `mypresta_updates`: **-- seleziona --** (`-`), **Abilita** (`1`), **Disabilita** (`0`). |
| Pagina del modulo | Link alla pagina del prodotto. L'indirizzo è nella sezione supporto. |
| Salva | `submit_settings_updates` scrive solo `mypresta_updates`. |

A ogni richiesta del back office il costruttore chiama `checkforupdates()`. Se `update_purls` manca o è più vecchio di 259200 secondi, `purlsUpdate::verify()` richiede `http://dev.mypresta.eu/update/get.php` se ci sono `allow_url_fopen` e `file_get_contents`. Salva il tempo Unix in `update_purls` e il corpo della risposta in `updatev_purls`. Il valore licenza di questo pacchetto è `nlc` (`$this->mkey`), salvo un `key.php` accanto al modulo. Questo pacchetto non contiene `key.php`.

Se `mypresta_updates` non è `0` e non è false, la versione remota salvata è maggiore di 3.0.0 e la richiesta non è AJAX, il back office mostra **Nuova versione disponibile, controlla http://MyPresta.eu per maggiori informazioni** e **Maggiori dettagli nel changelog**. Il valore `0` esegue comunque la richiesta a tempo e non aggiunge quell'avviso. Una chiave assente è false, e false equivale a `0`, quindi non aggiunge l'avviso.

## Installazione, disattivazione, attivazione, disinstallazione

`install()` chiama `parent::install()` e registra `displayHeader`, `ModuleRoutes` e `actionAdminControllerSetMedia`. Se uno di questi fallisce, l'installazione restituisce false. Non inserisce configurazione e non crea una tabella.

Il file non definisce `enable()` né `disable()`. Disattivare il modulo nel pannello non esegue un metodo di questo file. Le classi di override restano in `override/` del negozio, perché questo modulo non ha un `disable()` che le rimuova. I tre hook non vengono eseguiti mentre il modulo è disattivato.

`uninstall()` restituisce solo `parent::uninstall()`. Questo toglie il modulo, deregistra gli hook e cancella le copie di override installate da PrestaShop. Non cancella la configurazione. Non ripristina `PS_ROUTE_product_rule` né `PS_ROUTE_category_rule`. Non ripristina i `link_rewrite` cambiati dai pulsanti delle collisioni. Restano: `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, le quattro chiavi `PURLS_ROUTE_*`, `mypresta_updates`, `update_purls`, `updatev_purls` e le due chiavi `PS_ROUTE_*` scritte dal modulo.

## Quando una pagina non si risolve

- L'ID è ancora nell'URL: ID Prodotto è `0` o la chiave non è stata salvata, oppure lo schema prodotto/categoria contiene ancora `{id}`. L'abbinamento proprio di `getController()` gira solo con gli URL semplificati (`use_routes`) attivi.
- Un URL pulito finisce nel controller non trovato: due prodotti o categorie condividono `link_rewrite`. Il pannello collisioni elenca quelle righe. I pulsanti di correzione cambiano `link_rewrite` nel database.
- Un vecchio URL con id non reindirizza: `purls_301` non è `1`, oppure il tipo di pagina è il modo prodotto `2` o `3` (quei rami non chiamano `Tools::redirect`).
- L'URL produttore o fornitore apre il record sbagliato, o nessuno: l'abbinamento usa `Tools::str2url()` del nome.
- Il modulo è disattivato e gli URL passano ancora da questo codice: gli override restano in `override/` fino alla disinstallazione.
- Dopo la disinstallazione, gli schemi prodotto e categoria sono gli ultimi valori salvati da questo modulo.

## Supporto

Pagina del prodotto: [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). Il campo **Pagina del modulo** nel pannello aggiornamenti apre questo indirizzo. L'aiuto delle impostazioni apre anche `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
