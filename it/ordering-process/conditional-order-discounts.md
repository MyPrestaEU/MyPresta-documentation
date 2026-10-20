---
title: "Sconti Condizionali sull'Ordine - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sconti Condizionali sull'Ordine di MyPresta.eu."
sidebar:
  label: "Sconti Condizionali sull'Ordine - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Order Discounts su MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/conditional-order-discounts/)
>
> ---


# Sconti Condizionali sull'Ordine

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo.

-   **Abilita Sconti Condizionali sull'Ordine:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo. Quando abilitato, la logica del modulo per l'applicazione degli sconti condizionali sarà attiva sul tuo negozio. Quando disabilitato, nessun sconto condizionale verrà applicato, indipendentemente dalle politiche che hai creato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a valutare le tue politiche di sconto definite e ad applicare sconti o regali gratuiti ai carrelli dei clienti quando si qualificano.
        -   *Quando disabilitato:* Tutte le politiche di sconto condizionali create con questo modulo verranno ignorate e nessun sconto verrà applicato.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Hai appena finito di impostare la tua prima politica "Compra 2, Ricevi 1 Gratis" e vuoi che vada online. Abiliteresti questa impostazione. Se hai bisogno di sospendere temporaneamente tutti gli sconti condizionali per una vendita a livello di negozio gestita con altri mezzi, la disabiliteresti.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Il modulo Sconti Condizionali sull'Ordine aggiunge una nuova voce di menu principale al tuo Back Office di PrestaShop, solitamente sotto **Catalogo** o **Marketing**, denominata **"Sconti Condizionali"**. Questo menu contiene diverse sotto-voci per la gestione delle tue politiche e la revisione dei registri.

#### 2.2.1 Sconti Condizionali > Politiche (AdminConorderdisPoliciesController)

Qui è dove definisci e gestisci tutte le tue politiche di sconto condizionale.

-   **Nome Schermata e Posizione Menu:** Back Office > Sconti Condizionali > Politiche
-   **Azioni e Impostazioni Disponibili:**

    -   **Elenco Politiche:** Vedrai una tabella che elenca tutte le tue politiche di sconto esistenti. Ogni politica mostrerà il suo nome, lo stato (attivo/inattivo) e altri dettagli chiave.
    -   **Aggiungi Nuova Politica:** Clicca sul pulsante "Aggiungi nuova politica" per creare una nuova regola di sconto condizionale.
    -   **Modifica Politica:** Clicca sull'icona "Modifica" accanto a una politica esistente per modificarne le condizioni, le promozioni o le impostazioni.
    -   **Duplica Politica:** Questa è una funzione molto utile! Clicca sull'icona "Duplica" per creare una copia esatta di una politica esistente. Questo fa risparmiare molto tempo se hai bisogno di creare promozioni simili.
    -   **Abilita/Disabilita Politica:** Puoi attivare o disattivare rapidamente singole politiche direttamente dall'elenco.
    -   **Elimina Politica:** Rimuovi una politica dal tuo negozio.
    -   **Modulo di Configurazione Politica (quando si aggiunge/modifica):**
        -   **Nome Politica:** Un nome descrittivo per il tuo riferimento interno (es. "BOGO T-Shirt", "Spendi $100 Ottieni 10% di Sconto").
        -   **Stato (Attivo/Inattivo):** Controlla se questa specifica politica è attualmente attiva sul tuo negozio.
        -   **Costruttore di Condizioni:** Questo è il cuore del modulo. Utilizzerai un'interfaccia visiva per definire *quando* lo sconto si applica. Esempi:
            -   "Il totale del carrello è maggiore di $100"
            -   "Il cliente è nel gruppo 'Grossisti'"
            -   "Il prodotto 'X' è nel carrello con quantità >= 2"
            -   "Qualsiasi prodotto della categoria 'Saldi Estivi' è nel carrello"
            -   Puoi combinare più condizioni con la logica "AND" o "OR".
        -   **Costruttore di Promozioni:** Questo definisce *quale* sconto o regalo il cliente riceve se le condizioni sono soddisfatte. Esempi:
            -   "Applica il 10% di sconto all'intero ordine"
            -   "Regala l'articolo più economico della categoria 'Accessori'"
            -   "Aggiungi il prodotto 'Scatola Regalo' al carrello gratuitamente"
            -   "Applica il 50% di sconto sulla seconda unità del prodotto 'Y'"
        -   **Selettore di Ambito:** Definisci a quali negozi (per configurazioni multistore), gruppi di clienti o valute si applica questa politica.
        -   **Priorità:** Se più politiche potessero applicarsi a un singolo carrello, questo determina quale ha la precedenza. Numeri più bassi significano priorità più alta.
        -   **Date di Validità:** Imposta una data di inizio e fine per la promozione.
        -   **Simulatore di Carrello:** Uno strumento potente all'interno dell'editor di politiche che ti consente di aggiungere prodotti a un carrello simulato e vedere istantaneamente se la tua politica si applica e quale sconto viene dato. Questo è fondamentale per i test!
