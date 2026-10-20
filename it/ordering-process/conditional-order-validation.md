---
title: "Validazione Condizionale Ordini - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Validazione Condizionale Ordini di MyPresta.eu."
sidebar:
  label: "Validazione Condizionale Ordini - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Order Validation su MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/conditional-order-validation/)
>
> ---


# Validazione Condizionale Ordini

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura > Validazione Condizionale Ordini)

Questo è il punto di ingresso principale per le impostazioni globali del modulo.

- **Posizione del Menu:** Back Office > Moduli > Gestione moduli > Validazione Condizionale Ordini > Configura

#### 2.1.1 Impostazioni Generali

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Abilita Validazione Condizionale Ordini** | SÌ | **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo. Se disabilitato, nessuna delle tue politiche definite sarà attiva e i clienti potranno effettuare il checkout senza alcuna restrizione da parte di questo modulo.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Il modulo inizierà a valutare tutte le politiche attive che hai creato. Se un carrello viola una politica, il cliente vedrà avvisi o verrà bloccato dal checkout secondo le impostazioni della tua politica.   *Quando disabilitato:* Il modulo diventa inattivo. Nessuna politica viene controllata e nessun messaggio viene visualizzato.   **Valore consigliato:** SÌ (una volta configurate le tue politiche).   **Scenario del commerciante:** Abilitalo dopo aver impostato le tue prime politiche e averle testate utilizzando il simulatore. |
| **Visualizza Messaggi di Validazione Su** | Carrello e Checkout | **Cosa fa questa impostazione:** Controlla dove vengono mostrati al cliente i messaggi di avviso o di blocco del modulo.   **Effetto della modifica di questa impostazione:**   *Quando impostato su "Carrello e Checkout":* I messaggi appariranno sia sulla pagina del carrello che durante le varie fasi del processo di checkout. Ciò fornisce la massima visibilità e un feedback tempestivo al cliente.   *Quando impostato su "Solo Carrello":* I messaggi appariranno solo sulla pagina del carrello. I clienti potrebbero procedere ulteriormente nel checkout prima di essere bloccati se ignorano l'avviso del carrello.   *Quando impostato su "Solo Checkout":* I messaggi appariranno solo durante il processo di checkout. I clienti non vedranno avvisi sulla pagina del carrello, il che potrebbe portare a frustrazione più avanti nel processo.   **Valore consigliato:** Carrello e Checkout.   **Scenario del commerciante:** Per la migliore esperienza del cliente, mostra i messaggi presto e spesso (Carrello e Checkout) in modo che i clienti possano correggere il loro carrello prima di investire tempo nel processo di checkout. |
| **Consenti Checkout con Avvisi** | NO | **Cosa fa questa impostazione:** Determina se i clienti possono procedere al checkout anche se il loro carrello attiva una politica di "avviso" (anziché una politica di "blocco").   **Effetto della modifica di questa impostazione:**   *Quando abilitato (SÌ):* Se una politica è impostata su "Avviso", il cliente vedrà il messaggio di avviso ma potrà comunque cliccare sul pulsante "Procedi al checkout" o "Effettua ordine". Questo è utile per raccomandazioni soft o problemi non critici.   *Quando disabilitato (NO):* Se una politica è impostata su "Avviso", il cliente vedrà il messaggio di avviso e il pulsante "Procedi al checkout" o "Effettua ordine" sarà disabilitato fino a quando la condizione di avviso non sarà risolta. Questo rende effettivamente gli "avvisi" simili ai "blocchi" nella fase di checkout.   **Valore consigliato:** NO (a meno che tu non abbia avvisi "soft" molto specifici).   **Scenario del commerciante:** Se hai una politica come "I clienti che acquistano oltre $100 ottengono la spedizione gratuita" e vuoi *suggerire* loro di aggiungere altro al carrello ma non *forzarli*, potresti abilitare questa opzione. Tuttavia, per la maggior parte delle regole aziendali, vorrai disabilitarla per garantire la conformità. |

### 2.2 Schermate di Amministrazione Dedicate e Viste del Controller

Il modulo introduce due nuove potenti sezioni nel menu del tuo Back Office di PrestaShop: "Politiche" e "Registro di Controllo".

#### 2.2.1 Politiche (Back Office > Validazione Condizionale Ordini > Politiche)

