---
title: "Product Tag Icons Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Product Tag Icons Pro di MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product Tag Icons Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste e sono presenti sulla maggior parte degli ambienti di hosting moderni. Non è necessaria alcuna configurazione speciale del server.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

Il modulo "Product Tag Icons Pro" fornisce un set completo di opzioni di configurazione distribuite su diverse schermate dedicate nel tuo back office di PrestaShop.

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Gestione moduli > Configura Product Tag Icons Pro)

Questa è la schermata di configurazione principale per le impostazioni generali del modulo.

-   **Cosa fa questa impostazione:** Controlla il comportamento generale e le opzioni di visualizzazione predefinite per le icone dei tuoi prodotti.
-   **Effetto della modifica di questa impostazione:** Queste impostazioni influenzano il modo in cui le icone vengono visualizzate in tutto il tuo negozio, o come il modulo interagisce con altre parti di PrestaShop.
-   **Valore consigliato:** Varia in base al design del tuo negozio e alla funzionalità desiderata.

**Tabella di Riferimento Rapido della Configurazione (Configurazione Principale del Modulo)**

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Abilita Modulo** | SÌ | **Scopo:** Attiva o disattiva la funzionalità del modulo. **Impatto:** Se disabilitato, nessuna icona apparirà nel tuo front office e le funzionalità del modulo saranno inattive. Mantienilo abilitato per utilizzare il modulo. |
| **Dimensione Icona (px)** | 32 | **Scopo:** Imposta la dimensione predefinita (larghezza e altezza) per tutte le icone visualizzate nel front office. **Impatto:** Tutte le icone verranno renderizzate con questa dimensione in pixel specificata. Scegli una dimensione che si adatti bene alle immagini dei tuoi prodotti e al design generale senza essere troppo piccola per essere vista o troppo grande per essere invadente. |
| **Posizione Icona (Hook)** | `displayProductAdditionalInfo` (o hook simile per la pagina prodotto) | **Scopo:** Determina dove sulla pagina prodotto le icone verranno visualizzate per impostazione predefinita. Puoi scegliere da un elenco di hook PrestaShop disponibili. **Impatto:** Le icone appariranno nella sezione selezionata della pagina prodotto. Sperimenta con diversi hook per trovare il miglior posizionamento visivo per il tuo tema. Le scelte comuni includono `displayProductAdditionalInfo`, `displayProductPriceBlock` o `displayAfterProductThumbs`. |
| **Mostra Icone nell'Elenco Prodotti** | SÌ | **Scopo:** Controlla se le icone sono visibili nelle pagine di elenco prodotti (categorie, risultati di ricerca, prodotti in evidenza della homepage). **Impatto:** Se abilitato, le icone assegnate ai prodotti appariranno sulle rispettive schede/miniature dei prodotti negli elenchi. Se disabilitato, le icone verranno mostrate solo nelle singole pagine prodotto. Consigliato abilitare per il massimo impatto. |
| **Tipo di Tooltip** | Light | **Scopo:** Seleziona il tema visivo per il tooltip che appare quando un cliente passa il mouse su un'icona. Le opzioni di solito includono Light, Noir, Punk, Shadow. **Impatto:** Cambia l'aspetto della casella del tooltip (sfondo, colore del testo, bordo) che visualizza la descrizione dell'icona. Scegli quello che si abbina all'estetica del tuo negozio. |
| **Posizione Tooltip** | Top | **Scopo:** Determina dove appare il tooltip rispetto all'icona quando ci si passa sopra con il mouse (es. Top, Bottom, Left, Right). **Impatto:** Influisce sull'esperienza utente quando si interagisce con le icone. Scegli una posizione che non oscuri altre informazioni importanti sulla pagina. |
| **Abilita Animazioni Tooltip** | SÌ | **Scopo:** Aggiunge animazioni sottili (dissolvenza, scorrimento) quando i tooltip appaiono e scompaiono. **Impatto:** Rende l'interazione con il tooltip più moderna e coinvolgente. Se preferisci un aspetto statico e istantaneo, disabilita questa opzione. |
| **CSS Personalizzato** | (Vuoto) | **Scopo:** Ti consente di aggiungere regole CSS personalizzate per stilizzare ulteriormente le tue icone o i tooltip senza modificare i file del modulo. **Impatto:** Qualsiasi regola CSS inserita qui verrà applicata agli elementi del modulo, sovrascrivendo gli stili predefiniti. Usalo per perfezionare colori, margini o comportamenti specifici delle icone. |

