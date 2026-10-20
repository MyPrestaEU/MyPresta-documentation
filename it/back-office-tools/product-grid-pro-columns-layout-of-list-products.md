---
title: "Product Grid Pro - colonne e layout dei prodotti in elenco - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Product Grid Pro - colonne e layout dei prodotti in elenco di MyPresta.eu."
sidebar:
  label: "Product Grid Pro - colonne e layout dei prodotti in elenco"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product Grid Pro - columns & layout of list products su MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - colonne e layout dei prodotti in elenco

## 1. Requisiti e compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo funziona principalmente sovrascrivendo il controller predefinito dell'elenco prodotti di PrestaShop. La sua configurazione è gestita principalmente direttamente all'interno della sezione "Catalogo > Prodotti" stessa, con una semplice opzione di "reset" disponibile nella configurazione principale del modulo.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedervi, vai su **Moduli > Gestione moduli**, cerca "Product Grid Pro" e clicca su "Configura".

Questa schermata offre un'unica, cruciale opzione:

-   **Reimposta configurazione modulo**
    -   **Cosa fa questa impostazione:** Questo pulsante ti consente di ripristinare tutte le modifiche apportate dal modulo alle sue impostazioni predefinite. Ciò significa che qualsiasi ordine di colonna personalizzato, visibilità o colonne aggiunte che hai configurato nell'elenco "Catalogo > Prodotti" verrà ripristinato allo stato iniziale del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando cliccato:* Il modulo cancellerà le sue preferenze memorizzate per il layout della tua griglia prodotti. Questo è utile se hai apportato molte modifiche e vuoi ricominciare da capo, o se incontri un problema di visualizzazione inaspettato e vuoi escludere problemi di configurazione.
    -   **Valore consigliato:** Clicca su questo solo se desideri esplicitamente reimpostare la personalizzazione della tua griglia prodotti.
    -   **Scenario / esempio per il commerciante:** Hai sperimentato diversi layout di colonna per mesi, e ora il tuo elenco prodotti sembra disordinato o disorganizzato. Cliccando su "Reimposta configurazione modulo" lo riporterai a uno stato pulito e predefinito, permettendoti di riconfigurarlo da zero.

### 2.2 Schermate di amministrazione dedicate e viste del controller

La funzionalità principale di "Product Grid Pro" è sperimentata direttamente all'interno della sezione **Catalogo > Prodotti** del tuo Back Office PrestaShop. Questo modulo migliora l'elenco prodotti standard, aggiungendo nuove colonne e permettendoti di personalizzare il suo layout.

