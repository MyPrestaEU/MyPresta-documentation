---
title: "Sconti quantità sugli elenchi prodotti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Sconti quantità sugli elenchi prodotti' di MyPresta.eu."
sidebar:
  label: "Sconti quantità sugli elenchi prodotti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Quantity discounts on products lists su MyPresta.eu](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Sconti quantità sugli elenchi prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile dopo l'installazione cliccando sul pulsante "Configura".

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Questa sezione contiene le impostazioni principali per abilitare o disabilitare la funzionalità del modulo e controllarne il comportamento di base.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando abilitato:* Il modulo inizierà a visualizzare gli sconti quantità sulle pagine di elenco prodotti in base alle altre impostazioni.
    *   *Quando disabilitato:* Il modulo smetterà di visualizzare qualsiasi sconto quantità sulle pagine di elenco prodotti.
-   **Valore consigliato:** SÌ (a meno che non sia necessario disabilitarlo temporaneamente per manutenzione).
-   **Scenario / esempio del commerciante:** Se stai eseguendo una promozione speciale che sovrascrive gli sconti quantità, potresti disabilitare temporaneamente il modulo. Altrimenti, tienilo abilitato per sfruttarne i vantaggi.

#### Opzioni di visualizzazione

-   **Cosa fa questa impostazione:** Queste opzioni controllano l'aspetto visivo e il posizionamento delle informazioni sugli sconti quantità negli elenchi dei tuoi prodotti.
-   **Effetto della modifica di questa impostazione:**
    *   *Esempio: "Visualizza sulla pagina del prodotto":*
        *   *Quando abilitato:* Gli sconti quantità verranno mostrati anche nella pagina di dettaglio del singolo prodotto.
        *   *Quando disabilitato:* Gli sconti quantità appariranno solo nelle pagine di elenco prodotti (categorie, risultati di ricerca, ecc.), supponendo che siano già presenti nella pagina del prodotto per impostazione predefinita della funzionalità di PrestaShop.
    *   *Esempio: "Posizione delle informazioni sullo sconto":*
        *   *Opzione A (es. "Sotto il prezzo del prodotto"):* I dettagli dello sconto appariranno direttamente sotto il prezzo principale del prodotto.
        *   *Opzione B (es. "Sopra il nome del prodotto"):* I dettagli dello sconto appariranno sopra il nome del prodotto.
-   **Valore consigliato:** Sperimenta con le posizioni per trovare ciò che si adatta meglio al tuo tema. Spesso, "Sotto il prezzo del prodotto" è un buon punto di partenza. "Visualizza sulla pagina del prodotto" può essere abilitato se il tuo tema non mostra già in modo prominente gli sconti quantità lì.
-   **Scenario / esempio del commerciante:** Se le tue schede prodotto sono molto compatte, potresti scegliere una posizione discreta. Se vuoi evidenziare gli sconti, una posizione più prominente potrebbe essere migliore.

#### Stile e personalizzazione

-   **Cosa fa questa impostazione:** Queste impostazioni ti consentono di personalizzare l'aspetto della visualizzazione dello sconto per abbinarlo al tema del tuo negozio. Ciò potrebbe includere opzioni per il colore del testo, il colore di sfondo, la dimensione del carattere o persino CSS personalizzato.
-   **Effetto della modifica di questa impostazione:**
    *   *Esempio: "Colore del testo":*
        *   *Se impostato su rosso:* Il testo dello sconto apparirà in rosso.
        *   *Se impostato su verde:* Il testo dello sconto apparirà in verde.
-   **Valore consigliato:** Scegli colori e stili che si integrino con il tuo tema esistente.
-   **Scenario / esempio del commerciante:** Se il tuo marchio utilizza una specifica palette di colori, vorresti che le informazioni sugli sconti si fondessero senza soluzione di continuità piuttosto che stonare.

#### Impostazioni avanzate

