---
title: "HTML Box Pro - istruzioni per il venditore"
sidebar:
  label: "HTML Box Pro - istruzioni per il venditore"
description: "Configurazione dei box HTML, delle posizioni hook e delle regole di visibilità per un negozio che ha già il modulo."
---
> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo HTML Box Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/html-box-pro/)
>
> ---



Il nome tecnico del modulo è `htmlboxpro`, versione 4.0.5. In questa lingua l'elenco moduli mostra **HTML Box Pro**.

## 1. Dove sono le schermate

Moduli, poi Gestore moduli, poi il modulo **HTML Box Pro**, poi Configura. La pagina è la configurazione del modulo (`configure=htmlboxpro`).

La barra sotto il titolo ha due pulsanti: **Impostazioni** e **Box**. **Impostazioni** scrive `hbp_lasttab` = 1. **Box** scrive `hbp_lasttab` = 2. Se la chiave manca, l'apertura della pagina scrive 1, quindi la prima vista è **Impostazioni**.

Nella stessa barra, **Supporto** apre `https://mypresta.eu/contact.html` in una scheda nuova. **Aggiornamenti** apre la pagina del modulo su MyPresta in una scheda nuova. Il controllo versione è il pannello in fondo a **Impostazioni**, non quel pulsante.

Non c'è importazione e non c'è un blocco sulla scheda prodotto. Un box compare in negozio solo quando il suo hook è acceso, il blocco è attivo e supera i filtri più sotto.

Se `firsttime_hbp` non è 1, la pagina mostra un avviso con `https://www.youtube.com/watch?v=uxzhSr5TrF4`. La chiusura invia `firsttime_hbp` = 1 e l'avviso non torna.

## 2. Cosa scrive l'installazione

L'installazione esegue l'installazione padre, crea le tabelle, scrive `hbp_notinyjs` = 1 e registra `actionAdminControllerSetMedia` più ogni hook dell'elenco più sotto.

Non accende quegli hook. Un hook stampa i box solo quando la chiave `hbp_` più il nome dell'hook vale 1. Finché la casella in **Box** non viene salvata, la chiave manca e l'hook non restituisce nulla.

Aprire la configurazione controlla sempre le colonne e aggiunge quelle mancanti in `hbp_block`. Le righe già presenti restano.

## 3. Impostazioni

![Schermata in inglese. Settings è Impostazioni. Global module settings è Impostazioni globali del modulo. Updates notifications è Notifiche di aggiornamento.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)

Il titolo è **Impostazioni globali del modulo**. Il pulsante è **Salva**. Ogni interruttore è **On** (1) o **Off** (0). Nel file `translations/it.php` queste due parole sono On e Off.

| Etichetta | Chiave | Dopo l'installazione |
| --- | --- | --- |
| Usa l'editor di testo ricco interno del modulo | `hbp_tiny` | chiave assente; il modulo mostra **Off** |
| Impedisci la rimozione degli URL dalle immagini | `hbp_forceurls` | chiave assente; il modulo mostra **Off** |
| Non caricare (duplicare) i box con le query ajax della pagina prodotto | `hbp_noajax` | chiave assente; il modulo mostra **Off** |
| Non caricare le librerie tinyMCE | `hbp_notinyjs` | 1, quindi **On** |

**Salva** invia i nomi dei quattro interruttori. Il modulo scrive ogni valore inviato. `hbp_tiny` = 1 carica in questa pagina `views/js/tinymce16.inc.js`. Lo stesso interruttore insieme a `hbp_forceurls` = 1 carica al suo posto `views/js/tinymce16-force-urls.inc.js`. `hbp_tiny` = 0 carica il file del negozio `js/admin/tinymce.inc.js` e chiama `tinySetup()`. `hbp_notinyjs` = 1 salta `js/tiny_mce/tinymce.min.js`. La pagina include comunque `js/tiny_mce/tiny_mce.js`, `views/js/script.js` e `views/css/styles.css`.

`hbp_noajax` = 1 fa restituire vuoto a `generateHookContents` quando la richiesta ha `ajax` = 1 e `action` = refresh. Le altre richieste stampano ancora i box.

Sotto gli interruttori la pagina aggiunge il pannello aggiornamenti di `checkforupdates`. L'elenco **Notifiche di aggiornamento** ha `-- select --`, **Abilita** (1) e **Disabilita** (0). **Verifica ora** è il pulsante `submit_settings_updates_now`. **Salva** di quel pannello è `submit_settings_updates` e scrive solo `mypresta_updates`.

