---
title: "Microsoft Merchant Center Product Feed - documentazione e manuale utente"
description: "Manuale per chi possiede già il modulo e deve configurare i feed di Microsoft Merchant Center o risolvere problemi di generazione e catalogo."
sidebar:
  label: "Microsoft Merchant Center Product Feed - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Microsoft Merchant Center Product Feed su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Requisiti

Prima di installare il modulo, verifichi che negozio e hosting soddisfino questi requisiti:

- PrestaShop 1.7, 8 o 9.
- PHP dalla versione 7.1 alla 8.5.
- Estensioni PHP: cURL, JSON, hash e SimpleXML quando genera feed XML.
- Un account Microsoft Merchant Center attivo nel quale creare un catalogo e fornire l'indirizzo del feed.
- Non è richiesto alcun altro modulo PrestaShop.

Un catalogo ampio richiede tempo di esecuzione e memoria PHP sufficienti per raccogliere i prodotti, calcolare prezzi e spedizioni e creare l'output. Se un feed completo supera i limiti dell'hosting, usi **Limit number of products in feed** insieme a **Part of feed** per dividerlo.

## 2. Installazione

1. Apra **Modules → Module Manager**.
2. Faccia clic su **Upload a module** e carichi il file ZIP del modulo.
3. Installi **Microsoft Merchant Center Feed**.
4. Apra **Catalog → Microsoft Merchant Feed**. È l'area per creare feed, copiare indirizzi, controllare le esecuzioni e abbinare le categorie.
5. Se alcuni nomi di categoria si ripetono in rami diversi, apra **Modules → Module Manager**, trovi il modulo, faccia clic su **Configure** e abiliti **Show categories tree**.

L'installazione non svuota la cache di PrestaShop.

Per rimuovere il modulo, lo disinstalli in **Module Manager**. La disinstallazione rimuove **Microsoft Merchant Feed** dal menu **Catalog**, ma conserva feed, cronologia, abbinamenti, impostazioni ricordate, file generati e tassonomie scaricate. Una reinstallazione può quindi riutilizzare questi dati.

## 3. Configurazione e flusso di lavoro del back office

Per pubblicare un catalogo:

1. Apra **Catalog → Microsoft Merchant Feed** e selezioni **Create new feed**.
2. Inserisca un **Feed name**, lasci **Active** su **Yes**, scelga le opzioni, abbini le **Microsoft Categories** e faccia clic su **Save feed**.
3. Scelga un metodo di pubblicazione:
   - Per un feed live, lasci **Save to file** su **No**. Copi la **Live catalog URL**. Microsoft richiama questo indirizzo e il modulo rigenera il feed a ogni richiesta.
   - Per un file statico, imposti **Save to file** su **Yes**. Richiami la **Generate / cron URL** segreta manualmente o tramite pianificazione. Dopo la prima generazione corretta, copi la **Catalog file URL**. Fornisca a Microsoft l'indirizzo del file, mai quello di generazione.
4. Crei o apra il catalogo in Microsoft Merchant Center e incolli l'indirizzo live o del file come origine.
5. Torni a **Dashboard** e verifichi le esecuzioni e la disponibilità del file.
6. Nella sezione **Microsoft Categories**, sincronizzi la tassonomia della lingua e usi **Pair categories** per collegare le categorie del negozio a quelle Microsoft.
7. Per sospendere la pubblicazione senza cambiare indirizzo, disattivi il feed in **Feeds**. **Active** su **No** interrompe la generazione; la riattivazione riprende lo stesso feed allo stesso indirizzo.

Le schermate di questo manuale provengono da un back office in inglese.

### 3.1 Impostazioni del modulo

Apra **Modules → Module Manager**, trovi **Microsoft Merchant Center Feed** e faccia clic su **Configure**.