-   **Cosa fa questa impostazione:** Questa sezione potrebbe contenere impostazioni per la cache, l'ottimizzazione delle prestazioni o opzioni di integrazione specifiche.
-   **Effetto della modifica di questa impostazione:**
    *   *Esempio: "Abilita caching":*
        *   *Quando abilitato:* Il modulo memorizzerà l'HTML dello sconto generato per caricarsi più velocemente, migliorando la velocità della pagina.
        *   *Quando disabilitato:* Il modulo genererà l'HTML dello sconto ad ogni caricamento della pagina, potenzialmente rallentando le pagine ma garantendo che vengano sempre mostrati i dati più recenti (utile durante lo sviluppo).
-   **Valore consigliato:** SÌ per il caching sui negozi live.
-   **Scenario / esempio del commerciante:** Se noti problemi di prestazioni sulle pagine con molti elenchi di prodotti, l'abilitazione del caching può aiutare. Durante lo sviluppo del tema, potresti disabilitare il caching per vedere le modifiche istantaneamente.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminPlqdSearchController (Back Office > Moduli > Sconti quantità sugli elenchi prodotti > Impostazioni di ricerca)

Questo controller probabilmente gestisce le impostazioni relative a come il modulo identifica ed elabora i prodotti per la visualizzazione degli sconti, possibilmente includendo uno strumento di ricerca per prodotti o categorie specifici.

-   **Nome schermata e posizione nel menu:** Questa schermata potrebbe essere accessibile tramite una sotto-scheda o un link dedicato all'interno della pagina di configurazione principale del modulo, possibilmente etichettata "Impostazioni di ricerca" o "Selezione prodotto".
-   **Azioni e impostazioni disponibili:** Questa schermata tipicamente presenterebbe una griglia o un modulo per:
    *   **Cerca prodotti:** Consente di trovare prodotti specifici per nome, ID o riferimento.
    *   **Escludi prodotti/categorie:** Definisci prodotti specifici o intere categorie in cui gli sconti quantità NON devono essere visualizzati, anche se li hanno configurati.
    *   **Gestisci regole di visualizzazione:** Potrebbe impostare regole più granulari per quando e dove gli sconti appaiono in base agli attributi del prodotto o ad altri criteri.
-   **Effetto delle modifiche:**
    *   *Esclusione di un prodotto:* Le informazioni sullo sconto quantità per quel prodotto specifico non appariranno più in nessuna pagina di elenco prodotti.
    *   *Esclusione di una categoria:* Tutti i prodotti all'interno della categoria selezionata avranno le loro informazioni sullo sconto quantità nascoste nelle pagine di elenco.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata se hai prodotti o categorie specifici in cui la visualizzazione degli sconti quantità negli elenchi non è desiderata (es. articoli di altissimo valore, prodotti su ordinazione, o prodotti con prezzi complessi che potrebbero confondere i clienti se semplificati).

#### index.php (plqd/controllers/admin/index.php)

Questo file, sebbene elencato come controller di amministrazione, è spesso un segnaposto o un reindirizzatore nei moduli PrestaShop. Nel contesto di questo modulo, è altamente probabile che `plqd/index.php` (il file principale del modulo) gestisca il modulo di configurazione primario tramite `getContent()`, e `AdminPlqdSearchController.php` gestisca eventuali interfacce di amministrazione secondarie più complesse. L'`index.php` nella directory `controllers/admin` potrebbe semplicemente garantire che l'accesso diretto alla directory sia gestito in modo elegante, oppure potrebbe essere un file legacy. Per i commercianti, tutte le impostazioni pertinenti si troveranno nella configurazione principale del modulo o in `AdminPlqdSearchController`.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita modulo | SÌ | Attiva/disattiva la funzionalità principale del modulo. |
| | Visualizza sulla pagina del prodotto | SÌ/NO (Dipende dal tema) | Mostra gli sconti sulle singole pagine del prodotto. |
| | Posizione delle informazioni sullo sconto | Sotto il prezzo del prodotto | Controlla dove appare il testo dello sconto sulle schede prodotto. |
| | Colore del testo | (Predefinito del tema) | Imposta il colore del testo dello sconto. |
| | Colore di sfondo | (Predefinito del tema) | Imposta il colore di sfondo del blocco sconto. |
| | Abilita caching | SÌ | Migliora le prestazioni memorizzando l'HTML generato. |
| **AdminPlqdSearchController** | Escludi prodotto (per ID/Nome) | N/A | Impedisce la visualizzazione dello sconto per prodotti specifici. |
| | Escludi categoria | N/A | Impedisce la visualizzazione dello sconto per tutti i prodotti di una categoria. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Gli sconti quantità non vengono visualizzati negli elenchi dei miei prodotti dopo l'installazione.**
R:

1.  **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Sconti quantità sugli elenchi prodotti" sia installato e abilitato.
2.  **Configura il modulo:** Clicca su "Configura" per il modulo e assicurati che l'impostazione principale "Abilita modulo" sia impostata su SÌ.
3.  **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
4.  **Controlla gli sconti sui prodotti:** Assicurati che i prodotti per i quali ti aspetti di visualizzare gli sconti abbiano effettivamente sconti quantità configurati nelle loro impostazioni (Back Office > Catalogo > Prodotti > Modifica prodotto > Scheda Prezzi > Prezzi specifici).
5.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se dopo aver svuotato la cache e controllato le impostazioni, non appare ancora, contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D2: Il testo dello sconto viene visualizzato, ma non si adatta bene al mio tema (colori, carattere o allineamento sbagliati).**
R:

1.  **Configurazione del modulo:** Vai alla pagina di configurazione del modulo (**Moduli > Gestione moduli > Configura** per "Sconti quantità sugli elenchi prodotti"). Cerca le opzioni "Stile e personalizzazione". Potresti essere in grado di regolare colori, dimensioni del carattere o spaziatura direttamente da qui.
2.  **CSS personalizzato:** Se le impostazioni del modulo non offrono un controllo sufficiente, il tuo webmaster o sviluppatore può aggiungere CSS personalizzato al tuo tema per sovrascrivere gli stili predefiniti del modulo. I file CSS del modulo (vedi Sezione 7.5) forniranno loro i selettori di classe necessari.

**D3: Voglio nascondere gli sconti quantità per alcuni prodotti o categorie, ma non per tutti.**
R:

1.  **AdminPlqdSearchController:** Naviga alla schermata di amministrazione dedicata del modulo (probabilmente una sotto-scheda o un link dalla configurazione principale, potenzialmente denominata "Impostazioni di ricerca" o "Esclusioni").
2.  **Aggiungi esclusioni:** Utilizza gli strumenti su questa schermata per cercare e aggiungere prodotti specifici o intere categorie a un elenco di esclusione. Una volta aggiunti, il modulo ignorerà questi elementi quando visualizza gli sconti negli elenchi dei prodotti.

**D4: Questo modulo rallenterà il mio negozio?**
R: Il modulo è progettato per essere efficiente. Sfrutta i dati esistenti sugli sconti quantità di PrestaShop.