-   **Effetto delle modifiche:**

    -   L'aggiunta di una nuova politica rende disponibile una nuova promozione (se attiva) sul tuo negozio.
    -   La modifica di una politica cambia le condizioni o le promozioni di un'offerta esistente.
    -   L'abilitazione/disabilitazione delle politiche controlla direttamente la loro visibilità e applicazione sul front office.
    -   La duplicazione delle politiche consente la rapida creazione di promozioni simili senza partire da zero.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Pianifica la tua promozione:** Decidi l'offerta (es. "Compra 3, ricevi 1 gratis su tutti i calzini").
    2.  **Crea una nuova politica:** Vai su "Politiche" e clicca su "Aggiungi nuova politica".
    3.  **Definisci le condizioni:** Usa il costruttore visivo per specificare quali prodotti, categorie, quantità o valori del carrello attivano lo sconto.
    4.  **Definisci le promozioni:** Specifica il tipo di sconto (percentuale, importo fisso, regalo gratuito) e a cosa si applica.
    5.  **Testa accuratamente con il Simulatore di Carrello:** Prima di salvare, usa il simulatore per aggiungere vari prodotti e quantità per assicurarti che lo sconto si applichi esattamente come previsto.
    6.  **Imposta le date di validità e la priorità:** Assicurati che la promozione sia attiva solo quando lo desideri e interagisca correttamente con altre promozioni.
    7.  **Attiva la politica:** Una volta testata e pronta, imposta il suo stato su "Attivo".
    8.  **Monitora con il Registro di Controllo:** Controlla il Registro di Controllo (vedi sezione successiva) per confermare che le politiche vengano applicate correttamente nei carrelli reali.

#### 2.2.2 Sconti Condizionali > Registro di Controllo (AdminConorderdisAuditLogController)

Questa schermata fornisce una cronologia dettagliata di come le tue politiche di sconto condizionale sono state applicate (o tentate di applicare) ai carrelli dei clienti.

-   **Nome Schermata e Posizione Menu:** Back Office > Sconti Condizionali > Registro di Controllo
-   **Azioni e Impostazioni Disponibili:**
    -   **Elenco Log:** Una tabella che mostra le voci per ogni volta che una politica è stata valutata. Ogni voce include tipicamente:
        -   **Data/Ora:** Quando si è verificato l'evento.
        -   **Cliente:** Quale cliente (se loggato) è stato coinvolto.
        -   **ID Carrello:** L'ID del carrello acquisti.
        -   **Nome Politica:** Quale politica è stata valutata.
        -   **Risultato:** Se le condizioni della politica sono state soddisfatte e se è stato applicato uno sconto.
        -   **Dettagli:** Informazioni più specifiche sulle condizioni soddisfatte, lo sconto applicato o il motivo per cui non è stato applicato.
    -   **Filtro e Ricerca:** Puoi filtrare il log per data, cliente, politica o risultato per trovare rapidamente eventi specifici.
-   **Effetto delle modifiche:** Questa è una schermata di sola lettura. Non apporti modifiche qui, ma piuttosto osservi il comportamento del modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   **Risoluzione dei problemi:** Se un cliente segnala un problema con uno sconto che non si applica, o se sospetti che una politica non funzioni come previsto, controlla il registro di controllo. Puoi vedere esattamente cosa è successo quando il loro carrello è stato valutato.
    -   **Monitoraggio:** Rivedi regolarmente il log per assicurarti che le tue promozioni vengano attivate correttamente e per identificare eventuali comportamenti inaspettati.
    -   **Comprensione delle Interazioni tra Politiche:** Se hai più politiche, il log può aiutarti a capire quali politiche vengono considerate e quale alla fine si applica in base alle priorità.

#### 2.2.3 Sconti Condizionali > Dashboard (AdminConorderdisDashboardController)

Questa schermata fornisce una panoramica e potenzialmente un accesso rapido alle funzionalità chiave del modulo.