### 2.2 Schermata Amministrativa Dedicata: Gestisci Tutte le Icone (Back Office > Product Tag Icons Pro > Gestisci Tutte le Icone)

Questa schermata ti consente di creare, modificare ed eliminare le definizioni delle icone che in seguito assocerai ai tuoi prodotti.

-   **Nome Schermata e Posizione Menu:** La troverai sotto **Product Tag Icons Pro > Gestisci Tutte le Icone** nel menu del tuo back office di PrestaShop.
-   **Azioni e Impostazioni Disponibili:**
    -   **Aggiungi Nuova Icona:** Clicca sul pulsante "Aggiungi nuova icona" per creare una nuova icona.
        -   **Nome Icona:** Un nome descrittivo per la tua icona (es. "Spedizione Gratuita", "Nuovo Arrivo"). Questo è per il tuo riferimento interno.
        -   **Immagine Icona:** Carica il file immagine per la tua icona. Dovrebbe essere un'immagine piccola e chiara (es. PNG, JPG, SVG).
        -   **Descrizione Icona:** Un breve testo che apparirà come tooltip quando i clienti passano il mouse sull'icona nel front office. Spiega cosa significa l'icona.
        -   **Attiva:** Attiva o disattiva se questa icona è attualmente disponibile per l'uso e la visualizzazione.
        -   **Campi specifici per la lingua:** Se il tuo negozio è multilingue, puoi fornire nomi e descrizioni diversi per ogni lingua.
    -   **Modifica Icona:** Clicca sul pulsante "Modifica" accanto a un'icona esistente nell'elenco per modificarne i dettagli.
    -   **Elimina Icona:** Clicca sul pulsante "Elimina" per rimuovere un'icona. Fai attenzione, poiché questo rimuoverà anche le sue associazioni con qualsiasi prodotto.
    -   **Griglia / Vista di Gestione:** Una tabella che elenca tutte le icone create, mostrando il loro nome, immagine, descrizione e stato attivo. Puoi ordinare e filtrare questo elenco.
-   **Effetto delle modifiche:**
    -   **Aggiunta di un'icona:** Rende una nuova icona disponibile per l'associazione con i prodotti.
    -   **Modifica di un'icona:** Aggiorna l'immagine, il nome o la descrizione per tutte le istanze di quell'icona in tutto il tuo negozio.
    -   **Eliminazione di un'icona:** Rimuove completamente l'icona e non apparirà più su nessun prodotto a cui era stata precedentemente assegnata.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Pianifica le tue icone: Decidi le caratteristiche chiave o le promozioni che vuoi evidenziare.
    2.  Crea immagini di icone piccole e di alta qualità (es. 32x32px o 64x64px) che si abbinino al tuo brand.
    3.  Vai a "Gestisci Tutte le Icone" e aggiungi ogni icona, fornendo un nome chiaro e una descrizione tooltip utile.
    4.  Assicurati che tutte le icone siano "Attive" se intendi usarle.

### 2.3 Schermata Amministrativa Dedicata: Gestisci Associazioni Icone (Back Office > Product Tag Icons Pro > Gestisci Associazioni Icone)

Questa schermata è dove colleghi le tue icone create a prodotti specifici nel tuo catalogo.

-   **Nome Schermata e Posizione Menu:** La troverai sotto **Product Tag Icons Pro > Gestisci Associazioni Icone** nel menu del tuo back office di PrestaShop.
-   **Azioni e Impostazioni Disponibili:**
    -   **Ricerca Prodotto:** Usa la barra di ricerca per trovare prodotti per nome, ID o riferimento.
    -   **Elenco Prodotti:** Una volta cercati i prodotti, appariranno in un elenco.
    -   **Assegna Icone:** Per ogni prodotto, vedrai una sezione in cui puoi selezionare quali delle tue icone create devono essere visualizzate per quel prodotto specifico. Questo è di solito un menu a discesa a selezione multipla o un elenco di caselle di controllo.
    -   **Salva Modifiche:** Dopo aver assegnato o disassegnato icone per un prodotto, ricorda di salvare le modifiche.
    -   **Griglia / Vista di Gestione:** Una tabella che mostra i prodotti e le loro icone attualmente associate.
