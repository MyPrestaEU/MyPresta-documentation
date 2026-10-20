---
title: "Feed di Google Merchant Center - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Feed di Google Merchant Center' di MyPresta.eu."
sidebar:
  label: "Feed di Google Merchant Center - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google merchant center feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-merchant-center-feed/)
>
> ---


# Feed di Google Merchant Center

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Potrebbero essere necessarie risorse server sufficienti (CPU, RAM) per la generazione di feed di prodotti molto grandi, specialmente per negozi con decine di migliaia di prodotti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

-   **Cosa fa questa impostazione:** Questa opzione controlla se un selettore ad albero delle categorie viene visualizzato nella schermata di esportazione del prodotto, consentendoti di includere o escludere prodotti in base alla loro categoria.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando abilitato (selezionato):* Nella schermata di esportazione del prodotto (`AdminExportProductsFeedGoogle`), vedrai un albero visivo delle categorie del tuo negozio. Questo ti consente di selezionare facilmente quali categorie di prodotti devono essere incluse o escluse dal tuo feed di Google Merchant Center. Questo è fondamentale per filtrare il tuo feed per includere solo prodotti pertinenti o per escludere categorie specifiche che non desideri pubblicizzare su Google.
    *   *Quando disabilitato (deselezionato):* Il selettore ad albero delle categorie non apparirà nella schermata di esportazione. Ciò significa che non sarai in grado di filtrare i prodotti per categoria direttamente all'interno dell'interfaccia del modulo. Esporteresti quindi tutti i prodotti, o ti affideresti ad altre opzioni di filtraggio se disponibili (es. esclusioni specifiche del prodotto).
-   **Valore consigliato:** **SÌ (selezionato)**.
-   **Scenario / esempio del commerciante:** Vendi sia abbigliamento che download digitali. Vuoi pubblicizzare solo i tuoi prodotti di abbigliamento su Google Shopping. Abilitando "Mostra albero delle categorie", puoi selezionare facilmente solo le tue categorie "Abbigliamento" per l'inclusione nel feed, escludendo la tua categoria "Download digitali".

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminExportProductsFeedGoogleController (Back Office > Moduli > Feed di Google Merchant Center > Esporta Feed Prodotti)

Questa è la schermata principale in cui genererai e gestirai i tuoi feed di prodotti di Google Merchant Center. Vi si accede navigando in **Moduli > Gestione moduli**, trovando "Feed di Google Merchant Center" e quindi cliccando sul link "Esporta Feed Prodotti" (o simile, a seconda della versione di PrestaShop, potrebbe essere una voce di sottomenu sotto la voce principale del modulo).

Questa schermata ti consente di definire il contenuto e il formato del tuo feed di prodotti.

**Azioni e impostazioni disponibili:**

La schermata presenta un modulo con vari campi corrispondenti agli attributi richiesti da Google Merchant Center. Li compilerai per personalizzare il tuo feed.

-   **ID:**
    *   **Scopo:** Questo è l'identificatore univoco per ogni prodotto nel tuo feed. Google lo usa per abbinare il tuo prodotto ai suoi dati.
    *   **Effetto delle modifiche:** Assicura che ogni prodotto abbia un ID distinto, il che è fondamentale per Google per elaborare correttamente il tuo feed.
    *   **Valore consigliato:** Di solito si mappa all'ID interno o al riferimento del tuo prodotto.
-   **GTIN (Global Trade Item Number):**
    *   **Scopo:** I Global Trade Item Numbers (come EAN, UPC, ISBN) sono identificatori di prodotto univoci utilizzati a livello globale. Google li richiede per la maggior parte dei prodotti.
    *   **Effetto delle modifiche:** L'inclusione di GTIN corretti aiuta Google a identificare i tuoi prodotti in modo accurato, migliorando la visibilità e la fiducia. GTIN mancanti o errati possono portare a disapprovazioni del prodotto.
    *   **Valore consigliato:** Mappa al campo EAN/UPC del tuo prodotto.