-   **Nome schermata e posizione menu:** **Catalogo > Prodotti**
-   **Azioni e impostazioni disponibili:**
    -   **Nuove colonne:** Il modulo introduce diverse nuove colonne, molto utili, al tuo elenco prodotti. Queste includono:
        -   **EAN13:** European Article Number (codice a barre).
        -   **Riferimento fornitore:** Il tuo riferimento interno per il prodotto dal tuo fornitore.
        -   **Produttore:** Il marchio o il produttore del prodotto.
        -   **Combinazioni:** Indica se il prodotto ha varianti (taglie, colori, ecc.).
        -   **Unità vendute:** Il numero totale di unità di questo prodotto vendute.
        -   **Ultima vendita:** La data in cui l'ultima unità di questo prodotto è stata venduta.
        -   **Peso:** Il peso del prodotto.
        -   **Ingrosso:** Il prezzo all'ingrosso del prodotto.
        -   **Creato:** La data in cui il prodotto è stato aggiunto al tuo catalogo.
        -   **Condizione:** La condizione del prodotto (Nuovo, Usato, Ricondizionato).
        -   **In saldo:** Indica se il prodotto è attualmente in saldo.
        -   **Disponibile per l'ordine:** Se i clienti possono attualmente acquistare il prodotto.
        -   **Mostra prezzo:** Se il prezzo del prodotto è visualizzato sul front office.
        -   **Solo online:** Indica se il prodotto è disponibile solo online (non nei negozi fisici).
        -   **Visibilità:** Dove il prodotto è visibile (Catalogo, Ricerca, Entrambi, Nessuno).
        -   **Virtuale:** Indica se il prodotto è un prodotto virtuale (es. download, servizio).
        -   **Pacco:** Indica se il prodotto è un pacco di prodotti.
        -   **Indicizzato:** Se il prodotto è indicizzato per la ricerca.
        -   **Personalizzabile:** Se il prodotto ha campi di personalizzazione.
        -   **Fornitore:** Il fornitore specifico associato al prodotto.
    -   **Visibilità delle colonne:** Puoi scegliere quali di queste nuove e esistenti colonne sono visibili nel tuo elenco prodotti. Questo aiuta a ridurre il disordine della vista e a concentrarsi su ciò che è importante.
    -   **Ordine delle colonne (Drag & Drop):** Puoi facilmente riordinare le colonne trascinandole e rilasciandole nella sequenza preferita. Questo ti consente di disporre le informazioni più critiche a sinistra per un accesso rapido.
    -   **Filtro e ordinamento:** Ciascuna delle nuove colonne supporta il filtro e l'ordinamento, proprio come le colonne predefinite di PrestaShop. Ciò significa che puoi, ad esempio, ordinare i prodotti per "Unità vendute" per vedere i tuoi bestseller, o filtrare per "Produttore" per gestire i prodotti di un marchio specifico.