-   **Nome Schermata e Posizione Menu:** Back Office > Sconti Condizionali > Dashboard
-   **Azioni e Impostazioni Disponibili:** Questa dashboard tipicamente fornisce:
    -   **Statistiche Riepilogative:** Conteggi rapidi di politiche attive, politiche totali o voci recenti del registro di controllo.
    -   **Link Rapidi:** Scorciatoie per "Aggiungi Nuova Politica", "Visualizza Politiche" o "Visualizza Registro di Controllo".
    -   **Accesso al Simulatore:** Un link prominente o uno strumento incorporato per il Simulatore di Carrello per testare rapidamente le politiche.
    -   **Stato del Modulo:** Indicazione se il modulo è abilitato o disabilitato.
-   **Effetto delle modifiche:** Questa è principalmente una schermata informativa e di navigazione. Le modifiche vengono apportate tramite le sezioni collegate "Politiche" o "Registro di Controllo".
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Usala come punto di partenza per gestire le tue promozioni, ottenere una rapida panoramica delle tue campagne attive e accedere al simulatore per i test.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Sconti Condizionali sull'Ordine | SÌ | Interruttore principale per attivare/disattivare tutte le funzionalità del modulo. |
| Politiche (Aggiungi/Modifica) | Nome Politica | Nome Descrittivo | Etichetta interna per la tua promozione. |
| Politiche (Aggiungi/Modifica) | Stato | Attivo | Controlla se una specifica politica è attiva sul negozio. |
| Politiche (Aggiungi/Modifica) | Costruttore di Condizioni | Varia | Definisce i criteri di idoneità allo sconto (es. totale carrello, prodotti nel carrello). |
| Politiche (Aggiungi/Modifica) | Costruttore di Promozioni | Varia | Definisce lo sconto o il regalo gratuito applicato (es. % di sconto, prodotto gratuito). |
| Politiche (Aggiungi/Modifica) | Selettore di Ambito | Tutti i Negozi/Gruppi/Valute | Limita l'applicazione della politica a contesti specifici. |
| Politiche (Aggiungi/Modifica) | Priorità | Numero più basso = priorità più alta | Determina quale politica si applica se più sono idonee. |
| Politiche (Aggiungi/Modifica) | Date di Validità | Nessuna data di fine | Imposta il periodo attivo per la promozione. |
| Politiche (Aggiungi/Modifica) | Simulatore di Carrello | N/A | Strumento per testare l'applicazione della politica prima di salvare. |
| Politiche (Elenco) | Azione Duplica Politica | N/A | Crea una copia di una politica esistente, risparmiando tempo di configurazione. |
| Registro di Controllo | Voci di Log | N/A | Registra ogni valutazione della politica, mostrando successo/fallimento e dettagli. |
| Dashboard | Link Rapidi / Riepilogo | N/A | Fornisce una panoramica e scorciatoie alle funzionalità chiave del modulo. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Il mio sconto non si applica, anche se ho impostato una politica.**
R1:

-   **Il modulo è abilitato?** Controlla **Moduli > Gestione moduli > Sconti Condizionali sull'Ordine** e assicurati che l'interruttore principale sia su ON.
-   **La politica specifica è attiva?** Vai su **Sconti Condizionali > Politiche** e controlla la colonna "Stato" per la tua politica.
-   **Le condizioni sono soddisfatte?** Usa il **Simulatore di Carrello** all'interno dell'editor di politiche. Aggiungi prodotti al carrello simulato esattamente come farebbe un cliente. Il simulatore mostra lo sconto applicato? In caso contrario, rivedi attentamente le tue condizioni.
-   **Controlla le date di validità:** La politica rientra nel suo intervallo di date attivo?
-   **Controlla la priorità:** Se più politiche potessero applicarsi, assicurati che quella che ti aspetti si applichi abbia la priorità corretta (numero più basso = priorità più alta).
-   **Svuota la cache di PrestaShop:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache". A volte, i dati memorizzati nella cache possono impedire che le nuove regole abbiano effetto immediatamente.

**D2: Lo sconto si applica, ma non è l'importo o il prodotto corretto.**
R2:

-   **Rivedi il tuo Costruttore di Promozioni:** Ricontrolla il tipo di sconto (percentuale, importo fisso), il valore e a cosa si applica (intero ordine, prodotti specifici, articolo più economico, ecc.).
-   **Controlla di nuovo le condizioni:** A volte, una condizione sottile potrebbe portare a un risultato inaspettato. Ad esempio, se hai "qualsiasi prodotto della categoria X" ma il cliente ha prodotti di altre categorie che soddisfano anche una regola "articolo più economico".
-   **Usa ampiamente il Simulatore di Carrello:** Questo è il tuo migliore amico per verificare regole complesse. Testa i casi limite.
-   **Registro di Controllo:** Controlla **Sconti Condizionali > Registro di Controllo** per vedere i dettagli esatti di come il modulo ha valutato il carrello e quale sconto ha tentato di applicare. Questo può rivelare discrepanze.

