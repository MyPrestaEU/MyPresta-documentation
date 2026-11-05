---
title: "Google Merchant Center Feed - istruzioni per il venditore"
sidebar:
  label: "Google Merchant Center Feed - istruzioni per il venditore"
description: "Come configurare il file prodotti per Google Merchant Center e cosa fare quando quel file non riesce."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google merchant center feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Requisiti

Il modulo gira su PrestaShop 1.6, 1.7, 8 e 9, e su PHP da 5.6 a 8.5.

Il server deve avere cURL e JSON. Non serve un altro modulo.

Con decine di migliaia di prodotti, aprire l'indirizzo del file richiede più tempo e più memoria.

L'account Google Merchant Center lo crea lei.

## 2. Installazione

1. Carichi il modulo in **Moduli**, **Gestione moduli**, e lo attivi.
2. Dopo l'installazione, **Catalogo** ha la voce **Feed di Google Merchant**.
3. Il modulo non svuota la cache durante l'installazione.

La disinstallazione toglie solo la voce di Catalogo. L'elenco dei file, gli abbinamenti delle categorie, i file salvati sul server e l'impostazione dell'albero delle categorie restano. Tornano quando reinstalla il modulo.

## 3. Configurazione

Le immagini arrivano da un back office in inglese. Sotto ci sono i nomi italiani, quando il pannello italiano li mostra.

### 3.1 Pagina delle impostazioni del modulo

Apra **Moduli**, **Gestione moduli**, **Google Merchant Center Feed**, **Configura**. Il titolo è **Impostazioni del modulo**. C'è un campo.