-   **Effetto delle modifiche:**
    -   **Assegnazione di un'icona a un prodotto:** L'icona selezionata apparirà ora nel front office per quel prodotto specifico (sulla sua pagina prodotto e negli elenchi prodotti, a seconda delle impostazioni principali del modulo).
    -   **Disassegnazione di un'icona da un prodotto:** L'icona non verrà più visualizzata per quel prodotto.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Dopo aver creato le tue icone (in "Gestisci Tutte le Icone"), vai a questa schermata.
    2.  Cerca il prodotto che vuoi taggare.
    3.  Seleziona le icone pertinenti dall'elenco per quel prodotto.
    4.  Ripeti per tutti i prodotti che desideri taggare.
    5.  Rivedi periodicamente i tuoi tag di prodotto, specialmente quando lanci nuovi prodotti o promozioni.

### 2.4 Tabella di Riferimento Rapido della Configurazione (Tutte le Schermate)

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Configurazione Modulo** | Abilita Modulo | SÌ | Attiva/disattiva il modulo. |
| | Dimensione Icona (px) | 32 | Imposta la dimensione predefinita di visualizzazione delle icone. |
| | Posizione Icona (Hook) | `displayProductAdditionalInfo` | Posizionamento predefinito sulla pagina prodotto. |
| | Mostra Icone nell'Elenco Prodotti | SÌ | Visualizza le icone sulle pagine di categoria/ricerca. |
| | Tipo di Tooltip | Light | Tema visivo per le descrizioni delle icone. |
| | Posizione Tooltip | Top | Dove appare il tooltip rispetto all'icona. |
| | Abilita Animazioni Tooltip | SÌ | Animazioni fluide per i tooltip. |
| | CSS Personalizzato | (Vuoto) | Aggiungi stili personalizzati per icone/tooltip. |
| **Gestisci Tutte le Icone** | Aggiungi Nuova Icona | N/A | Crea una nuova definizione di icona. |
| | Nome Icona | (Descrittivo) | Nome interno per l'icona. |
| | Immagine Icona | (Carica file) | Rappresentazione visiva dell'icona. |
| | Descrizione Icona | (Testo tooltip) | Testo mostrato al passaggio del mouse. |
| | Attiva | SÌ | Abilita/disabilita l'icona per l'uso. |
| | Modifica Icona | N/A | Modifica i dettagli di un'icona esistente. |
| | Elimina Icona | N/A | Rimuove una definizione di icona. |
| **Gestisci Associazioni Icone** | Ricerca Prodotto | N/A | Trova prodotti da taggare. |
| | Assegna Icone | N/A | Collega le icone create a prodotti specifici. |
| | Salva Modifiche | N/A | Applica le assegnazioni di icone ai prodotti. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Le mie icone non vengono visualizzate nel front office, cosa devo fare?**
R:

1.  **Controlla lo Stato del Modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Product Tag Icons Pro" sia abilitato.
2.  **Controlla lo Stato delle Icone:** Vai su **Product Tag Icons Pro > Gestisci Tutte le Icone** e verifica che le icone specifiche che stai cercando di visualizzare siano contrassegnate come "Attive".
3.  **Controlla le Associazioni dei Prodotti:** Vai su **Product Tag Icons Pro > Gestisci Associazioni Icone** e conferma che le icone siano correttamente assegnate ai prodotti su cui ti aspetti che appaiano.
4.  **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache Smarty" e "Svuota cache" (se disponibile). A volte, i vecchi dati memorizzati nella cache impediscono la visualizzazione delle nuove modifiche del modulo.
5.  **Controlla la Posizione dell'Hook:** Nella configurazione principale del modulo, assicurati di aver selezionato un hook valido e appropriato per la visualizzazione delle icone (es. `displayProductAdditionalInfo`). Alcuni temi potrebbero avere hook personalizzati o potrebbero non renderizzare determinati hook standard.

**D2: Le icone sembrano troppo grandi/piccole o non si adattano al design del mio tema.**
R:

1.  **Regola la Dimensione dell'Icona:** Nella configurazione principale del modulo, cambia l'impostazione "Dimensione Icona (px)" alle dimensioni desiderate.
2.  **CSS Personalizzato:** Se la semplice regolazione della dimensione non è sufficiente, usa il campo "CSS Personalizzato" nella configurazione principale del modulo per perfezionare lo stile. Puoi mirare a classi di icone specifiche (es. `.ticon-image`) per regolare margini, padding o persino applicare filtri.
3.  **Compatibilità del Tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche CSS. Se hai familiarità con il CSS, ispeziona gli elementi utilizzando gli strumenti per sviluppatori del tuo browser per identificare i selettori pertinenti.

**D3: I tooltip non appaiono o sembrano strani.**
R:

1.  **Abilita i Tooltip:** Assicurati che la funzione tooltip sia abilitata nella configurazione principale del modulo.
2.  **Controlla il Contenuto del Tooltip:** Verifica di aver inserito una "Descrizione" per ogni icona in **Product Tag Icons Pro > Gestisci Tutte le Icone**. Questa descrizione è ciò che appare nel tooltip.
3.  **Tema/Posizione del Tooltip:** Sperimenta con diverse impostazioni di "Tipo di Tooltip" e "Posizione Tooltip" nella configurazione principale del modulo per vedere se un'opzione diversa risolve il problema o si adatta meglio al tuo tema.
4.  **Conflitti JavaScript:** In rari casi, il JavaScript di un altro modulo potrebbe entrare in conflitto. Controlla la console per sviluppatori del tuo browser per eventuali errori JavaScript. Se trovi errori, prova a disabilitare temporaneamente altri moduli uno per uno per isolare il conflitto.

**D4: Posso tradurre i nomi e le descrizioni delle icone per diverse lingue?**
R: Sì! Quando crei o modifichi un'icona in **Product Tag Icons Pro > Gestisci Tutte le Icone**, vedrai le schede linguistiche (es. "Italiano", "Inglese", "Francese") accanto ai campi "Nome Icona" e "Descrizione Icona". Basta passare alla scheda della lingua desiderata e inserire la traduzione per quella lingua specifica. Il modulo visualizzerà automaticamente la traduzione corretta in base alla lingua selezionata dal cliente.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Product Tag Icons Pro", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo "Product Tag Icons Pro" (`ticons`) segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente il pattern MVC. Estende `Module` per la sua funzionalità principale e utilizza istanze dedicate di `AdminController` per la gestione delle icone e delle loro associazioni. I dati sono archiviati in tabelle di database personalizzate e la visualizzazione nel front-office è ottenuta tramite vari hook di PrestaShop e template Smarty. Il modulo integra anche librerie di terze parti per una UI migliorata (ad esempio, Tooltipster per i tooltip, un autocomplete personalizzato per la ricerca dei prodotti).

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questo modulo non definisce esplicitamente controller front-office personalizzati. Tutto il rendering front-office è gestito tramite metodi `hook` all'interno della classe principale del modulo (`ajax_ticons.php`) e i template Smarty associati.

#### Controller Admin Back-Office

-   **`ticons/controllers/admin/AdminTiconsAllController.php`**

    -   **Nome Classe:** `AdminTiconsAllController` (estende `ModuleAdminController`)
    -   **Nome Tab:** "Gestisci Tutte le Icone"
    -   **Responsabilità:** Gestisce la creazione, la modifica e l'eliminazione delle singole definizioni di icone. Gestisce le operazioni CRUD per l'entità `ticon`. Questo controller utilizza `HelperList` per visualizzare l'elenco delle icone e `HelperForm` per il modulo di aggiunta/modifica. Gestisce il caricamento delle immagini delle icone.
-   **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**

    -   **Nome Classe:** `AdminTiconsAssociationsController` (estende `ModuleAdminController`)
    -   **Nome Tab:** "Gestisci Associazioni Icone"
    -   **Responsabilità:** Gestisce l'associazione delle icone create con prodotti specifici. Fornisce un'interfaccia per cercare prodotti e quindi assegnare/disassegnare più icone ad essi. Questo controller utilizza anche `HelperList` per la visualizzazione dei prodotti e un modulo personalizzato per la selezione delle icone. Gestisce le richieste AJAX per l'autocomplete della ricerca dei prodotti.
