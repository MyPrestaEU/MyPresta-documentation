---
title: "Caratteristiche delle combinazioni - manuale del commerciante"
description: "Manuale di configurazione e risoluzione problemi per chi ha già il modulo installato."
sidebar:
  label: "Caratteristiche delle combinazioni - manuale del commerciante"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product combination features su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-combination-features/)
>
> ---


Nome tecnico: `combfeat`. Versione **1.4.0**. Nel back-office il modulo si chiama **Caratteristiche delle combinazioni**.

## 1. Requisiti e compatibilità

- **PrestaShop:** da 1.7.0.0 a 9.x (`ps_versions_compliancy` fino a 9.99.99).
- **PHP:** la versione richiesta da quella versione di PrestaShop.
- **Scheda prodotto:** il tema deve esporre la combinazione scelta nell’attributo `data-product` di `#product-details` (standard di PrestaShop) e lanciare l’evento `updatedProduct` al cambio degli attributi. Classic e i temi che ne derivano lo fanno.
- **PrestaShop 8 e 9, scheda Moduli del prodotto:** il file `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` deve essere scrivibile all’installazione o alla prima apertura della configurazione. Vedi la sezione 3.
- **Navigazione a faccette (facoltativa):** `ps_facetedsearch` installato, permesso di creare una vista SQL e scrittura su `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Controllo aggiornamenti (facoltativo):** `allow_url_fopen` perché il modulo possa chiamare `https://dev.mypresta.eu`.

## 2. Dove lavorare nel back-office

| Luogo | Percorso | A cosa serve |
| --- | --- | --- |
| Configurazione del modulo | **Moduli > Gestore moduli**, cerca **Caratteristiche delle combinazioni**, **Configura** | Interruttori, selettori CSS, modalità titolo, navigazione a faccette, importazione CSV, aggiornamenti |
| Contenuto della combinazione | **Catalogo > Prodotti**, modifica il prodotto, scheda **Moduli**, blocco **Contenuto della combinazione** | Caratteristiche, descrizione e titoli di ogni combinazione |
| Catalogo caratteristiche | **Catalogo > Attributi e caratteristiche** (il nome dipende dalla versione di PrestaShop) | Creare caratteristiche e valori prima di assegnarli al prodotto. L’importazione CSV può creare quelli mancanti |
| Modello della navigazione a faccette | Configurazione del modulo Navigazione a faccette | Aggiungere la caratteristica al modello dei filtri. Questo modulo non lo fa da solo |

Il modulo non ha una voce di menu propria e non ha un controller di negozio o di back-office.

## 3. File che il modulo modifica

### 3.1 Scheda Moduli del prodotto in PrestaShop 8 e 9

All’installazione, e a ogni apertura della pagina di configurazione, il modulo modifica:

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

Sostituisce `{{ module.content|raw_purified }}` con `{{ module.content|raw }}`. La prima volta copia il file originale in `modules-content.html.twig.raw.bak` accanto.

PrestaShop 8 e 9 depurano l’HTML stampato dai moduli nella scheda prodotto. Senza questa modifica l’editor **Contenuto della combinazione** è vuoto oppure i suoi campi non partono con il salvataggio del prodotto. In PrestaShop 1.7 quel file Twig non esiste. Il modulo salta la modifica.

Se il file non si può leggere o scrivere, il modulo non mostra un errore. Controlla i permessi se la scheda Moduli resta vuota.

### 3.2 Adattatore della navigazione a faccette

Con **Filter combination features in Faceted Search** attivo (valore predefinito), il modulo crea la vista SQL `{prefix}combfeat_feature_product` e punta `modules/ps_facetedsearch/src/Adapter/MySQL.php` a quella vista. La vista è l’elenco delle caratteristiche del prodotto più le caratteristiche attive delle combinazioni.

Disattivare l’opzione, disattivare il modulo o disinstallarlo riscrive il sorgente originale dell’adattatore. La disinstallazione elimina anche la vista quando l’adattatore non la cita più.

La pagina di configurazione mostra un avviso se la vista non si può creare, se il file dell’adattatore manca, non è leggibile, non è scrivibile, o non coincide con il sorgente Faceted Search atteso. I messaggi (in inglese nel modulo):

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Configurazione del modulo

Apri **Configura**. Nella pagina ci sono due formulari, poi il pannello **Aggiornamenti MyPresta**. **Salva** nel formulario **Impostazioni** invia `submitCombfeatSettings`. **Import** invia `submitCombfeatImport`.

### 4.1 Attiva le caratteristiche per le combinazioni

Chiave: `combfeat_p_feat`. Predefinito: **Abilitato**.

