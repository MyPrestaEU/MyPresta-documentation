---
title: "Feed di prodotti Microsoft Merchant Center - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Feed di prodotti Microsoft Merchant Center' di MyPresta.eu."
sidebar:
  label: "Feed di prodotti Microsoft Merchant Center - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Microsoft Merchant Center Product Feed su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Feed di prodotti Microsoft Merchant Center

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve essere in grado di eseguire cron job per la generazione automatica del feed.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" si accederà alla pagina di configurazione principale del modulo. Qui imposterai il comportamento generale e accederai agli strumenti di gestione del feed.

#### Impostazioni generali

Questa sezione copre tipicamente le impostazioni globali che influenzano il funzionamento del modulo e la generazione dei feed.

- **Cosa fa questa impostazione:** Queste sono le impostazioni principali che definiscono come i dati dei tuoi prodotti vengono preparati per Microsoft Merchant Center. Tipicamente troverai opzioni per selezionare la lingua, la valuta e il paese per il tuo feed, oltre alle preferenze generali di esportazione.
- **Effetto della modifica di questa impostazione:**
  - *Lingua:* Determina quale versione linguistica dei nomi, descrizioni e categorie dei tuoi prodotti sarà inclusa nel feed. Cruciale per il targeting di specifici mercati internazionali.
  - *Valuta:* Imposta la valuta per tutti i prezzi nel feed. Deve corrispondere alla valuta configurata nel tuo account Microsoft Merchant Center per il paese di destinazione.
  - *Paese:* Specifica il paese di destinazione per il feed. Questo influenza le regole fiscali, le impostazioni di spedizione e altri requisiti specifici del paese in Microsoft Merchant Center.
  - *Altre opzioni di esportazione:* Possono includere impostazioni per la gestione delle varianti di prodotto, l'esclusione di determinate categorie o la definizione di come vengono esportati attributi specifici (come taglia o colore).
- **Valore consigliato:**
  - *Lingua, Valuta, Paese:* Seleziona la lingua, la valuta e il paese principali che stai targetizzando con i tuoi annunci Microsoft Shopping. Se fai pubblicità in più paesi/lingue, probabilmente creerai feed separati per ciascuno.
  - *Altre opzioni:* Segui le raccomandazioni del modulo o regola in base al tuo catalogo prodotti specifico e alla strategia pubblicitaria.
- **Scenario/esempio del commerciante:** Se vendi in Francia e la lingua predefinita del tuo negozio è il francese, selezioneresti francese per la lingua, EUR per la valuta e Francia per il paese. Se vendi anche in Germania, creeresti un feed separato configurato per la lingua tedesca, la valuta EUR e la Germania come paese.

#### Gestione e generazione del feed

Questa sezione fornisce l'accesso per creare, gestire e generare i tuoi feed di prodotti.

- **Cosa fa questa impostazione:** Questo è il cuore del modulo, che ti consente di definire e generare i file di feed di prodotti effettivi. Tipicamente troverai opzioni per creare nuovi feed, visualizzare quelli esistenti e attivare il processo di generazione.
- **Effetto della modifica di questa impostazione:**
  - *Creazione di un nuovo feed:* Avvia il processo di impostazione di un nuovo feed di prodotti con le sue impostazioni specifiche (lingua, valuta, categorie, ecc.).
  - *Generazione di un feed:* Elabora i dati dei tuoi prodotti PrestaShop e crea il file CSV, XML o TSV che caricherai su Microsoft Merchant Center. Questo file contiene tutti gli attributi del prodotto nel formato richiesto da Microsoft.
  - *URL Cron:* Fornisce un indirizzo web speciale che, quando visitato, attiva automaticamente la generazione del feed. Questo è essenziale per impostare aggiornamenti automatici giornalieri o orari del tuo feed di prodotti senza intervento manuale.
- **Valore consigliato:**
  - Crea almeno un feed per il tuo mercato di riferimento principale.
  - Imposta un cron job utilizzando l'URL fornito per assicurarti che il tuo feed di prodotti venga regolarmente aggiornato (ad esempio, quotidianamente) con le ultime informazioni sui prodotti (livelli di stock, prezzi, nuovi prodotti).
- **Scenario/esempio del commerciante:** Hai appena lanciato una nuova linea di prodotti. Avendo un cron job giornaliero, i tuoi annunci Microsoft Shopping rifletteranno automaticamente questi nuovi prodotti e i loro attuali livelli di stock il giorno successivo, senza che tu debba ricaricare manualmente il feed.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminExportProductsFeedMicrosoftController (Back Office > Microsoft Merchant Center > Esporta feed prodotti)