![Impostazioni del modulo](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Mostra albero delle categorie** | **No** | **Sì** mostra le categorie padre mentre abbina le categorie Google. Non sceglie quali prodotti entrano nel file. |

Clicchi **Save**. Compare **Impostazioni salvate correttamente**.

### 3.2 Dashboard

Apra **Catalogo**, **Feed di Google Merchant**. Il titolo è **Feed Google Merchant Center**. La scheda è **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

La dashboard mostra quanti file sono salvati, quante volte oggi qualcuno ha aperto un indirizzo, quante volte negli ultimi 7 giorni e quanti file stanno sul server. Il grafico e l'elenco delle esecuzioni recenti restano vuoti finché qualcuno non apre un indirizzo. In basso c'è l'elenco dei file impostati per il salvataggio sul server.

### 3.3 Elenco dei file

La scheda è **Feed**.

![Feed](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Se l'elenco è vuoto, vede che non ci sono ancora feed e **Crea nuovo feed**.

Quando i file ci sono, la riga mostra stato, nome, negozio, ultima esecuzione e l'indirizzo. **Crea nuovo feed** sta sopra l'elenco.

- L'interruttore accende e spegne il file. L'indirizzo resta.
- Un file dal vivo ha un indirizzo. Google lo legge e l'elenco nasce a ogni apertura.
- Il salvataggio sul server ha due indirizzi. L'indirizzo di generazione costruisce l'elenco e scrive il file. In Google incolli l'indirizzo del file, non quello di generazione. Se il file non c'è ancora, apra prima l'indirizzo di generazione.
- **Edit** apre il formulario. Una copia aggiunge un segno di copia al nome. **Delete** chiede conferma e toglie la riga. Il file sul disco resta.

### 3.4 Aggiornamenti

La scheda è **Aggiornamenti**.

![Aggiornamenti](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **Aggiornamenti MyPresta**
- **Check Now** chiede una volta se esiste una versione più recente.
- Notifiche automatiche: **Enabled** o **Disabled**. **Enabled** controlla circa ogni tre giorni e può mostrare un avviso nel back office.
- **Product Page** apre la pagina del modulo.
- **Save** salva queste impostazioni.

### 3.5 Formulario del file

Clicchi **Crea nuovo feed** o **Edit**. In basso ci sono **Save feed** e **Save & download**.

L'immagine mostra la parte alta del formulario.

![Formulario del file](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Un nome vuoto al salvataggio diventa **Feed senza titolo**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Feed name** | vuoto, obbligatorio | Il nome nell'elenco. |
| **Active** | **Yes** | **No** tiene l'indirizzo. Aprendolo dice che il file è spento. |
| **Shop** | il negozio attuale | Il campo c'è solo con più negozi. L'indirizzo vale nel negozio scelto. |

### 3.6 Opzioni del catalogo

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Remember settings** | **Yes** | Il file nuovo successivo parte dalle stesse scelte. Quello appena salvato tiene le proprie. |

### 3.7 Cosa esportare

Qui sceglie il file che Google leggerà, e se l'elenco nasce all'apertura oppure si scrive sul server.

![Cosa esportare](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Lasci **CSV**, salvo che Google debba ricevere XML. **Products** è una riga per prodotto. L'altra scelta è una riga per variante. **Combination title** compare solo in quel caso. **Save to file** su **No** mostra l'elenco subito. **Yes** lo scrive anche sul server. L'indirizzo copiato dall'elenco ha già la chiave. Senza, vede **Access denied**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Tipo di file | **CSV** | **CSV** o **XML**. |
| Cosa esportare | **Products** | **Products**: una riga per prodotto. L'altra scelta: una riga per variante. |
| **Save to file** | **No** | **No**: l'indirizzo mostra l'elenco subito. **Yes**: l'elenco si scrive anche sul server. Per scrivere, l'indirizzo deve avere la chiave di questa pagina. Senza chiave vede **Access denied**. Entrato nel back office, scrive il file senza incollare la chiave. |
| **File name** | vuoto | Restano lettere, cifre, trattino e trattino basso. Un nome vuoto viene riempito dal tipo di esportazione. |
| Come riconoscere il prodotto | id prodotto | Id prodotto, id variante, o entrambi. È la colonna ID del file. |

### 3.8 Taglia, genere, colore ed età

Google chiede queste colonne per l'abbigliamento e i prodotti simili. Partono spente. Accenda un gruppo solo se il negozio ha davvero quel dato. Gli altri campi compaiono quando il gruppo è su **Yes**.

![Taglia, genere, colore ed età](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

| Gruppo | Campi |
|---|---|
| Taglia | esportare o no, attributo taglia, valore predefinito |
| Genere | esportare o no, origine, caratteristica, attributo, predefinito: male, female, unisex |
| Colore | esportare o no, origine, attributo, caratteristica, valore predefinito |
| Età | esportare o no, origine, caratteristica, attributo, predefinito: newborn, infant, toddler, kids, adult |

### 3.9 Impostazioni del file

Qui c'è il contenuto di una riga: identificatori, spedizione, descrizioni, nomi, giacenza, foto e prezzi. Lasci i valori iniziali se Google deve ricevere un catalogo normale.

![Identificatori e spedizione](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

![Spedizione, descrizioni e nome](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

![Formato, lingua e giacenza](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

![Foto e prezzi](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

Valuta e paese partono da quelli del negozio. L'immagine mostra quelli del negozio di prova.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Id gruppo | **No** | Colonna che lega le varianti di un prodotto. |
| Identificatore unico | UPC | UPC, EAN-13, riferimento, MPN, ISBN o vuoto. Vuoto dice che l'identificatore non esiste. |
| Campo identifier_exists | **No** | Colonna che dice se l'identificatore esiste. |
| Campo adult | non includere | Lasciarlo fuori, includerlo come true o includerlo come false. |
| Prezzo di spedizione | non includere | Calcolato per articolo, oppure scritto a mano. |
| Costo di spedizione aggiuntivo del prodotto | **No** | Somma il supplemento di spedizione dalla scheda prodotto. |
| Importo di spedizione manuale | 0 | L'importo quando la spedizione è manuale. |
| Zona per calcolare la spedizione | la prima zona | La zona da cui esce il prezzo di spedizione. |
| Peso | **No** | Colonna del peso. |
| Tipo di prodotto | **No** | Il suo percorso di categorie nel file. |
| Aggiungere l'id categoria al tipo | **No** | Il numero di categoria accanto al nome. |
| Descrizione breve | descrizione breve | Descrizione breve o descrizione lunga. |
| Togliere l'HTML dalle descrizioni | **No** | **Yes** toglie i tag. |
| Nome prodotto | nome prodotto | Oppure il meta titolo. |
| Titolo della variante | solo il nome | Il nome, il nome più il valore della variante, oppure il nome più «etichetta: valore». |
| Formato del nome | invariato | Prima lettera, ogni parola, oppure tutto minuscolo. |
| Caratteri da togliere dal nome | vuoto | I caratteri che scrive spariscono dal nome. |
| Lingua | lingua del negozio | Nomi e descrizioni nel file. |
| Separatore | barra verticale | Il carattere tra le colonne CSV. |
| Virgolette intorno al testo | **No** | **Yes** avvolge i campi tra virgolette. |
| Informazione di giacenza | la giacenza reale | Tutti disponibili, tutti esauriti, tutti in backorder, oppure il backorder trattato come disponibile. |
| Data di disponibilità | vuoto | La data per i prodotti in backorder che non ne hanno una propria. |
| Quantità | **No** | **Yes** inserisce la quantità. |
| Marca se manca | Default | Il testo della marca quando il prodotto non ha un produttore. |
| Dimensione foto | dimensioni del negozio | Quale dimensione foto mettere nell'indirizzo. |
| Foto prodotto se la variante non ne ha | **No** | Per le varianti senza foto propria. |
| Quante foto | solo la copertina | Oppure tutte le foto. |
| Valuta | valuta del negozio | Prezzi nel file. |
| Imposta nel prezzo | con imposta | Con imposta o senza. |
| Prezzi specifici | **Yes** | Quando la valuta del file non è la valuta con cui guarda il negozio. |
| Gruppo prezzi | gruppo visitatori | Prezzi per quel gruppo di clienti. |
| Prezzo unitario | **No** | Una colonna extra del prezzo per unità. |
| Paese dei prezzi | paese del negozio | Il paese per imposta e sconti. |

### 3.10 Prodotti scelti

Lasci **All** se devono entrare tutti i produttori, i fornitori e le categorie. Una sola scelta taglia il catalogo. Non sostituisce le esclusioni sotto.

![Produttore, fornitore e categoria](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Produttore | **All** | Un produttore, oppure tutti. |
| Fornitore | **All** | Un fornitore, oppure tutti. |
| Categoria | **All** | Una categoria, oppure tutte. |

### 3.11 Esclusioni

Qui escono i prodotti che hanno passato il filtro del punto 3.10. All'inizio non si esclude quasi nulla.

![Esclusioni](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Categorie da saltare | vuoto | Scriva un nome. I prodotti di quella categoria escono. |
| Prodotti senza foto | **No** | **Yes** salta i prodotti senza foto. |
| Disponibilità | tutti i prodotti | Oppure solo quelli attivi nel negozio. |
| Giacenza | tutti i prodotti | Oppure solo quelli disponibili. |
| Saltare per riferimento | spento | Accende un filtro sull'inizio del riferimento. Vale anche per le varianti. |
| Inizio del riferimento | vuoto | Testo da cui il riferimento esce. |
| Saltare più economici di | spento | Una soglia di prezzo nella valuta del negozio. |
| Importo della soglia | vuoto | I prodotti sotto questo importo escono. |
| Prodotti indicati | vuoto | Una ricerca dei prodotti da saltare. |

### 3.12 Limite

Lasci 0 se tutto il catalogo deve stare in un file. Accanto al campo si vede quanti prodotti ha il negozio. Con un hosting stretto, imposti un limite e un numero di parte. L'esempio del formulario: 3000 prodotti e un limite di 1000 danno le parti 1, 2 e 3.

![Limite e codice negozio](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Limite prodotti | 0 | 0 o vuoto significa nessun limite. Accanto si vede il numero di prodotti del negozio. |
| Parte del file | 0 | Il numero di parte quando divide un catalogo in più file. Con 3000 prodotti e un limite di 1000 fa le parti 1, 2 e 3. |

### 3.13 Codice del negozio fisico

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Includere il codice negozio | **No** | Una colonna per il codice del negozio fisico. |
| Codice negozio | vuoto | Lo stesso codice di Google Business. Contano maiuscole e minuscole. |

### 3.14 Categorie Google

In fondo c'è una riga per ogni lingua del negozio. **Pair categories** apre l'abbinamento. **Synchronize** scarica l'elenco Google di quella lingua. Se l'elenco manca, il pulsante è rosso. Nell'immagine en-us ha già il file e fr no.

![Categorie Google](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Mostra albero delle categorie** del punto 3.1 cambia solo il disegno di questo elenco. In fondo ci sono di nuovo **Save & download** e **Save feed**.

**Mostra albero delle categorie** del punto 3.1 cambia solo il disegno di questo elenco. Non cambia quali prodotti entrano nel file.

## 4. Negozio

Il cliente non vede nulla nel negozio. Non c'è un blocco sulla scheda, nel carrello né nel piè di pagina. Non c'è un'immagine del negozio.

C'è un indirizzo che apre Google o il browser. Lo copi dall'elenco. Non lo componga da solo.

Un'apertura dal vivo restituisce CSV o XML. Con il salvataggio sul server, l'indirizzo di generazione scrive il file, e l'indirizzo per Google è quello del file.

Aggiungere parametri propri non cambia nulla. Il modulo usa le impostazioni salvate su quel file.

Salvare il formulario non manda i prodotti a Google. L'elenco nasce all'apertura dell'indirizzo.

| Cosa vede aprendolo | Cosa fare |
|---|---|
| feed does not exists | Il numero è sbagliato, oppure il file è stato tolto. Copi l'indirizzo dall'elenco. |
| Feed is disabled | Accenda **Active**. |
| Feed is not available in this store | Il file appartiene a un altro negozio. |
| Access denied | Il salvataggio sul server è acceso e nell'indirizzo manca la chiave. Copi l'indirizzo dall'elenco. |
| Invalid export path | Accorci il nome del file. |
| Unable to save export file | Controlli lo spazio e il permesso di scrittura nella cartella del modulo. |

## 5. Problemi

**Google mostra ancora i prodotti di ieri.** Il modulo non manda nulla a Google. Apra l'indirizzo e controlli l'elenco. Poi lo scarichi a mano in Merchant Center.

**Nel file non ci sono quasi prodotti.** Controlli se sono rimasti solo i prodotti attivi, solo quelli con giacenza, un produttore, un fornitore, una categoria, esclusioni, un limite o un numero di parte.

**L'albero delle categorie è acceso e il file ha gli stessi prodotti.** L'albero mostra solo le categorie padre durante l'abbinamento.

**Ho disinstallato il modulo e l'elenco è sparito.** Lo reinstalli. I dati restano. È sparita solo la voce di Catalogo.

**Un catalogo grande si interrompe a metà.** Imposti un limite e un numero di parte. Faccia più file.

## 6. Per lo sviluppatore

### 6.1 Panoramica

`gmfeed` 2.4.3. La classe `gmfeed` estende `Module`. Il nome nell'elenco moduli è la stringa fissa `Google Merchant Center Feed`. Autore MyPresta.eu. Scheda `administration`.

Il formulario salva una riga `gms`. Il campo `conf` è una stringa di query. L'indirizzo pubblico legge quella riga, costruisce CSV o XML e chiude la risposta. Il salvataggio su file lo scrive in `/modules/gmfeed/`.

### 6.2 File

- `gmfeed.php`: install, uninstall, la pagina delle impostazioni, la chiave di scrittura e la pulizia di nome, estensione e tipo.
- `controllers/admin/AdminExportProductsFeedGoogle.php`: dashboard, elenco, formulario, salvataggio.
- `controllers/front/feed.php`: generazione. `initContent()` chiama `generateFeed()` e `die()`.
- `model/gms.php`: la riga del file e l'indirizzo. Classe `gms`.
- `model/google.php`: coppie di categorie. Classe `pixelgoogle`.
- `lib/updateChecker.php`: classe `gmfeedUpdate`.
- `lib/searchTool/searchTool.php`: suggerimenti di categorie e prodotti.
- `views/templates/admin/`: `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt`: la tassonomia. Prima riga `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` nella cartella del modulo blocca l'esecuzione di PHP.

### 6.3 Controller

Admin: `AdminExportProductsFeedGoogle`, padre `AdminCatalog`. Viste in `gmfeed_view`: `dashboard`, `feeds`, `form`, `updates`.

Front: `gmfeedfeedModuleFrontController`. Indirizzo `module/gmfeed/feed?feed=` e il numero.

La chiave di scrittura è HMAC-SHA256 di `gmfeed.write.` più l'id negozio, segreto `_COOKIE_KEY_`. Un dipendente connesso scrive senza la chiave. I parametri `export_` e `gmfeed_` in arrivo vengono scartati e sostituiti con quelli salvati. Restano la chiave e `debug_feed`.

Un file spento risponde HTTP 503 e `Feed is disabled`. Un `conf` vuoto o troppo corto termina con `feed does not exists`. Un altro `id_shop` termina con `Feed is not available in this store`.

### 6.4 Hook

C'è un hook: `actionAdminControllerSetMedia`. Carica fancybox e l'autocompletamento solo su `AdminExportProductsFeedGoogle`. Il modulo non espone hook propri. Non ci sono `enable()` né `disable()`.

### 6.5 Override

Questo modulo non sovrascrive classi né controller di PrestaShop.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `pixelgoogle` | Una coppia di categorie: `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | Un file: `name`, `id_shop`, `conf`, `active`. `CREATE` non mette una chiave primaria. |
| `gms_log` | Un'apertura dell'indirizzo: ora, numero, stato, scrittura del file, nome, formato, origine. |

`ensureSchema` sulla pagina catalogo aggiunge `active` e `id_shop`, crea `gms_log` se manca e riempie `id_shop` 0 con il negozio predefinito. La disinstallazione non cancella le tabelle.

### 6.7 Chiavi e traduzioni

`pf_tree`: se la chiave manca, è spento. Il resto del formulario vive in `gms.conf`. **Remember settings** inviato come 1 copia i campi in `gm_{campo}`, senza la chiave di scrittura, il link breve, attivo, il negozio e l'id del file. Con un file aperto, un campo assente usa il valore iniziale del formulario, non la copia `gm_`. Una chiave vecchia `notepad_products` viene copiata in `gmfeed_products` se manca quella nuova.

Aggiornamenti: `mypresta_updates`, `update_gmfeed` (172800 secondi tra i controlli), `updatev_gmfeed`. Se manca `mkey`, viene inviato `nokey`.

Una lingua nuova è un file `translations/{iso}.php`. I testi di `$this->l()` partono dalla fonte inglese. Il nome nell'elenco moduli non passa da `$this->l()`. In `translations/de.php` i testi della pagina impostazioni sono in ceco.

Il tipo di esportazione salvato come `product` in generazione è trattato come `products`. Le estensioni permesse sono `csv`, `xml` e `txt`. Il formulario mostra CSV e XML.

### 6.8 Estendere

Il tema non ha nulla da sovrascrivere sulla pagina del negozio, perché il front non disegna un template. Un altro ordine di colonne richiede di cambiare il codice del modulo. Una tassonomia in un'altra lingua si aggiunge come `google/{codice}.txt`.

## 7. Supporto

Pagina del modulo: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

Per scrivere su questo modulo, acceda all'account cliente su [mypresta.eu](https://mypresta.eu/), apra il [contatto](https://mypresta.eu/contact.html) e scelga l'oggetto **Support for paid modules**. Il formulario indica che l'accesso è obbligatorio. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