1.  **Abilita caching:** Assicurati che l'opzione "Abilita caching" nelle impostazioni avanzate del modulo sia impostata su SÌ. Ciò riduce significativamente il carico di elaborazione sulle visualizzazioni di pagina successive.
2.  **Prestazioni del server:** Se il tuo server è già sottodimensionato o pesantemente caricato, qualsiasi modulo aggiuntivo può avere un impatto minore. Assicurati che il tuo hosting soddisfi le specifiche raccomandate da PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Sconti quantità sugli elenchi prodotti" (`plqd`) è un modulo PrestaShop standard che segue il modello MVC. Estende principalmente la classe `Module`, sfruttando il sistema di hook di PrestaShop per iniettare contenuto nei template degli elenchi prodotti. Non introduce entità `ObjectModel` personalizzate, ma legge i dati `SpecificPrice` esistenti. Il modulo utilizza un controller di amministrazione dedicato (`AdminPlqdSearchController`) per la gestione delle esclusioni di prodotti/categorie e integra JavaScript e CSS per la visualizzazione nel front-office.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno esplicitamente definito come controller frontale autonomo. Il modulo probabilmente inietta il suo contenuto direttamente nei template tramite hook e gestisce qualsiasi contenuto dinamico o AJAX tramite metodi `displayAjax` all'interno della classe principale del modulo o tramite JS incluso.
-   **Controller Admin Back-Office**:
    -   `plqd/controllers/admin/AdminPlqdSearchController.php`
        -   **Nome classe e classe genitore**: `AdminPlqdSearchController` estende `ModuleAdminController`.
        -   **Nome tab e entità gestita**: Questo controller è responsabile della gestione delle impostazioni di ricerca ed esclusione per prodotti e categorie. Probabilmente fornisce un'interfaccia a griglia o un modulo per selezionare prodotti/categorie che *non* dovrebbero visualizzare sconti quantità negli elenchi prodotti. Non gestisce un `ObjectModel` specifico ma piuttosto dati di configurazione (es. `Configuration::updateValue` per ID separati da virgola).
    -   `plqd/controllers/admin/index.php`
        -   Questo file è tipicamente una misura di sicurezza in PrestaShop, che impedisce l'elenco diretto delle directory. Di solito contiene un semplice `header('Location: ../../index.php?controller=AdminHome');` o `die('No direct script access');`. Non funge da controller funzionale per la logica o l'interfaccia utente del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Nessuna classe personalizzata o definizione `ObjectModel` si trova nella directory `classes/` per questo modulo. Il modulo interagisce direttamente con le classi `Product` e `SpecificPrice` di PrestaShop e con la classe `Configuration` per le sue impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   `plqd/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito**: Back-office (probabilmente utilizzato all'interno di `AdminPlqdSearchController`).
    -   **Scopo**: Fornisce la funzionalità di autocompletamento per la ricerca di prodotti o categorie all'interno dell'interfaccia di esclusione dell'amministratore. Si lega ai campi di input, invia richieste AJAX a un endpoint backend (possibilmente `AdminPlqdSearchController` stesso o un gestore AJAX dedicato) e visualizza suggerimenti all'utente.
-   `plqd/views/js/plqd.js`
    -   **Ambito**: Front-office.
    -   **Scopo**: Questo è il JavaScript principale del front-office per il modulo. Probabilmente:
        -   Scansiona gli elementi dell'elenco prodotti al caricamento della pagina o dopo gli aggiornamenti AJAX (es. scorrimento infinito, filtri di categoria).
        -   Inietta o formatta dinamicamente le informazioni sugli sconti quantità nelle schede prodotto.
        -   Può gestire aggiustamenti reattivi o piccole interazioni UI relative alla visualizzazione dello sconto.
        -   Potrebbe potenzialmente effettuare chiamate AJAX per recuperare i dati dello sconto se non pre-renderizzati da Smarty.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `plqd/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito**: Back-office.
    -   **Scopo**: Stila il menu a discesa di autocompletamento e i campi di input utilizzati in `AdminPlqdSearchController` per la ricerca di prodotti/categorie.
    -   **Selettori chiave**: Probabilmente si rivolge a classi come `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, ecc.
-   `plqd/views/css/plqd-classic.css`
    -   **Ambito**: Front-office.
    -   **Scopo**: Fornisce uno stile predefinito per la visualizzazione degli sconti quantità, potenzialmente adattato per temi PrestaShop più vecchi o un aspetto "classico".
    -   **Selettori chiave**: Si rivolge al contenitore principale per le informazioni sullo sconto (es. `.plqd-discounts-wrapper`), singole righe di sconto (`.plqd-discount-item`), quantità (`.plqd-quantity`) e prezzi (`.plqd-price`).
-   `plqd/views/css/plqd-hide-default.css`
    -   **Ambito**: Front-office.
    -   **Scopo**: Questo foglio di stile probabilmente contiene regole per nascondere le visualizzazioni predefinite degli sconti quantità che potrebbero essere presenti in alcuni temi, per prevenire la duplicazione quando il modulo inietta la propria versione stilizzata.
    -   **Selettori chiave**: Potrebbe rivolgersi a elementi comuni del tema come `.product-price-and-shipping .discount-quantity` o simili.
-   `plqd/views/css/plqd.css`
    -   **Ambito**: Front-office.
    -   **Scopo**: Il foglio di stile principale del front-office per il modulo, che fornisce lo stile principale per la visualizzazione degli sconti quantità. Questo potrebbe essere un foglio di stile più moderno o generale rispetto a `plqd-classic.css`.
    -   **Selettori chiave**: Simili a `plqd-classic.css`, si rivolgono a `.plqd-discounts-wrapper`, `.plqd-discount-item`, ecc. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` o `theme.css` del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `plqd/views/tpl/html.tpl`
        -   **Hook**: Questo è probabilmente il template principale renderizzato dall'hook `hookDisplayProductListFunctionalButtons` (o hook simile per l'elenco prodotti) del modulo per produrre l'HTML dello sconto quantità per un singolo prodotto. Riceve i dati del prodotto e del prezzo specifico dal modulo.
        -   **Output**: Renderizza l'HTML strutturato per le righe dello sconto quantità (es. "Da X unità: Y€").