Questa è la schermata dedicata principale per la gestione dei dettagli dei tuoi feed di prodotti. Vi accederai tramite una nuova voce di menu aggiunta dal modulo, probabilmente sotto "Catalogo" o una nuova sezione "Microsoft Merchant Center".

- **Nome schermata e posizione menu:** **Back Office > Microsoft Merchant Center > Esporta feed prodotti** (o simile, a seconda della versione del modulo e della struttura del menu di PrestaShop).
- **Azioni e impostazioni disponibili:** Questa schermata è dove definisci il contenuto specifico e la mappatura per ciascuno dei tuoi feed di prodotti. Tipicamente vedrai un elenco di feed esistenti, con opzioni per "Aggiungi nuovo feed" o "Modifica" uno esistente. Quando aggiungi/modifica, configurerai:
  - **Nome feed:** Un nome descrittivo per il tuo feed (es. "Francia - Feed francese", "USA - Feed inglese").
  - **Paese di destinazione:** Il paese a cui è destinato questo feed (es. Francia, Stati Uniti). Questo influisce su valuta, lingua e regole fiscali.
  - **Lingua del contenuto:** La lingua dei dati del prodotto in questo feed (es. francese, inglese).
  - **Valuta:** La valuta utilizzata per i prezzi in questo feed (es. EUR, USD).
  - **Formato file:** Scegli tra CSV, XML o TSV, come richiesto da Microsoft Merchant Center.
  - **Mappatura categorie:** Questa è una sezione cruciale in cui mappi le tue categorie PrestaShop alla tassonomia dei prodotti di Microsoft. Questo aiuta Microsoft a capire quali sono i tuoi prodotti e a mostrarli nelle ricerche pertinenti.
  - **Filtro prodotti:** Opzioni per includere/escludere prodotti specifici o intere categorie dal feed.
  - **Mappatura attributi:** Mappa gli attributi del prodotto PrestaShop (come taglia, colore, materiale) agli attributi richiesti da Microsoft (es. `size`, `color`, `material`).
  - **Etichette personalizzate:** Definisci fino a 5 etichette personalizzate (`custom_label_0` a `custom_label_4`) per segmentare i tuoi prodotti per le strategie di offerta in Microsoft Ads.
  - **Disponibilità e condizione:** Impostazioni per definire come vengono esportate la disponibilità del prodotto (in stock, esaurito, preordine) e la condizione (nuovo, usato, ricondizionato).
  - **GTIN (Global Trade Item Number):** Impostazioni per l'esportazione dei codici EAN/UPC come GTIN.
  - **Marca:** Come vengono esportate le marche dei prodotti.
  - **Descrizione:** Opzioni per l'esportazione delle descrizioni dei prodotti, spesso con conversione in testo semplice.
  - **Link immagini:** Come vengono collegati le immagini dei prodotti.
  - **Prezzo e prezzo di vendita:** Come vengono esportati i prezzi normali e di vendita, incluse le considerazioni fiscali.
  - **URL Cron:** L'URL univoco per questo feed specifico che utilizzerai per gli aggiornamenti automatici.
- **Effetto delle modifiche:**
  - Le modifiche qui influiscono direttamente sul contenuto e sulla struttura del file di feed di prodotti generato. Impostazioni errate possono portare a disapprovazioni dei prodotti in Microsoft Merchant Center.
  - Una corretta mappatura delle categorie garantisce che i tuoi prodotti appaiano nelle categorie di acquisto pertinenti su Bing.
  - Dati accurati su prezzi e disponibilità prevengono la frustrazione dei clienti e le disapprovazioni degli annunci.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Configurazione iniziale:** Crea un feed per ogni combinazione di paese/lingua di destinazione in cui fai pubblicità. Mappa attentamente le tue categorie alla tassonomia di Microsoft.
  2. **Revisione attributi:** Assicurati che tutti gli attributi critici (GTIN, marca, prezzo, disponibilità, link immagini) siano correttamente mappati ed esportati.
  3. **Imposta Cron Job:** Implementa gli URL Cron forniti sul tuo server di hosting per automatizzare la generazione giornaliera (o più frequente) del feed. Questo è fondamentale per mantenere aggiornati i dati dei tuoi prodotti.
  4. **Monitora Microsoft Merchant Center:** Controlla regolarmente il tuo account Microsoft Merchant Center per eventuali disapprovazioni o avvisi sui prodotti e regola le impostazioni del modulo secondo necessità.
  5. **Aggiornamenti prodotti:** Quando aggiungi nuovi prodotti o apporti modifiche significative a quelli esistenti, assicurati che il tuo cron job sia in esecuzione, o rigenera manualmente il feed se è richiesto un aggiornamento immediato.