-   **Identifier\_exists:**
    *   **Scopo:** Indica se esiste un identificatore di prodotto univoco (come GTIN, Brand, MPN) per il prodotto.
    *   **Effetto delle modifiche:** Se vendi prodotti personalizzati o prodotti senza identificatori standard, impostare questo su 'no' (o 'false') può prevenire disapprovazioni. Per la maggior parte dei prodotti standard, dovrebbe essere 'sì'.
    *   **Valore consigliato:** Di solito 'sì' se vengono forniti i GTIN.
-   **Title:**
    *   **Scopo:** Il nome del tuo prodotto come apparirà su Google Shopping. Questo è un campo cruciale per attirare i clic.
    *   **Effetto delle modifiche:** Un titolo chiaro e descrittivo con parole chiave pertinenti migliora la visibilità di ricerca e i tassi di clic.
    *   **Valore consigliato:** Il nome del tuo prodotto, potenzialmente arricchito con attributi chiave (es. "T-shirt rossa - Taglia M - Cotone").
-   **Availability:**
    *   **Scopo:** Indica se il prodotto è disponibile, esaurito o disponibile per il pre-ordine.
    *   **Effetto delle modifiche:** La disponibilità accurata impedisce ai clienti di cliccare su articoli esauriti, migliorando l'esperienza utente e riducendo la spesa pubblicitaria sprecata.
    *   **Valore consigliato:** Estratto automaticamente dallo stato di stock del tuo prodotto.
-   **Availability\_date:**
    *   **Scopo:** La data in cui un prodotto pre-ordinato diventerà disponibile.
    *   **Effetto delle modifiche:** Fornisce trasparenza ai clienti interessati agli articoli in pre-ordine.
    *   **Valore consigliato:** Impostato se offri pre-ordini.
-   **Inventory:**
    *   **Scopo:** La quantità del prodotto attualmente in stock.
    *   **Effetto delle modifiche:** Mantiene le tue inserzioni Google sincronizzate con i tuoi livelli di stock effettivi, prevenendo l'overselling.
    *   **Valore consigliato:** Estratto automaticamente dalla quantità di stock del tuo prodotto.
-   **Brand:**
    *   **Scopo:** Il nome del marchio del tuo prodotto.
    *   **Effetto delle modifiche:** Aiuta i clienti a identificare marchi familiari e migliora la categorizzazione dei prodotti su Google.
    *   **Valore consigliato:** Il marchio/produttore del tuo prodotto.
-   **Link:**
    *   **Scopo:** L'URL diretto alla pagina del tuo prodotto sul tuo negozio.
    *   **Effetto delle modifiche:** Essenziale per indirizzare i clienti da Google al tuo sito web.
    *   **Valore consigliato:** L'URL canonico del tuo prodotto.
-   **Image link:**
    *   **Scopo:** L'URL dell'immagine principale del tuo prodotto.
    *   **Effetto delle modifiche:** Immagini di alta qualità e chiare sono fondamentali per attirare i clic su Google Shopping.
    *   **Valore consigliato:** L'URL dell'immagine principale del tuo prodotto.
-   **Additional\_image\_link:**
    *   **Scopo:** URL per immagini aggiuntive del tuo prodotto.
    *   **Effetto delle modifiche:** Fornisce maggiori informazioni visive ai potenziali clienti, aiutandoli a prendere decisioni di acquisto.
    *   **Valore consigliato:** URL delle immagini secondarie del prodotto.
-   **Item subtitle:**
    *   **Scopo:** Una descrizione opzionale, più breve o un dettaglio aggiuntivo per il prodotto.
    *   **Effetto delle modifiche:** Può essere utilizzato per evidenziare caratteristiche chiave o promozioni.
    *   **Valore consigliato:** Opzionale, utilizzare per dettagli brevi e di impatto.
