---
title: "Google Merchant Center Feed - istruzioni per il venditore"
sidebar:
  label: "Google Merchant Center Feed - istruzioni per il venditore"
description: "Configurazione e risoluzione dei problemi del file di catalogo, dei file salvati e dell'indirizzo del catalogo in un negozio che ha già il modulo."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google merchant center feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-merchant-center-feed/)
>
> ---


Il nome tecnico è `gmfeed`, versione 2.4.3, e la lista dei moduli mostra **Google Merchant Center Feed**, nome scritto nel file del modulo e non preso da `translations/it.php`.

## 1. Dove sono le schermate

Ci sono due schermate.

Moduli, poi Gestione moduli, poi **Google Merchant Center Feed**, poi Configura. Questa pagina ha un campo, **Mostra albero delle categorie**.

Catalogo, poi **Feed di Google Merchant**. È il controller `AdminExportProductsFeedGoogle`. Il titolo è **Feed Google Merchant Center**. Le schede sono **Dashboard**, **Feed**, **Aggiornamenti** e **Crea / Modifica feed**. L'ultima resta disattivata finché non apri **Crea nuovo feed** o un feed esistente.

Non c'è una schermata di importazione né un blocco sulla scheda prodotto. La vetrina non disegna un riquadro. L'effetto pubblico è l'indirizzo di catalogo di un feed salvato.

## 2. Cosa scrive l'installazione

L'installazione esegue l'installazione della classe padre, registra `actionAdminControllerSetMedia`, crea una scheda sotto Catalogo e crea le tabelle del punto 8.

La classe della scheda è `AdminExportProductsFeedGoogle`. L'etichetta passata all'installazione è **Feed di Google Merchant**. La stessa etichetta è scritta per ogni lingua del negozio esistente in quel momento.

`actionAdminControllerSetMedia` carica i plugin fancybox e autocomplete solo quando il controller è `AdminExportProductsFeedGoogle`.

La classe non ha `enable()` né `disable()`.

## 3. Impostazioni del modulo