Qui è dove definisci, gestisci e attivi le tue regole di validazione condizionale degli ordini. Ogni "politica" è un insieme di condizioni che, se soddisfatte, bloccheranno o avviseranno il cliente.

- **Posizione del Menu:** Back Office > Validazione Condizionale Ordini > Politiche
- **Azioni e Impostazioni Disponibili:**

  - **Elenco Politiche:** Una tabella che mostra tutte le politiche create, indicando il loro nome, stato (abilitato/disabilitato), tipo (blocco/avviso) e priorità.
  - **Aggiungi Nuova Politica:** Clicca questo pulsante per creare una nuova politica di validazione.
  - **Modifica Politica:** Modifica il nome, le condizioni, i messaggi e lo stato di una politica esistente.
  - **Duplica Politica:** Crea rapidamente una copia di una politica esistente da utilizzare come punto di partenza per una nuova. Questo fa risparmiare tempo quando si creano regole simili.
  - **Abilita/Disabilita Politica:** Attiva o disattiva lo stato di una politica senza eliminarla.
  - **Elimina Politica:** Rimuovi una politica in modo permanente.
  - **Simulatore:** Uno strumento cruciale (spesso presente nella schermata di creazione/modifica della politica o come scheda dedicata) che ti consente di testare le tue politiche con un carrello simulato prima che vadano online. Questo aiuta a prevenire il blocco involontario di ordini legittimi.
- **Modulo di Creazione/Modifica Politica:**

  - **Nome Politica:** Un nome descrittivo per la tua politica (ad esempio, "Valore Minimo Ordine per Grossisti", "Restrizione Età per Alcolici").
  - **Stato:** Abilita o Disabilita la politica.
  - **Tipo di Politica:**
    - **Blocco:** Se le condizioni sono soddisfatte, al cliente viene *impedito* di effettuare il checkout.
    - **Avviso:** Se le condizioni sono soddisfatte, il cliente vede un messaggio di avviso ma *potrebbe o meno* essere in grado di procedere, a seconda dell'impostazione globale "Consenti Checkout con Avvisi".
  - **Priorità:** Se più politiche sono attive e attivate, questo determina l'ordine in cui vengono visualizzati i messaggi o quale politica ha la precedenza (numero inferiore = priorità più alta).
  - **Costruttore di Condizioni:** Questo è il cuore della politica. Costruirai un albero di condizioni utilizzando la logica "AND" / "OR".
    - **Tipi di Condizione:** Puoi tipicamente scegliere tra una vasta gamma di condizioni:
      - **A livello di carrello:** Valore totale del carrello, quantità totale di articoli, numero di prodotti unici.
      - **A livello di prodotto:** ID prodotto specifici, categorie, produttori, fornitori, attributi del prodotto, quantità minima/massima di un prodotto specifico.
      - **A livello di cliente:** Gruppo di clienti, ID cliente specifico, paese del cliente.
      - **A livello di spedizione:** Vettore selezionato, zona di spedizione.
    - **Operatori:** (ad esempio, "è uguale a", "è maggiore di", "contiene", "non è").
    - **Valori:** Il punto dati specifico con cui confrontare (ad esempio, "100" per un valore minimo, "Elettronica" per una categoria).
  - **Messaggio Cliente:** Il messaggio visualizzato al cliente nel front office quando questa politica viene attivata. Rendilo chiaro, utile e attuabile (ad esempio, "Il tuo carrello deve contenere almeno 5 unità del prodotto X per procedere.").
  - **Messaggio Amministratore (Opzionale):** Una nota interna per te o altri amministratori.
- **Effetto delle modifiche:**

  - L'aggiunta/modifica di una politica influisce direttamente sull'esperienza di checkout del front-office per i clienti.
  - L'abilitazione di una politica attiva le sue regole. La disabilitazione le disattiva senza eliminarle.
  - Il simulatore consente di testare le modifiche senza influire sui clienti reali.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. Identifica una regola aziendale che desideri applicare (ad esempio, "I clienti all'ingrosso devono ordinare un minimo di $500").
  2. Vai su "Politiche" e clicca su "Aggiungi Nuova Politica".
  3. Assegna un nome chiaro, impostala su "Blocco" e definisci le condizioni (ad esempio, "Gruppo Cliente È Grossista" E "Totale Carrello È MAGGIORE O UGUALE A 500").
  4. Scrivi un messaggio utile per il cliente (ad esempio, "Gli ordini all'ingrosso richiedono un totale minimo di $500. Aggiungi altri articoli al carrello.").
  5. Usa il "Simulatore" per testare vari scenari (ad esempio, un cliente all'ingrosso con un carrello da $400, un cliente al dettaglio con un carrello da $400, un cliente all'ingrosso con un carrello da $600).
  6. Una volta soddisfatto, abilita la politica.