Se è attivo, ogni combinazione nella scheda **Moduli** del prodotto ha una scheda **Caratteristiche**. Lì si agganciano valori già esistenti.

Se è disattivo, quella scheda è nascosta. Lo script del negozio è un altro punto: caratteristiche e descrizioni le aggiorna lo stesso script, descritto nella sezione 6.

**Salvare un prodotto con questo interruttore spento cancella le caratteristiche di combinazione di quel prodotto.** Il formulario del prodotto non contiene più i campi delle caratteristiche. Un salvataggio svuota le righe delle caratteristiche del modulo per il prodotto e riscrive solo ciò che il formulario ha inviato. Descrizioni e titoli restano. Riattiva l’opzione prima di modificare il prodotto se quelle caratteristiche devono restare.

### 4.2 Classe CSS della scheda tecnica

Chiave: `combfeat_ds`. Predefinito: `.data-sheet`.

Un selettore jQuery. Il modulo sostituisce l’**HTML interno** dell’elemento trovato con coppie:

```html
<dt class="name">Caratteristica</dt><dd class="value">Valore</dd>
```

Punta al `<dl>` che contiene già quelle righe. Nel tema Classic è `dl.data-sheet`, quindi il valore predefinito è quello giusto. Un blocco più ampio, come `.product-features` o `#product-details`, viene sostituito per intero dalle coppie `<dt>` / `<dd>`.

Se il selettore non trova nulla e la combinazione scelta ha caratteristiche, il modulo sostituisce tutto il contenuto di `#product-details` con una nuova sezione di scheda tecnica. Spariscono riferimento, marca e il resto di ciò che stava in `#product-details`. Imposta il selettore in modo che questo ripiego non scatti.

### 4.3 Flusso di lavoro

Chiave: `combfeat_workflow`. Predefinito: **Sostituisci le caratteristiche esistenti del prodotto** (valore `0`).

| Opzione | Valore | Scheda tecnica dopo la scelta di una combinazione |
| --- | --- | --- |
| **Sostituisci le caratteristiche esistenti del prodotto** | `0` | Le caratteristiche della combinazione sostituiscono la scheda tecnica. Se la combinazione non ne ha, vengono riscritte quelle del prodotto. |
| **Aggiungi alla lista esistente delle caratteristiche del prodotto** | `1` | Le caratteristiche del prodotto restano per prime. Quelle della combinazione seguono. Se la combinazione non ne ha, si vedono solo quelle del prodotto. |

Lo stesso valore sul prodotto e sulla combinazione compare due volte nella modalità **Aggiungi**. Il modulo non toglie i duplicati.

Sono ammessi più valori della stessa caratteristica. Ogni valore è una riga. L’ordine segue la posizione della caratteristica nel catalogo.

**Il flusso di lavoro cambia solo la scheda tecnica.** La descrizione viene sempre sostituita, in entrambe le modalità. Vedi la sezione 6.4.

Lo script del negozio dipende da questa impostazione: `views/js/combfeat.js` per Sostituisci, `views/js/combfeat-append.js` per Aggiungi.

### 4.4 Filter combination features in Faceted Search

Chiave: `combfeat_faceted`. Predefinito: **Enabled**.

L’etichetta a schermo è in inglese: **Filter combination features in Faceted Search**. Quel testo non è ancora nei file di traduzione del modulo. Anche il testo di aiuto è in inglese: i valori che esistono solo sulle combinazioni compaiono in `ps_facetedsearch`, e un prodotto viene contato se il valore è sul prodotto o su una qualsiasi combinazione. La caratteristica va aggiunta al modello Faceted Search. L’elenco delle caratteristiche del prodotto non cambia.

Con `ps_facetedsearch` installato e l’interruttore attivo:

- Nei filtri di categoria possono comparire valori che esistono solo sulle combinazioni.
- Un prodotto viene contato se il valore è sul prodotto **o su una qualsiasi delle sue combinazioni**. Il filtro non dipende dalla combinazione che il visitatore sceglierà dopo. Un prodotto conta una volta, anche se più combinazioni portano il valore.
- La caratteristica va comunque aggiunta al modello della navigazione a faccette. Il modulo non modifica i modelli.
- L’elenco delle caratteristiche nella scheda prodotto del catalogo resta com’è.

Dopo il salvataggio delle caratteristiche di combinazione, o dopo un’importazione CSV, il modulo svuota la cache dei blocchi della navigazione a faccette (`layered_filter_block`) perché i filtri si ricostruiscano.

### 4.5 Attiva le descrizioni per le combinazioni