-   **Description:**
    *   **Scopo:** Una descrizione dettagliata del tuo prodotto.
    *   **Effetto delle modifiche:** Fornisce informazioni complete ai clienti e aiuta Google a comprendere la rilevanza del tuo prodotto.
    *   **Valore consigliato:** La descrizione completa del tuo prodotto.
-   **Product\_type:**
    *   **Scopo:** La tua categorizzazione del prodotto all'interno del tuo negozio.
    *   **Effetto delle modifiche:** Aiuta Google a comprendere la tua gerarchia di prodotti e può essere utilizzato per il targeting delle campagne.
    *   **Valore consigliato:** Il tuo percorso di categoria interno (es. "Abbigliamento > T-shirt > T-shirt da uomo").
-   **Condition:**
    *   **Scopo:** La condizione del prodotto (es. nuovo, usato, ricondizionato).
    *   **Effetto delle modifiche:** Informazioni accurate sulla condizione sono vitali per la fiducia del cliente e le politiche di Google.
    *   **Valore consigliato:** Di solito 'nuovo' per la maggior parte dei negozi e-commerce.
-   **Price:**
    *   **Scopo:** Il prezzo di vendita attuale del tuo prodotto.
    *   **Effetto delle modifiche:** La precisione dei prezzi è fondamentale. Discrepanze tra il tuo feed e il tuo sito web possono portare a disapprovazioni.
    *   **Valore consigliato:** Il prezzo attuale del tuo prodotto.
-   **Sale Price:**
    *   **Scopo:** Il prezzo scontato del tuo prodotto se è in saldo.
    *   **Effetto delle modifiche:** Evidenzia le promozioni e attira i clienti in cerca di offerte.
    *   **Valore consigliato:** Il prezzo specifico del tuo prodotto.
-   **Tax rate:**
    *   **Scopo:** L'aliquota fiscale applicabile al prodotto.
    *   **Effetto delle modifiche:** Assicura informazioni accurate sui prezzi, specialmente per le regioni in cui l'imposta viene calcolata al checkout.
    *   **Valore consigliato:** L'aliquota fiscale applicabile del tuo negozio.
-   **Contextual keywords:**
    *   **Scopo:** Parole chiave aggiuntive per aiutare Google a comprendere il tuo prodotto.
    *   **Effetto delle modifiche:** Può migliorare la rilevanza del tuo prodotto nei risultati di ricerca.
    *   **Valore consigliato:** Termini di ricerca pertinenti non già presenti nel titolo o nella descrizione.
-   **Google product category:**
    *   **Scopo:** La categorizzazione standardizzata di Google per i prodotti. Questo è un campo critico per Google per capire cosa stai vendendo.
    *   **Effetto delle modifiche:** La corretta categorizzazione dei tuoi prodotti secondo la tassonomia di Google migliora la visibilità e assicura che i tuoi prodotti appaiano nelle ricerche pertinenti. Categorie errate possono portare a disapprovazioni.
    *   **Valore consigliato:** Seleziona la Categoria di prodotto Google più specifica che si applica al tuo prodotto.

**Altre impostazioni e opzioni:**

-   **Esporta attributo taglia:**
    *   **Scopo:** Determina se gli attributi di taglia del prodotto devono essere inclusi nel feed, il che è importante per l'abbigliamento e altri prodotti dipendenti dalla taglia.
    *   **Effetto delle modifiche:**
        *   *Quando abilitato:* Le taglie del prodotto (es. S, M, L) verranno esportate, consentendo a Google di visualizzare le informazioni sulla taglia e le opzioni di filtro.
        *   *Quando disabilitato:* Le informazioni sulla taglia non verranno incluse.
    *   **Valore consigliato:** **SÌ** per i negozi di abbigliamento, **NO** per altri tipi di prodotti.
-   **Esporta categorie escluse:**
    *   **Scopo:** Ti consente di selezionare categorie specifiche i cui prodotti devono essere *esclusi* dal feed. Questo funziona in combinazione con l'impostazione "Mostra albero delle categorie" dalla configurazione principale.
    *   **Effetto delle modifiche:** I prodotti appartenenti alle categorie selezionate non appariranno nel feed generato.
    *   **Valore consigliato:** Usalo per filtrare i prodotti che non desideri pubblicizzare su Google (es. categorie esaurite, servizi o prodotti con margini bassi).