#### 2.2.2 Registro di Controllo (Back Office > Validazione Condizionale Ordini > Registro di Controllo)

Il Registro di Controllo fornisce una cronologia di quando le politiche sono state attivate, da chi e quale è stato il risultato. Questo è inestimabile per la risoluzione dei problemi e la comprensione del comportamento dei clienti.

- **Posizione del Menu:** Back Office > Validazione Condizionale Ordini > Registro di Controllo
- **Azioni e Impostazioni Disponibili:**

  - **Elenco Log:** Una tabella che mostra le voci per ogni volta che una politica è stata valutata e attivata.
  - **Colonne:**
    - **Data/Ora:** Quando si è verificato l'evento.
    - **Cliente:** Il cliente che ha attivato la politica (se loggato).
    - **ID Carrello:** L'ID del carrello coinvolto.
    - **Nome Politica:** Il nome della politica che è stata attivata.
    - **Tipo di Politica:** Se era una politica di "Blocco" o "Avviso".
    - **Messaggio:** Il messaggio visualizzato al cliente.
    - **Stato:** Se l'ordine è stato infine convalidato, bloccato o avvisato.
  - **Filtro/Ricerca:** Il filtro standard dell'elenco di PrestaShop consente di cercare per cliente, politica, intervallo di date, ecc.
  - **Visualizza Dettagli Carrello:** Spesso, puoi cliccare su un ID carrello per ispezionare il contenuto del carrello al momento in cui la politica è stata attivata.
- **Effetto delle modifiche:** Questa schermata è solo per la visualizzazione e il controllo; non puoi apportare modifiche qui. È un registro degli eventi.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  - Se un cliente segnala un problema con il checkout, controlla il Registro di Controllo per vedere se sono state attivate politiche per il suo carrello. Questo può identificare rapidamente se una politica è configurata in modo errato o se il cliente semplicemente non ha soddisfatto i requisiti.
  - Rivedi periodicamente il log per capire quali politiche vengono attivate più frequentemente e se sono necessarie modifiche.

### 2.3 Tabella di Riferimento Rapido alla Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|
| **Configurazione Modulo** | Abilita Validazione Condizionale Ordini | SÌ | Interruttore principale per la funzionalità del modulo. |
| **Configurazione Modulo** | Visualizza Messaggi di Validazione Su | Carrello e Checkout | Dove appaiono i messaggi del cliente (carrello, checkout o entrambi). |
| **Configurazione Modulo** | Consenti Checkout con Avvisi | NO | Determina se le politiche di "avviso" bloccano il checkout o si limitano a informare. |
| **Politiche (Admin)** | Nome Politica | N/A | Identificatore descrittivo per la tua regola. |
| **Politiche (Admin)** | Stato | Abilitato | Attiva o disattiva una politica specifica. |
| **Politiche (Admin)** | Tipo di Politica | Blocco / Avviso | Definisce se la politica impedisce il checkout o visualizza solo un messaggio. |
| **Politiche (Admin)** | Priorità | N/A | Ordine di valutazione/visualizzazione per più politiche attivate. |
| **Politiche (Admin)** | Costruttore di Condizioni | N/A | Definisce le regole logiche per quando la politica viene attivata. |
| **Politiche (Admin)** | Messaggio Cliente | N/A | Il messaggio mostrato al cliente quando la politica viene attivata. |
| **Politiche (Admin)** | Messaggio Amministratore | N/A | Note interne per gli amministratori. |
| **Registro di Controllo (Admin)** | (Tutte le Colonne) | N/A | Registra tutte le istanze di politiche attivate per la revisione. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: Le mie politiche non funzionano, o i clienti continuano a effettuare il checkout quando non dovrebbero.**
R:

1.  **Il modulo è abilitato?** Controlla "Abilita Validazione Condizionale Ordini" nella configurazione principale del modulo.
2.  **Le politiche specifiche sono abilitate?** Vai su "Politiche" e assicurati che la colonna "Stato" per le tue politiche sia impostata su "Abilitato".
3.  **Controlla il Tipo di Politica:** È impostato su "Blocco" o "Avviso"? Se "Avviso", controlla l'impostazione globale "Consenti Checkout con Avvisi". Se è abilitato, i clienti possono ignorare gli avvisi.
4.  **Svuota Cache:** A volte la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache".
5.  **Simulatore:** Usa il "Simulatore" integrato nella schermata di creazione/modifica della politica per testare le tue condizioni con vari scenari di carrello. Questo è il modo più efficace per eseguire il debug.
6.  **Registro di Controllo:** Controlla il "Registro di Controllo" per vedere se le tue politiche vengono attivate e quale è stato il risultato.

**D: I messaggi di avviso/blocco non sono esteticamente gradevoli sul mio tema.**
R: Il modulo utilizza lo stile standard di PrestaShop ove possibile, ma i temi personalizzati potrebbero sovrascrivere o richiedere specifiche modifiche CSS.

1.  **CSS di Base:** Il CSS del modulo è progettato per essere generico. Se il tuo tema ha uno stile molto specifico, potresti aver bisogno di un webmaster per aggiungere CSS personalizzato al file `custom.css` del tuo tema per abbinarlo al tuo brand.
2.  **Sovrascritture di Template:** Gli utenti avanzati possono sovrascrivere i file di template del modulo (ad esempio, `views/templates/hook/validation_banner.tpl`) nel loro tema per personalizzare completamente la struttura HTML e l'aspetto.

**D: Posso tradurre i messaggi per diverse lingue?**
R: Sì, tutti i messaggi rivolti al cliente che definisci nelle tue politiche sono traducibili.

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office.
2.  Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e seleziona la lingua.
3.  Trova il modulo "Validazione Condizionale Ordini" e traduci i messaggi delle politiche lì.

**D: Ho creato una politica, ma sta bloccando *tutti* gli ordini, anche quelli validi.**
R: Questo di solito significa che le tue condizioni sono troppo ampie o configurate in modo errato.

1.  **Rivedi le Condizioni:** Rileggi attentamente ogni condizione nella tua politica. Assicurati che gli operatori (ad esempio, "È", "NON È", "MAGGIORE DI") e i valori siano corretti.
2.  **Logica AND/OR:** Presta molta attenzione se stai usando "AND" o "OR" tra i gruppi di condizioni. "AND" significa che *tutte* le condizioni devono essere vere; "OR" significa che *qualsiasi* condizione deve essere vera. Un errore comune è usare "OR" quando si intende "AND", o viceversa.
3.  **Usa il Simulatore:** Questo è fondamentale. Simula vari carrelli "buoni" e "cattivi" per vedere esattamente perché la politica si sta attivando.

**D: Come gestisco le configurazioni multi-negozio?**
R: Il modulo è progettato per essere compatibile con configurazioni multi-negozio. Quando crei o modifichi le politiche, dovresti vedere un'opzione per selezionare a quali negozi si applica la politica. Assicurati che le tue politiche siano assegnate ai contesti di negozio corretti.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Validazione Condizionale Ordini per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo Validazione Condizionale Ordini segue un robusto modello MVC (Model-View-Controller) all'interno del framework PrestaShop. Sfrutta ampiamente `ObjectModel` per la persistenza dei dati (politiche, registri di controllo), controller amministrativi personalizzati per la gestione di queste entità e un sofisticato motore di valutazione delle condizioni per elaborare le regole in tempo reale. Il modulo si integra profondamente nei hook di validazione degli ordini e di presentazione del carrello, garantendo che le politiche siano applicate nelle fasi critiche del percorso del cliente. Un aspetto chiave è il `ConordervalidEngine` che orchestra la valutazione degli oggetti `ConordervalidPolicy`, ognuno contenente un `ConordervalidConditionTree`.

### 4.2 Controller (`controllers/`)

#### 4.2.1 Controller Front-Office