-   **Effetto delle modifiche:**
    -   **Aggiunta/Rimozione di colonne:** Modifica direttamente le informazioni visualizzate nell'elenco "Catalogo > Prodotti". La rimozione di una colonna nasconde quei dati; l'aggiunta di una li rende visibili.
    -   **Riordinamento delle colonne:** Modifica il layout visivo dell'elenco prodotti, consentendoti di dare priorità alle informazioni.
    -   **Filtro/Ordinamento:** Ti aiuta a localizzare e analizzare rapidamente gruppi specifici di prodotti in base ai criteri impostati.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Identifica le tue metriche chiave:** Quali informazioni sui prodotti controlli più spesso? (es. stock, prezzo, unità vendute, riferimento fornitore).
    2.  **Abilita le colonne essenziali:** Vai su **Catalogo > Prodotti**, trova le opzioni di personalizzazione delle colonne (spesso un'icona a forma di ingranaggio o un pulsante "Colonne") e abilita solo le colonne di cui hai veramente bisogno.
    3.  **Organizza per efficienza:** Trascina e rilascia le colonne più importanti sul lato sinistro della griglia in modo che siano immediatamente visibili senza scorrimento orizzontale.
    4.  **Usa i filtri:** Quando gestisci lo stock, usa il filtro "Unità vendute" per identificare gli articoli a lento movimento, o filtra per "Ultima vendita" per trovare prodotti che non sono stati venduti di recente.
    5.  **Revisiona regolarmente:** Rivedi periodicamente la configurazione delle tue colonne per assicurarti che soddisfi ancora le tue esigenze operative.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | Reimposta configurazione modulo | N/A (pulsante) | Ripristina tutte le impostazioni personalizzate della griglia prodotti (visibilità colonne, ordine) ai valori predefiniti del modulo. Utilizzare per ricominciare da capo o per la risoluzione dei problemi. |
| Griglia Catalogo > Prodotti | Colonna EAN13 | Disabilitato | Visualizza il codice a barre EAN13 per ogni prodotto. Utile per l'inventario e la scansione. |
| Griglia Catalogo > Prodotti | Colonna Riferimento fornitore | Disabilitato | Mostra il riferimento interno del fornitore per il prodotto. Essenziale per la gestione dei fornitori. |
| Griglia Catalogo > Prodotti | Colonna Produttore | Disabilitato | Visualizza il produttore/marchio del prodotto. Utile per la gestione specifica del marchio. |
| Griglia Catalogo > Prodotti | Colonna Combinazioni | Disabilitato | Indica se un prodotto ha combinazioni. Controllo rapido per prodotti complessi. |
| Griglia Catalogo > Prodotti | Colonna Unità vendute | Disabilitato | Mostra il totale delle unità vendute per ogni prodotto. Ottimo per identificare i bestseller. |
| Griglia Catalogo > Prodotti | Colonna Ultima vendita | Disabilitato | Visualizza la data dell'ultima vendita per un prodotto. Aiuta a identificare lo stock a lento movimento. |
| Griglia Catalogo > Prodotti | Colonna Peso | Disabilitato | Mostra il peso del prodotto. Importante per i calcoli di spedizione. |
| Griglia Catalogo > Prodotti | Colonna Ingrosso | Disabilitato | Visualizza il prezzo all'ingrosso. Utile per i calcoli dei margini e i negozi B2B. |
| Griglia Catalogo > Prodotti | Colonna Creato | Disabilitato | Mostra la data di aggiunta del prodotto. Aiuta a tenere traccia della crescita del catalogo. |
| Griglia Catalogo > Prodotti | Colonna Condizione | Disabilitato | Visualizza la condizione del prodotto (Nuovo, Usato, Ricondizionato). Rilevante per alcuni tipi di prodotto. |
| Griglia Catalogo > Prodotti | Colonna In saldo | Disabilitato | Indica se il prodotto è attualmente in saldo. Panoramica rapida delle promozioni. |
| Griglia Catalogo > Prodotti | Colonna Disponibile per l'ordine | Disabilitato | Mostra se il prodotto può essere ordinato. Essenziale per la gestione dello stock. |
| Griglia Catalogo > Prodotti | Colonna Mostra prezzo | Disabilitato | Indica se il prezzo è visibile sul front office. |
| Griglia Catalogo > Prodotti | Colonna Solo online | Disabilitato | Mostra se il prodotto è esclusivo per le vendite online. |
| Griglia Catalogo > Prodotti | Colonna Visibilità | Disabilitato | Visualizza dove il prodotto è visibile (catalogo, ricerca, entrambi, nessuno). |
| Griglia Catalogo > Prodotti | Colonna Virtuale | Disabilitato | Indica se il prodotto è virtuale (scaricabile, servizio). |
| Griglia Catalogo > Prodotti | Colonna Pacco | Disabilitato | Mostra se il prodotto è un pacco di altri prodotti. |
| Griglia Catalogo > Prodotti | Colonna Indicizzato | Disabilitato | Indica se il prodotto è indicizzato per la ricerca. |
| Griglia Catalogo > Prodotti | Colonna Personalizzabile | Disabilitato | Mostra se il prodotto ha opzioni di personalizzazione. |
| Griglia Catalogo > Prodotti | Colonna Fornitore | Disabilitato | Visualizza il fornitore principale del prodotto. |
| Griglia Catalogo > Prodotti | Ordine colonne (Drag & Drop) | N/A (definito dall'utente) | Personalizza la sequenza visiva delle colonne per un flusso di lavoro ottimale. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho abilitato nuove colonne, ma non appaiono nell'elenco prodotti.**
R1: Dopo aver abilitato le colonne, assicurati di salvare le modifiche (se c'è un pulsante di salvataggio nell'interfaccia di personalizzazione delle colonne). A volte, la pulizia della cache del browser o della cache Smarty di PrestaShop può aiutare. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.

**D2: Il riordinamento tramite drag-and-drop non funziona, o il layout appare strano.**
R2: Questo potrebbe essere un conflitto JavaScript con un altro modulo o il tuo tema.
    1.  Prova a svuotare la cache del browser e la cache Smarty di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**).
    2.  Se il problema persiste, prova a cliccare sul pulsante "Reimposta configurazione modulo" nella pagina di configurazione del modulo (**Moduli > Gestione moduli > Product Grid Pro > Configura**). Questo ripristinerà il layout ai valori predefiniti e potrebbe risolvere il conflitto.
    3.  Se il problema persiste, disabilita temporaneamente altri moduli che modificano anche l'elenco prodotti o l'interfaccia di amministrazione per identificare un conflitto.

**D3: Posso aggiungere ancora più campi personalizzati alla griglia prodotti?**
R3: Questo modulo fornisce un set predefinito di campi comunemente richiesti. Non offre un modo generico per aggiungere *qualsiasi* campo personalizzato che potresti aver creato (ad esempio, con un altro modulo di campi personalizzati). Se hai bisogno di un campo personalizzato molto specifico, sarebbe necessario un ulteriore sviluppo personalizzato.

**D4: Questo modulo rallenterà il mio Back Office?**
R4: Il modulo è progettato per essere efficiente. Sebbene l'aggiunta di molte colonne significhi che vengono caricati più dati, l'impatto sulle prestazioni è generalmente minimo e superato dai guadagni di efficienza. Se noti rallentamenti significativi, considera di disabilitare le colonne meno critiche per ridurre i dati caricati.

**D5: Il modulo è installato, ma non vedo nuove opzioni in Catalogo > Prodotti.**
R5: Assicurati che il modulo sia correttamente installato e abilitato. A volte, dopo l'installazione, potrebbe essere necessario aggiornare il browser o persino disconnettersi e riconnettersi al Back Office affinché le modifiche abbiano effetto. Controlla anche eventuali messaggi di errore durante l'installazione. Se utilizzi PrestaShop 1.6, l'interfaccia per la personalizzazione delle colonne potrebbe essere leggermente diversa rispetto a 1.7/8/9.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Product Grid Pro".

### 4.1 Panoramica dell'architettura

Il modulo "Product Grid Pro" funziona principalmente sovrascrivendo il `AdminProductsController` di base in PrestaShop. Questa è una tecnica comune e potente nello sviluppo di moduli PrestaShop, che consente ai moduli di estendere o modificare il comportamento delle funzionalità di base senza alterare direttamente i file di base. Il modulo inietta colonne, filtri e capacità di ordinamento aggiuntivi nella tabella dell'elenco prodotti manipolando l'array `$this->fields_list` all'interno del controller sovrascritto. Utilizza anche un file JavaScript dedicato per gestire il riordinamento delle colonne tramite drag-and-drop e potenzialmente altri miglioramenti dinamici dell'interfaccia utente. La configurazione è memorizzata in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce nuovi controller front-office. La sua interazione principale è con il `AdminProductsController` del Back Office.

-   **Controller Front-Office**: Nessuno.
-   **Controller Admin Back-Office**:
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Nome classe e classe genitore**: `AdminProductsController` (sovrascrive il `AdminProductsController` di base).
        *   **Responsabilità**: Questo è il cuore della funzionalità del modulo. Estende la funzionalità predefinita dell'elenco prodotti.
            *   Modifica l'array `$this->fields_list` per aggiungere nuove definizioni di colonna (EAN13, Riferimento fornitore, Produttore, Unità vendute, Ultima vendita, Peso, Ingrosso, Creato, Condizione, In saldo, Disponibile per l'ordine, Mostra prezzo, Solo online, Visibilità, Virtuale, Pacco, Indicizzato, Personalizzabile, Fornitore).
            *   Assicura che questi nuovi campi siano ordinabili e filtrabili.
            *   Gestisce la logica per recuperare i dati per queste nuove colonne dal database.
            *   Integra il JavaScript per il riordinamento delle colonne e la gestione della visibilità.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Nome classe e classe genitore**: Questo file è probabilmente un segnaposto o un semplice reindirizzatore all'interno della struttura di override e non contiene una definizione completa di classe controller per un'entità specifica. La sua presenza nella directory `override/controllers/admin/` suggerisce che potrebbe far parte del meccanismo di override stesso, potenzialmente garantendo che l'override di `AdminProductsController.php` sia caricato correttamente o gestendo il contesto amministrativo generale. Nella maggior parte dei casi, la logica effettiva risiede in `AdminProductsController.php`.