#### index.php (mmcfeed/controllers/admin/index.php)

Questo controller probabilmente funge da dashboard o da vista di gestione generale per il modulo all'interno del Back Office di PrestaShop.

- **Nome schermata e posizione menu:** Probabilmente parte della sezione principale del menu "Microsoft Merchant Center", possibilmente la pagina di destinazione predefinita.
- **Azioni e impostazioni disponibili:** Questa schermata probabilmente visualizza una panoramica dei tuoi feed configurati, la loro ultima data di generazione, lo stato e collegamenti rapidi per modificarli o generarli. Potrebbe anche mostrare lo stato generale del modulo o avvisi importanti.
- **Effetto delle modifiche:** Questa vista fornisce una rapida occhiata alla configurazione del tuo feed. Le azioni qui (come cliccare su "Genera feed") attiveranno il processo di generazione del feed.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata come una dashboard rapida per monitorare lo stato dei tuoi feed di prodotti. Se hai bisogno di attivare manualmente un aggiornamento del feed, è qui che lo faresti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Lingua di destinazione | La tua lingua principale del negozio | Determina la lingua per nomi prodotti, descrizioni, ecc. |
|  | Valuta di destinazione | La tua valuta principale del negozio | Imposta la valuta per tutti i prezzi nel feed. |
|  | Paese di destinazione | Il tuo mercato di riferimento principale | Influisce su tasse, spedizioni e regole specifiche del paese. |
|  | URL Cron | Fornito dal modulo | Automatizza la generazione del feed a intervalli programmati. |
| **AdminExportProductsFeedMicrosoftController** | Nome feed | Descrittivo (es. "Francia - FR") | Identifica il feed specifico. |
|  | Formato file | CSV, XML o TSV | Scegli in base ai requisiti di Microsoft Merchant Center. |
|  | Mappatura categorie | Mappa PrestaShop alla tassonomia Microsoft | Assicura che i prodotti appaiano nelle categorie di acquisto corrette. |
|  | Filtro prodotti | Basato sulla tua strategia | Includi/escludi prodotti o categorie specifiche. |
|  | Mappatura attributi | Mappa PrestaShop agli attributi Microsoft | Fornisce informazioni dettagliate sui prodotti per gli annunci. |
|  | Etichette personalizzate (0-4) | Secondo necessità per le campagne pubblicitarie | Segmenta i prodotti per le strategie di offerta. |
|  | Esportazione GTIN | Abilitato se disponibile | Esporta EAN/UPC per l'identificazione del prodotto. |
|  | Data disponibilità | Abilitato se applicabile | Esporta la data di disponibilità del prodotto per i preordini. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prodotti non vengono visualizzati negli annunci di Microsoft Shopping. Cosa devo controllare?**
R:

1.  **Stato caricamento feed:** Innanzitutto, controlla il tuo account Microsoft Merchant Center per assicurarti che il tuo feed sia stato caricato ed elaborato con successo senza errori importanti.
2.  **Disapprovazioni prodotti:** Cerca eventuali disapprovazioni di prodotti nella sezione "Diagnostica" di Microsoft Merchant Center. Queste ti diranno esattamente perché i prodotti non vengono visualizzati. Le ragioni comuni includono GTIN mancanti, link immagine errati o violazioni delle policy.
3.  **Configurazione modulo:** Verifica che le impostazioni del tuo modulo (lingua, valuta, paese, mappatura categorie) siano corrette e corrispondano alle impostazioni del tuo account Microsoft Merchant Center.
4.  **Generazione feed:** Assicurati che il feed venga generato correttamente dal modulo. Prova a generarlo manualmente e a controllare il file di output.
5.  **Campagne pubblicitarie:** Conferma che le tue campagne Microsoft Ads siano attive, correttamente mirate e collegate al feed di prodotti corretto.

**D: I prezzi o i livelli di stock dei miei prodotti sono obsoleti negli annunci di Microsoft Shopping.**
R: Questo di solito significa che il tuo feed di prodotti non viene aggiornato abbastanza frequentemente.