**D3: Il mio tema personalizzato non visualizza chiaramente i messaggi di sconto o i regali gratuiti.**
R3:

-   Il modulo si integra con le regole carrello native di PrestaShop, quindi lo sconto stesso dovrebbe apparire nel riepilogo del carrello. Tuttavia, se desideri che messaggi personalizzati come "Ti sei qualificato per un regalo gratuito!" o "Compra 2, Ricevi 1 Gratis!" appaiano dinamicamente sulle pagine dei prodotti o nel carrello, ciò di solito richiede modifiche al tema personalizzate.
-   **Consulta uno sviluppatore:** Il tuo webmaster o uno sviluppatore PrestaShop può aiutarti a integrare messaggi dinamici nei file `product.tpl`, `cart.tpl` o `checkout.tpl` del tuo tema, potenzialmente utilizzando gli hook del modulo (vedi Guida per Sviluppatori).

**D4: Posso usare questo modulo con altri moduli di sconto o regole carrello native?**
A4:

-   Sì, questo modulo funziona creando e gestendo regole carrello native di PrestaShop in background. Ciò significa che è generalmente compatibile con altri moduli che si basano anche sul sistema di sconti principale di PrestaShop.
-   **La priorità è fondamentale:** Fai attenzione alle impostazioni di priorità per le tue politiche di Sconti Condizionali sull'Ordine e a qualsiasi altra regola carrello nativa che hai creato manualmente. PrestaShop applica gli sconti in base alla loro priorità. Testa accuratamente con il Simulatore di Carrello e rivedi il Registro di Controllo se hai molte promozioni sovrapposte.

**D5: Come gestisco le traduzioni multilingue per i nomi o le descrizioni delle politiche?**
A5:

-   I nomi delle politiche e qualsiasi testo personalizzato che inserisci per condizioni o promozioni sono tipicamente gestiti direttamente nella schermata di modifica della politica. L'interfaccia di traduzione standard di PrestaShop (sotto **Internazionale > Traduzioni**) potrebbe non applicarsi direttamente al contenuto dinamico generato dal costruttore di politiche del modulo.
-   Se il modulo fornisce campi specifici per diverse lingue all'interno dell'editor di politiche, usa quelli. Altrimenti, assicurati che i nomi delle tue politiche siano chiari e concisi, o considera l'aggiunta di blocchi informativi statici nel tuo tema per diverse lingue per spiegare le promozioni.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica del modulo Sconti Condizionali sull'Ordine, dettagliando la sua struttura di file, classi, controller e punti di integrazione per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo Sconti Condizionali sull'Ordine è costruito seguendo il modello MVC (Model-View-Controller) di PrestaShop. Sfrutta pesantemente il sistema `CartRule` nativo di PrestaShop, agendo efficacemente come un costruttore e gestore di regole avanzato per questi oggetti principali. Introduce diverse classi `ObjectModel` personalizzate per la gestione di politiche, condizioni, promozioni e un registro di controllo. Il modulo utilizza un motore robusto per valutare condizioni complesse rispetto allo stato del carrello di un cliente e quindi materializza gli oggetti `CartRule` appropriati. Include anche un sofisticato costruttore di condizioni e un simulatore nel Back Office per facilità d'uso.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `conorderdis/controllers/front/index.php`
    -   **Nome Classe:** `ConorderdisIndexModuleFrontController` (o simile, a seconda della versione di PrestaShop e della struttura del modulo, spesso `ModuleFrontController`).
    -   **Responsabilità:** Questo file funge tipicamente da segnaposto o punto di ingresso predefinito per le interazioni del modulo nel front-office. Nel contesto di questo modulo, i controller diretti del front-office sono meno critici poiché la maggior parte della logica è gestita tramite hook che interagiscono con il processo del carrello e dell'ordine. Potrebbe gestire richieste AJAX relative agli aggiornamenti del carrello o interazioni specifiche del front-end se implementate, ma la logica principale dello sconto viene eseguita tramite hook.

#### Controller Admin Back-Office