Chiave: `combfeat_p_desc`. Predefinito: **Abilitato**.

Nel testo sorgente inglese l’etichetta è **Turn on descriptionsfor combinations** (manca lo spazio prima di «for»). La traduzione italiana è **Attiva le descrizioni per le combinazioni**.

Se è attivo, ogni combinazione ha una scheda **Descrizione** con un campo di testo formattato per ogni lingua del negozio.

Se è disattivo, quella scheda è nascosta e il salvataggio del prodotto non cambia le descrizioni già salvate. Se le caratteristiche restano attive, lo script del negozio gira ancora e applica una descrizione salvata prima. Svuota i campi, salva e solo dopo spegni l’interruttore se il negozio non deve più usarle.

### 4.6 Descrizione della classe CSS / ID oggetto

Chiave: `combfeat_description`. Predefinito: `#description`.

Selettore jQuery del blocco il cui HTML viene sostituito dalla descrizione della combinazione. Nel tema Classic `#description` è la scheda della descrizione lunga, quindi il valore predefinito punta a quel blocco.

Se il selettore non trova nulla, la descrizione nella pagina non viene toccata.

Il testo usato quando una combinazione non ha una descrizione è la **descrizione lunga** del prodotto (`description`), nella lingua corrente. Non è la descrizione breve e non è la meta descrizione. Se questo selettore punta al blocco della descrizione breve, una combinazione senza testo proprio riempie quel blocco con la descrizione lunga.

### 4.7 Attiva il meta titolo per le combinazioni

Chiave: `combfeat_p_title`. Predefinito: **Abilitato**.

Se è attivo, la scheda prodotto carica `views/js/combfeat-title.js`. Scegliere una combinazione aggiorna `document.title` e, se presente, `<meta property="og:title">`.

Il titolo nell’HTML inviato dal server resta il meta titolo del prodotto. Il visitatore vede il titolo della combinazione dopo l’esecuzione di JavaScript. Un crawler che non esegue JavaScript tiene il titolo del prodotto.

Se è disattivo, la scheda **Meta titolo** è nascosta, lo script non viene caricato e il salvataggio non cambia i titoli salvati.

### 4.8 Modalità titolo predefinita

Chiave: `combfeat_title_default`. Predefinito: **Aggiungi nome attributo e valore (separati da virgola)** (valore `1`).

Si usa solo quando quella combinazione non ha **Titolo completo** né **Aggiungi al titolo** nella lingua corrente.

Il titolo di partenza è il titolo del browser memorizzato al primo caricamento della pagina. I cambi successivi non lo memorizzano di nuovo, quindi i frammenti aggiunti non si accumulano.

| Opzione | Valore | Risultato |
| --- | --- | --- |
| **Non modificare il titolo di default** | `0` | Resta il titolo di documento originale. |
| **Aggiungi nome attributo e valore (separati da virgola)** | `1` | Titolo originale, poi il separatore, poi gruppi e valori, per esempio `Colore: Rosso, Taglia: M`. |
| **Aggiungi solo i valori degli attributi (separati da virgola)** | `2` | Titolo originale, poi il separatore, poi solo i valori, per esempio `Rosso, M`. |

Nomi dei gruppi e valori arrivano dalla lingua corrente del negozio.

### 4.9 Separatore del titolo

Chiave: `combfeat_title_separator`. Predefinito: ` - ` (spazio, trattino, spazio).

Inserito tra il titolo di documento originale e la parte aggiunta. La parte aggiunta è il testo della modalità predefinita oppure **Aggiungi al titolo** della combinazione. Il separatore si usa come è stato salvato, spazi compresi.

**Titolo completo** non usa il separatore. Sostituisce da solo il titolo del documento.

Se il titolo originale è vuoto, si usa solo la parte aggiunta.

### 4.10 Riepilogo delle impostazioni