1.  **Cron Job:** Assicurati che il tuo cron job sia configurato correttamente sul tuo server di hosting e che venga eseguito alla frequenza desiderata (ad esempio, giornalmente). Il modulo fornisce un URL univoco per questo.
2.  **Generazione manuale:** Se hai apportato modifiche urgenti, puoi rigenerare manualmente il feed dalla pagina di configurazione del modulo e ricaricarlo su Microsoft Merchant Center (se non utilizzi recuperi programmati).

**D: Alcuni dei miei prodotti mancano dal feed.**
R:

1.  **Esclusione categorie:** Controlla se le categorie contenenti questi prodotti sono state accidentalmente escluse nelle impostazioni del modulo.
2.  **Stato prodotto:** Assicurati che i prodotti siano attivi, visibili e disponibili nel tuo negozio PrestaShop. I prodotti contrassegnati come "disabilitati" o "esauriti" (a seconda delle tue impostazioni) potrebbero essere esclusi.
3.  **Filtri specifici:** Rivedi eventuali filtri di prodotto specifici che potresti aver applicato nella configurazione del modulo.

**D: Come mappo le mie categorie PrestaShop alla tassonomia dei prodotti di Microsoft?**
R: Nella schermata di configurazione del feed del modulo, ci sarà una sezione per la "Mappatura categorie". Tipicamente vedrai un elenco delle tue categorie PrestaShop. Per ciascuna, dovrai selezionare la categoria più appropriata dall'elenco di tassonomia predefinita di Microsoft. Questo è un passaggio cruciale per la pertinenza degli annunci. Prenditi il tuo tempo per farlo correttamente.

**D: Il mio tema personalizzato sta causando problemi di visualizzazione con l'interfaccia di amministrazione del modulo.**
R: Sebbene l'impatto del modulo sul front-office sia nullo, la sua interfaccia di back-office potrebbe talvolta entrare in conflitto con temi di amministrazione pesantemente personalizzati.

1.  **Svuota cache:** Innanzitutto, prova a svuotare la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).
2.  **Tema predefinito:** Passa temporaneamente il tuo tema di back-office al tema PrestaShop predefinito per vedere se il problema persiste. Se si risolve, il conflitto è con il tuo tema di amministrazione personalizzato.
3.  **Contatta il supporto:** Se il problema persiste, raccogli screenshot e dettagli e contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Feed di prodotti Microsoft Merchant Center` (`mmcfeed`) segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i Controller Admin per la gestione del back-office e i Controller Front per la generazione del feed di prodotti tramite cron job. Non introduce nuove classi `ObjectModel` ma piuttosto interroga i dati dei prodotti PrestaShop esistenti e li formatta secondo le specifiche di Microsoft Merchant Center. Il modulo si basa fortemente sui valori di configurazione memorizzati in `ps_configuration` e utilizza i template Smarty per il rendering sia delle interfacce di amministrazione che potenzialmente di parti della logica di generazione del feed (anche se tipicamente i feed vengono generati programmaticamente).

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `mmcfeed/controllers/front/feed.php`
  - **Nome classe e classe padre:** `MmcfeedFeedModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è l'endpoint primario per la generazione del feed di prodotti. È progettato per essere chiamato tramite un URL univoco (l'"URL cron") per la generazione automatica del feed. Gestisce la logica di interrogazione dei dati dei prodotti, applicando le regole di filtraggio e mappatura definite nel back office e producendo il feed di prodotti nel formato specificato (CSV, XML, TSV). Tipicamente non renderizza una pagina visiva ma produce dati grezzi.
- `mmcfeed/controllers/front/index.php`
  - **Nome classe e classe padre:** `MmcfeedIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo è un controller frontale segnaposto o di fallback. In molti moduli, `index.php` in una directory di controller funge da punto di ingresso predefinito o semplice. Potrebbe reindirizzare o semplicemente restituire una risposta vuota se non è definita alcuna azione specifica. Il suo ruolo funzionale diretto nella generazione del feed è probabilmente minimo rispetto a `feed.php`.

#### Controller Admin Back-Office

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Nome tab e entità gestita:** Gestisce la configurazione e la generazione dei singoli feed di prodotti di Microsoft Merchant Center. Crea una nuova voce di menu nel back office di PrestaShop.
  - **Responsabilità:** Questo controller gestisce le operazioni CRUD per le configurazioni del feed di prodotti. Visualizza l'elenco dei feed configurati, consente di aggiungere nuovi feed, modificare quelli esistenti e attivarne la generazione. Elabora le sottomissioni di moduli per definire impostazioni specifiche del feed come paese di destinazione, lingua, valuta, formato file, mappatura delle categorie, filtraggio dei prodotti e mappatura degli attributi (es. `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). Interagisce con `ps_configuration` per memorizzare queste impostazioni e orchestra il recupero e la formattazione dei dati per il processo di generazione del feed.