-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `plqd/lib/searchTool/views/scripts.tpl`
        -   **Scopo**: Questo template è probabilmente incluso nella vista `AdminPlqdSearchController`. Contiene l'inizializzazione JavaScript per la funzionalità di autocompletamento (es. blocchi `$(document).ready()`, definizioni di variabili per URL AJAX, ecc.) e potenzialmente inclusioni CSS.
    -   `plqd/views/tpl/selectedProducts.tpl`
        -   **Scopo**: Utilizzato all'interno di `AdminPlqdSearchController` per visualizzare l'elenco dei prodotti o delle categorie che sono stati selezionati per l'esclusione. Tipicamente renderizzerebbe una tabella o un elenco di questi elementi, possibilmente con opzioni per rimuoverli.
-   **Template Front-office (`views/templates/front/`)**:
    -   `plqd/views/tpl/html-product-page.tpl`
        -   **Scopo**: Questo template è specificamente progettato per visualizzare gli sconti quantità nella pagina del singolo prodotto, se il modulo è configurato per farlo. Potrebbe avere uno stile o una struttura leggermente diversi rispetto al template della pagina di elenco (`html.tpl`) per adattarsi meglio al layout della pagina del prodotto.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Il modulo non crea tabelle SQL personalizzate. Si basa sulla tabella `ps_specific_price` di PrestaShop per i dati degli sconti quantità.
    -   Le impostazioni di configurazione (es. stato abilitato, opzioni di stile, ID di prodotti/categorie esclusi) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `PLQD_`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere CSS del modulo (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) e JavaScript (`plqd.js`). |
| `displayProductListFunctionalButtons` | All'interno degli elementi dell'elenco prodotti (es. categoria, risultati di ricerca). | Hook primario per iniettare l'HTML dello sconto quantità (`html.tpl`) nelle schede prodotto. |
| `displayProductPriceBlock` (tipo `after_price`) | Dopo il blocco prezzo principale nelle pagine prodotto. | Utilizzato per iniettare `html-product-page.tpl` se configurato per mostrare sconti nelle pagine prodotto. |
| `displayRightColumn` / `displayLeftColumn` | Nelle colonne della barra laterale destra/sinistra. | Meno probabile per questo modulo, ma potrebbe essere utilizzato per un blocco promozionale relativo agli sconti quantità se implementato. |
| `displayFooter` | Nella parte inferiore di ogni pagina del front-office. | Potrebbe essere utilizzato per JS a caricamento tardivo o script aggiuntivi se necessario. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Potrebbe essere utilizzato per svuotare la cache del modulo relativa a quel prodotto, garantendo che i prezzi specifici aggiornati siano riflessi. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Crea voci di configurazione in `ps_configuration`. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Pulisce le voci di configurazione ed eventualmente eventuali dati personalizzati. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto sviluppatori dedicato per il modulo "Sconti quantità sugli elenchi prodotti", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team è disponibile per assistere con qualsiasi problema tecnico o domanda riguardante la funzionalità e l'integrazione del modulo.