- `conordervalid/controllers/front/index.php`
  - **Nome Classe:** `ConordervalidIndexModuleFrontController` (probabilmente estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso generale o gestire specifiche richieste AJAX del front-office relative alla validazione del carrello o alla visualizzazione dei messaggi. Dato il suo nome, potrebbe essere un fallback o un semplice controller di visualizzazione.
- `conordervalid/controllers/front/validate.php`
  - **Nome Classe:** `ConordervalidValidateModuleFrontController` (probabilmente estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller è cruciale per la validazione del carrello in tempo reale. Probabilmente gestisce le richieste AJAX dalle pagine del carrello o del checkout per verificare se lo stato attuale del carrello viola le politiche attive. Restituirebbe risposte JSON che indicano se il carrello è valido, eventuali messaggi di avviso o motivi di blocco. Qui verrebbe invocato il `ConordervalidEngine`.

#### 4.2.2 Controller Amministrativi Back-Office

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Nome Classe:** `AdminconordervalidAuditLogController` (estende `ModuleAdminController`)
  - **Nome Scheda:** Registro di Controllo (sotto il menu Validazione Condizionale Ordini)
  - **Entità Gestita:** `ConordervalidAuditLog` (mappata alla tabella `ps_conordervalid_log`)
  - **Responsabilità:** Gestisce la visualizzazione e il filtraggio delle voci del registro di controllo. Utilizza `HelperList` per il rendering della griglia, consentendo agli amministratori di visualizzare i record storici degli attivazioni delle politiche.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Nome Classe:** `AdminconordervalidPoliciesController` (estende `ModuleAdminController`)
  - **Nome Scheda:** Politiche (sotto il menu Validazione Condizionale Ordini)
  - **Entità Gestita:** `ConordervalidPolicy` (mappata alla tabella `ps_conordervalid_policy`)
  - **Responsabilità:** Questo è il controller principale per la gestione delle politiche di validazione. Gestisce le operazioni CRUD per le politiche, inclusa la complessa interfaccia del costruttore di condizioni. Utilizza `HelperList` per la panoramica delle politiche e `HelperForm` per la creazione/modifica delle politiche, integrando la logica di `ConordervalidConditionTree` e `ConordervalidConditionBuilder`.
- `conordervalid/controllers/admin/index.php`
  - **Nome Classe:** (Probabilmente un semplice reindirizzamento o segnaposto)
  - **Responsabilità:** Spesso, `index.php` in una directory di controller è una misura di sicurezza per prevenire l'elenco diretto della directory o un semplice reindirizzamento alla configurazione principale del modulo o alla dashboard.

### 4.3 Classi e Modelli Core (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Responsabilità:** Probabilmente contiene metodi di aiuto o utilità specifici per l'interfaccia di amministrazione, come la registrazione del menu, la gestione delle schede o la logica comune di rendering dei moduli.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Estende:** `ObjectModel`
  - **Tabella Database:** `ps_conordervalid_log`
  - **Campi `$definition`:** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Responsabilità:** Rappresenta una singola voce nel registro di controllo, memorizzando i dettagli su una politica attivata.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Responsabilità:** Una classe di utilità per incapsulare lo stato attuale del carrello di un cliente (prodotti, quantità, totale, informazioni cliente, vettore selezionato, ecc.). Questo oggetto viene passato al `ConordervalidConditionEvaluator`.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Responsabilità:** Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (ad esempio, differenze nei nomi dei hook, nelle strutture delle classi o nelle chiamate API tra PS 1.7, 8.x e 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Estende:** (Probabilmente una classe base o `ObjectModel` se le condizioni sono memorizzate individualmente)
  - **Responsabilità:** Rappresenta una singola condizione all'interno di una politica (ad esempio, "Totale Carrello > 100"). Definisce il tipo di condizione, l'operatore e il valore.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Responsabilità:** La logica principale per la valutazione di un `ConordervalidCondition` o `ConordervalidConditionGroup` rispetto a un oggetto `ConordervalidCartState`. Contiene metodi per confrontare diversi tipi di dati e applicare operatori.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Estende:** (Probabilmente una classe base)
  - **Responsabilità:** Rappresenta un raggruppamento logico di condizioni (ad esempio, "Condizione A AND (Condizione B OR Condizione C)"). Gestisce la logica `AND`/`OR`.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Estende:** (Probabilmente una classe base o `ObjectModel`)
  - **Responsabilità:** Rappresenta l'intera struttura gerarchica delle condizioni per una politica. È una struttura dati ad albero composta da oggetti `ConordervalidConditionGroup` e `ConordervalidCondition`.
- `conordervalid/classes/ConordervalidContext.php`
  - **Responsabilità:** Un wrapper o un'estensione della classe `Context` di PrestaShop, che potenzialmente aggiunge dati di contesto specifici del modulo o metodi di aiuto.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Responsabilità:** Probabilmente fornisce dati e logica per una potenziale dashboard del modulo nel Back Office, riassumendo le prestazioni delle politiche o le statistiche del registro di controllo.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Responsabilità:** L'orchestratore centrale. Recupera gli oggetti `ConordervalidPolicy` attivi, li itera e utilizza `ConordervalidConditionEvaluator` per verificare se un dato carrello viola una politica. Determina il risultato finale (bloccato, avvisato, valido) e raccoglie i messaggi.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Responsabilità:** Una classe di utilità per il rendering di elenchi o tabelle nel Back Office, che potenzialmente personalizza il comportamento di `HelperList` o fornisce una formattazione specifica delle colonne.
- `conordervalid/classes/ConordervalidLog.php`
  - **Estende:** `ObjectModel` (probabilmente un alias o una versione precedente di `ConordervalidAuditLog`)
  - **Tabella Database:** `ps_conordervalid_log`
  - **Campi `$definition`:** Simili a `ConordervalidAuditLog`.
  - **Responsabilità:** Memorizza le voci del registro di controllo.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Estende:** `ObjectModel`
  - **Tabella Database:** `ps_conordervalid_policy`
  - **Campi `$definition`:** `id_conordervalid_policy`, `name`, `active`, `type` (blocco/avviso), `priority`, `conditions_json` (memorizza il `ConordervalidConditionTree` come JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Responsabilità:** Rappresenta una singola politica di validazione, incluse le sue condizioni, messaggi e impostazioni.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Responsabilità:** Gestisce la logica per la duplicazione degli oggetti `ConordervalidPolicy`, assicurando che tutte le condizioni e le impostazioni associate siano correttamente copiate.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Responsabilità:** Probabilmente definisce set predefiniti di condizioni o template di politiche che possono essere caricati rapidamente dagli amministratori.
- `conordervalid/classes/ConordervalidRule.php`
  - **Estende:** (Probabilmente una classe base o `ObjectModel`)
  - **Responsabilità:** Potrebbe essere un alias per `ConordervalidCondition` o un'astrazione di livello superiore per una singola regola all'interno di una politica.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Responsabilità:** Gestisce l'archiviazione e il recupero degli oggetti `ConordervalidConditionTree`, probabilmente serializzandoli/deserializzandoli da/verso il campo `conditions_json` in `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Responsabilità:** Misura di sicurezza standard per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office (moduli amministrativi)
  - **Responsabilità:** Fornisce la funzionalità di autocompletamento per i campi di input nell'amministrazione, probabilmente utilizzata per la selezione di prodotti, categorie, clienti, ecc., all'interno del costruttore di condizioni.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Ambito:** Back-office (moduli amministrativi)
  - **Responsabilità:** Duplicato del precedente, probabilmente un errore nel packaging o un percorso legacy.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Ambito:** Back-office (AdminconordervalidPoliciesController)
  - **Responsabilità:** Alimenta l'interfaccia interattiva di costruzione delle condizioni nel modulo di creazione/modifica delle politiche. Gestisce l'aggiunta/rimozione di condizioni, la gestione della logica AND/OR e l'aggiornamento della struttura JSON sottostante dell'albero delle condizioni.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Ambito:** Back-office (Dashboard amministrativa, se implementata)
  - **Responsabilità:** Fornisce funzionalità dinamiche per una potenziale dashboard del modulo, come il rendering di grafici, il filtraggio dei dati o gli aggiornamenti AJAX.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Ambito:** Back-office (moduli amministrativi)
  - **Responsabilità:** Integra lo strumento di ricerca (ad esempio, per prodotti, categorie) in vari moduli amministrativi, probabilmente utilizzato dal costruttore di condizioni.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Ambito:** Back-office (AdminconordervalidPoliciesController)
  - **Responsabilità:** Gestisce la logica per il simulatore di politiche. Acquisisce i dati del carrello simulato, li invia tramite AJAX a un controller front-office (ad esempio, `validate.php`) e visualizza i risultati della validazione.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Ambito:** Back-office (AdminconordervalidPoliciesController)
  - **Responsabilità:** Contiene la logica JS specifica per la gestione della visualizzazione e dell'interazione delle regole delle politiche all'interno dell'interfaccia amministrativa, potenzialmente correlata al riordino tramite drag-and-drop o alle modifiche rapide.
- `conordervalid/views/js/validation.js`
  - **Ambito:** Front-office (pagine Carrello, Checkout)
  - **Responsabilità:** Questo è il JS principale del front-office. Ascolta i cambiamenti del carrello (ad esempio, aggiornamento della quantità, rimozione del prodotto), attiva le chiamate AJAX al controller front-office `validate.php` e quindi aggiorna dinamicamente l'interfaccia utente per visualizzare messaggi di avviso/blocco o abilitare/disabilitare i pulsanti di checkout in base alla risposta. Probabilmente utilizza `prestashop.on` per il binding degli eventi.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office (moduli amministrativi)
  - **Componenti UI principali:** Stili per i menu a discesa di autocompletamento e i campi di input utilizzati nello strumento di ricerca amministrativo.
  - **Selettori chiave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Ambito:** Back-office (moduli amministrativi)
  - **Componenti UI principali:** Duplicato del precedente.
  - **Selettori chiave:** Uguali a quelli sopra.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Ambito:** Back-office (moduli e liste amministrative)
  - **Componenti UI principali:** Stili per l'elenco delle politiche, il modulo di creazione/modifica delle politiche, il costruttore di condizioni e il registro di controllo.
  - **Selettori chiave:** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Ambito:** Front-office (pagine Carrello, Checkout)
  - **Componenti UI principali:** Stili per i banner e i messaggi di avviso/blocco visualizzati ai clienti.
  - **Selettori chiave:** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### 4.6.1 Template Hook (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hook:** `DisplayAdminOrder`
  - **Output:** Un blocco all'interno della vista dell'ordine del Back Office, che potenzialmente mostra quali politiche sono state attivate per un ordine o un carrello specifico.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hook:** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Output:** La struttura HTML per i messaggi di avviso/blocco del front-office visualizzati al cliente. Questo template riceve variabili come `$validation_messages`, `$is_blocked`, ecc.

#### 4.6.2 Template Admin (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Output:** Template Smarty per l'inclusione di risorse JS/CSS relative allo strumento di ricerca nell'amministrazione.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Output:** Duplicato del precedente.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Output:** Un template parziale per la visualizzazione di un'anteprima o un riepilogo delle voci del registro di controllo, possibilmente utilizzato all'interno di una dashboard o di una vista specifica.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Output:** Il template principale per una potenziale dashboard del modulo nel Back Office, che visualizza statistiche, log recenti o riepiloghi delle politiche.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Output:** Pulsante di azione personalizzato per la duplicazione delle politiche all'interno della vista `HelperList` per `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Output:** Un template parziale per la visualizzazione di un'anteprima o un riepilogo delle politiche, simile a `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Output:** La complessa struttura HTML per l'interfaccia interattiva del costruttore di condizioni utilizzata durante la creazione o la modifica di una politica. Questo template funziona a stretto contatto con `adminConditionBuilder.js`.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Output:** Un template più piccolo e riutilizzabile per la visualizzazione di una singola regola o condizione all'interno del costruttore di condizioni.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Output:** Una struttura simile a una tabella per la visualizzazione di un elenco di regole, possibilmente utilizzata nella panoramica delle politiche o nel simulatore.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Output:** Template per la selezione dell'ambito di una politica (ad esempio, negozi specifici in un ambiente multi-negozio).

#### 4.6.3 Template Front-office (`views/templates/front/`)

- (Nessun template front-office autonomo dedicato identificato, poiché la visualizzazione front-office è gestita tramite template hook come `validation_banner.tpl`.)

### 4.7 Schema del Database e Mappa dei Hook

#### 4.7.1 Tabelle del Database

- `ps_conordervalid_policy`
  - **Scopo:** Memorizza la definizione di ogni politica di validazione.
  - **Campi Chiave:** `id_conordervalid_policy` (PK), `name`, `active` (booleano), `type` (enum: 'blocking', 'warning'), `priority`, `conditions_json` (TEXT, memorizza `ConordervalidConditionTree` serializzato), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Scopo:** Memorizza le voci del registro di controllo per le politiche attivate.
  - **Campi Chiave:** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Scopo:** Memorizza le impostazioni globali del modulo.
  - **Campi Chiave:** `CONORDERVALID_DISPLAY_SURFACES` (ad esempio, 'cart,checkout'), `CONORDERVALID_ENABLED` (booleano), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (booleano).

#### 4.7.2 Tabella dei Hook Registrati

| Nome Hook | Tempistica e Contesto di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `DisplayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Inietta le risorse CSS (`front.css`) e JS (`validation.js`) del front-office. |
| `ActionFrontControllerInitAfter` | Dopo che un controller front-office è stato inizializzato. | Potenzialmente utilizzato per inizializzare il contesto del modulo, caricare le politiche o eseguire controlli di validazione precoci. |
| `ActionObjectProductInCartDeleteBefore` | Prima che un prodotto venga rimosso dal carrello. | Potrebbe essere utilizzato per registrare lo stato del carrello prima di una modifica, o per impedire la cancellazione se viola una politica. |
| `ActionObjectProductInCartDeleteAfter` | Dopo che un prodotto è stato rimosso dal carrello. | Rivaluta le politiche del carrello dopo la rimozione di un prodotto, attiva l'aggiornamento AJAX. |
| `ActionCartSave` | Dopo che un carrello è stato salvato (ad esempio, aggiornamento della quantità, aggiunta/rimozione del prodotto). | Attiva la rivalutazione di tutte le politiche attive rispetto al carrello aggiornato. |
| `actionPresentCart` | Quando il carrello viene preparato per la visualizzazione (ad esempio, sulla pagina del carrello). | Inietta i messaggi di validazione nel template della pagina del carrello. |
| `DisplayShoppingCartFooter` | In fondo alla pagina del carrello. | Renderizza `validation_banner.tpl` con eventuali messaggi di avviso/blocco. |
| `DisplayPaymentTop` | In cima alla sezione di selezione del pagamento durante il checkout. | Renderizza `validation_banner.tpl` con eventuali messaggi di avviso/blocco, potenzialmente disabilitando le opzioni di pagamento. |
| `DisplayCheckoutSummaryTop` | In cima alla pagina di riepilogo del checkout (prima della conferma finale dell'ordine). | Renderizza `validation_banner.tpl` con eventuali messaggi di avviso/blocco, potenzialmente disabilitando il pulsante di conferma dell'ordine. |
| `ActionFilterPaymentOptions` | Filtra le opzioni di pagamento disponibili durante il checkout. | Può essere utilizzato per nascondere o disabilitare i metodi di pagamento se una politica viene violata (ad esempio, "COD non consentito per ordini superiori a $X"). |
| `ActionValidateOrderBefore` | Poco prima che un ordine venga ufficialmente convalidato. | L'ultimo controllo critico per bloccare un ordine se vengono violate politiche di blocco. Registra il tentativo. |
| `ActionValidateOrder` | Dopo che un ordine è stato convalidato e creato con successo. | Registra la convalida dell'ordine riuscita, potenzialmente registra quali politiche *non* sono state violate. |
| `DisplayAdminOrder` | Renderizza un blocco all'interno della pagina dei dettagli dell'ordine del Back Office. | Visualizza informazioni sulle politiche che sono state attivate (o superate) per l'ordine specifico, utilizzando `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | Quando un controller amministrativo sta impostando i suoi media (JS/CSS). | Inietta JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) e CSS (`admin_conordervalid.css`) specifici del Back Office per la gestione delle politiche. |
| `DisplayReassurance` | Spesso utilizzato per visualizzare elementi di fiducia (ad esempio, icone di pagamento sicuro). | Potrebbe potenzialmente essere utilizzato per visualizzare un piccolo avviso o stato persistente se un carrello non è valido. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Validazione Condizionale Ordini, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