- `mmcfeed/controllers/admin/index.php`
  - **Nome tab e entità gestita:** Probabilmente una dashboard o una pagina di panoramica per il modulo nel back office di PrestaShop.
  - **Responsabilità:** Questo controller probabilmente funge da punto di ingresso principale per l'interfaccia di amministrazione del modulo, fornendo un riepilogo dei feed configurati, il loro stato e azioni rapide. Potrebbe renderizzare un template simile a una dashboard (`dashboard.tpl`) per fornire una panoramica dell'attività del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Le informazioni fornite indicano l'assenza di classi o modelli personalizzati all'interno della directory `classes/`. Ciò suggerisce che il modulo opera principalmente interrogando direttamente le classi `ObjectModel` principali di PrestaShop come `Product`, `Category`, `Language`, `Currency`, ecc., e `ps_configuration` per le sue impostazioni. La logica per l'elaborazione dei dati e la generazione del feed è probabilmente incapsulata all'interno del file del modulo principale `mmcfeed.php` e dei controller admin/front.

### 4.4 Risorse JavaScript (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Responsabilità:** Fornisce la funzionalità di completamento automatico, probabilmente per la ricerca di prodotti, categorie o attributi all'interno dei moduli di configurazione del modulo. Questo migliora l'esperienza utente durante la mappatura delle categorie o il filtraggio dei prodotti. Si lega ai campi di input ed esegue richieste AJAX per recuperare suggerimenti.
- `mmcfeed/views/js/admin-app.js`
  - **Ambito:** Back-office.
  - **Responsabilità:** Questo è il file JavaScript principale per l'interfaccia di back-office del modulo. Gestisce vari elementi interattivi, validazioni di moduli, caricamento dinamico di contenuti (ad esempio, modali Fancybox per la selezione delle categorie) e chiamate AJAX relative al salvataggio delle configurazioni o all'attivazione della generazione del feed. Probabilmente lega i listener di eventi a pulsanti, selezioni e campi di input all'interno dei moduli del controller `AdminExportProductsFeedMicrosoft`.

### 4.5 Fogli di stile CSS (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Stile del modulo di amministrazione del back-office.
  - **Responsabilità:** Stila i menu a discesa di completamento automatico e i campi di input utilizzati dallo script `autocomplete.js`, garantendo un aspetto coerente e intuitivo all'interno del back office di PrestaShop.
- `mmcfeed/views/admin-theme.css`
  - **Ambito:** Stile del modulo di amministrazione del back-office.
  - **Responsabilità:** Fornisce aggiustamenti e override di stile generali per le pagine del back-office del modulo per integrarsi perfettamente con il tema di amministrazione di PrestaShop. Potrebbe definire stili per layout, pulsanti, tabelle ed elementi del modulo specifici del modulo.
- `mmcfeed/views/css/admin-app.css`
  - **Ambito:** Stile del modulo di amministrazione del back-office.
  - **Responsabilità:** Contiene stili specifici per i componenti UI personalizzati e i layout del modulo all'interno del pannello di amministrazione, come interfacce di mappatura delle categorie, elenchi di esclusione dei prodotti o elementi della dashboard. Funziona in combinazione con `admin-theme.css` per fornire l'identità visiva del modulo nel back office.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, indicando che il modulo non renderizza contenuti direttamente in hook standard del front-office.
- **Template admin (`views/templates/admin/`)**:
  - `mmcfeed/views/templates/admin/dashboard.tpl`: Probabilmente il template principale della dashboard renderizzato da `controllers/admin/index.php`, che fornisce una panoramica del modulo e dei suoi feed configurati.
  - `mmcfeed/views/templates/admin/feeds.tpl`: Probabilmente renderizza l'elenco dei feed di prodotti gestiti da `AdminExportProductsFeedMicrosoftController`, mostrando il loro stato, l'ultima data di generazione e le azioni.
  - `mmcfeed/views/templates/admin/form-chrome.tpl`: Un template generico per avvolgere i moduli nell'interfaccia di amministrazione di PrestaShop, fornendo uno stile e una struttura coerenti (es. intestazione, piè di pagina, pulsanti di salvataggio).
  - `mmcfeed/views/templates/admin/layout.tpl`: Un template di layout di base per le pagine di amministrazione del modulo, che definisce la struttura generale, inclusi intestazioni, menu e aree di contenuto.