![Impostazioni del modulo con Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Show categories tree** | No | L'area feed si trova in **Catalog → Microsoft Merchant Feed**. Imposti **Yes** per mostrare il percorso padre di ogni categoria nella finestra di abbinamento e distinguere nomi uguali. Faccia clic su **Save**; la pagina conferma **Settings saved properly**. |

### 3.2 Elenco dei feed

Apra **Catalog → Microsoft Merchant Feed** e selezioni **Feeds**.

![Elenco dei feed](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

Se non esistono feed, la pagina mostra **You have no feeds yet** e **Create your first feed**. In caso contrario:

| Colonna | Contenuto |
|---|---|
| **Status** | **On** o **Off**. Sospende o riprende il feed senza eliminarlo o modificarne l'indirizzo. |
| **Feed** | Nome e badge per formato, prodotti o varianti, lingua e modalità **Live** o **File**. |
| **Shop** | Negozio proprietario. In modalità multistore, un feed esterno al negozio corrente è **Not available in this store**. |
| **Last run** | Numero di elementi e ora dell'ultima esecuzione. Prima del primo richiamo: **Never** e **No cron call yet**. |
| **Catalog URL** | In modalità live, indirizzo **Live catalog**. In modalità file, indirizzi **Generate / cron** segreto e **Catalog file** pubblico. Li copi con il pulsante adiacente. |
| **Actions** | Comandi disponibili. |

- **Edit** apre tutte le opzioni salvate.
- **Duplicate** crea una copia da controllare. Modifichi nome, file, negozio, filtri o altre opzioni se deve essere indipendente.
- **Generate** richiama il generatore in modalità file.
- **Open file** apre il file salvato.
- **Open** genera e apre un feed live.
- **Delete** elimina definitivamente il record dopo conferma.

Dopo un'operazione possono apparire:

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Selezioni **Dashboard** per controllare l'attività.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

Il riepilogo mostra **Saved feeds**, **Cron runs today**, prodotti generati oggi, **Runs last 7 days**, durata media e **Saved files** pronti. **Catalog generation activity** copre 14 giorni. **Recent runs** elenca feed, ora, elementi, durata, formato e scrittura del file.

La tabella **Generated files** mostra negozio, nome, dimensione, stato e aggiornamento. **Waiting for first cron** significa che l'indirizzo di generazione non ha ancora prodotto il file. **On disk** significa che il file è disponibile.

### 3.4 Scheda Updates

Selezioni **Updates** per confrontare il modulo con gli aggiornamenti MyPresta.

![Scheda Updates](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Manual Check** | Nessun risultato fino al controllo | Faccia clic su **Check Now** dopo l'installazione o quando attende una versione. Il modulo mostra **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Preferenza MyPresta condivisa corrente | **Enabled** controlla ogni tre giorni circa e avvisa i dipendenti. **Disabled** è adatto al controllo manuale. Faccia clic su **Save**. |
| **Product Page** | Collegamento disponibile | Apre la pagina ufficiale e le risorse di supporto. Non richiede impostazioni. |

### 3.5 Creare/modificare un feed

Selezioni **Create new feed** o faccia clic su **Edit**. I campi seguono l'ordine sullo schermo. Le opzioni dipendenti dal negozio derivano da lingue, valute, paesi, gruppi, tipi di immagine, caratteristiche, attributi, categorie, produttori, fornitori, zone e negozi configurati in PrestaShop.

**Save feed** salva e torna all'elenco. **Save & download** salva e scarica subito un CSV o XML. Durante la modifica appaiono anche la **Live catalog URL** oppure **Generate / cron URL** e **Catalog file URL**.

![Creazione o modifica: nome, stato, formato, tipo e modalità file](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Identità e output del feed**

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Feed name** | Vuoto | Inserisca un nome obbligatorio e riconoscibile. Un invio vuoto arrivato al salvataggio diventa **Untitled feed**. |
| **Active** | Yes | Lo lasci attivo per consentire la generazione. **No** sospende il feed conservando indirizzo e impostazioni. |
| **Shop** | Negozio corrente; solo multistore | Assegna il feed a un negozio. L'indirizzo funziona solo per quel negozio. |
| **Remember settings** | Yes | Ricorda le scelte per il prossimo feed. Usi **No** se non devono diventare valori iniziali. |
| **Type of file module will generate** | CSV | **CSV** crea un feed di testo; **XML** un feed Atom. Per TSV scelga **CSV** e `Tab` in **Delimiter**. |
| **What you want to export?** | Products | **Products** crea una riga per prodotto; **All products variants** esporta le combinazioni separatamente. |
| **Save to file** | No | **No** genera il feed a ogni richiesta. **Yes** fa scrivere un file statico dall'indirizzo segreto; a Microsoft fornisca l'indirizzo pubblico separato. |
| **File name** | Vuoto | Con **Save to file**, indichi il nome base. Se vuoto, usa il tipo di esportazione. Preferisca lettere, numeri, trattini e underscore. |
| **How to identify product?** | `id_product` | Scelga `id_product`, `id_combination` o `id_product-id_attribute`. Usi un'opzione che considera le combinazioni quando esporta varianti separate. |

**Taglia, genere, colore e fascia d'età**

![Campi per taglia, genere, colore ed età](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Export size** | No | **Yes** include `size`. |
| **Size attribute** | None | Selezioni il gruppo della taglia. Tenga premuto Ctrl per più gruppi. Se manca un valore usa **Default size value**. |
| **Default size value** | Vuoto | Taglia sostitutiva. |
| **Export gender** | No | **Yes** include `gender`. |
| **Export gender value from** | Nessuna origine | Scelga **Attribute** o **Feature** e completi il campo corrispondente. |
| **Gender feature** | Nessuna caratteristica | Con **Feature**, scelga la caratteristica del genere. |
| **Gender attribute** | Nessun attributo | Con **Attribute**, scelga il gruppo del genere. |
| **Default gender value** | Vuoto | Scelga **Male**, **Female** o **Unisex** come valore sostitutivo. |
| **Export color** | No | **Yes** include `color`. |
| **Export color value from** | Nessuna origine | Scelga **Attribute** o **Feature**. |
| **Color attribute** | Nessun attributo | Gruppo che contiene il colore. |
| **Color feature** | Nessuna caratteristica | Caratteristica che contiene il colore. |
| **Default color value** | Vuoto | Valore sostitutivo. Usi nomi di colori in inglese, accettati da Microsoft. |
| **Export age_group** | No | **Yes** include `age_group`. |
| **Export age group value from** | Nessuna origine | Scelga **Attribute** o **Feature**. |
| **age group feature** | Nessuna caratteristica | Caratteristica della fascia d'età. |
| **age group attribute** | Nessun attributo | Gruppo della fascia d'età. |
| **Default age group value** | Nessun valore | Scelga **adult**, **kids**, **toddler**, **infant** o il valore mostrato **newbord**. In produzione usi valori accettati da Microsoft. |

**Campi, spedizione, testo, scorte, immagini e prezzi**

![Impostazioni con identificatori, spedizione, descrizioni, lingua e delimitatore](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Include item_group_id** | No | **Yes** raggruppa varianti diverse per taglia, colore, motivo, età o genere. |
| **Unique product identifier** | Product UPC barcode | Scelga **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code** o **Make this field empty, identifier_exists field will have value false then**. Fornisca gli identificatori del produttore disponibili. |
| **Include identifier_exists field** | No | **Yes** aggiunge `identifier_exists`. |
| **Include adult field** | Do not include | Scelga **Include as true**, **Include as false** o **- do not include -**. Non usi l'etichetta estranea **Lowercase all letters, example: product name**. |
| **Include shipping price** | Do not include | Scelga **Do not include**, **Include (shipping price calculated for each item separately)** o **Set shipping price manually**. Il calcolo automatico è per articolo. |
| **Include product's additional shipping cost** | No | **Yes** aggiunge il supplemento di spedizione del prodotto. |
| **Manual shipping value** | 0 | Importo applicato a ogni articolo in modalità manuale. |
| **Automatic shipping price zone select** | Zona iniziale | Zona di destinazione per il calcolo automatico, più oneroso di un importo fisso. |
| **Include weight** | No | **Yes** include il peso nell'unità del negozio. |
| **Product type** | No | **Yes** include la struttura delle categorie come `product_type`. |
| **Product type - include category ID** | No | Aggiunge l'ID per distinguere categorie omonime. |
| **Short description** | Short description | Scelga **Short description** o **Long description** come origine. |
| **Remove html from descriptions** | Yes | Microsoft richiede testo semplice. Tag e interruzioni vengono eliminati anche con **No**; mantenga **Yes**. |
| **Product name** | Product name | Scelga **Product name** o **Meta title**. |
| **Format name** | Do not format name | Nessuna modifica, iniziale o ogni parola maiuscola, oppure tutto minuscolo. |
| **Remove selected characters from product name** | Vuoto | `x=,` rimuove `x`, `=` e `,`. Lasci il campo realmente vuoto per non rimuovere nulla. |
| **Language** | Lingua predefinita | Lingua di titoli, descrizioni e dati tradotti. |
| **Delimiter** | `|` | Separatore CSV. Inserisca `Tab` per TSV, raccomandato da Microsoft. Non influisce su XML. |
| **Wrap strings in double quotes** | Yes | Evita che separatori o caratteri speciali interrompano le righe CSV. |
| **Information about stock** | Include real stock information | Usi la disponibilità reale o forzi **in-stock**, **out-of-stock** o **backorder**. L'ultima opzione segnala come disponibili i prodotti con ordini arretrati consentiti. |
| **Availability date** | Vuoto | Data sostitutiva richiesta per prodotti arretrati senza data propria. |
| **Include quantity info** | No | **Yes** include la quantità di prodotto o combinazione. |
| **Default manufacturer value** | `Default` | Marca sostitutiva per prodotti senza produttore. |
| **Image size for product pictures** | Tipo iniziale del negozio | Tipo immagine PrestaShop usato negli indirizzi. |
| **Use default product picture if combination will not have associated photo** | No | **Yes** usa l'immagine principale se una combinazione non ha foto. |
| **How many pictures you want to export?** | Export cover only | Scelga **Export cover only** o **Export all pictures**, che aggiunge altri link. |
| **Currency** | Valuta predefinita | Valuta dei prezzi; deve corrispondere al mercato Microsoft. |
| **Price tax included or excluded** | Price Tax Included | Include o esclude le imposte dai prezzi normali e scontati. |
| **Include specific prices** | Yes | Mantenga attivo se i prezzi specifici PrestaShop devono essere riflessi. |
| **Export prices for selected group** | Gruppo cliente non identificato | Contesto prezzo usato dal modulo. |
| **Export also unit price** | No | **Yes** include le misure di prezzo unitario disponibili. |
| **Export prices for selected country** | Paese predefinito | Contesto nazionale per imposte e sconti. |

**Selezione, esclusioni, limiti, inventario locale e categorie**

![Filtri, limiti, codice negozio e Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Campo | Valore iniziale | Funzione |
|---|---|---|
| **Product Manufacturer** | All | Tutti i produttori o quello selezionato. |
| **Product Supplier** | All | Tutti i fornitori o quello selezionato. |
| **Product Category** | All | Tutte le categorie o quella selezionata. |
| **Exclude categories** | Vuoto | Cerchi e aggiunga categorie da escludere. I prodotti assegnati vengono omessi. |
| **Exclude products without pictures** | No | **Yes** esclude prodotti senza immagine utilizzabile. |
| **Products's availability** | Export all products | **Export only active products** esclude i prodotti disabilitati. |
| **Products's stock** | Export all products | **Export only in-stock products** esclude quelli senza scorte. |
| **Exclude products with specific reference** | No | **Yes** abilita il filtro per prefisso del riferimento. |
| **Exclude product where reference starts with:** | Vuoto | Prefisso da escludere per prodotti e combinazioni. |
| **Exclude products worth less than defined value** | No | **Yes** esclude sotto un valore minimo nella valuta predefinita. |
| **Value of products (worth less) to exclude** | Vuoto | Minimo usato dal filtro precedente. |
| **Exclude products** | Elenco vuoto | Cerchi e selezioni un prodotto. **Add all search results** aggiunge tutti i risultati; il pulsante rimuove un elemento. |
| **Limit number of products in feed** | 0 | Numero massimo. Vuoto o `0` significa nessun limite. Lo usi quando tempo o memoria non bastano. |
| **Part of feed** | 0 | `0` senza divisione. Per 3.000 prodotti con limite 1.000, crei le parti 1, 2 e 3. |
| **Include store code to feed** | No | **Yes** identifica un negozio fisico nel feed di inventario locale. Usi lo stesso ID dell'account Microsoft. |
| **Store code** | Vuoto | Identificatore alfanumerico esatto, sensibile alle maiuscole. |
| **Microsoft Categories** | Tassonomia non necessariamente sincronizzata | Controlli ogni lingua. Faccia clic su **Synchronize** o scelga **Synchronize specific**, quindi **Pair categories**. L'icona di ripetizione applica un valore a tutti i campi; quella di eliminazione rimuove l'abbinamento. |

## 4. Storefront e indirizzi del feed

Il modulo non aggiunge blocchi, pulsanti, contenuti prodotto, moduli, pagine account o altre interfacce al negozio. I clienti non interagiscono con esso.

- **Live catalog URL** rigenera il catalogo a ogni richiesta, senza salvare un file statico.
- **Generate / cron URL** contiene il segreto di scrittura. La richiami con un pianificatore o **Generate** e non la fornisca a Microsoft.
- **Catalog file URL** punta al file statico. La usi come origine quando **Save to file** è attivo.

| Messaggio | Azione |
|---|---|
| **Feed is disabled** | In **Feeds**, imposti **On** oppure **Active** su **Yes**. |
| **feed does not exists** | Copi di nuovo l'indirizzo da **Feeds**. Il feed è stato eliminato, l'indirizzo è incompleto o la configurazione non è valida. |
| **Feed is not available in this store** | Passi al negozio assegnato, modifichi **Shop** e ricopi l'indirizzo. |
| **Access denied** | Usi la **Generate / cron URL** completa senza modificare la parte segreta. |

## 5. Problemi e soluzioni

### 5.1 Il feed risulta disabilitato

**Sintomo:** **Feed is disabled**.  
**Causa:** Lo stato è spento o **Active** è **No**.  
**Azione:** Apra **Catalog → Microsoft Merchant Feed → Feeds** e imposti **On**. L'indirizzo rimane valido.

### 5.2 Il feed non esiste

**Sintomo:** **feed does not exists**.  
**Causa:** Feed eliminato, indirizzo incompleto o configurazione inutilizzabile.  
**Azione:** Copi nuovamente l'indirizzo da **Feeds** o ricrei il feed.

### 5.3 Il feed appartiene a un altro negozio

**Sintomo:** **Not available in this store** o **Feed is not available in this store**.  
**Causa:** Assegnazione a un altro negozio multistore.  
**Azione:** Passi al negozio assegnato oppure modifichi **Shop**, salvi e ricopi l'indirizzo.

### 5.4 La generazione del file nega l'accesso

**Sintomo:** **Access denied** e file non aggiornato.  
**Causa:** Nell'indirizzo manca l'autorizzazione segreta.  
**Azione:** Copi di nuovo **Generate / cron URL**, la usi senza modifiche e la mantenga privata.

### 5.5 Microsoft riceve la risposta del generatore

**Sintomo:** Il recupero non riesce o rigenera a ogni richiesta con **Save to file** attivo.  
**Causa:** A Microsoft è stata fornita la **Generate / cron URL**.  
**Azione:** La usi solo nel pianificatore, verifichi **On disk** in **Dashboard** e fornisca **Catalog file URL**.

### 5.6 Il feed è vuoto o incompleto

**Sintomo:** La generazione riesce con meno elementi del previsto.  
**Causa:** Filtri di produttore, fornitore, categoria, esclusioni, immagine, stato, scorte, riferimento, valore, limite o parte rimuovono prodotti.  
**Azione:** Scelga temporaneamente **All**, disabiliti le esclusioni, svuoti gli elenchi e imposti limite e parte su `0`. Reintroduca i filtri uno alla volta.

### 5.7 Mancano le categorie Microsoft

**Sintomo:** Valori assenti o ricerca impossibile in **Pair categories**.  
**Causa:** Tassonomia non sincronizzata o categorie non abbinate.  
**Azione:** In **Microsoft Categories**, usi **Synchronize** o **Synchronize specific**, quindi **Pair categories**.

### 5.8 Un catalogo ampio esaurisce tempo o memoria

**Sintomo:** Interruzione, lentezza o file non aggiornato.  
**Causa:** L'hosting non elabora catalogo, prezzi, immagini e spedizione automatica in una sola esecuzione.  
**Azione:** Definisca **Limit number of products in feed**, crei valori consecutivi di **Part of feed**, preferisca se opportuno una spedizione fissa e pianifichi le parti separatamente.

### 5.9 Microsoft segnala problemi di qualità

**Sintomo:** Avvisi su identificatori, descrizioni, prezzi, disponibilità, immagini, varianti, età, genere, colori o spedizione.  
**Causa:** Origini vuote, valori non ammessi o mercato incoerente.  
**Azione:** Allinei **Language**, **Currency**, paese e imposte. Fornisca GTIN, marca, testo semplice, disponibilità, immagini e categorie. Per l'abbigliamento controlli **size**, **gender**, **color**, **age_group** e **item_group_id**, quindi rigeneri.

## 6. Riferimento per sviluppatori

### 6.1 Panoramica del modulo

| Elemento | Valore |
|---|---|
| Nome tecnico | `mmcfeed` |
| Versione | `1.1.0` |
| Nome visualizzato | `Microsoft Merchant Center Feed` |
| Autore | `MyPresta.eu` |
| Scheda modulo | `administration` |
| Scheda back office | `AdminExportProductsFeedMicrosoft`, sotto `AdminCatalog` |
| Endpoint frontale | `controllers/front/feed.php` |

`mmcfeed` estende `Module`. L'ObjectModel `mmc` memorizza nome, negozio, stato attivo e configurazione serializzata. Download immediati e controller frontale creano CSV o XML dai dati PrestaShop. La modalità file scrive un nome sanificato nella directory del modulo; quella live trasmette la risposta.

### 6.2 File e classi importanti

| File | Responsabilità |
|---|---|
| `mmcfeed.php` | Metadati, installazione, modulo globale, sanificazione, percorsi sicuri e convalida HMAC. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, elenco, modulo, duplicazione, eliminazione, tassonomia, esportazione e valori ricordati. |
| `controllers/front/feed.php` | Carica e convalida il feed, applica opzioni, trasmette o scrive il file. |
| `model/mmc.php` | ObjectModel `mmc`, schema, URL, elenco, log, statistiche e file. |
| `model/categorymap.php` | ObjectModel `pixelgoogle` per gli abbinamenti. |
| `model/google.php` | Duplica `pixelgoogle` di `model/categorymap.php`; caricarli entrambi ridefinisce la classe. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, controlli e modulo Updates. |
| `lib/searchTool/searchTool.php` | Completamento automatico di prodotti e categorie. |
| `views/templates/admin/layout.tpl` | Intestazione, navigazione, avvisi e risorse. |
| `views/templates/admin/feeds.tpl` | Schede, URL, stati e azioni. |
| `views/templates/admin/dashboard.tpl` | KPI, grafico, esecuzioni e file. |
| `views/templates/admin/form-chrome.tpl` | Intestazione del modulo e URL. |
| `views/category_taxonomy.tpl` | Stato, sincronizzazione e abbinamento. |
| `views/categories-fancybox.tpl` | Finestra categorie e percorsi padre. |
| `views/exclude-products.tpl` | Completamento e lista di esclusione. |
| `views/js/admin-app.js` e `views/css/admin-app.css` | Interazioni e stile. |

### 6.3 Controller e flusso delle richieste

`AdminExportProductsFeedMicrosoftController` estende `ModuleAdminController`. `mmcfeed_view` seleziona `dashboard`, `feeds`, `updates` o `form`. Gestisce:

- `saveonly` per salvare e tornare all'elenco;
- `submitExport` per salvare e scaricare;
- `updatemmc` con `id_mmc`;
- `duplicatemmc` e `deletemmc`;
- AJAX `toggleFeedActive`;
- sincronizzazione, abbinamento, completamento e salvataggio/eliminazione delle associazioni via AJAX.

`mmcfeedfeedModuleFrontController` estende `ModuleFrontController`. Accetta l'ID salvato, carica solo parametri memorizzati, rifiuta feed mancanti, disabilitati o di un altro negozio e genera. La modalità file richiede `mmcfeed_write_key`. I parametri esterni di debug ed esportazione vengono ignorati per impedire la sostituzione delle impostazioni.

I file `index.php` sono segnaposto; non esiste un secondo controller frontale funzionante.

### 6.4 Hook e ciclo di vita

L'unico hook è `actionAdminControllerSetMedia`. Per `AdminExportProductsFeedMicrosoft` abilita Fancybox e il completamento jQuery, senza output front office.

Il modulo non definisce metodi `enable()` o `disable()` personalizzati né hook propri.

`install()` richiama il genitore, registra l'hook, crea scheda e tabelle e completa lo schema senza svuotare la cache. `uninstall()` rimuove la scheda e richiama `parent::uninstall()` senza eliminare tabelle, configurazioni, feed, file o tassonomie.

### 6.5 Override

Il modulo non installa override di classi o controller PrestaShop.

### 6.6 Database

Il prefisso effettivo è quello configurato dal negozio.

| Tabella | Contenuto |
|---|---|
| `pixelgoogle` | Abbinamenti: `id_pixelgoogle`, precedente `id_google`, `id_category`, `id_lang` e `value`. |
| `mmc` | Feed: `id_mmc`, `name`, `id_shop`, `conf` serializzato e `active`. I controlli completano gli impianti precedenti. |
| `mmc_log` | Cronologia: ID, data, durata, elementi, stato, modalità file, nome, formato e origine. Le voci oltre 90 giorni sono rimosse quando si registra un'esecuzione. |

La disinstallazione conserva tutte le tabelle, i feed, gli abbinamenti e la cronologia.

### 6.7 Chiavi di configurazione e valori predefiniti

| Chiave | Valore o comportamento |
|---|---|
| `mmc_pf_tree` | Se assente vale `0`; controlla i percorsi padre. |
| `mypresta_updates` | Preferenza condivisa; se assente, controllo periodico disabilitato. |
| `update_mmcfeed` | Timestamp dell'ultimo controllo. |
| `updatev_mmcfeed` | Ultima versione restituita. |

Con **Remember settings**, i valori usano il prefisso `mmc_`:

| Chiavi | Valori di ripiego |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` o false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` o true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Precedente `product`, normalizzato in `products`. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Valori predefiniti del negozio. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Precedente `all`; opzione visibile **All**. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Stringa vuota. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | ID separati da virgole; vuoto. |
| `mmc_mmcfeed_products` | ID esclusi separati da virgole; vuoto. |

Il modulo legge anche `delete_images` come `mmc_delete_images`, sebbene non abbia un campo visibile. La disinstallazione non elimina queste chiavi.

### 6.8 File generati, tassonomia, sicurezza ed estensioni

I feed sono scritti come `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}`. I nomi sono limitati a lettere, numeri, trattini e underscore; i controlli impediscono di uscire dalla directory. Le tassonomie sono in `modules/mmcfeed/google/{language-code}.txt`. Nessuno dei due gruppi viene rimosso.

Il token è `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. Un dipendente può scrivere direttamente; una chiamata esterna deve presentare il token, confrontato con `hash_equals`. Il controller scarta parametri non attendibili `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*`, di limite, debug ed esclusione prima di applicare la configurazione.

CSV usa `fputcsv`, un delimitatore normalizzato e virgolette doppie. Il testo decodifica le entità, normalizza gli spazi e rimuove interruzioni, tab e HTML. XML usa `SimpleXMLElement`. Gli aggiornamenti usano cURL o l'accesso URL ai file.

Le traduzioni usano `translations/{iso}.php`. La maggior parte delle stringhe passa dalle chiamate di traduzione; alcune etichette, come **All**, **Price Tax Included** e **Price Tax Excluded**, restano in inglese. Le descrizioni dei campi sono negli array HelperForm del controller; quelle degli aggiornamenti in `lib/updateChecker.php`.

Non esiste un template front office sovrascrivibile dal tema. I template Smarty del back office richiedono la modifica o l'estensione del modulo. Per una personalizzazione sicura usi un fork mantenuto o un'integrazione separata; non è esposto alcun hook formale.

## 7. Assistenza

Pagina del prodotto: [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

Per ricevere assistenza, acceda al suo account mypresta.eu, apra la pagina dei contatti e selezioni **Support for paid modules**. Dopo l'accesso scelga il modulo dalla cronologia acquisti e descriva feed, negozio e messaggio esatto.