-   `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
    -   **Nome Tab:** Sconti Condizionali > Registro di Controllo
    -   **Entità Gestita:** `ConorderdisAuditLog` (mappa alla tabella `ps_conorderdis_log`).
    -   **Responsabilità:** Gestisce la visualizzazione e il filtraggio delle voci del registro di controllo. Estende `AdminController` e utilizza `HelperList` per renderizzare la tabella del log, consentendo agli amministratori di rivedere come le politiche sono state applicate o valutate rispetto ai carrelli dei clienti.
-   `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
    -   **Nome Tab:** Sconti Condizionali > Politiche
    -   **Entità Gestita:** `ConorderdisPolicy` (mappa alla tabella `ps_conorderdis_policy`).
    -   **Responsabilità:** Questo è il controller principale per la gestione delle politiche di sconto. Estende `AdminController` e fornisce funzionalità CRUD (Create, Read, Update, Delete) per le politiche. Integra i costruttori visivi di condizioni e promozioni, il selettore di prodotti e il simulatore di carrello. Utilizza `HelperList` per la panoramica delle politiche e `HelperForm` per i moduli di aggiunta/modifica delle politiche.
-   `conorderdis/controllers/admin/index.php`
    -   **Responsabilità:** Questa è una pratica standard di PrestaShop per prevenire l'elenco delle directory. Tipicamente contiene una semplice istruzione `die('No direct script access allowed');`. Non gestisce alcuna entità specifica né fornisce funzionalità oltre la sicurezza.

### 4.3 Classi e Modelli Core (`classes/`)

-   `conorderdis/classes/ConorderdisAdmin.php`
    -   **Responsabilità:** Probabilmente contiene metodi di aiuto o utilità specifici per l'amministrazione del Back Office, come il rendering di elementi di modulo specifici, la gestione delle richieste AJAX dai moduli di amministrazione o la gestione delle configurazioni specifiche del modulo.
-   `conorderdis/classes/ConorderdisAuditLog.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `ps_conorderdis_log`
    -   **Campi `$definition`:** Memorizza i dettagli sulle valutazioni delle politiche, inclusi `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
    -   **Responsabilità:** Rappresenta una voce nel registro di controllo. Fornisce metodi per la registrazione degli eventi di applicazione delle politiche, successi e fallimenti.
-   `conorderdis/classes/ConorderdisCartRuleManager.php`
    -   **Responsabilità:** Gestisce la creazione, l'aggiornamento e l'eliminazione degli oggetti `CartRule` nativi di PrestaShop basati sulle definizioni `ConorderdisPolicy` del modulo. Questa classe è cruciale per tradurre le regole complesse del modulo in sconti standard di PrestaShop.
-   `conorderdis/classes/ConorderdisCartState.php`
    -   **Responsabilità:** Incapsula lo stato attuale del carrello di un cliente, fornendo un livello di astrazione per il motore di sconto per valutare le condizioni. Potrebbe includere metodi per recuperare il totale del carrello, le quantità dei prodotti, il gruppo clienti, ecc.
-   `conorderdis/classes/ConorderdisCompatibility.php`
    -   **Responsabilità:** Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (es. 1.7.x, 8.x, 9.x) o specifiche versioni di PHP. Assicura che il modulo funzioni correttamente nell'intervallo di ambienti supportati fornendo polyfill o implementazioni alternative per funzioni/metodi deprecati.
-   `conorderdis/classes/ConorderdisConditionTree.php`
    -   **Responsabilità:** Gestisce la complessa struttura logica delle condizioni (es. gruppi "AND", "OR", condizioni annidate). Probabilmente analizza i dati delle condizioni dal database e fornisce metodi per valutare se un dato `ConorderdisCartState` soddisfa le condizioni definite.
-   `conorderdis/classes/ConorderdisContext.php`
    -   **Responsabilità:** Un wrapper attorno all'oggetto `Context` globale di PrestaShop, potenzialmente aggiungendo dati di contesto specifici del modulo o semplificando l'accesso alle proprietà di contesto comuni.
-   `conorderdis/classes/ConorderdisDashboard.php`
    -   **Responsabilità:** Fornisce dati e logica per la vista della dashboard del Back Office, riassumendo le statistiche chiave e fornendo link rapidi.
-   `conorderdis/classes/ConorderdisEngine.php`
    -   **Responsabilità:** Il motore logico principale del modulo. Questa classe orchestra la valutazione delle politiche. Prende un `ConorderdisCartState`, itera attraverso gli oggetti `ConorderdisPolicy` attivi, valuta il loro `ConorderdisConditionTree` e, se le condizioni sono soddisfatte, istruisce `ConorderdisPromoMaterializer` ad applicare lo sconto.
-   `conorderdis/classes/ConorderdisFreeGift.php`
    -   **Responsabilità:** Gestisce specificamente la logica per l'aggiunta di prodotti regalo gratuiti al carrello quando una promozione lo richiede. Interagisce con l'oggetto `Cart` per garantire che il prodotto sia aggiunto correttamente e contrassegnato come gratuito.