-   **`ticons/controllers/admin/index.php`**

    -   **Responsabilità:** Questo è un file `index.php` vuoto standard, tipicamente presente nelle directory di PrestaShop per prevenire l'elenco delle directory. Non contiene alcuna logica di controller funzionale.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce esplicitamente file PHP separati in una directory `classes/`. Invece, il file principale del modulo `ajax_ticons.php` probabilmente contiene le definizioni di `ObjectModel` per `Ticon` e `TiconProduct` (o entità simili) direttamente al suo interno, oppure sono gestite implicitamente tramite interazioni con il database.

-   **`Ticon` (ObjectModel Implicito):**

    -   **Tabella Database:** `ps_ticons` (o simile, basato sul metodo `install()` del modulo).
    -   **Campi:** Probabilmente include `id_ticon`, `name` (multilingua), `description` (multilingua), `image`, `active`.
    -   **Scopo:** Rappresenta una singola definizione di icona, inclusa la sua immagine, il nome e la descrizione del tooltip.
-   **`TiconProduct` (ObjectModel Implicito):**

    -   **Tabella Database:** `ps_ticon_products` (o simile, basato sul metodo `install()` del modulo).
    -   **Campi:** Probabilmente include `id_ticon_product`, `id_ticon`, `id_product`.
    -   **Scopo:** Rappresenta la relazione molti-a-molti tra icone e prodotti.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`ticons/lib/searchTool/views/js/autocomplete.js`**

    -   **Ambito:** Back-office (AdminTiconsAssociationsController).
    -   **Funzionalità:** Fornisce una funzionalità di ricerca con autocomplete per i prodotti all'interno della schermata "Gestisci Associazioni Icone". Probabilmente invia richieste AJAX al controller admin per recuperare suggerimenti di prodotti mentre l'utente digita.
-   **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Questa è la libreria principale per il plugin Tooltipster. Gestisce la creazione, il posizionamento e lo stile dei tooltip interattivi che appaiono quando gli utenti passano il mouse sulle icone dei prodotti. Collega gli eventi hover agli elementi con classi specifiche (es. `.tooltipster`).
-   **`ticons/views/js/ticons-front.js`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Contiene JavaScript personalizzato specifico per la visualizzazione delle icone nel front-office. Questo script probabilmente inizializza il plugin Tooltipster sugli elementi icona pertinenti, passando le opzioni di configurazione (tema, posizione, animazione) in base alle impostazioni del back-office del modulo. Assicura che le icone siano renderizzate correttamente e siano interattive.
-   **`ticons/views/js/ticons.js`**

    -   **Ambito:** Back-office.
    -   **Funzionalità:** Contiene JavaScript generale per le schermate di configurazione e gestione del back-office del modulo. Questo potrebbe includere la validazione dei moduli, la manipolazione dinamica degli elementi o altri miglioramenti dell'interfaccia utente per l'interfaccia di amministrazione.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   **`ticons/lib/searchTool/views/css/autocomplete.css`**

    -   **Ambito:** Back-office.
    -   **Funzionalità:** Stila il menu a discesa di autocomplete e il campo di input utilizzati nella schermata "Gestisci Associazioni Icone".
-   **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Definisce gli stili per il tema "Light" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Definisce gli stili per il tema "Noir" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Definisce gli stili per il tema "Punk" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Definisce gli stili per il tema "Shadow" del plugin Tooltipster.
-   **`ticons/lib/tooltipster/css/tooltipster.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Il CSS principale per il plugin Tooltipster, che fornisce stili di base per tutti i tooltip.
-   **`ticons/views/css/ticons-admin.css`**

    -   **Ambito:** Back-office.
    -   **Funzionalità:** Contiene CSS personalizzato specificamente per le interfacce del back-office del modulo (ad esempio, stile per elenchi di icone, moduli ed elementi personalizzati nei controller admin).
-   **`ticons/views/css/ticons-fontawesome.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Probabilmente include o importa le icone di Font Awesome, che potrebbero essere utilizzate come icone di fallback o per elementi UI specifici all'interno della visualizzazione del modulo.
-   **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** Questi fogli di stile probabilmente contengono regole specifiche per diverse dimensioni di icone. Quando il commerciante seleziona una "Dimensione Icona" nella configurazione, il modulo carica dinamicamente il file CSS corrispondente per garantire che le icone siano renderizzate con le dimensioni corrette e potenzialmente con spaziatura ottimizzata. Definiscono classi come `.ticon-24`, `.ticon-32`, ecc.
-   **`ticons/views/css/ticons.css`**

    -   **Ambito:** Front-office.
    -   **Funzionalità:** CSS generale del front-office per il modulo, inclusi stili di base per i contenitori delle icone, le immagini e il layout generale. Questo file potrebbe contenere regole comuni applicate indipendentemente dalla dimensione dell'icona selezionata.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/front/`)

