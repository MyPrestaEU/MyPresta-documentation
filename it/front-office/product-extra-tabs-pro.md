---
title: "Product Extra Tabs Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Product Extra Tabs Pro di MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product Extra Tabs Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Product Extra Tabs Pro" è configurato principalmente direttamente dalla pagina di modifica del prodotto, consentendoti di gestire le schede su base per prodotto. La schermata di configurazione principale del modulo gestisce le impostazioni globali.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione principale, vai su **Moduli > Gestione moduli**, cerca "Product Extra Tabs Pro" e clicca su "Configura".

Su questa schermata, troverai le impostazioni che si applicano globalmente o che definiscono il comportamento del modulo in tutto il tuo negozio.

-   **Impostazione: Abilita Editor TinyMCE per il Contenuto delle Schede**

    -   **Cosa fa questa impostazione:** Questo interruttore determina se un editor di testo ricco (TinyMCE, lo stesso editor che PrestaShop usa per le descrizioni dei prodotti) è disponibile quando crei o modifichi il contenuto delle schede.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Vedrai un editor facile da usare con opzioni di formattazione (grassetto, corsivo, elenchi, immagini, link, ecc.) quando aggiungi contenuto alle tue schede extra. Questo rende facile creare contenuti visivamente accattivanti e ben strutturati senza conoscere l'HTML.
        -   *Quando disabilitato:* Avrai solo un'area di testo semplice per il contenuto delle schede. Dovresti scrivere manualmente i tag HTML per formattare il tuo testo, il che è più complesso per gli utenti non tecnici.
    -   **Valore consigliato:** **SÌ**
    -   **Scenario / esempio per il commerciante:** Se vuoi aggiungere immagini, video o testo stilizzato alle tue schede (ad esempio, una scheda "Tabella taglie" con un'immagine, o una scheda "Garanzia" con termini chiave in grassetto), abilita questa opzione. Se hai bisogno solo di testo semplice, puoi disabilitarla per un'interfaccia più semplice.
-   **Impostazione: Visualizza Schede Globalmente (per tutti i prodotti)**

    -   **Cosa fa questa impostazione:** Questa opzione ti consente di creare schede "globali" che appaiono automaticamente su *ogni* pagina prodotto del tuo negozio. Questo è utile per informazioni che si applicano universalmente, come le politiche di spedizione generali o le storie del marchio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutte le schede che crei all'interno dell'interfaccia di configurazione del modulo (non sulle singole pagine prodotto) verranno visualizzate su tutte le pagine prodotto. Puoi quindi gestire queste schede globali dalla configurazione principale del modulo.
        -   *Quando disabilitato:* Le schede devono essere create e gestite individualmente per ogni prodotto dalla rispettiva pagina di modifica del prodotto. Le schede globali non verranno visualizzate.
    -   **Valore consigliato:** **SÌ** (se hai informazioni che si applicano a tutti i prodotti, altrimenti NO).
    -   **Scenario / esempio per il commerciante:** Vuoi aggiungere una scheda "Politica di reso" che sia identica per tutti i prodotti. Abilita questa opzione, crea la scheda qui, e apparirà su ogni pagina prodotto. Se hai bisogno solo di schede uniche per prodotti specifici, mantieni questa opzione disabilitata.
-   **Impostazione: Posizione di Visualizzazione delle Schede**

    -   **Cosa fa questa impostazione:** Questo menu a discesa controlla dove vengono visualizzate le schede extra sulla pagina del prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzione: `displayProductExtraContent` (Predefinito):* Le schede appariranno nell'area standard del contenuto del prodotto, di solito sotto i dettagli principali del prodotto, accanto alle schede predefinite di descrizione/scheda tecnica. Questa è la posizione più comune e consigliata.
        -   *Opzione: `displayFooterProduct` (solo PrestaShop 1.6):* Le schede appariranno nella sezione del piè di pagina della pagina del prodotto. Questo potrebbe essere adatto per informazioni supplementari meno critiche.
        -   *Opzione: `displayRightColumnProduct` (solo PrestaShop 1.6):* Le schede appariranno nella colonna destra della pagina del prodotto. Questo è meno comune per le schede e potrebbe dipendere molto dal layout del tuo tema.
        -   *Opzione: `displayLeftColumnProduct` (solo PrestaShop 1.6):* Le schede appariranno nella colonna sinistra della pagina del prodotto. Simile alla colonna destra, questo è meno comune per le schede.
    -   **Valore consigliato:** `displayProductExtraContent`
    -   **Scenario / esempio per il commerciante:** Per la maggior parte dei negozi, `displayProductExtraContent` offre la migliore esperienza utente in quanto mantiene tutte le informazioni relative al prodotto raggruppate. Se il tuo tema ha un layout molto specifico o vuoi dare meno enfasi alle schede, potresti sperimentare con le posizioni del piè di pagina o delle colonne (anche se queste sono meno comuni per le schede).

#### 2.1.1 Gestione delle schede globali (se "Visualizza schede globalmente" è abilitato)

Se hai abilitato "Visualizza schede globalmente", questa sezione apparirà nella pagina di configurazione del modulo. Qui puoi aggiungere, modificare o eliminare schede che verranno mostrate su *tutte* le pagine prodotto.

-   **Pulsante Aggiungi nuova scheda:** Clicca qui per aprire un modulo dove puoi definire una nuova scheda globale.
    -   **Titolo scheda:** Il testo che appare sulla scheda stessa (es. "Info spedizione", "Garanzia"). Questo è solitamente multilingua.
    -   **Contenuto scheda:** Il contenuto effettivo che appare quando si clicca sulla scheda. Usa l'editor TinyMCE se abilitato. Questo è anche multilingua.
    -   **Attivo:** Un interruttore per abilitare o disabilitare la scheda senza eliminarla.
    -   **Posizione:** Un numero per controllare l'ordine della scheda rispetto ad altre schede globali. I numeri più bassi appaiono per primi.
-   **Elenco schede esistenti:** Una tabella che mostra tutte le tue schede globali attualmente configurate.
    -   **Icona Modifica:** Clicca per modificare il titolo, il contenuto o le impostazioni di una scheda esistente.
    -   **Icona Elimina:** Clicca per rimuovere permanentemente una scheda globale.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modo principale per gestire le schede extra specifiche del prodotto è direttamente dalla **pagina di modifica del prodotto** nel Back Office di PrestaShop.

-   **Nome schermata e posizione nel menu:**

    1.  Naviga su **Catalogo > Prodotti**.
    2.  Modifica un prodotto esistente o creane uno nuovo.
    3.  All'interno dell'interfaccia di modifica del prodotto, cerca una nuova scheda o sezione etichettata **"Extra Tabs Pro"** (o simile, a seconda della tua versione di PrestaShop e del tema).
-   **Azioni e impostazioni disponibili all'interno della sezione "Extra Tabs Pro" su una pagina prodotto:**

    -   **Pulsante Aggiungi nuova scheda:** Clicca qui per creare una nuova scheda *specificamente per questo prodotto*.
        -   **Titolo scheda:** Inserisci il titolo per questa scheda specifica del prodotto (es. "Specifiche tecniche per il Modello X"). Questo è multilingua.
        -   **Contenuto scheda:** Inserisci il contenuto per questa scheda. L'editor TinyMCE sarà disponibile se abilitato nella configurazione principale del modulo. Questo è multilingua.
        -   **Attivo:** Abilita/disabilita questa specifica scheda per questo prodotto.
        -   **Posizione:** Imposta l'ordine di visualizzazione per questa scheda rispetto ad altre schede su questa pagina prodotto.
    -   **Elenco schede esistenti:** Una tabella che mostra tutte le schede extra che hai creato per *questo particolare prodotto*.
        -   **Icona Modifica:** Modifica il titolo, il contenuto o lo stato di una scheda specifica del prodotto esistente.
        -   **Icona Elimina:** Rimuovi una scheda da questo prodotto.
-   **Effetto delle modifiche:**

    -   Quando aggiungi, modifichi o elimini una scheda dalla sezione "Extra Tabs Pro" di un prodotto, tali modifiche *influenzano solo quella specifica pagina prodotto*.
    -   Il contenuto e la visibilità di queste schede vengono immediatamente aggiornati sulla pagina prodotto del front office dopo aver salvato le modifiche.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Identifica le informazioni universali:** Se hai informazioni che si applicano a TUTTI i prodotti (es. spedizione generale, resi, storia del marchio), usa la funzione **schede globali** nella configurazione principale del modulo.
    2.  **Identifica le informazioni specifiche del prodotto:** Per i dettagli unici di un prodotto (es. dimensioni specifiche, composizione del materiale, istruzioni per l'uso, recensioni video), vai alla **pagina di modifica del singolo prodotto** e usa la sezione "Extra Tabs Pro" lì.
    3.  **Usa l'editor TinyMCE:** Abilita sempre l'editor TinyMCE nella configurazione principale del modulo per una più facile creazione e formattazione dei contenuti.
    4.  **Revisiona regolarmente:** Controlla periodicamente le tue pagine prodotto per assicurarti che le schede vengano visualizzate correttamente e che il contenuto sia aggiornato.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Editor TinyMCE | SÌ | Fornisce un editor di testo ricco per il contenuto delle schede; formattazione più semplice. |
| | Visualizza Schede Globalmente | NO (o SÌ se necessario) | SÌ: Le schede globali appaiono su tutti i prodotti. NO: Le schede sono specifiche del prodotto. |
| | Posizione Visualizzazione Schede | `displayProductExtraContent` | Controlla dove appaiono le schede sulla pagina del prodotto. |
| | **Elenco Schede Globali** | (N/A) | Aggiungi/Modifica/Elimina schede che appaiono su TUTTE le pagine prodotto. |
| **Pagina Modifica Prodotto** | **Sezione Extra Tabs Pro** | (N/A) | Aggiungi/Modifica/Elimina schede specifiche per il prodotto corrente. |
| | Titolo Scheda | (Definito dall'utente) | Il nome visibile della scheda sulla pagina del prodotto. |
| | Contenuto Scheda | (Definito dall'utente) | Le informazioni visualizzate quando si clicca sulla scheda. |
| | Attivo | SÌ | Controlla se la scheda è visibile o nascosta. |
| | Posizione | (Definito dall'utente) | Determina l'ordine delle schede sulla pagina del prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

-   **D: Le mie nuove schede non vengono visualizzate sulla pagina del prodotto.**
    -   **R:** Innanzitutto, assicurati che la scheda sia contrassegnata come "Attiva" sia nella configurazione globale del modulo (se è una scheda globale) sia nella pagina del singolo prodotto (se è specifica del prodotto). In secondo luogo, svuota la cache di PrestaShop: vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Inoltre, svuota la cache del tuo browser.
-   **D: L'editor TinyMCE non appare quando cerco di aggiungere contenuto alla scheda.**
    -   **R:** Vai alla pagina di configurazione principale del modulo (**Moduli > Gestione moduli > Product Extra Tabs Pro > Configura**) e assicurati che l'impostazione "Abilita Editor TinyMCE per il Contenuto delle Schede" sia impostata su **SÌ**. Salva le modifiche e svuota la cache.
-   **D: Le mie schede sembrano strane o non corrispondono allo stile del mio tema.**
    -   **R:** Il modulo cerca di integrarsi senza problemi, ma i temi personalizzati a volte possono sovrascrivere lo stile predefinito. Se l'aspetto è sbagliato, di solito richiede piccole modifiche CSS nel tuo tema. Contatta il tuo webmaster o il supporto MyPresta.eu con screenshot per assistenza.
-   **D: Posso avere schede diverse per lingue diverse?**
    -   **R:** Sì! I campi "Titolo scheda" e "Contenuto scheda" sono multilingua. Quando modifichi una scheda, vedrai le bandiere delle lingue accanto a questi campi. Clicca sulla bandiera per passare a una lingua diversa e inserire il contenuto tradotto.
-   **D: Voglio visualizzare una scheda solo per alcuni prodotti, non per tutti.**
    -   **R:** Assicurati che l'impostazione "Visualizza schede globalmente" nella configurazione principale del modulo sia impostata su **NO**. Quindi, naviga su ogni prodotto specifico a cui vuoi aggiungere una scheda (**Catalogo > Prodotti > Modifica Prodotto > sezione Extra Tabs Pro**) e crea le schede lì.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Product Extra Tabs Pro` è progettato come un modulo PrestaShop standard, estendendo principalmente la classe `Module`. Sfrutta il sistema di hook di PrestaShop per iniettare il suo contenuto nelle pagine dei prodotti e utilizza una tabella di database personalizzata per archiviare i dati delle schede. La configurazione è gestita tramite `getContent()` nel file principale del modulo, e la gestione delle schede specifiche del prodotto è integrata direttamente nella pagina di amministrazione del prodotto tramite una scheda personalizzata. Utilizza AJAX per il caricamento e il salvataggio dinamico dei contenuti.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nella directory `controllers/`. Tutto il rendering del front-office è gestito tramite hook e file di template, e la configurazione del back-office è gestita all'interno del metodo `getContent()` del file principale del modulo e delle chiamate AJAX.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi personalizzate nella directory `classes/`. La sua logica principale di gestione dei dati è incorporata nel file principale del modulo `extratabspro/ajax_extratabspro.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `extratabspro/js/tinymce16.inc.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Questo file contiene probabilmente l'inizializzazione e la configurazione per l'editor di testo ricco TinyMCE, specificamente adattato per gli ambienti PrestaShop 1.6. Assicura che l'editor sia caricato e configurato correttamente per i campi di input del contenuto delle schede.
-   `extratabspro/lib/searchTool/views/js/autocomplete.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Questo script fa parte di una libreria di strumenti di ricerca, probabilmente utilizzata per la funzionalità di autocompletamento in un campo di input di ricerca all'interno dell'interfaccia di amministrazione del modulo (ad esempio, ricerca di prodotti a cui assegnare schede, anche se questa specifica funzionalità non è esplicitamente menzionata nella guida del commerciante, è un modello comune per una tale libreria). Lega i listener di eventi ai campi di input e gestisce le richieste AJAX per i suggerimenti di ricerca.
-   `extratabspro/views/admin/extratabspro.js`:
    -   **Ambito:** Back-office (PrestaShop 1.7.x, 8.x, 9.x).
    -   **Scopo:** Questo è il file JavaScript principale per l'interfaccia di amministrazione del modulo. Gestisce:
        -   Chiamate AJAX per aggiungere, modificare, eliminare schede globali.
        -   Chiamate AJAX per aggiungere, modificare, eliminare schede specifiche del prodotto nella pagina di modifica del prodotto.
        -   Aggiornamenti dinamici delle tabelle dell'elenco delle schede.
        -   Listener di eventi per l'invio di moduli, i clic sui pulsanti (aggiungi/modifica/elimina) e potenzialmente il riordino delle schede tramite drag-and-drop.
        -   Integrazione con TinyMCE per i campi di contenuto.
-   `extratabspro/views/admin/extratabspro8.js`:
    -   **Ambito:** Back-office (PrestaShop 8.x, 9.x).
    -   **Scopo:** Simile a `extratabspro.js`, ma probabilmente contiene adattamenti o correzioni specifici per gli ambienti PrestaShop 8.x e 9.x, affrontando i cambiamenti nella struttura DOM del Back Office o nelle API JavaScript. Esegue le stesse funzioni principali di `extratabspro.js` ma garantisce la compatibilità con le versioni più recenti di PrestaShop.
-   `extratabspro/views/js/extratabspro.js`:
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script gestisce la visualizzazione e l'interazione front-end delle schede extra sulla pagina del prodotto. Probabilmente:
        -   Inizializza il meccanismo di cambio scheda (ad esempio, schede jQuery UI, schede Bootstrap o logica personalizzata).
        -   Lega gli eventi di clic alle intestazioni delle schede per mostrare/nascondere il contenuto corrispondente.
        -   Garantisce transizioni fluide o caricamento del contenuto.
        -   Potrebbe gestire il comportamento reattivo per le schede su diverse dimensioni dello schermo.
-   `extratabspro/views/js/tinymce16.inc.js`: (Duplicato, probabilmente per contesti diversi o una svista nell'imballaggio)
    -   **Ambito:** Back-office.
    -   **Scopo:** Come quello in `extratabspro/js/`, probabilmente per l'inizializzazione di TinyMCE.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `extratabspro/lib/searchTool/views/css/autocomplete.css`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Fornisce lo stile per il menu a discesa dei suggerimenti di autocompletamento e gli elementi UI correlati della libreria dello strumento di ricerca.
-   `extratabspro/views/admin/extratabspro.css`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Stila i moduli di configurazione del modulo, le tabelle di elenco delle schede e qualsiasi elemento UI personalizzato all'interno del Back Office di PrestaShop, garantendo un aspetto e una sensazione coerenti.
-   `extratabspro/views/css/extratabspro.css`:
    -   **Ambito:** Front-office.
    -   **Scopo:** Fornisce lo stile principale per le schede extra sulla pagina del prodotto. Ciò include l'aspetto delle intestazioni delle schede, gli stati delle schede attive e le aree del contenuto. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` o `theme.css` del loro tema mirando a classi come `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   `extratabspro/views/front/footer.tpl`: Questo template è probabilmente destinato agli hook `displayFooter` o `displayFooterProduct` (anche se il modulo utilizza principalmente `displayProductExtraContent`). Outputterebbe il contenuto nell'area del piè di pagina.
    -   `extratabspro/views/front/tab.tpl`: Questo template renderizza una singola intestazione di scheda (la parte cliccabile). Viene utilizzato all'interno di un ciclo per generare tutte le intestazioni delle schede.
    -   `extratabspro/views/front/tab16.tpl`: Una versione di `tab.tpl` specificamente per PrestaShop 1.6, che si adatta alla sua diversa struttura HTML o classi CSS.
    -   `extratabspro/views/front/tabcontents.tpl`: Questo template renderizza l'area del contenuto per tutte le schede extra. Tipicamente contiene un ciclo che itera attraverso il contenuto di ogni scheda, avvolgendolo in un contenitore che può essere mostrato/nascosto da JavaScript.
    -   `extratabspro/views/front/tabcontents16.tpl`: Una versione di `tabcontents.tpl` specificamente per PrestaShop 1.6.
-   **Template di amministrazione (`views/templates/admin/`)**:

    -   `extratabspro/lib/searchTool/views/scripts.tpl`: Questo template include probabilmente risorse JavaScript e CSS per la libreria dello strumento di ricerca nel contesto di amministrazione.
    -   `extratabspro/views/admin/tabs-list.tpl`: Questo template renderizza la tabella che elenca tutte le schede configurate (sia schede globali nella pagina di configurazione del modulo che schede specifiche del prodotto nella pagina di modifica del prodotto). Include controlli per la modifica e l'eliminazione delle schede.
    -   `extratabspro/views/admin/tabs17.tpl`: Questo template è il modulo di configurazione principale o la visualizzazione per il modulo nel Back Office di PrestaShop 1.7.x / 8.x / 9.x. Probabilmente contiene i campi del modulo per le impostazioni globali e l'inclusione di `tabs-list.tpl` per la gestione delle schede.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_extratabspro_tab`: Memorizza le informazioni principali per ogni scheda extra (ID, ID prodotto, posizione, stato attivo).
    -   `ps_extratabspro_tab_lang`: Memorizza il contenuto multilingua per ogni scheda (titolo, contenuto), collegato a `ps_extratabspro_tab` tramite `id_extratabspro_tab` e `id_lang`.
    -   `ps_configuration`: Memorizza le impostazioni globali del modulo (es. `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta i file CSS e JS del modulo per la visualizzazione nel front-office. |
| `displayBackOfficeHeader` | Nella sezione `<head>` delle pagine del Back Office. | Inietta i file CSS e JS del modulo per la configurazione del Back Office e l'integrazione della pagina del prodotto. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Inietta la sezione "Extra Tabs Pro" nell'interfaccia di amministrazione del prodotto, consentendo la gestione delle schede per prodotto. |
| `displayProductExtraContent` | Nell'area del contenuto principale della pagina del prodotto, tipicamente sotto la descrizione del prodotto. | Renderizza le schede extra e il loro contenuto effettivi nella pagina del prodotto del front-office. Questo è l'hook principale per la visualizzazione front-end. |
| `displayFooterProduct` | Nella sezione del piè di pagina della pagina del prodotto. | Hook alternativo per la visualizzazione delle schede, se configurato dal commerciante. |
| `displayRightColumnProduct` | Nella colonna destra della pagina del prodotto. | Hook alternativo per la visualizzazione delle schede, se configurato dal commerciante. |
| `displayLeftColumnProduct` | Nella colonna sinistra della pagina del prodotto. | Hook alternativo per la visualizzazione delle schede, se configurato dal commerciante. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Potenzialmente utilizzato per svuotare la cache o eseguire altre azioni relative alle modifiche dei dati del prodotto. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Pulisce le schede specifiche del prodotto dal database. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente utilizzato per la configurazione iniziale o la creazione di schede predefinite per i nuovi prodotti. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un oggetto prodotto. | Simile a `actionProductUpdate`, per gli aggiornamenti del modello oggetto. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore domanda riguardante il modulo "Product Extra Tabs Pro", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto e gli sviluppatori sono disponibili per assistervi.