-   `conorderdis/classes/ConorderdisListRenderer.php`
    -   **Responsabilità:** Una classe di aiuto per il rendering di elenchi nel Back Office, potenzialmente estendendo `HelperList` o fornendo una logica di rendering personalizzata per colonne o azioni specifiche (es. l'azione di duplicazione).
-   `conorderdis/classes/ConorderdisLog.php`
    -   **Estende:** `ObjectModel` (probabilmente un alias o una versione precedente di `ConorderdisAuditLog`).
    -   **Tabella Database:** `ps_conorderdis_log`
    -   **Responsabilità:** Simile a `ConorderdisAuditLog`, gestisce la registrazione degli eventi del modulo.
-   `conorderdis/classes/ConorderdisPolicy.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `ps_conorderdis_policy`
    -   **Campi `$definition`:** Memorizza tutti i dati relativi alla politica, inclusi `name`, `active`, `conditions_data` (array JSON serializzato), `promotions_data` (array JSON serializzato), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
    -   **Responsabilità:** Rappresenta una singola politica di sconto condizionale. Fornisce metodi per salvare, caricare e gestire i dati della politica, incluse le sue condizioni e promozioni.
-   `conorderdis/classes/ConorderdisPolicyDuplicator.php`
    -   **Responsabilità:** Gestisce la logica per la duplicazione degli oggetti `ConorderdisPolicy`, assicurando che tutti i dati associati (condizioni, promozioni) siano copiati correttamente.
-   `conorderdis/classes/ConorderdisProductPicker.php`
    -   **Responsabilità:** Fornisce funzionalità per la selezione di prodotti, categorie o produttori all'interno del costruttore di politiche del Back Office, probabilmente tramite uno strumento di ricerca basato su AJAX.
-   `conorderdis/classes/ConorderdisPromoMaterializer.php`
    -   **Responsabilità:** Prende l'output del `ConorderdisEngine` (cioè, "questa promozione dovrebbe applicarsi") e lo traduce in modifiche effettive nel carrello di PrestaShop, principalmente creando o modificando oggetti `CartRule` tramite `ConorderdisCartRuleManager`.
-   `conorderdis/classes/ConorderdisPromotionCalculator.php`
    -   **Responsabilità:** Calcola l'importo esatto dello sconto o identifica il prodotto gratuito in base alle regole di promozione definite e allo stato attuale del carrello.
-   `conorderdis/classes/ConorderdisPromotionType.php`
    -   **Responsabilità:** Definisce e gestisce diversi tipi di promozioni (es. sconto percentuale, importo fisso, regalo gratuito, articolo più economico gratuito). Probabilmente contiene la logica specifica per ogni tipo di promozione.
-   `conorderdis/classes/ConorderdisRule.php`
    -   **Responsabilità:** Una classe generica che rappresenta una singola regola o condizione all'interno del `ConorderdisConditionTree`.
-   `conorderdis/classes/ConorderdisSchema.php`
    -   **Responsabilità:** Gestisce lo schema del database del modulo, inclusa l'installazione e la disinstallazione di tabelle personalizzate (`ps_conorderdis_policy`, `ps_conorderdis_log`).
-   `conorderdis/classes/ConorderdisUnitPool.php`
    -   **Responsabilità:** Probabilmente utilizzato in scenari complessi "Compra N, Ricevi M" o "articolo più economico gratuito" per gestire e tracciare le singole unità di prodotto all'interno del carrello per il calcolo dello sconto.
-   `conorderdis/classes/index.php`
    -   **Responsabilità:** Pratica standard di PrestaShop per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

-   `conorderdis/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (utilizzato nei moduli di amministrazione).
    -   **Dettagli:** Fornisce funzionalità di completamento automatico per i campi di input, probabilmente utilizzato nel costruttore di politiche per la selezione di prodotti, categorie o produttori. Si lega ai campi di input, effettua chiamate AJAX a un controller di ricerca e visualizza suggerimenti.
-   `conorderdis/views/js/adminConditionBuilder.js`
    -   **Ambito:** Back-office (controller AdminConorderdisPolicies).
    -   **Dettagli:** Alimenta l'interfaccia visiva del costruttore di condizioni. Gestisce l'aggiunta/rimozione di condizioni, il raggruppamento di condizioni (AND/OR), la selezione dei tipi di condizione e l'aggiornamento dinamico dell'interfaccia utente in base all'input dell'utente. Gestisce la struttura dati che rappresenta l'albero delle condizioni.
-   `conorderdis/views/js/adminConorderdisDashboard.js`
    -   **Ambito:** Back-office (controller AdminConorderdisDashboard).
    -   **Dettagli:** Fornisce elementi interattivi o contenuti dinamici per la dashboard del modulo, come il recupero di statistiche riepilogative tramite AJAX o la gestione dei clic sui link rapidi.
-   `conorderdis/views/js/adminConorderdisSearchTool.js`
    -   **Ambito:** Back-office (controller AdminConorderdisPolicies).
    -   **Dettagli:** Uno strumento di ricerca più generale, potenzialmente utilizzato per la selezione di prodotti/categorie all'interno del costruttore di politiche, simile a `autocomplete.js` ma probabilmente con opzioni di filtraggio o visualizzazione più avanzate.
-   `conorderdis/views/js/adminConorderdisSimulator.js`
    -   **Ambito:** Back-office (controller AdminConorderdisPolicies).
    -   **Dettagli:** Implementa il simulatore di carrello interattivo. Si lega ai campi di input per l'aggiunta di prodotti simulati, effettua chiamate AJAX a un endpoint di simulazione (probabilmente in `AdminConorderdisPolicies`) e aggiorna l'interfaccia utente con lo stato del carrello simulato e gli sconti applicati.
-   `conorderdis/views/js/adminPolicyRules.js`
    -   **Ambito:** Back-office (controller AdminConorderdisPolicies).
    -   **Dettagli:** Gestisce l'interazione e la logica complessiva per il modulo di creazione/modifica delle politiche, coordinando il costruttore di condizioni, il costruttore di promozioni e il simulatore.
-   `conorderdis/views/js/adminPromotionBuilder.js`
    -   **Ambito:** Back-office (controller AdminConorderdisPolicies).
    -   **Dettagli:** Alimenta l'interfaccia visiva del costruttore di promozioni. Gestisce l'aggiunta/rimozione di promozioni, la selezione dei tipi di promozione (es. percentuale, regalo gratuito) e l'aggiornamento dinamico dell'interfaccia utente in base al tipo di promozione scelto.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `conorderdis/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office (moduli di amministrazione).
    -   **Dettagli:** Stila i menu a discesa di completamento automatico e i risultati di ricerca forniti dallo script `autocomplete.js`.
-   `conorderdis/views/css/admin_conorderdis.css`
    -   **Ambito:** Back-office (moduli e pagine di amministrazione).
    -   **Dettagli:** Contiene lo stile generale per le interfacce del Back Office del modulo, inclusi l'elenco delle politiche, l'editor delle politiche (costruttori di condizioni e promozioni), la dashboard e il registro di controllo. Definisce layout, colori e componenti specifici dell'interfaccia utente per un aspetto e una sensazione coerenti all'interno dell'amministrazione di PrestaShop.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `conorderdis/views/templates/hook/admin_order.tpl`
    -   **Hook:** `displayAdminOrder`
    -   **Output:** Questo template viene renderizzato nel Back Office quando si visualizza un ordine. Probabilmente visualizza informazioni relative a eventuali sconti condizionali applicati a quell'ordine specifico, potenzialmente collegandosi al registro di controllo o mostrando quali politiche erano attive.

#### Template Admin (`views/templates/admin/`)

-   `conorderdis/lib/searchTool/views/scripts.tpl`
    -   **Output:** Contiene l'inizializzazione o la configurazione JavaScript per lo strumento di ricerca, spesso incluso nei moduli di amministrazione dove lo strumento di ricerca è utilizzato.
-   `conorderdis/views/templates/admin/auditPreview.tpl`
    -   **Output:** Renderizza un'anteprima o una vista dettagliata di una voce del registro di controllo, possibilmente all'interno di un modale o di una sezione specifica della pagina `AdminconorderdisAuditLog`.
-   `conorderdis/views/templates/admin/dashboard.tpl`
    -   **Output:** Il template principale per il controller `AdminConorderdisDashboard`, che visualizza statistiche riepilogative, link rapidi e potenzialmente il simulatore incorporato.
-   `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
    -   **Output:** Un template personalizzato per il rendering dell'icona e del link dell'azione "Duplica" all'interno di una tabella `HelperList`, specificamente per le politiche.
-   `conorderdis/views/templates/admin/policiesPreview.tpl`
    -   **Output:** Renderizza un'anteprima o una vista dettagliata di una politica, possibilmente all'interno di un modale o di una sezione specifica della pagina `AdminconorderdisPolicies`.
-   `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
    -   **Output:** Il template Smarty per l'interfaccia visiva del costruttore di condizioni all'interno dell'editor di politiche. Definisce la struttura per l'aggiunta, il raggruppamento e la configurazione delle condizioni.
-   `conorderdis/views/templates/admin/policyRuleCard.tpl`
    -   **Output:** Un template riutilizzabile per la visualizzazione di una singola regola o condizione all'interno del costruttore di condizioni, spesso utilizzato per il rendering dinamico tramite JavaScript.
-   `conorderdis/views/templates/admin/policyRulesTable.tpl`
    -   **Output:** Renderizza la tabella o l'elenco di regole/condizioni all'interno dell'editor di politiche.
-   `conorderdis/views/templates/admin/scopeSelector.tpl`
    -   **Output:** Renderizza l'interfaccia per la selezione di negozi, gruppi di clienti e valute per una politica.

#### Template Front-office (`views/templates/front/`)

-   `conorderdis/controllers/front/index.php` (Nessun file `.tpl` specifico elencato per il front-office, il che implica un rendering front-end diretto minimo, basandosi su hook per iniettare contenuto o modificare elementi esistenti.)

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

-   `ps_conorderdis_policy`: Memorizza la definizione di ogni politica di sconto condizionale.
    -   `id_conorderdis_policy` (Chiave Primaria)
    -   `name` (Nome della politica)
    -   `active` (Booleano, 1 per attivo, 0 per inattivo)
    -   `conditions_data` (TESTO, array di condizioni codificato in JSON)
    -   `promotions_data` (TESTO, array di promozioni codificato in JSON)
    -   `priority` (INT, numero più basso = priorità più alta)
    -   `date_from` (DATETIME)
    -   `date_to` (DATETIME)
    -   `id_shop` (INT, per l'ambito multistore)
    -   `id_customer_group` (INT, per l'ambito del gruppo clienti)
    -   `id_currency` (INT, per l'ambito della valuta)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_conorderdis_log`: Memorizza le voci del registro di controllo per le valutazioni delle politiche.
    -   `id_conorderdis_log` (Chiave Primaria)
    -   `id_cart` (INT)
    -   `id_customer` (INT)
    -   `id_policy` (INT, chiave esterna a `ps_conorderdis_policy`)
    -   `result` (VARCHAR, es. 'applied', 'not\_met', 'error')
    -   `details` (TESTO, dettagli della valutazione codificati in JSON)
    -   `date_add` (DATETIME)
-   `ps_configuration`: Il modulo memorizza la sua impostazione principale `CONORDERDIS_ENABLED` qui.

#### Tabella degli Hook Registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere CSS/JS del front-office del modulo, se presenti, o per iniettare meta tag. |
| `actionFrontControllerInitAfter` | Dopo l'inizializzazione del controller frontale. | Punto iniziale per modificare il contesto, registrare servizi o prepararsi per la valutazione delle regole del carrello. |
| `actionCartSave` | Dopo il salvataggio di un carrello (es. prodotto aggiunto/rimosso). | Hook primario per rivalutare le politiche di sconto condizionale in base al contenuto aggiornato del carrello. |
| `actionValidateCartRule` | Prima che una regola del carrello venga convalidata/applicata. | Consente al modulo di intervenire o modificare il comportamento nativo delle regole del carrello, anche se meno probabile per questo modulo che crea le proprie. |
| `actionValidateOrderBefore` | Prima della convalida di un ordine. | Controllo finale per gli sconti condizionali prima della creazione dell'ordine, garantendo che tutte le regole siano applicate correttamente. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Utilizzato per finalizzare eventuali azioni specifiche del modulo dopo l'ordine, come la registrazione dell'applicazione finale dello sconto o la cancellazione dei dati temporanei. |
| `actionObjectProductInCartDeleteBefore` | Prima che un prodotto venga eliminato dal carrello. | Consente al modulo di reagire alla rimozione del prodotto, potenzialmente regolando sconti o regali gratuiti. |
| `actionObjectProductInCartDeleteAfter` | Dopo che un prodotto è stato eliminato dal carrello. | Simile a `DeleteBefore`, ma per la logica post-eliminazione, potenzialmente attivando una rivalutazione delle regole del carrello. |
| `actionAdminControllerSetMedia` | Quando un controller admin sta impostando i suoi media (CSS/JS). | Utilizzato per includere i file CSS e JavaScript del Back Office del modulo per le sue pagine di configurazione e i controller personalizzati. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine del Back Office. | Utilizzato per visualizzare informazioni specifiche del modulo relative agli sconti condizionali applicati all'ordine visualizzato (es. tramite `admin_order.tpl`). |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai i tuoi moduli acquistati e l'accesso ai nostri canali di supporto.
"""