Questi template vengono renderizzati quando il modulo è agganciato a varie posizioni del front-office. Tipicamente ricevono un array di dati delle icone dai metodi `hook` del modulo.

-   **`ticons/views/templates/front/deliveryTime.tpl`**

    -   **Hook:** Potenzialmente `displayProductDeliveryTime` o simile.
    -   **Output:** Renderizza icone relative alle informazioni di consegna.
-   **`ticons/views/templates/front/displayActions.tpl`**

    -   **Hook:** `displayProductActions` o simile.
    -   **Output:** Renderizza icone vicino ai pulsanti di azione del prodotto (es. "Aggiungi al carrello").
-   **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**

    -   **Hook:** `displayAfterProductThumbs` (PrestaShop 1.7+).
    -   **Output:** Renderizza icone direttamente sotto le immagini in miniatura del prodotto nella pagina del prodotto.
-   **`ticons/views/templates/front/displayColumns.tpl`**

    -   **Hook:** `displayLeftColumn`, `displayRightColumn`.
    -   **Output:** Renderizza icone all'interno dei moduli della colonna sinistra o destra.
-   **`ticons/views/templates/front/displayLeftColumn.tpl`**

    -   **Hook:** `displayLeftColumn`.
    -   **Output:** Renderizza icone specificamente nella colonna sinistra.
-   **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**

    -   **Hook:** `displayProductAdditionalInfo` (PrestaShop 1.7+).
    -   **Output:** Renderizza icone nella sezione "Informazioni Aggiuntive" della pagina del prodotto, un posizionamento comune e consigliato.
-   **`ticons/views/templates/front/displayProductPriceBlock.tpl`**

    -   **Hook:** `displayProductPriceBlock`.
    -   **Output:** Renderizza icone vicino al blocco del prezzo del prodotto.
-   **`ticons/views/templates/front/displayTop.tpl`**

    -   **Hook:** `displayTop` (intestazione).
    -   **Output:** Renderizza icone nella sezione dell'intestazione del negozio.
-   **`ticons/views/templates/front/listReviews.tpl`**

    -   **Hook:** Potenzialmente `displayProductListReviews` o simile.
    -   **Output:** Renderizza icone relative alle recensioni o valutazioni dei prodotti.
-   **`ticons/views/templates/front/productFooter.tpl`**

    -   **Hook:** `displayFooterProduct` o simile.
    -   **Output:** Renderizza icone nella sezione del piè di pagina della pagina del prodotto.
-   **`ticons/views/templates/front/showIcons.tpl`**

    -   **Hook:** Questo è probabilmente un template generico incluso da altri template hook per renderizzare la struttura HTML effettiva dell'icona (es. tag `<img>` con classi `tooltipster`). Itera sulla variabile `$icons` passata ad esso.

#### Template Admin (`views/templates/admin/`)

Questi template sono utilizzati per le schermate di configurazione e gestione del back-office del modulo.

-   **`ticons/lib/searchTool/views/scripts.tpl`**

    -   **Ambito:** Back-office.
    -   **Output:** Contiene JavaScript per lo strumento di ricerca, probabilmente inclusa l'inizializzazione dell'autocomplete di jQuery UI o simile.
-   **`ticons/views/templates/admin/customHook.tpl`**

    -   **Ambito:** Back-office.
    -   **Output:** Un template generico che potrebbe essere utilizzato per renderizzare il contenuto per hook personalizzati definiti all'interno dell'interfaccia admin del modulo, o per visualizzare messaggi specifici.
-   **`ticons/views/templates/admin/tabs.tpl`**

    -   **Ambito:** Back-office.
    -   **Output:** Renderizza le schede di navigazione (es. "Gestisci Tutte le Icone", "Gestisci Associazioni Icone") per le pagine di configurazione del modulo.