- **Altri template (`views/`)**:
  - `mmcfeed/lib/searchTool/views/scripts.tpl`: Contiene codice JavaScript o inclusioni di script relativi alla funzionalità di ricerca/completamento automatico.
  - `mmcfeed/views/categories-fancybox.tpl`: Renderizza il contenuto per un modale Fancybox utilizzato per la selezione o la mappatura delle categorie, probabilmente fornendo una struttura ad albero per una facile navigazione.
  - `mmcfeed/views/category_taxonomy.tpl`: Un template parziale utilizzato all'interno di `categories-fancybox.tpl` o del modulo di configurazione del feed principale per visualizzare e gestire la mappatura delle categorie PrestaShop alla tassonomia di Microsoft.
  - `mmcfeed/views/exclude-products.tpl`: Renderizza l'interfaccia per la selezione e la gestione dei prodotti da escludere dal feed.
  - `mmcfeed/views/google_lang_links.tpl`: Questo nome di template è curioso per un modulo Microsoft. Potrebbe essere un residuo di un modulo Google Merchant Center o un componente generico per la gestione di link specifici per la lingua, potenzialmente per gli URL del feed stessi.
  - `mmcfeed/views/returnAlert.tpl`: Un template generico per visualizzare messaggi di successo o di errore all'utente nel back office.
  - `mmcfeed/views/script-fancybox.tpl`: Contiene codice JavaScript o inclusioni di script specificamente per la libreria Fancybox, utilizzata per i popup modali.
  - `mmcfeed/views/script.tpl`: Un template di inclusione di script generale, potenzialmente per variabili JavaScript a livello di modulo o inizializzazioni.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate in base alle informazioni fornite.
  - Tutte le configurazioni del modulo sono memorizzate nella tabella `ps_configuration`, utilizzando chiavi prefissate con `mmc_` (es. `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - Interagisce con le tabelle standard di PrestaShop come `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule`, ecc., per recuperare i dati dei prodotti.
- **Tabella degli hook registrati**:
  Il modulo utilizza principalmente hook di back-office per la sua interfaccia di amministrazione e potenzialmente hook `action` per la logica interna. Gli hook di front-office non vengono utilizzati per il rendering del contenuto, ma il controller frontale del modulo `feed.php` funge da endpoint diretto per servizi esterni (come i cron job).

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` delle pagine del front-office. | *Non utilizzato per il rendering del contenuto.* Se registrato, probabilmente per il caricamento interno di JS/CSS, ma la funzione principale del modulo è la generazione del feed, non la visualizzazione del front-office. |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | *Non utilizzato per il rendering del contenuto.* |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | *Non utilizzato per il rendering del contenuto.* |
| `displayFooter` | Nel piè di pagina delle pagine del front-office. | *Non utilizzato per il rendering del contenuto.* |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel back office. | *Potenzialmente utilizzato* per aggiungere una scheda o una sezione per esclusioni o override specifici del feed del prodotto. |
| `actionAdminControllerSetMedia` | Quando un controller admin viene inizializzato e prima che i suoi media (JS/CSS) vengano caricati. | Utilizzato per registrare JavaScript (`admin-app.js`, `autocomplete.js`) e CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) specifici del modulo per l'interfaccia del back-office. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per creare voci di configurazione in `ps_configuration` e potenzialmente registrare schede admin. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per pulire le voci di configurazione e rimuovere le schede admin. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | *Improbabile per questo modulo.* Se presente, sarebbe per il tracciamento delle conversioni o l'aggiornamento dei dati del feed in base alle vendite, ma non una funzione principale per un generatore di feed. |
| `actionProductUpdate` | Dopo che un prodotto è stato aggiornato. | *Potenzialmente utilizzato* per attivare un flag per la rigenerazione del feed o per aggiornare le cache interne se il modulo ne mantiene qualcuna. |
| `actionProductAdd` | Dopo che un nuovo prodotto è stato aggiunto. | *Potenzialmente utilizzato* per attivare un flag per la rigenerazione del feed o per aggiornare le cache interne. |
| `displayAdminNavBarBefore` | Prima della barra di navigazione principale nel back office. | *Potenzialmente utilizzato* per aggiungere un collegamento rapido o una notifica relativa al modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fornisce supporto dedicato per tutti i moduli acquistati, garantendo che il tuo negozio rimanga aggiornato e funzionale.