-   **Esporta data disponibilità:**
    *   **Scopo:** Controlla se l'attributo `availability_date` è incluso nel feed.
    *   **Effetto delle modifiche:**
        *   *Quando abilitato:* La data in cui un prodotto diventa disponibile (per i pre-ordini) verrà inclusa.
        *   *Quando disabilitato:* Questa informazione verrà omessa.
    *   **Valore consigliato:** **SÌ** se utilizzi la funzionalità di pre-ordine di PrestaShop e desideri comunicare le date di disponibilità a Google.
-   **Pulsante Genera feed:**
    *   **Scopo:** Avvia il processo di generazione del feed di prodotti XML/CSV in base a tutte le opzioni selezionate.
    *   **Effetto delle modifiche:** Crea il file del feed, che puoi quindi scaricare o fornire l'URL a Google Merchant Center per recuperi programmati.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Configurazione iniziale:** Mappa attentamente tutti gli attributi di Google Merchant Center ai campi del prodotto di PrestaShop. Presta particolare attenzione a GTIN, Brand e Categoria di prodotto Google.
2.  **Filtro per categoria:** Utilizza l'opzione "Esporta categorie escluse" per affinare quali prodotti vengono inviati a Google.
3.  **Genera e testa:** Genera un feed e caricalo su Google Merchant Center. Monitora eventuali errori o avvisi nel tuo account Google Merchant Center.
4.  **Recuperi programmati:** Una volta approvato il tuo feed, imposta un recupero programmato in Google Merchant Center utilizzando l'URL fornito dal modulo. Ciò garantisce che Google abbia sempre i dati più recenti del prodotto.
5.  **Revisione regolare:** Rivedi periodicamente le diagnostiche di Google Merchant Center per eventuali disapprovazioni o avvisi e regola di conseguenza le impostazioni del modulo o i dati del prodotto in PrestaShop.

#### index.php (gmfeed/controllers/admin/index.php)

Questo file probabilmente funge da segnaposto o da reindirizzamento all'interno della struttura del controller di amministrazione del modulo e non rappresenta una schermata distinta e configurabile per il commerciante. La configurazione e la gestione principali avvengono tramite `AdminExportProductsFeedGoogleController`.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Mostra albero delle categorie | SÌ | Abilita il filtro per categoria nella schermata di esportazione per una selezione precisa dei prodotti. |
| **AdminExportProductsFeedGoogle** | ID | ID prodotto | Identificatore univoco per ogni prodotto nel feed. |
| | GTIN | EAN/UPC prodotto | Global Trade Item Number per l'identificazione del prodotto. |
| | Identifier\_exists | Sì | Indica se sono presenti identificatori univoci. |
| | Titolo | Nome prodotto | Titolo del prodotto per Google Shopping. |
| | Disponibilità | Rilevato automaticamente | Stato di stock del prodotto (disponibile, esaurito). |
| | Availability\_date | Rilevato automaticamente | Data di disponibilità per il pre-ordine. |
| | Inventario | Rilevato automaticamente | Quantità di stock attuale. |
| | Brand | Produttore prodotto | Nome del marchio del prodotto. |
| | Link | URL prodotto | Link diretto alla pagina del prodotto. |
| | Image link | URL immagine principale prodotto | URL dell'immagine principale del prodotto. |
| | Additional\_image\_link | URL immagini secondarie prodotto | URL delle immagini aggiuntive del prodotto. |
| | Item subtitle | Opzionale | Breve dettaglio aggiuntivo del prodotto. |
| | Descrizione | Descrizione prodotto | Descrizione dettagliata del prodotto. |
| | Product\_type | Il tuo percorso di categoria | La tua categorizzazione interna del prodotto. |
| | Condizione | Nuovo | Condizione del prodotto (nuovo, usato, ricondizionato). |
| | Prezzo | Prezzo prodotto | Prezzo di vendita attuale. |
| | Sale Price | Prezzo specifico prodotto | Prezzo scontato se in saldo. |
| | Tax rate | Aliquota fiscale del negozio | Aliquota fiscale applicabile. |
| | Contextual keywords | Opzionale | Parole chiave aggiuntive per la rilevanza del prodotto. |
| | Google product category | Seleziona dalla Tassonomia Google | Categoria di prodotto standardizzata di Google. |
| | Esporta attributo taglia | SÌ (per abbigliamento) | Include gli attributi di taglia del prodotto nel feed. |
| | Esporta categorie escluse | Seleziona secondo necessità | Esclude i prodotti dalle categorie selezionate. |
| | Esporta data disponibilità | SÌ (per pre-ordini) | Include l'attributo `availability_date`. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prodotti non appaiono su Google Shopping, o ricevo disapprovazioni. Cosa dovrei controllare per primo?**
R1:

-   **Account Google Merchant Center (GMC):** Accedi al tuo account GMC e controlla la sezione "Diagnostica". È qui che Google segnala errori o avvisi specifici per i tuoi prodotti e il tuo feed.
-   **Elaborazione del feed:** Assicurati che il tuo feed sia stato elaborato con successo da Google. Controlla la sezione "Feed" in GMC.
-   **Attributi richiesti:** Verifica che tutti gli attributi Google obbligatori (ID, Titolo, Link, Link immagine, Prezzo, Descrizione, GTIN/Brand/MPN, Disponibilità, Categoria di prodotto Google) siano correttamente mappati e popolati nelle impostazioni di esportazione del modulo.
-   **Discrepanze di dati:** Google è molto severo riguardo alla corrispondenza di prezzo e disponibilità tra il tuo feed e il tuo sito web. Assicurati che i dati dei tuoi prodotti PrestaShop siano accurati e che Google stia recuperando il feed più recente.
-   **Categoria di prodotto Google:** Assicurati di aver selezionato la Categoria di prodotto Google più accurata per i tuoi prodotti.

**D2: Ho apportato modifiche ai miei prodotti in PrestaShop, ma non si stanno aggiornando su Google Shopping.**
R2:

-   **Genera nuovo feed:** Dopo aver apportato modifiche in PrestaShop, devi generare un nuovo feed utilizzando il pulsante "Genera feed" del modulo.
-   **Recupero programmato di Google:** Google Merchant Center deve recuperare questo feed aggiornato. Se hai impostato un recupero programmato, si aggiornerà automaticamente al prossimo orario programmato. Puoi anche attivare manualmente un recupero nel tuo account Google Merchant Center in "Feed" > "Recupera ora".
-   **Caching:** Svuota la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni) e la cache del browser per assicurarti di visualizzare l'ultima versione della configurazione del modulo e del feed generato.

**D3: Come posso escludere determinati prodotti o categorie dal feed di Google?**
R3:

-   Nella schermata di configurazione principale del modulo, assicurati che "Mostra albero delle categorie" sia abilitato.
-   Quindi, nella schermata `AdminExportProductsFeedGoogle`, utilizza l'opzione "Esporta categorie escluse". Vedrai un albero delle tue categorie. Seleziona le categorie i cui prodotti desideri escludere dal feed.
-   Genera un nuovo feed dopo aver effettuato queste selezioni.

**D4: Il processo di generazione del feed richiede molto tempo o va in timeout per il mio grande negozio.**
R4:

-   **Risorse del server:** La generazione di feed di grandi dimensioni può richiedere molte risorse. Contatta il tuo provider di hosting per assicurarti che il tuo server abbia un limite di memoria PHP, un tempo di esecuzione e risorse CPU sufficienti.
-   **Impostazioni PHP:** Aumenta `max_execution_time` e `memory_limit` nel tuo file `php.ini` (o tramite il pannello di controllo del tuo hosting).
-   **Filtra prodotti:** Se possibile, prova a segmentare il tuo feed escludendo categorie o prodotti meno importanti per ridurre le dimensioni del feed.
-   **Aggiornamenti del modulo:** Assicurati di utilizzare l'ultima versione del modulo, poiché i miglioramenti delle prestazioni sono spesso inclusi negli aggiornamenti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Feed di Google Merchant Center` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i controller del Back-Office per la configurazione e la generazione del feed. Utilizza un controller frontale per esporre l'URL del feed generato per i recuperi programmati di Google. Il modulo non estende `ObjectModel` per tabelle di database personalizzate, ma si basa sulla classe `Configuration` di PrestaShop per le impostazioni. Integra una libreria di strumenti di ricerca di terze parti per la funzionalità di completamento automatico.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/feed.php`
    *   **Nome classe:** `GmfeedFeedModuleFrontController`
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo controller è responsabile di servire il feed di prodotti XML/CSV generato a Google Merchant Center. Quando Google esegue un recupero programmato, accede a un URL gestito da questo controller. Il controller recupera i dati del feed generato più di recente e li restituisce, tipicamente con intestazioni appropriate per il download del file o la visualizzazione diretta.
-   `controllers/front/index.php`
    *   **Nome classe:** `GmfeedIndexModuleFrontController`
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo è probabilmente un segnaposto o un controller frontale predefinito che potrebbe reindirizzare o semplicemente visualizzare una pagina vuota. Non sembra avere un ruolo funzionale diretto nella generazione o visualizzazione del feed in base alle informazioni fornite.

#### Controller di amministrazione Back-Office

-   `controllers/admin/AdminExportProductsFeedGoogle.php`
    *   **Nome classe:** `AdminExportProductsFeedGoogleController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** "Esporta Feed Prodotti" (o simile, collegato dalla configurazione principale del modulo)
    *   **Entità gestita:** Generazione del feed di prodotti.
    *   **Responsabilità:** Questo è il controller di amministrazione principale per la gestione e la generazione del feed di Google Merchant Center. Gestisce la visualizzazione del modulo di configurazione per gli attributi del feed (GTIN, Titolo, Prezzo, ecc.), elabora le sottomissioni del modulo e attiva la logica di generazione del feed. Interagisce con i dati di prodotto, categoria e attributo di PrestaShop per compilare il feed. Gestisce anche l'esclusione delle categorie (`gm_export_exclude_categories`) e altre impostazioni specifiche del feed.
-   `controllers/admin/index.php`
    *   **Nome classe:** `GmfeedIndexModuleAdminController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** (Probabilmente non una scheda diretta, ma parte del routing interno del modulo)
    *   **Responsabilità:** Simile alla sua controparte front-office, questo è probabilmente un segnaposto o un controller di amministrazione predefinito. Non sembra gestire un'entità specifica o fornire un'interfaccia utente distinta.

### 4.3 Classi e modelli principali (`classes/`)

Le informazioni fornite indicano l'assenza di classi o modelli personalizzati all'interno della directory `classes/`. Il modulo probabilmente esegue le sue operazioni direttamente all'interno del file principale del modulo (`gmfeed.php`) e dei suoi controller, sfruttando le classi `ObjectModel` esistenti di PrestaShop (come `Product`, `Category`, `Manufacturer`, `AttributeGroup`, `Attribute`) e la classe `Configuration` per le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   `gmfeed/lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Probabilmente Back-office.
    *   **Dettagli:** Questo script fa parte di una libreria di strumenti di ricerca, probabilmente utilizzata per la funzionalità di completamento automatico all'interno dei moduli di configurazione di amministrazione, come la selezione delle categorie di prodotto Google o l'esclusione di prodotti/categorie specifici. Si legherebbe ai campi di input, effettuerebbe richieste AJAX a un endpoint backend (possibilmente gestito da uno dei controller di amministrazione) per recuperare suggerimenti e visualizzarli all'utente.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `gmfeed/lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Dettagli:** Fornisce lo stile per i suggerimenti di completamento automatico e i campi di input, garantendo un aspetto coerente e intuitivo per lo strumento di ricerca all'interno dell'interfaccia di amministrazione del modulo.
    *   **Selettori CSS chiave:** Probabilmente include classi per il contenitore di completamento automatico, l'elenco dei suggerimenti, il suggerimento attivo e il campo di input.