### 4.3 Classi e modelli di base (`classes/`)

Questo modulo non definisce classi `ObjectModel` personalizzate. Interagisce direttamente con gli oggetti `Product` e `Configuration` esistenti di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Ambito**: Back-office (specificamente la pagina `Catalogo > Prodotti`).
    *   **Responsabilità**:
        *   Gestisce la manipolazione dinamica della tabella dell'elenco prodotti nel Back Office di PrestaShop.
        *   Implementa la funzionalità drag-and-drop per il riordinamento delle colonne, consentendo agli amministratori di personalizzare il layout.
        *   Gestisce la visibilità delle colonne (mostrandole/nascondendole in base alle preferenze dell'utente).
        *   Probabilmente memorizza e recupera le preferenze dell'utente per l'ordine e la visibilità delle colonne utilizzando chiamate AJAX o archiviazione locale/cookie, che vengono poi utilizzate dal `AdminProductsController` sovrascritto per renderizzare la griglia.
        *   Può includere listener di eventi per elementi dell'interfaccia utente che controllano la selezione delle colonne (ad esempio, un'icona a forma di ingranaggio o un menu a discesa per attivare/disattivare le colonne).

### 4.5 Fogli di stile CSS (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Ambito**: Back-office (specificamente la pagina `Catalogo > Prodotti`).
    *   **Responsabilità**:
        *   Fornisce lo stile per la griglia prodotti migliorata, assicurando che le nuove colonne e gli elementi dell'interfaccia utente (come i handle di trascinamento o i toggle delle colonne) siano visualizzati correttamente e si integrino perfettamente con il tema del Back Office di PrestaShop.
        *   Può includere stili per indicatori di drag-and-drop, stati di colonne nascoste o larghezze specifiche per nuove colonne.
        *   Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema: Cerca classi con prefisso `product-grid-pro` o simili, o classi specifiche di intestazione/cella di tabella che potrebbero essere mirate per uno stile personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non sembra utilizzare file `.tpl` personalizzati in base all'inventario fornito. Ciò suggerisce che le modifiche alla griglia prodotti sono ottenute principalmente tramite PHP (nel controller sovrascritto) e JavaScript, che manipola dinamicamente la struttura HTML esistente generata dai template di base di PrestaShop per il `AdminProductsController`. Il modulo probabilmente inietta i suoi JS e CSS tramite hook come `displayBackOfficeHeader`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo memorizza principalmente le sue impostazioni di configurazione (ad esempio, ordine preferito delle colonne, visibilità) all'interno della tabella `ps_configuration`. Le chiavi di configurazione sarebbero tipicamente prefissate con `MYPRODUCTGRIDPRO_` o simili.
    *   Non crea nuove tabelle di database personalizzate.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` del Back Office. | Utilizzato per includere le risorse `product_grid_admin.js` e `product_grid_admin.css` del modulo, assicurando che vengano caricate sulla pagina `AdminProductsController`. |
| `actionAdminProductsControllerSave` (o hook `actionAdminController` simili) | Eseguito quando un controller admin salva i dati. | Sebbene non esplicitamente elencato, il modulo potrebbe utilizzare tali hook per salvare le preferenze di colonna personalizzate (ordine, visibilità) in `ps_configuration` quando un utente admin le modifica. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Eseguito prima che vengano renderizzati i campi dell'elenco prodotti. | Questo hook è cruciale per i moduli che modificano `$this->fields_list` di `AdminProductsController`. Consente al modulo di aggiungere, rimuovere o modificare dinamicamente le definizioni delle colonne. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Eseguito dopo che i dati del prodotto sono stati recuperati ma prima del rendering. | Consente al modulo di modificare le righe di dati effettive per le nuove colonne (ad esempio, calcolando "Unità vendute" o "Ultima vendita" se non direttamente disponibili dalla query principale del prodotto). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Product Grid Pro - colonne e layout dei prodotti in elenco", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