-   **`ticons/views/templates/admin/ticonsSelection.tpl`**

    -   **Ambito:** Back-office (AdminTiconsAssociationsController).
    -   **Output:** Renderizza l'interfaccia per selezionare e assegnare icone a un prodotto, tipicamente un menu a discesa a selezione multipla o un elenco di caselle di controllo all'interno del modulo di associazione del prodotto.
-   **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**

    -   **Ambito:** Back-office (AdminTiconsAllController).
    -   **Output:** Personalizza il contenuto della tabella `HelperList` per visualizzare l'elenco di tutte le icone create. Potrebbe includere colonne personalizzate per le immagini delle icone o lo stato attivo.
-   **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**

    -   **Ambito:** Back-office (AdminTiconsAssociationsController).
    -   **Output:** Personalizza il `HelperForm` per la schermata di associazione del prodotto. Questo template probabilmente include l'input di ricerca del prodotto e il `ticonsSelection.tpl` per l'assegnazione delle icone.
-   **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**

    -   **Ambito:** Back-office (AdminTiconsAssociationsController).
    -   **Output:** Personalizza il contenuto della tabella `HelperList` per visualizzare l'elenco dei prodotti e delle loro icone associate.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo crea tabelle personalizzate durante il suo metodo `install()` per archiviare le definizioni delle icone e le loro associazioni:

-   **`ps_ticons`**: Archivia le definizioni principali delle icone.
    -   `id_ticon` (PK, INT)
    -   `image` (VARCHAR): Nome del file dell'immagine dell'icona.
    -   `active` (TINYINT): 1 se attiva, 0 se inattiva.
-   **`ps_ticons_lang`**: Archivia i campi multilingua per le icone.
    -   `id_ticon` (PK, INT)
    -   `id_lang` (PK, INT)
    -   `name` (VARCHAR): Nome dell'icona per uso interno.
    -   `description` (TEXT): Testo del tooltip per l'icona.
-   **`ps_ticon_products`**: Archivia la relazione molti-a-molti tra icone e prodotti.
    -   `id_ticon_product` (PK, INT)
    -   `id_ticon` (FK, INT)
    -   `id_product` (FK, INT)

Le impostazioni di configurazione sono archiviate in `ps_configuration` con chiavi come `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST`, ecc.

#### Tabella degli Hook Registrati

Il modulo registra diversi hook per visualizzare le icone nel front office. Gli hook esatti utilizzati dipendono dalla versione di PrestaShop e dalla configurazione del commerciante.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inserisce risorse CSS e JS (Tooltipster, JS/CSS personalizzato). |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, all'interno del blocco "Informazioni Aggiuntive" (PS 1.7+). | Renderizza le icone associate al prodotto corrente. |
| `displayProductPriceBlock` | Nella pagina del prodotto, vicino al prezzo. | Renderizza le icone associate al prodotto corrente. |
| `displayAfterProductThumbs` | Nella pagina del prodotto, sotto le immagini del prodotto (PS 1.7+). | Renderizza le icone associate al prodotto corrente. |
| `displayProductListFunctionalButtons` | Negli elementi dell'elenco prodotti (es. pagine di categoria). | Renderizza le icone sulle schede/miniature dei prodotti. |
| `displayProductListReviews` | Negli elementi dell'elenco prodotti, vicino alle recensioni. | Renderizza le icone sulle schede/miniature dei prodotti. |
| `displayProductDeliveryTime` | Nella pagina del prodotto, vicino alle informazioni di consegna. | Renderizza le icone associate al prodotto corrente. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine. | Renderizza le icone se configurate per la visualizzazione generale. |
| `displayRightColumn` | Nella colonna destra delle pagine. | Renderizza le icone se configurate per la visualizzazione generale. |
| `displayFooterProduct` | Nella parte inferiore della pagina del prodotto. | Renderizza le icone associate al prodotto corrente. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel back office. | Potenzialmente svuota la cache o aggiorna le associazioni delle icone. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Pulisce le voci delle icone associate da `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | Dopo l'aggiunta di una nuova lingua. | Assicura che i campi specifici della lingua per le icone siano gestiti. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo al modulo "Product Tag Icons Pro".