-   `gmfeed/views/admin-theme.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Dettagli:** Contiene regole di stile generali specifiche per le pagine di configurazione del modulo nel Back Office di PrestaShop. Ciò potrebbe includere regolazioni del layout, stile dei pulsanti, stile degli elementi del modulo o segnali visivi specifici per l'interfaccia del modulo.
    *   **Selettori CSS chiave:** ID o classi di contenitori specifici del modulo, classi di elementi del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

Il dossier del modulo indica `actionAdminControllerSetMedia` come un hook del front-office, il che è insolito in quanto è un hook di amministrazione. È più probabile che il modulo utilizzi `actionAdminControllerSetMedia` per caricare le sue risorse JS/CSS nel back office, e i template elencati di seguito vengano renderizzati nel contesto di amministrazione.

#### Template di amministrazione (`views/templates/admin/`)

-   `gmfeed/lib/searchTool/views/scripts.tpl`
    *   **Scopo:** Probabilmente include codice JavaScript o inizializza la funzionalità di completamento automatico. Questo template verrebbe renderizzato nel Back Office per configurare lo strumento di ricerca.
-   `gmfeed/views/categories-fancybox.tpl`
    *   **Scopo:** Questo template viene utilizzato per visualizzare l'albero delle categorie per la selezione/esclusione, probabilmente all'interno di un popup Fancybox (o simile). Renderizzerebbe l'elenco gerarchico delle categorie.
-   `gmfeed/views/exclude-products.tpl`
    *   **Scopo:** Questo template visualizzerebbe l'interfaccia per la selezione dei prodotti da escludere dal feed, potenzialmente utilizzando lo strumento di ricerca e l'albero delle categorie.
-   `gmfeed/views/google_lang_links.tpl`
    *   **Scopo:** Questo template potrebbe essere utilizzato per visualizzare collegamenti o informazioni relative a Google Merchant Center per diverse lingue, possibilmente guidando il commerciante a configurare i feed per varie lingue del negozio.
-   `gmfeed/views/returnAlert.tpl`
    *   **Scopo:** Un template generico per la visualizzazione di avvisi o messaggi all'utente nel Back Office, come messaggi di successo dopo la generazione del feed o notifiche di errore.
-   `gmfeed/views/script-fancybox.tpl`
    *   **Scopo:** Questo template probabilmente contiene codice JavaScript per inizializzare e configurare la libreria Fancybox (o simile), utilizzata per visualizzare popup come l'albero delle categorie.
-   `gmfeed/views/script.tpl`
    *   **Scopo:** Un template di script generale per il Back Office del modulo, che potenzialmente contiene varie funzionalità JavaScript, listener di eventi o chiamate AJAX relative al processo di configurazione e generazione del feed.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   Il modulo non sembra creare tabelle SQL personalizzate in base alle informazioni fornite (nessuna `classes/` con `ObjectModel` o file SQL di `install/uninstall`).
    *   Le impostazioni di configurazione (es. `pf_tree`, `gm_export_size_attribute`, `gm_export_exclude_categories`, `gm_export_availability_date`) sono memorizzate nella tabella `ps_configuration`. Il valore di `gm_export_exclude_categories` sarebbe probabilmente un array serializzato di ID di categoria.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin viene inizializzato e i suoi media (JS/CSS) vengono impostati. | Utilizzato dal modulo per caricare i suoi file JavaScript e CSS specifici (es. `autocomplete.js`, `admin-theme.css`) nel Back Office per le sue schermate di configurazione. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Feed di Google Merchant Center", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità del modulo e all'integrazione con il vostro negozio PrestaShop.