Il costruttore interroga il server remoto quando `mypresta_updates` non è 0, oppure quando la chiave manca (`Configuration::get` è false), e `update_htmlboxpro` è più vecchio di 259200 secondi. La richiesta parte se `allow_url_fopen` è attivo. Il valore di licenza di questo pacchetto è `nlc`. Un avviso compare quando la versione restituita è maggiore di 4.0.5 e la richiesta non è ajax. **Disabilita** (0) entra comunque nel ramo con il tempo; la condizione dell'avviso è quella di quel ramo.

## 4. Box

![Schermata in inglese. Boxes è Box. Default positions è Posizioni predefinite. Search hooks non è in translations/it.php, lo schermo mostra quella fonte inglese.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)

**Box** ha due colonne. A sinistra, **Posizioni predefinite**. Sopra le righe c'è un campo di ricerca. Il segnaposto **Search hooks** non è in `translations/it.php`, lo schermo mostra quella fonte inglese. **Posizioni personalizzate** è il pannello sotto quell'elenco, nella stessa colonna sinistra. La colonna destra mostra i blocchi dell'hook scelto oppure lo stato vuoto. La colonna principale inizia con il titolo **No box selected** e la frase **Si prega di selezionare i blocchi dalla lista disponibile a sinistra. O creare un nuovo blocco.** **No box selected** e **No boxes in this position yet** (hook aperto senza blocchi) non sono in `translations/it.php`, lo schermo mostra quella fonte inglese.

Ogni hook predefinito è una riga: casella, nome dell'hook e il pulsante di un box nuovo. Il nome porta a `https://mypresta.eu/prestashop/hook/` più il nome in minuscolo. La casella invia `togglehook`. Selezionata scrive `hbp_{hook}` = 1 e chiama di nuovo `registerHook`. Deselezionata non invia `status`, quindi la chiave diventa 0. Spegnere l'hook non lo deregistra. Il testo di successo è **Visibilità dell'hook modificata correttamente**.

La riga del blocco mostra il nome interno, oppure **nessun nome di blocco interno** se il nome è vuoto. I pulsanti sono **Modifica questo blocco**, **Duplica questo blocco** e **Rimuovi questo blocco**. Il successo dell'interruttore di attività è **Visibilità del blocco modificata correttamente**. Trascinare una riga invia `action=updateSlidesPosition` e `elements{hook}[]` e scrive `hbp_block.position`. La scheda carica jQuery UI sortable. Un hook vuoto mostra **nessun blocco definito**. In multinegozio la riga può mostrare **per questo negozio**.

**Duplica questo blocco** copia il blocco e mette `[duplicato] ` davanti al nome. Il testo di successo è **Blocco duplicato correttamente**. **Rimuovi questo blocco** cancella la riga tramite il modello oggetto. Il testo di successo è **Blocco rimosso correttamente**. L'interruttore della lista esegue `smart_clean` sul corpo di ogni lingua, salva il blocco e imposta `active` con SQL.

## 5. Aggiungere e modificare un blocco

![Schermata in inglese. Create new block è Crea nuovo blocco. Contents è Contenuti. Smarty templates manager è Gestore dei template Smarty. Placement non ha traduzione.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)

Aggiungere un box apre **Crea nuovo blocco**. Modificare apre **Modifica blocco esistente**. Il pulsante è **Salva**. L'aggiunta invia `submitAddNewHbox`. La modifica invia `submitEditHbox`. Il testo di aggiunta è **Blocco aggiunto correttamente**. Il testo di salvataggio è **Blocco salvato correttamente**.

Il corpo di ogni lingua del negozio va in `hbp_block_lang.body`. Prima del salvataggio il modulo esegue `addslashes(smart_clean(...))`. `smart_clean` riduce un carattere di spazio ripetuto a uno solo e taglia le estremità. L'ultima sostituzione di `prepare()` riscrive `\'`, `\\` e `\"`. Le righe precedenti di `prepare()` partono dalla stringa originale e non cambiano il valore restituito. La funzione non toglie i tag HTML. La stessa pulizia riparte quando l'interruttore della lista cambia l'attività.

Le etichette dei campi sono in `translations/it.php`. Il titolo prodotti è **Prodotti**. **Placement**, **Pages**, **Cart**, **Customers** e **Schedule** non hanno una voce in quel file, lo schermo mostra questa fonte inglese.