| Impostazione | Chiave | Predefinito |
| --- | --- | --- |
| Attiva le caratteristiche per le combinazioni | `combfeat_p_feat` | Abilitato (`1`) |
| Classe CSS della scheda tecnica | `combfeat_ds` | `.data-sheet` |
| Flusso di lavoro | `combfeat_workflow` | Sostituisci (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Abilitato (`1`) |
| Attiva le descrizioni per le combinazioni | `combfeat_p_desc` | Abilitato (`1`) |
| Descrizione della classe CSS / ID oggetto | `combfeat_description` | `#description` |
| Attiva il meta titolo per le combinazioni | `combfeat_p_title` | Abilitato (`1`) |
| Modalità titolo predefinita | `combfeat_title_default` | Nome attributo e valore (`1`) |
| Separatore del titolo | `combfeat_title_separator` | ` - ` |

## 5. Importazione delle caratteristiche di combinazione

Secondo formulario della pagina di configurazione. Queste etichette sono per ora i testi sorgente inglesi in ogni lingua (non sono ancora nei file di traduzione).

L’importazione assegna valori di caratteristiche alle combinazioni. Non importa descrizioni né titoli e non scrive righe nell’elenco delle caratteristiche del prodotto (`feature_product`). Una caratteristica o un valore mancante viene creato nel catalogo.

### 5.1 Import mode

| Modalità | Effetto |
| --- | --- |
| **Append to combination features** (predefinita) | Tiene le assegnazioni già salvate. Una riga già presente su quella combinazione viene saltata. |
| **Replace features of listed combinations** | Per ogni combinazione presente nel file, cancella le caratteristiche di quella combinazione nel modulo e poi scrive le righe del file. Le combinazioni assenti dal file restano. Descrizioni e titoli non vengono cancellati. |

### 5.2 Regole del file

- UTF-8, estensione `.csv` o `.txt`. Un BOM iniziale è accettato. Dimensione massima **8 MB**.
- Il separatore si rileva dalla riga di intestazione: punto e virgola, virgola o tabulazione. Se non compare nessuno, si usa il punto e virgola.
- L’intestazione deve identificare la combinazione con `id_product_attribute` o `combination_reference`.
- L’intestazione deve identificare la caratteristica con `feature` e `value`, oppure con `id_feature_value`.
- Le righe vuote si saltano. Si elencano al massimo 30 errori di riga; il resto viene contato.

Nomi di colonna accettati (spazi e trattini diventano trattini bassi, le maiuscole non contano):

| Colonna | Accettato anche |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` e `product_reference` sono facoltativi. Se li compili, devono appartenere a quella combinazione. Uno scostamento rifiuta la riga.

Ricerca della combinazione:

- `id_product_attribute` si usa quando è maggiore di zero. Se ID e `combination_reference` sono entrambi compilati, il riferimento deve coincidere con quella riga.
- Altrimenti si usa il riferimento della combinazione. Se più combinazioni lo condividono, aggiungi `id_product` o `id_product_attribute`. Messaggio: Combination reference matches more than one combination.

Ricerca del valore:

- `id_feature_value` maggiore di zero carica quel valore. Le celle di nome e valore vengono ignorate.
- Altrimenti `feature` e `value` sono obbligatori. Una cella di caratteristica fatta solo di cifre è un ID di caratteristica.
- I nomi si cercano in modo esatto e poi senza distinzione di maiuscole. Se corrisponde più di una caratteristica o un valore, la riga viene rifiutata. Non si indovina nulla.
- Una caratteristica che non esiste viene creata. Il suo nome viene copiato in ogni lingua del negozio. Lunghezza massima 128.
- Un valore che non esiste viene creato come valore normale (non personalizzato), con lo stesso testo in ogni lingua. Lunghezza massima 255. Modifica poi **Catalogo > Attributi e caratteristiche** se le lingue devono avere testi diversi.

**Download sample file** invia `import/combfeat-features-sample.csv`:

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Le righe dell’esempio significano:

1. Combinazione 45 del prodotto 12, i riferimenti devono coincidere, caratteristica Material / Cotton (creata se manca).
2. Combinazione 46 del prodotto 12, Material / Wool.
3. La combinazione il cui riferimento è `DEMO-2-XL` sul prodotto il cui riferimento è `DEMO-2`, caratteristica Composition / 100% cotton. Senza ID numerici.
4. Combinazione 25 del prodotto 10, valore di caratteristica esistente 83. Nome e valore vuoti.

Dopo un’importazione riuscita la cache dei blocchi della navigazione a faccette viene svuotata. La conferma indica quante assegnazioni sono state salvate, quante c’erano già e quali righe sono fallite.

## 6. Contenuto della combinazione sul prodotto

**Catalogo > Prodotti**, modifica il prodotto, scheda **Moduli**. Titolo del blocco: **Contenuto della combinazione**. Sottotitolo: **Caratteristiche, descrizioni e meta titoli per combinazione**.

Crea prima le combinazioni (scheda **Combinazioni** del prodotto). Se il prodotto non ne ha, il blocco lo dice e non c’è nulla da modificare.

### 6.1 L’elenco

- **Espandi tutto** / **Riduci tutto**.
- **Filtra combinazioni…** corrisponde al nome della combinazione, all’ID della combinazione e al riferimento della combinazione.
- Ogni riga mostra l’immagine della combinazione (o un segnaposto), i nomi degli attributi, **Combination ID**, **Reference** quando la combinazione ne ha uno, e dei contrassegni. I contrassegni **Caratteristiche**, **Descrizione** e **Titolo** si accendono quando quella parte è compilata. Quello delle caratteristiche indica il numero di valori. Combination ID e Reference sono i testi sorgente inglesi.
- La prima combinazione è aperta. **Configura** apre una riga, **Chiudi** la richiude.
- Nella riga, le schede degli interruttori attivi: **Caratteristiche**, **Descrizione**, **Meta titolo**.

Se i tre interruttori sono spenti, il blocco mostra: Tutte le opzioni di combinazione sono disabilitate. Abilita caratteristiche, descrizioni o titoli nella configurazione del modulo.

### 6.2 Caratteristiche

Testo di aiuto: Cerca e collega i valori delle caratteristiche usati per questa combinazione nella pagina del prodotto.

Digita almeno **2 caratteri** del nome della caratteristica o del valore, nella lingua corrente del dipendente. Compaiono fino a 20 corrispondenze, etichettate `Caratteristica: valore`. Sceglierne una aggiunge un token. La ricerca trova solo valori che esistono già. Creali nel catalogo oppure con l’importazione CSV.

Lo stesso valore non si può aggiungere due volte. Si possono aggiungere più valori della stessa caratteristica. **×** toglie un token. La rimozione si salva con il prodotto.

### 6.3 Descrizione

Un campo di testo formattato per lingua. L’elenco delle lingue compare quando il negozio ha più di una lingua. Un HTML vuoto significa nessuna descrizione: nel negozio torna la descrizione lunga del prodotto e, al salvataggio, la riga di quella lingua viene cancellata.

### 6.4 Meta titolo

Entrambi i campi sono per lingua, 512 caratteri ciascuno. Un campo vuoto salta quella sostituzione.

| Campo | Effetto nel negozio |
| --- | --- |
| **Titolo completo (sovrascrive l intero titolo)** | Sostituisce tutto il titolo del documento. Separatore e modalità predefinita non si usano. Se entrambi i campi sono compilati, vince questo. |
| **Aggiungi al titolo (frammento aggiunto alla fine)** | Titolo di documento originale, poi il separatore, poi questo frammento. Si usa quando il titolo completo è vuoto. |

Se entrambi sono vuoti, vale la modalità titolo predefinita della sezione 4.8.

### 6.5 Salvataggio

Le modifiche si salvano con il prodotto. Usa il pulsante **Salva** del prodotto (compreso salva e anteprima, secondo la versione di PrestaShop). Nel blocco non c’è un salvataggio separato.

Al salvataggio il modulo:

1. Cancella ogni riga di caratteristiche di combinazione di questo prodotto e inserisce i token presenti nel formulario.
2. Per ogni lingua salva o cancella la descrizione.
3. Per ogni lingua salva la riga del titolo, o la cancella quando entrambi i campi titolo sono vuoti.
4. Svuota la cache dei blocchi della navigazione a faccette se quell’opzione è attiva.

Il formulario invia un campo nascosto `combfeat_submitted`. Se quel campo manca, il modulo non tocca i dati. In PrestaShop 8 e 9 questo dipende dalla modifica Twig della sezione 3.1.

Cancellare una combinazione in PrestaShop non cancella le sue righe in questo modulo. Le righe non vengono usate perché la combinazione non esiste più. Le caratteristiche spariscono quando salvi il prodotto (il formulario invia solo le combinazioni attuali). Le righe di descrizione e titolo di una combinazione cancellata restano finché non le togli dal database.

## 7. Negozio

Gli script vengono aggiunti solo nella scheda prodotto, solo se la richiesta non è un aggiornamento ajax dell’intero controller, solo se il prodotto ha combinazioni e solo se almeno uno dei tre interruttori è attivo.

| Interruttore | Script |
| --- | --- |
| Caratteristiche o descrizioni, flusso = Sostituisci | `views/js/combfeat.js` |
| Caratteristiche o descrizioni, flusso = Aggiungi | `views/js/combfeat-append.js` |
| Meta titolo | `views/js/combfeat-title.js` |

Cambiare combinazione non fa un’altra richiesta. I dati di tutte le combinazioni sono stampati nella pagina per la **lingua corrente**. Lo script legge la combinazione scelta dall’attributo `data-product` di `#product-details` (`id_product_attribute`) e riparte sull’evento `updatedProduct`.

`displayProductAdditionalInfo` stampa anche un elemento nascosto `#product-details-combfeat` con la combinazione risolta per la prima vista (gruppi di attributi dall’URL, `id_product_attribute` dalla richiesta, o la combinazione predefinita). Le combinazioni non disponibili seguono l’impostazione di magazzino di PrestaShop e **Mostra gli attributi non disponibili**. L’elemento nascosto si usa solo quando `#product-details` stesso manca. Un tema che tiene `#product-details` deve mettere `data-product` su quell’elemento. È così nel modello prodotto standard.

Il modulo non carica un foglio di stile nel negozio. I nuovi `<dt class="name">` e `<dd class="value">` usano le regole della scheda tecnica del tema.

### 7.1 Caratteristiche e descrizioni condividono uno script

`combfeat.js` e `combfeat-append.js` aggiornano la scheda tecnica **e** la descrizione appena vengono caricati. Non rileggono i due interruttori.

- Caratteristiche attive e descrizioni disattive: una descrizione salvata prima viene ancora applicata, finché non la svuoti e salvi.
- Descrizioni attive e caratteristiche disattive: le caratteristiche ancora salvate vengono ancora applicate. Salvare il prodotto con l’interruttore delle caratteristiche spento cancella quelle caratteristiche salvate. Vedi la sezione 4.1.

Lo script del titolo è separato e gira solo se l’interruttore del titolo è attivo.

### 7.2 Scheda tecnica

Sostituisci e Aggiungi sono descritti nella sezione 4.3. A ogni esecuzione il modulo ricostruisce le righe. Il markup in più che il tema aveva nella scheda tecnica (link, classi aggiuntive su un valore) non viene tenuto.

### 7.3 Descrizione

Se la combinazione ha una descrizione nella lingua corrente, quell’HTML sostituisce il contenuto del selettore della descrizione. Altrimenti lo sostituisce la descrizione lunga del prodotto. La modalità Aggiungi non accoda testo di descrizione.

### 7.4 Titolo

Priorità per la combinazione scelta, nella lingua corrente:

1. **Titolo completo**, quando non è vuoto.
2. Altrimenti **Aggiungi al titolo**, unito con il separatore della sezione 4.9.
3. Altrimenti la modalità titolo predefinita della sezione 4.8.

`og:title` riceve lo stesso testo quando quel meta tag esiste.

## 8. Navigazione a faccette

Con l’opzione attiva, i filtri di categoria leggono una vista che unisce:

- `feature_product` — caratteristiche assegnate al prodotto;
- `combfeat` — caratteristiche attive assegnate alle combinazioni, unite a `feature_value` per ottenere l’ID della caratteristica.

Ricostruisci l’indice della navigazione a faccette o svuota la cache di PrestaShop se un filtro resta vecchio dopo aver risolto l’avviso nella pagina di configurazione. Salvare le caratteristiche di combinazione e importare un CSV svuotano già `layered_filter_block`.

La scheda prodotto nel negozio continua a mostrare le caratteristiche prodotto di PrestaShop finché non gira lo script di questo modulo. Il filtro e la scheda tecnica sono due fonti diverse.

## 9. Aggiornamenti MyPresta

Il pannello sotto i formulari:

| Controllo | Comportamento |
| --- | --- |
| **Controlla ora** | Contatta MyPresta e mostra **Nuova versione disponibile!** o **Il modulo è aggiornato!** |
| **Notifiche di aggiornamento** | **Attiva** mostra un avviso nel back-office quando c’è una versione più recente: **Nuova versione disponibile, controlla http://MyPresta.eu per maggiori informazioni**, con il link **Maggiori dettagli nel changelog**. **Disattiva** nasconde quell’avviso. |
| **Pagina del modulo** | Apre la pagina dell’add-on: [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

Finché un dipendente è nel back-office, il modulo contatta il server degli aggiornamenti al massimo una volta ogni 3 giorni. Il controllo ha bisogno di `allow_url_fopen`. Se non è disponibile, resta la versione installata e una più recente non viene segnalata.

## 10. Risoluzione dei problemi

**Il blocco della scheda Moduli è vuoto in PrestaShop 8 o 9.**  
Controlla che `modules-content.html.twig` contenga `{{ module.content|raw }}` e che il negozio abbia potuto scrivere quel file. Riapri la configurazione del modulo perché la modifica venga ritentata. Poi svuota la cache di Symfony (**Parametri avanzati > Prestazioni**).

**La scheda tecnica non cambia.**  
Il prodotto deve avere combinazioni, l’interruttore delle caratteristiche deve essere attivo oppure le caratteristiche devono essere già salvate, e la combinazione deve avere almeno un valore (nella modalità Sostituisci una combinazione senza valori ripristina le caratteristiche del prodotto, e può sembrare che non sia successo nulla). Controlla il selettore nella console del browser: `document.querySelectorAll('.data-sheet')` con il tuo selettore reale. Il tema deve aggiornare `data-product` su `#product-details` e lanciare `updatedProduct`.

**L’intero blocco product-details è stato sostituito da un breve elenco di caratteristiche.**  
Il selettore della scheda tecnica non ha trovato nulla. Impostalo sul vero `<dl>`, di solito `.data-sheet`.

**La descrizione non cambia, oppure la descrizione breve è stata sostituita da quella lunga.**  
Il selettore predefinito `#description` è la descrizione lunga in Classic. Il testo di riserva è sempre la descrizione lunga. In **Descrizione della classe CSS / ID oggetto** punta l’elemento che deve cambiare.

**Ho spento le descrizioni e il testo vecchio si vede ancora.**  
Svuota i campi, salva il prodotto, poi spegni l’interruttore. Oppure spegni anche le caratteristiche, così nessuno di quegli script si carica. Spegnere le caratteristiche e salvare cancella le caratteristiche di combinazione salvate.

**Ho spento le caratteristiche e sono sparite dopo il salvataggio del prodotto.**  
È così che funziona il salvataggio quando i campi delle caratteristiche non sono nel formulario del prodotto. Riattiva l’interruttore prima di modificare se i dati servono ancora. Reimporta il CSV se hai il file.

**Il titolo della scheda del browser non cambia.**  
Attiva l’interruttore del titolo. Un titolo completo vuoto e un campo Aggiungi al titolo vuoto insieme significano che si usa la modalità predefinita. **Non modificare il titolo di default** lascia il titolo com’era. Il cambio è nel browser: apri la pagina, cambia combinazione, leggi il titolo della scheda. Il sorgente HTML ha ancora il meta titolo del prodotto.

**Manca una caratteristica nel filtro di categoria.**  
Attiva **Filter combination features in Faceted Search**, aggiungi la caratteristica al modello della navigazione a faccette e leggi l’avviso nella configurazione del modulo. Il file dell’adattatore deve essere scrivibile. Il valore deve essere salvato sul prodotto o su una combinazione.

**Errori di riga CSV.**

| Messaggio | Causa |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | L’intestazione non identifica una combinazione |
| The CSV must contain feature and value, or id_feature_value | L’intestazione non identifica un valore di caratteristica |
| Combination was not found | L’ID o il riferimento non esiste |
| Product ID does not match this combination | `id_product` è compilato e punta a un altro prodotto |
| Product reference does not match this combination | `product_reference` non coincide |
| Combination reference does not match this combination ID | ID e riferimento sono compilati e si contraddicono |
| Combination reference matches more than one combination | Aggiungi `id_product` o `id_product_attribute` |
| Feature name or value matches more than one | Due schede del catalogo condividono quell’etichetta. Usa `id_feature_value` |
| Feature and value are required when id_feature_value is empty | La cella del nome o del valore è vuota |
| The CSV file is larger than 8 MB | Dividi il file |

**Più lingue.**  
Descrizioni e entrambi i campi titolo sono salvati per lingua. I valori delle caratteristiche usano la traduzione PrestaShop della caratteristica nella lingua del visitatore. L’assegnazione in sé non è per lingua.

## 11. Riferimento tecnico

### 11.1 Hook

| Hook | Quando | Cosa fa |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Back-office, controller `AdminProducts` e `AdminModules` | Carica `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js` e l’autocompletamento jQuery. Assicura anche la configurazione e l’integrazione Faceted Search |
| `displayAdminProductsExtra` | Modifica del prodotto, scheda Moduli | Mostra `views/templates/admin/combfeat.tpl` |
| `actionProductUpdate` | Salvataggio del prodotto | Scrive caratteristiche, descrizioni e titoli quando è presente `combfeat_submitted` |
| `displayHeader` | Scheda prodotto, non ajax | Stampa i dati di combinazione della lingua corrente e aggiunge gli script del negozio |
| `displayProductAdditionalInfo` | Scheda prodotto | Mostra il file nascosto `views/templates/hook/product-details.tpl` |

Registrati all’installazione: `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

La pagina di configurazione risponde anche alla ricerca delle caratteristiche. Una richiesta con `ajax=1` e `q` restituisce le corrispondenze JSON e termina. L’editor del prodotto chiama quell’URL tramite `AdminModules` con `configure=combfeat`.

### 11.2 Database

Il prefisso è quello del negozio. La disinstallazione **non** elimina queste tabelle, quindi il contenuto delle combinazioni sopravvive alla disinstallazione ed è ancora lì dopo un’installazione successiva (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — una riga per valore di caratteristica su una combinazione:

| Colonna | Ruolo |
| --- | --- |
| `id_combfeat` | Chiave primaria |
| `id_product` | Prodotto |
| `id_product_attribute` | Combinazione |
| `id_feature_value` | Valore di caratteristica del catalogo |
| `active` | `1` quando la riga è usata. Negozio e vista Faceted Search leggono le righe attive |

`combfeat_details` — descrizione, una riga per combinazione e lingua:

| Colonna | Ruolo |
| --- | --- |
| `id_combfeat` | Chiave primaria |
| `id_product`, `id_product_attribute`, `id_lang` | Destinazione |
| `details` | HTML |
| `active` | Salvato come `1` |

`combfeat_title` — titoli, una riga per combinazione e lingua:

| Colonna | Ruolo |
| --- | --- |
| `id_combfeat` | Chiave primaria |
| `id_product`, `id_product_attribute`, `id_lang` | Destinazione |
| `title_full` | Fino a 512 caratteri. Sostituisce il titolo del documento |
| `title_append` | Fino a 512 caratteri. Aggiunto dopo il titolo originale |
| `active` | Salvato come `1` |

`{prefix}combfeat_feature_product` — vista SQL, non una tabella di contenuto da modificare. Unione di `feature_product` e delle righe attive di `combfeat`. Il valore di configurazione `COMBFEAT_FEATURE_VIEW` tiene la versione della vista (`1`).

Altre chiavi di configurazione: `update_combfeat` e `updatev_combfeat` (controllo aggiornamenti), `mypresta_updates` (interruttore delle notifiche).

### 11.3 Classi PHP

| File | Classe | Ruolo |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Classe del modulo: installazione, configurazione, hook, dati dell’editor prodotto, dati del negozio |
| `combfeat.php` | `combfeatUpdate` | Confronto di versione e richiesta al server degli aggiornamenti |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | Analisi CSV, risoluzione di combinazione e caratteristica, download dell’esempio |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | Vista, patch dell’adattatore, ripristino, svuotamento della cache dei filtri |
| `models/cfeat.php` | `cfeat` | Righe di `combfeat`. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, cancellazioni |
| `models/cfeatdesc.php` | `cfeatdesc` | Righe di `combfeat_details` |
| `models/cfeattitle.php` | `cfeattitle` | Righe di `combfeat_title`. `saveTitleRow` cancella la riga quando entrambi i titoli sono vuoti |

Non c’è una cartella `controllers/`.

### 11.4 Risorse e modelli

| File | Dove | Ruolo |
| --- | --- | --- |
| `views/js/acplt.js` | Back-office | Autocompletamento della ricerca caratteristiche |
| `views/js/admin-combfeat.js` | Back-office | Accordion, filtro, schede, bandiere lingua, token, aggiornamento TinyMCE, copia del contenuto dell’editor prima del salvataggio del prodotto |
| `views/css/combfeat.css` | Solo back-office | Impaginazione di **Contenuto della combinazione** |
| `views/js/combfeat.js` | Negozio, modalità Sostituisci | Ricostruisce scheda tecnica e descrizione |
| `views/js/combfeat-append.js` | Negozio, modalità Aggiungi | Uguale, con le caratteristiche del prodotto davanti a quelle della combinazione |
| `views/js/combfeat-title.js` | Negozio | `document.title` e `og:title` |
| `views/templates/admin/combfeat.tpl` | Scheda Moduli del prodotto | L’editor |
| `views/templates/hook/product-details.tpl` | Scheda prodotto | `#product-details-combfeat` nascosto, con `data-product` |
| `import/combfeat-features-sample.csv` | Download dalla configurazione | Esempio di importazione |

### 11.5 Installazione e disinstallazione

L’installazione crea le tre tabelle, scrive la configurazione predefinita, registra i cinque hook, applica la modifica Twig e applica l’integrazione Faceted Search.

`disable` ripristina l’adattatore della navigazione a faccette. `enable` scrive le chiavi di configurazione mancanti e riapplica l’integrazione quando l’interruttore Faceted Search è attivo.

La disinstallazione ripristina l’adattatore, elimina la vista quando non è più citata e disinstalla il modulo. Le righe di combinazione delle tre tabelle restano nel database.

## 12. Assistenza

Changelog e aggiornamenti: [Product combination features su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Ordini e assistenza: [account cliente MyPresta.eu](https://mypresta.eu/my-account/orders/). E-mail: support@mypresta.eu.