![Impostazioni del modulo](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

Lo schermo è in inglese. In queste istruzioni questa pagina si chiama **Impostazioni del modulo**.

La legenda è **Impostazioni del modulo**. Il pulsante è **Salva**. L'unico campo è **Mostra albero delle categorie** (`pf_tree`). **No** vale 0. **Sì** vale 1. Se la chiave manca, `(int)Configuration::get('pf_tree')` vale 0 e la lista mostra **No**.

**Salva** invia `submitgmfeedSettings` e scrive `pf_tree`. Il testo dopo il salvataggio è **Impostazioni salvate correttamente**.

**Sì** fa mostrare le categorie padre nell'elenco di associazione sul formulario del feed. La descrizione collega **Vedi screenshot** a `https://i.imgur.com/enzXRaJ.png`. La stessa descrizione collega **Catalogo > Feed di Google Merchant**.

Questa pagina non genera il file di catalogo.

## 4. Pagina del catalogo

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Lo schermo è in inglese. In queste istruzioni questa scheda si chiama **Dashboard**.

![Feed](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Lo schermo è in inglese. In queste istruzioni questa scheda si chiama **Feed**.

Apri **Catalogo > Feed di Google Merchant**.

**Dashboard** mostra **Feed salvati**, **Esecuzioni cron di oggi**, **Esecuzioni ultimi 7 giorni** e **File salvati**. I numeri vengono da `gms` e `gms_log`. Se nessun indirizzo è stato chiamato, la pagina mostra **Nessun cron o generazione di URL ancora effettuata. Salva un feed, quindi chiama il suo URL di catalogo da uno scheduler.**

**Feed** elenca le righe di `gms`, dal `id_gms` più alto. **Crea nuovo feed** apre il formulario. **Duplica** copia la stringa di query salvata, toglie `export_id_gms`, `id_gms` e `gmfeed_write_key` e aggiunge ` (copia)` al nome. Se il nome è vuoto, la copia parte da **Feed senza titolo**. Il testo dopo la copia è **Feed duplicato. Rivedi la copia e salvala se ti serve un nome file o un URL diverso.** **Elimina** cancella quella riga di `gms`. Il testo è **Feed rimosso.** Il file salvato sul disco non viene cancellato da questa azione.

![Aggiornamenti](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

Lo schermo è in inglese. In queste istruzioni questa scheda si chiama **Aggiornamenti**.

**Aggiornamenti** è il formulario di `lib/updateChecker.php`. **Controlla ora** invia `submit_settings_updates_now`. **Salva** invia `submit_settings_updates` e scrive `mypresta_updates`. Il costruttore interroga il server remoto quando `mypresta_updates` non è 0 e `update_gmfeed` è più vecchio di 172800 secondi. Il valore di licenza inviato se manca `mkey` è `nokey`. Un avviso compare quando `updatev_gmfeed` è superiore a 2.4.3 e la richiesta non è ajax.

## 5. Formulario del feed

![Crea nuovo feed](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Lo schermo è in inglese. In queste istruzioni questa vista si chiama **Crea nuovo feed**. Il ritaglio mostra la parte alta del formulario. Gli altri campi stanno sotto.

**Crea feed** e **Modifica feed** usano lo stesso formulario. Il campo **Nome feed** è obbligatorio. **Attivo** **Sì** / **No** è salvato in `gms.active`. Un nuovo feed è attivo. **Negozio** salva `gms.id_shop`. Gli altri campi sono salvati in `gms.conf` come stringa di query.

Una chiave assente su un nuovo formulario prende il valore della tabella. Durante la modifica, una chiave assente prende lo stesso valore e non legge la configurazione condivisa `gm_`.

| Chiave | Valore predefinito di un nuovo feed | Cosa ne fa il codice |
|---|---|---|
| `export_file_format` | `csv` | `csv` o `xml`. Ogni altra estensione viene riportata a `csv` da `sanitizeExportExtension`. |
| `export_type` | `product` | `sanitizeExportType` tiene solo `products` e `combinations`. Il valore salvato `product` è quindi trattato come `products`. |
| `export_save_file` | `0` | `0` invia il catalogo nella risposta. `1` scrive un file in `/modules/gmfeed/`. |
| `export_filename` | vuoto | Usato solo con il salvataggio su file. Vuoto diventa il tipo di export. I caratteri diversi da lettere, cifre, `_` e `-` vengono rimossi. |
| `export_identification` | `id_product` | Id prodotto scritto come id del catalogo. |
| `export_delimiter` | barra verticale | Separatore delle colonne CSV. |
| `export_enclosure` | `0` | Valore enclosure passato alla scrittura CSV. |
| `export_language` | `PS_LANG_DEFAULT` | Lingua di nomi e descrizioni. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Valuta dei prezzi. |
| `export_tax` | `price_tin` | Quale colonna di prezzo viene compilata. |
| `export_specific` | `1` | Quando la valuta predefinita del negozio differisce dalla valuta del contesto, un valore diverso da zero fa usare i prezzi specifici al passo del prezzo. |
| `export_category` | `all` | Categorie incluse nel catalogo. |
| `export_manufacturers` | `all` | Produttori inclusi. |
| `export_manufacturers_default` | `Default` | Testo del brand quando il prodotto non ha un produttore. |
| `export_suppliers` | `all` | Fornitori inclusi. |
| `export_gtin` | `upc` | Quale codice prodotto viene scritto come GTIN. |
| `export_img` | `1` | Tipo di immagine passato a `getImageLink`. L'elenco mostra i nomi dei tipi di immagine. |
| `export_what_pictures` | `0` | `0` è **Esporta solo copertina** e toglie la colonna delle immagini aggiuntive. `1` è **Esporta tutte le immagini**. |
| `export_active` | false | Passato a `Product::getProducts` come flag solo attivi. `0` è **Esporta tutti i prodotti.** `1` è **Esporta solo i prodotti attivi**. |
| `export_instock` | false | `1` salta una riga quando la quantità è 0 o inferiore. `0` è **Esporta tutti i prodotti.** `1` è **Esporta solo i prodotti disponibili in magazzino**. |
| `export_igid` | `0` | `0` toglie `item_group_id`. |
| `export_gender` | `0` | `0` toglie la colonna genere. |
| `export_age_group` | `0` | `0` toglie la colonna fascia di età. |
| `export_size` | `0` | `0` toglie la colonna taglia. |
| `export_color` | `0` | `0` toglie la colonna colore. |
| `export_shipping_info` | `0` | `0` è **Non includere**. `1` è **Includi (prezzo di spedizione calcolato separatamente per ogni articolo)**. `2` è **Imposta il prezzo di spedizione manualmente**. |
| `export_product_weight` | `0` | Il peso resta spento finché questo valore non viene cambiato. |
| `export_product_type` | `0` | Il tipo di prodotto resta spento finché questo valore non viene cambiato. |
| `export_removehtml` | `0` | Un valore diverso da `0` toglie l'HTML dalla descrizione. |
| `export_nophoto_exclude` | `0` | `1` esclude un prodotto senza foto. |
| `export_adult` | `0` | Il campo adult resta spento finché questo valore non viene cambiato. |
| `export_storecode` | `0` | `0` toglie la colonna codice negozio. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | Paese usato per il prezzo. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Gruppo clienti usato per il prezzo. |
| `remember_settings` | true | Quando il valore inviato è `1`, lo stesso salvataggio scrive anche `gm_{chiave}` in Configuration. La chiave di scrittura, il negozio, l'id del feed e il flag attivo sono esclusi. |
| `feed_active` | attivo per un nuovo feed | `gms.active`. `0` fa rispondere all'indirizzo con HTTP 503 e la fonte inglese `Feed is disabled`. |

**Salva su file** descrive la directory `modules/gmfeed/` e indica che scrivere il file dall'indirizzo richiede la chiave segreta mostrata su questo formulario. La chiave è `gmfeed_write_key`, un HMAC di `gmfeed.write.` più l'id del negozio, con `_COOKIE_KEY_`. Un dipendente connesso scrive il file senza questa chiave. Chiunque altro riceve la fonte inglese `Access denied`.

Il testo dopo il salvataggio è **Feed salvato. Il suo URL di catalogo è pronto per l'uso.**

## 6. Indirizzo del catalogo e file

L'indirizzo del catalogo è il controller frontale `feed` del modulo, più `?feed=` e l'id di `gms`. `gms::getFeedUrl` aggiunge anche `gmfeed_write_key` quando costruisce il link per il back office.

L'apertura di questo indirizzo carica la stringa di query salvata e sostituisce i valori `export_` e `gmfeed_` della richiesta, tranne la chiave di scrittura e `debug_feed`. Un feed assente, oppure un `conf` di 20 caratteri o meno, si ferma sulla fonte inglese `feed does not exists`. Un feed con `id_shop` impostato e diverso dal negozio corrente si ferma sulla fonte inglese `Feed is not available in this store`.

`debug_feed` stampa i parametri salvati e non scrive il file.

Il nome del file è `export_filename` ripulito più `.csv`, `.xml` o `.txt`. Il percorso resta in `/modules/gmfeed/`. `.htaccess` in questa directory vieta l'esecuzione diretta dei file PHP. `index.php` resta consentito. Il catalogo è servito dal controller frontale, non dall'apertura dei file PHP.

Ogni esecuzione inserisce `gms_log`: ora, durata, numero di articoli, stato, se un file è stato salvato, nome del file, formato e fonte `url`.

## 7. Categorie Google

Il formulario elenca i file di tassonomia da `/modules/gmfeed/google/`. Una lingua del negozio è segnata come presente quando esiste `google/{language_code}.txt`. Questo pacchetto contiene `google/en-us.txt`. La prima riga di quel file è `# Google_Product_Taxonomy_Version: 2015-02-19`.

L'associazione di una categoria del negozio scrive `pixelgoogle`: `id_google`, `id_category`, `id_lang`, `value`. **Mostra albero delle categorie** cambia solo il modo in cui viene disegnata questa lista.

## 8. Tabelle

L'installazione crea tre tabelle quando mancano. Il prefisso del negozio precede ogni nome.

| Tabella | Cosa scrive l'istruzione CREATE |
|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, chiave primaria, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Set di caratteri `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` predefinito 0, `conf` text, `active` predefinito 1. Chiavi `idtoskey` e `id_shop`. L'istruzione CREATE non ha chiave primaria. |
| `gms_log` | `id_gms_log` auto increment, chiave primaria, `id_gms`, `date_add`, `duration_ms`, `items`, `status` predefinito `ok`, `save_file`, `file_name`, `format`, `source` predefinito `url`. |

L'apertura della pagina del catalogo esegue `gms::ensureSchema()`. Questo aggiunge `gms.active` e `gms.id_shop` se mancano, crea `gms_log` se la tabella manca e riempie `id_shop` 0 con `PS_SHOP_DEFAULT`.

Configurazione condivisa che non è una colonna: `pf_tree`, `gm_{campo}` quando il formulario la scrive fuori da un feed, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Risorse della pagina del catalogo: `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. La pagina di configurazione del modulo carica fancybox. Lo script di ricerca degli id viene da `lib/searchTool/`.

## 9. Disinstallazione

`uninstall()` cancella la scheda Catalogo `AdminExportProductsFeedGoogle` e poi esegue la disinstallazione della classe padre. La classe padre toglie il modulo e la registrazione dell'hook.

Il metodo non cancella `pixelgoogle`, `gms` né `gms_log`. Non cancella `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` né le chiavi `gm_`. Non cancella i file scritti in `/modules/gmfeed/`. Un'installazione successiva usa `CREATE TABLE IF NOT EXISTS`, quindi le righe lasciate nelle tabelle restano.

## 10. Supporto

Pagina del modulo: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