| Sezione | Cosa fanno i campi |
| --- | --- |
| Contenuto | **Contenuti** (`hbp_body`, un valore per lingua) e **Nome** (`hbp_name`, 150 caratteri). L'interruttore dell'editor in `views/js/script.js` chiama `tinyMCE.execCommand('mceToggleEditor')` per il campo di quella lingua. Sotto l'editor c'è **Gestore dei template Smarty**. Il pulsante apre il gestore di `lib/smartyTemplatesManager/`. |
| Placement | Negozio, posizione (`hbp_hook`), **Active** (`hbp_active`, 0 nella tabella finché il salvataggio non mette 1), solo pagine SSL (`hbp_bssl`), **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices**. Un valore dispositivo assente viene salvato come 1. Le etichette italiane sono in `translations/it.php`. |
| Pages | Home, offerte, conferma ordine, categoria, categoria e sottocategorie, categorie escluse, categoria CMS, pagina CMS, pagina produttore, URL esatto e parole di ricerca. Gli id sono separati da virgole. Il campo di ricerca accanto a un id è lo strumento di ricerca del modulo (`ajax=1` e `searchType`). |
| Products | Includere o escludere id prodotto, tutte le schede, prezzo specifico, esaurito, acquistabile, non acquistabile, a magazzino, valore minimo e massimo, categoria del prodotto, produttore, fornitore e valore caratteristica. |
| Cart | Il box solo se il carrello contiene, o non contiene, gli id di categoria o di prodotto indicati. |
| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) in `hbp_logged`. I testi italiani di queste tre opzioni sono in `translations/it.php`. **Show for all groups** e le caselle dei gruppi vanno in `hbp_cgroup` come elenco separato da virgole. **Hide for (users' groups)** è `hbp_hcgroup`. Geolocalizzazione e paese dell'indirizzo di consegna sono in questa sezione. |
| Schedule | Valuta, data da / a, giorni della settimana e ora da / a. |

I giorni chiamano la traduzione con il dominio `forms` (`Sunday` fino a `Saturday`). I file `translations/*.php` tengono queste parole nel dominio `htmlboxpro`, non `forms`. Lo schermo mostra la fonte inglese: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.

Il testo di geolocalizzazione indica `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` e la cartella `/app/Resources/geoip/`. Lo stesso testo dice che la geolocalizzazione non funziona su localhost. I paesi scelti vanno in `selected_geoip`, separati da punto e virgola. I paesi di consegna vanno in `delivery_address_selected`, separati da punto e virgola. È un interruttore diverso dalla geolocalizzazione.

## 6. Quando il negozio nasconde un blocco

`generateHookContents` carica i blocchi con `active` = 1 per la lingua e l'hook correnti, ordinati per `position`. Se il multinegozio è acceso, `shop` deve essere l'id del negozio corrente oppure 0. Il template `html.tpl` nasconde il corpo quando una regola sotto non passa. Un interruttore lasciato su **Off** non applica quella regola.

| Interruttore acceso | Il corpo è nascosto quando |
| --- | --- |
| Solo home | il controller non è `index` |
| Intervallo date | oggi è prima della data da o dopo la data a (`Y-m-d`) |
| Parole di ricerca | la ricerca non è una delle parole separate da virgole |
| Solo pagine SSL | `$_SERVER['HTTPS']` non è `on` |
| Solo connessi | il cliente non è connesso |
| Solo non connessi | il cliente è connesso |
| Solo schede prodotto scelte | l'id prodotto non è nell'elenco. Un primo elemento vuoto lascia il blocco se c'è un id prodotto |
| Esaurito | lo stock usato dal template è maggiore di 0 |
| A magazzino | quello stock non è maggiore di 0 |
| Non acquistabile / acquistabile | il valore `oos` non coincide con la regola deny o allow di `html.tpl` |
| Prezzo specifico / senza prezzo specifico | `hook_params.product` non ha un prezzo specifico corrispondente |
| Categorie scelte | il controller non è quello di categoria o l'id non è scelto |
| Categorie e sottocategorie | la categoria non è scelta e non è figlia secondo `htmlboxpro::checkIfChildren` |
| Categoria CMS, pagina CMS, pagina produttore | l'id corrente non è nell'elenco o il controller è un'altra pagina |
| URL scelto | `htmlboxpro::currentPageURL()` non è nell'elenco salvato. Il confronto toglie `rand=` |
| Prodotto in categoria | le categorie del prodotto non intersecano l'elenco |
| Caratteristica | il prodotto non ha il valore di caratteristica scelto |
| Conferma ordine | il controller non è `orderconfirmation` |
| Produttore o fornitore del prodotto | produttore o fornitore non è scelto |
| Carrello, categoria o prodotto, contiene o non contiene | il carrello non coincide con l'elenco. Il PHP di `get_blocks` toglie il blocco prima del template per questi quattro filtri |
| Nascondi per il gruppo | il gruppo del cliente coincide con `hbp_hcgroup`. I gruppi 1 e 2 si confrontano con il gruppo predefinito. Un altro gruppo nasconde il blocco se è tra i gruppi del cliente |
| Dispositivo | `Context::getDevice()` è 1 e il PC è spento; 2 e il tablet è spento; 4 e il cellulare è spento |
| Valore min / max | il prezzo convertito è fuori dall'importo o l'hook non ha un prodotto |
| Giorni | `hbp_daytype_on` è 1 e il `%w` di oggi non è nell'elenco |
| Valuta | `hbp_currency_on` è 1 e l'id valuta non è `hbp_currency` |
| Indirizzo di consegna | il paese di consegna non è in `delivery_address_selected` |
| Geolocalizzazione | `hbp_geoip` è 1 e il paese risolto non è in `selected_geoip` |
| Prodotti esclusi, tutte le schede, categorie escluse | il prodotto o la categoria corrente è escluso |

Il filtro orario gira in PHP, prima del template. Se `hbp_tim` è 1, `timfrom` e `timto` si confrontano con `date("H:i:s")` dopo la rimozione dei due punti. `timto` passa da `ltrim` con la maschera di caratteri `0`, quindi gli zeri a sinistra di quel limite spariscono. Un blocco fuori dalla finestra esce dall'elenco.

## 7. Segnaposto nel corpo del box

La sostituzione gira quando la richiesta ha un `controller` e non è `AdminModules`. Un segnaposto non riempito diventa una stringa vuota alla fine. L'eccezione è `{current_url}`.

| Segnaposto | Riempito quando |
| --- | --- |
| `{currency_iso}` | c'è una valuta; il valore è il codice ISO |
| `{id_lang}` | sempre in quel ramo; il valore è il codice ISO della lingua, non l'id numerico |
| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | il cliente è connesso |
| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | il controller è `product` oppure l'hook riceve `product` |
| `{product_price_tax_incl}`, `{product_price_tax_excl}` | scheda prodotto; importo tramite l'helper prezzi del modulo |
| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | gli stessi importi senza il segno della valuta |
| `{id_category}`, `{name_category}`, `{path_array_category}` | nella richiesta c'è un id categoria |
| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | c'è un carrello |
| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | il ramo di conferma ordine ha un id ordine |
| `{current_url}` | ogni richiesta, dopo il ramo sopra. Schema, host e URI |
| `{HOOK:HookName}` | `Hook::exec` di quel nome, tranne quando il nome è l'hook che sta disegnando questo box; allora il segnaposto è vuoto |
| `{HOOK:HookName:moduleName}` | `Hook::exec` limitato all'id di quel modulo |
| `{smartyTemplate:name}` | il template caricato da `loadSmartyTemplateFromManager` |

`{shop_name}` riceve il nome del negozio e il passaggio di pulizia sostituisce poi `{shop_name}` con una stringa vuota. Il segnaposto non resta come nome del negozio. `{id_product_attribute}` è vuoto quando l'id attributo è 0.

## 8. Posizioni personalizzate

![Schermata in inglese. Custom positions è Posizioni personalizzate. Add support of new hook è Aggiungi supporto per un nuovo hook. Hook name è Nome dell'hook. Add new hook è Aggiungi nuovo hook. regenerate now! è rigenera ora!](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)

**Posizioni personalizzate** elenca le righe di `hbp_customhook`. Il titolo sopra il campo è **Aggiungi supporto per un nuovo hook**. **Aggiungi nuovo hook** legge **Nome dell'hook**. Il nome salvato tiene solo lettere e cifre (`preg_replace("/[^\da-z]/i", '')`). Se il negozio non ha un hook con quel nome, il modulo crea una riga `Hook` con `live_edit` 1, `position` 1, il titolo uguale al nome e la descrizione `Custom hook created with usage of HTML BOX PRO module`. Inserisce `hbp_customhook` se la riga manca, riscrive `htmlboxpro.php` e registra l'hook.

Se l'hook esiste già e il metodo `hook{Name}` è già in `htmlboxpro.php`, la pagina mostra **L'hook esiste già nel database del negozio** e non aggiunge un'altra riga. Se l'hook esiste e il metodo manca, il modulo riscrive comunque il file e registra l'hook.

**rigenera ora!** invia `hbp_rh_submit`. L'avviso del pulsante è **usa questa opzione per ricostruire il file del modulo se gli hook personalizzati non funzionano**. Il titolo accanto è **Rigenera hook**. La riscrittura sostituisce la parte di `htmlboxpro.php` tra `//~~explode~~//` con un metodo per hook: `hook{Name}` restituisce `generateHookContents("{Name}", $params)`. Il file deve essere scrivibile. Testo di errore: **Il file principale del modulo non è scrivibile. Si prega di controllare i permessi (CHMOD) per il file /modules/htmlboxpro/htmlboxpro.php**. Testo di successo: **File principale del modulo ricostruito correttamente. Il modulo dovrebbe ora supportare gli hook personalizzati.**

**Remove hook** chiede **Remove this custom hook?** Queste due stringhe non sono in `translations/it.php`, lo schermo mostra questa fonte inglese. L'azione cancella la riga `hbp_customhook` e, se l'id dell'hook esiste nel negozio, cancella quel `Hook`, poi riscrive il file.

Il link **Come usare gli hook personalizzati?** apre `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. Nel modulo, un blocco su un hook proprio mostra **Questo blocco usa un hook personalizzato** e due frammenti:

`{hook::exec('HookName') nofilter}`

`{hook h='HookName' product=$product}`

Il secondo frammento è quello descritto per un elenco prodotti.

## 9. Hook registrati all'installazione

`actionAdminControllerSetMedia` aggiunge il plugin jQuery autocomplete solo quando `configure` è `htmlboxpro`. Non stampa un box.

Questi hook chiamano `generateHookContents` con il nome dell'hook. L'output dipende ancora da `hbp_{hook}` = 1 e da un blocco attivo:

`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.

`displayHeader` non allega un file CSS o JS in negozio. Stampa i box di quell'hook. Il negozio non riceve un foglio di stile proprio del modulo. HTML, CSS e JavaScript sono il corpo salvato dal venditore.

`registerHook` usa il metodo padre quando `hook{Name}` esiste già. Altrimenti inserisce la riga `Hook` se serve e inserisce `hook_module`.

## 10. Tabelle e file

L'installazione crea tre tabelle se mancano, motore InnoDB, set di caratteri `utf8_general_ci`. Davanti al nome c'è il prefisso del negozio.

| Tabella | Colonne dell'istruzione CREATE |
| --- | --- |
| `hbp_block` | `id` (auto increment, chiave primaria), `position` predefinito 1, `hook` varchar(50), `active` predefinito 0, `logged` predefinito 0, `name` varchar(150), indice `indek1` |
| `hbp_customhook` | `id`, `hook` varchar(70) |
| `hbp_block_lang` | `id`, `id_lang`, `body` text. L'istruzione CREATE non ha chiave primaria |

Il modello `models/hbox.php` mappa `hbp_block`, `body` è multilingue. L'apertura successiva della configurazione aggiunge le colonne dei filtri: `bssl`, `shop` (predefinito 1), i flag di pagina e di prodotto, le colonne di testo degli id scelti, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (portato a varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (predefinito 1), i campi prezzo, `daytype`, `currency`, `geoip` e le colonne di carrello e consegna. `inconsistency()` allarga `hook` a varchar(255).

Altri file: `views/templates/hook/html.tpl` è il corpo in negozio, `views/templates/admin/_configure/helpers/form/form.tpl` sostituisce il form helper di questo modulo, `lib/searchTool/` è la ricerca id, `lib/smartyTemplatesManager/` serve `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` è l'helper del prezzo. `key.php` è facoltativo e non è in questo pacchetto. La licenza di aggiornamento in `checkforupdates` è il letterale `nlc`.

Chiavi di configurazione che non sono colonne: `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.

## 11. Disattivare, attivare, disinstallare

La classe non ha `disable()` né `enable()`. Disattivare usa il padre di PrestaShop: il modulo resta installato, tabelle e configurazione restano, gli hook non vengono eseguiti. Attivare usa l'attivazione padre.

La classe non ha `uninstall()`. La disinstallazione usa il metodo padre: il modulo viene deregistrato e le registrazioni hook che PrestaShop ha salvato per lui vengono rimosse. Il metodo padre non cancella `hbp_block`, `hbp_block_lang` né `hbp_customhook`. Non cancella le chiavi di configurazione dell'elenco. Non cancella le righe `Hook` create con **Aggiungi nuovo hook** e non ripristina `htmlboxpro.php` dopo **rigenera ora!** né dopo l'aggiunta di un hook proprio. Un'installazione successiva usa `CREATE TABLE IF NOT EXISTS`, quindi le righe rimaste in quelle tabelle restano.

## 12. Area vuota sotto le schede

Il codice accetta `selecttab` = 3 e può salvare `hbp_lasttab` = 3. La barra non ha un terzo pulsante e il render del form non ha una pagina per 3. Con quel valore l'area sotto la barra è vuota. **Impostazioni** o **Box** riscrivono 1 o 2.

## 13. Supporto

Pagina del modulo: [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).
