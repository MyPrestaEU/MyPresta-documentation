---
title: "Quote Enterprise - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Quote Enterprise di MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Quote Enterprise su MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste le estensioni PHP standard (cURL, JSON, OpenSSL). Assicurati che il tuo server soddisfi i requisiti minimi di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Quote Enterprise)

Questa è la schermata di configurazione principale dove definisci il comportamento e l'aspetto principali del modulo Quote Enterprise.

#### Scheda Impostazioni generali

-   **Abilita Quote Enterprise:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il sistema di quotazione diventa attivo sul tuo negozio e i clienti possono iniziare a richiedere preventivi.
        -   *Quando disabilitato:* Tutte le funzionalità di quotazione sono nascoste dal front office e non è possibile richiedere nuovi preventivi. I preventivi esistenti nel back office rimangono accessibili per la gestione.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Abilita questa opzione quando sei pronto a offrire servizi di quotazione. Disabilitala temporaneamente durante la manutenzione o se decidi di smettere di offrire preventivi.
-   **Consenti richieste di preventivo dal carrello:**

    -   **Cosa fa questa impostazione:** Determina se i clienti possono convertire l'intero carrello in una richiesta di preventivo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un pulsante o un link "Richiedi un preventivo" apparirà nel riepilogo del carrello, consentendo ai clienti di inviare tutti gli articoli nel carrello per un preventivo.
        -   *Quando disabilitato:* I clienti possono richiedere preventivi solo dalle singole pagine prodotto o tramite il pulsante fluttuante (se abilitato), non direttamente dal carrello.
    -   **Valore consigliato:** SÌ (per la maggior parte degli scenari B2B e di ordini all'ingrosso)
    -   **Scenario / esempio del commerciante:** Se ti occupi principalmente di ordini di grandi dimensioni, con più articoli, dove i prezzi sono spesso negoziati, abilita questa opzione. Se i tuoi preventivi sono solitamente per prodotti singoli e personalizzati, potresti disabilitarla.
-   **Consenti richieste di preventivo dalla pagina prodotto:**

    -   **Cosa fa questa impostazione:** Controlla se un pulsante "Richiedi un preventivo" appare sulle singole pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono aggiungere un prodotto specifico a una richiesta di preventivo direttamente dalla sua pagina, invece di aggiungerlo al carrello.
        -   *Quando disabilitato:* L'opzione di richiesta preventivo viene rimossa dalle pagine prodotto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Essenziale per prodotti personalizzati, articoli di alto valore o quando si desidera offrire un'alternativa all'acquisto diretto per qualsiasi prodotto.
-   **Visualizza pulsante preventivo fluttuante:**

    -   **Cosa fa questa impostazione:** Aggiunge un pulsante persistente e fluttuante al front office del tuo negozio, consentendo ai clienti di avviare una richiesta di preventivo da quasi ogni pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Apparirà un piccolo pulsante cliccabile (spesso in un angolo dello schermo), che aprirà il modulo di richiesta preventivo o un elenco di preventivi esistenti.
        -   *Quando disabilitato:* Il pulsante fluttuante non sarà visibile.
    -   **Valore consigliato:** SÌ (per alta visibilità e facilità di accesso)
    -   **Scenario / esempio del commerciante:** Usa questa opzione per rendere l'opzione di quotazione altamente visibile in tutto il tuo negozio, incoraggiando più richieste.
-   **Valore minimo dell'ordine per la richiesta di preventivo:**

    -   **Cosa fa questa impostazione:** Imposta un valore totale minimo (nella tua valuta predefinita) che una richiesta di preventivo deve raggiungere per essere inviata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore (es. 100):* I clienti non possono inviare una richiesta di preventivo se il valore totale degli articoli nella loro richiesta è inferiore a questo importo. Verrà visualizzato un messaggio di errore.
        -   *Quando impostato su 0 o lasciato vuoto:* Non viene applicato alcun valore minimo.
    -   **Valore consigliato:** 0 (o un valore che filtra le richieste banali)
    -   **Scenario / esempio del commerciante:** Se desideri elaborare preventivi solo per ordini significativi, imposta un valore minimo (es. $500) per ridurre il carico amministrativo per le piccole richieste.
-   **Validità predefinita del preventivo (Giorni):**

    -   **Cosa fa questa impostazione:** Definisce per quanti giorni un preventivo appena creato sarà valido, per impostazione predefinita.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un numero (es. 30):* Tutti i nuovi preventivi creati dal tuo team avranno automaticamente una data di scadenza di 30 giorni dalla loro creazione.
        -   *Quando impostato su 0 o lasciato vuoto:* I preventivi non avranno un periodo di validità predefinito e il tuo team dovrà impostarne uno manualmente o gestirli senza scadenza.
    -   **Valore consigliato:** 30 (o un periodo tipico per il tuo settore)
    -   **Scenario / esempio del commerciante:** Impostare una validità di 30 giorni incoraggia i clienti ad agire entro un lasso di tempo ragionevole e ti protegge dalle fluttuazioni dei prezzi.

#### Scheda Modelli email

Questa sezione ti consente di personalizzare le notifiche email inviate dal modulo.

-   **Gestore modelli email:**
    -   **Cosa fa questa impostazione:** Fornisce un'interfaccia visiva per modificare il contenuto di vari modelli email relativi ai preventivi (es. nuova richiesta di preventivo, preventivo aggiornato, preventivo accettato).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modifichi un modello:* L'email corrispondente inviata ai clienti o al tuo team rifletterà le tue modifiche, inclusi testo, branding e layout.
    -   **Valore consigliato:** Personalizza per adattarlo alla voce del tuo brand e fornire istruzioni chiare.
    -   **Scenario / esempio del commerciante:** Modifica l'email "Nuova richiesta di preventivo" per includere istruzioni specifiche per il tuo team di vendita o aggiungi un saluto personalizzato per i clienti.

#### Scheda Impostazioni avanzate

-   **Abilita REST API:**

    -   **Cosa fa questa impostazione:** Attiva un'interfaccia programmatica (API) per il modulo, consentendo a sistemi esterni o applicazioni personalizzate di interagire con i tuoi preventivi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo espone endpoint che possono essere utilizzati dagli sviluppatori per creare, leggere, aggiornare ed eliminare preventivi in modo programmatico.
        -   *Quando disabilitato:* L'API è inattiva e non può essere accessata.
    -   **Valore consigliato:** NO (a meno che tu non abbia esigenze di integrazione specifiche)
    -   **Scenario / esempio del commerciante:** Se ti integri con un CRM, ERP o un'app mobile personalizzata, l'abilitazione dell'API consente a questi sistemi di creare o aggiornare automaticamente i preventivi in PrestaShop. Richiede esperienza da sviluppatore.
-   **Gestione chiavi API:**

    -   **Cosa fa questa impostazione:** Ti consente di generare e gestire chiavi API, necessarie per autenticare le richieste all'API REST del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando crei una chiave:* Ottieni un identificatore univoco che le applicazioni esterne devono utilizzare per accedere all'API.
        -   *Quando revochi una chiave:* Qualsiasi applicazione che utilizza quella chiave perderà l'accesso all'API.
    -   **Valore consigliato:** Genera chiavi solo quando necessario per integrazioni specifiche.
    -   **Scenario / esempio del commerciante:** Crea una nuova chiave API per il tuo sistema CRM per inviare nuovi lead come richieste di preventivo in PrestaShop.
-   **URL Cron Job per scadenza e riepilogo:**

    -   **Cosa fa questa impostazione:** Fornisce un URL che, quando acceduto, attiva attività in background come il controllo delle scadenze dei preventivi e l'invio di riepiloghi giornalieri al tuo team.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando configurato sul tuo server:* Il modulo eseguirà automaticamente queste attività a intervalli regolari (es. giornalmente), assicurando che i preventivi siano contrassegnati come scaduti e che il tuo team riceva riepiloghi tempestivi.
        -   *Quando non configurato:* I controlli di scadenza e le email di riepilogo non saranno automatizzati.
    -   **Valore consigliato:** Configura questo URL come un cron job giornaliero sul tuo server di hosting.
    -   **Scenario / esempio del commerciante:** Imposta un cron job per eseguire questo URL una volta al giorno per assicurarti che i clienti siano avvisati dei preventivi in scadenza e che il tuo team di vendita riceva un riepilogo giornaliero delle nuove richieste.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Gestione preventivi (Back Office > Quote Enterprise > Preventivi)

Questo è l'hub centrale per il tuo team di vendita per gestire tutte le richieste di preventivo.

-   **Nome schermata e posizione menu:** **Quote Enterprise > Preventivi**
-   **Azioni e impostazioni disponibili:**
    -   **Tabella elenco preventivi:** Visualizza tutti i preventivi inviati con informazioni chiave come nome cliente, stato, valore totale e data di creazione.
    -   **Filtro e ricerca:** Strumenti per trovare preventivi specifici per cliente, stato, intervallo di date, ecc.
    -   **Visualizza/Modifica preventivo:** Clicca su qualsiasi preventivo per aprire una vista dettagliata dove puoi:
        -   **Regola prodotti e quantità:** Modifica gli articoli, le quantità e i prezzi all'interno del preventivo.
        -   **Aggiungi/Rimuovi prodotti:** Cerca e aggiungi nuovi prodotti al preventivo o rimuovi quelli esistenti.
        -   **Applica sconti:** Offri sconti specifici sul totale del preventivo o sui singoli articoli.
        -   **Imposta validità:** Definisci la data di scadenza del preventivo.
        -   **Aggiungi note/messaggi:** Comunica con il cliente direttamente tramite l'interfaccia del preventivo.
        -   **Cambia stato:** Aggiorna lo stato del preventivo (es. In sospeso, Inviato, Accettato, Rifiutato, Scaduto).
        -   **Genera PDF:** Crea una fattura proforma PDF professionale per il cliente.
        -   **Converti in ordine:** Con un solo clic, converti un preventivo accettato in un ordine PrestaShop standard, pronto per il checkout.
        -   **Invia email:** Invia dettagli del preventivo aggiornati o messaggi al cliente.
    -   **Azioni di massa:** Seleziona più preventivi per eseguire azioni come cambiare stato, eliminare o esportare.
-   **Effetto delle modifiche:**
    -   La modifica di un preventivo aggiorna i suoi dettagli nel database e può attivare notifiche email al cliente.
    -   La conversione in ordine crea un nuovo ordine nel sistema di gestione ordini standard di PrestaShop, precompilato con gli articoli e i prezzi quotati.
    -   La modifica dello stato aggiorna la vista del cliente nel suo account e può attivare modelli email specifici.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla regolarmente l'elenco "Preventivi" per nuove richieste "In sospeso".
    2.  Apri ogni nuova richiesta, rivedi gli articoli, regola prezzi/quantità se necessario e aggiungi eventuali note interne.
    3.  Imposta un periodo di validità e genera una proforma PDF.
    4.  Cambia lo stato in "Inviato" e invia il preventivo al cliente via email.
    5.  Dai seguito ai preventivi "Inviati". Se accettati, converti in ordine. Se rifiutati o scaduti, aggiorna lo stato di conseguenza.

#### 2.2.2 Registro di controllo (Back Office > Quote Enterprise > Registro di controllo)

Questa schermata fornisce una cronologia dettagliata di tutte le azioni eseguite sui preventivi.

-   **Nome schermata e posizione menu:** **Quote Enterprise > Registro di controllo**
-   **Azioni e impostazioni disponibili:**
    -   **Tabella elenco log:** Visualizza un elenco cronologico degli eventi relativi ai preventivi, inclusi chi ha eseguito l'azione, quale azione è stata intrapresa (es. "Preventivo creato", "Prezzo modificato", "Stato aggiornato") e quando è avvenuta.
    -   **Filtro:** Filtra il log per data, utente o tipo di azione per trovare eventi specifici.
-   **Effetto delle modifiche:** Questo è un log di sola lettura; non puoi apportare modifiche qui. Serve come registro storico.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Usa il registro di controllo per tracciare le modifiche, risolvere problemi o rivedere l'attività del team sui preventivi. È inestimabile per la responsabilità e per comprendere il ciclo di vita di ogni preventivo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita Quote Enterprise | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Consenti richieste di preventivo dal carrello | SÌ | Aggiunge il pulsante preventivo alla pagina del carrello. |
| | Consenti richieste di preventivo dalla pagina prodotto | SÌ | Aggiunge il pulsante preventivo alle pagine prodotto. |
| | Visualizza pulsante preventivo fluttuante | SÌ | Mostra un pulsante preventivo persistente nel front office. |
| | Valore minimo dell'ordine per la richiesta di preventivo | 0 | Imposta un valore minimo per l'invio dei preventivi. |
| | Validità predefinita del preventivo (Giorni) | 30 | Imposta la scadenza predefinita per i nuovi preventivi. |
| | Gestore modelli email | Personalizza | Modifica il contenuto delle email per vari eventi di preventivo. |
| | Abilita REST API | NO | Attiva l'API per integrazioni esterne (solo sviluppatori). |
| | Gestione chiavi API | N/A | Gestisci le chiavi API per un accesso sicuro all'API (solo sviluppatori). |
| | URL Cron Job per scadenza e riepilogo | Configura | Automatizza i controlli di scadenza dei preventivi e i riepiloghi del team. |
| **Gestione preventivi** | Elenco preventivi | N/A | Visualizza, filtra e gestisci tutti i preventivi. |
| | Visualizza/Modifica preventivo | N/A | Regola articoli, prezzi, stato, genera PDF, converti in ordine. |
| | Azioni di massa | N/A | Applica azioni a più preventivi selezionati. |
| **Registro di controllo** | Elenco log | N/A | Rivedi le azioni storiche su tutti i preventivi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei pulsanti "Richiedi un preventivo" non vengono visualizzati nel front office.**
R:

1.  **Controlla lo stato del modulo:** Assicurati che "Abilita Quote Enterprise" sia impostato su SÌ nella configurazione del modulo.
2.  **Controlla le impostazioni specifiche:** Verifica che "Consenti richieste di preventivo dal carrello" e "Consenti richieste di preventivo dalla pagina prodotto" siano abilitate secondo necessità.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache di PrestaShop (cache Smarty, cache del filesystem). A volte, le modifiche non appaiono finché la cache non viene aggiornata.
4.  **Compatibilità del tema:** Se stai utilizzando un tema personalizzato, potrebbe esserci un problema di compatibilità. Contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D: I clienti non ricevono le email di notifica del preventivo.**
R:

1.  **Controlla i modelli email:** Nella configurazione del modulo, vai alla scheda "Modelli email" e assicurati che i modelli siano configurati e salvati correttamente.
2.  **Impostazioni email di PrestaShop:** Verifica le tue impostazioni email generali di PrestaShop (SMTP, PHP mail) in **Parametri avanzati > E-mail**. Invia un'email di prova da lì per confermare che il sistema di posta del tuo negozio funzioni.
3.  **Cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
4.  **Cron Job (per riepiloghi/promemoria):** Se si tratta di promemoria di scadenza o riepiloghi giornalieri, assicurati che l'URL del cron job sia configurato correttamente sul tuo server per essere eseguito regolarmente.

**D: Posso personalizzare l'aspetto del modulo di richiesta preventivo o dei pulsanti?**
R: Sì, il modulo utilizza la templating standard di PrestaShop. Per modifiche di stile di base (colori, font), puoi spesso sovrascrivere il CSS del modulo nel file CSS personalizzato del tuo tema. Per modifiche di layout più complesse, dovresti sovrascrivere i file TPL del modulo nel tuo tema. Questo di solito richiede uno sviluppatore web.

**D: Come converto un preventivo accettato in un ordine regolare?**
R: Nel Back Office di PrestaShop, vai su **Quote Enterprise > Preventivi**. Apri il preventivo specifico che desideri convertire. All'interno della vista dettagliata del preventivo, ci sarà un pulsante (es. "Converti in ordine" o "Crea ordine"). Cliccando su questo verrà generato un nuovo ordine nell'elenco ordini standard di PrestaShop, precompilato con gli articoli e i prezzi quotati.

**D: Cosa succede se un preventivo scade?**
R: Se il cron job è configurato, il modulo contrassegnerà automaticamente i preventivi scaduti come "Scaduti". I clienti non potranno più accettare o convertire un preventivo scaduto in un ordine. Il tuo team di vendita può comunque visualizzare i preventivi scaduti e potenzialmente riattivarli o crearne uno nuovo se necessario.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Quote Enterprise segue una robusta architettura MVC (Model-View-Controller) di PrestaShop, sfruttando pesantemente `ObjectModel` per la persistenza dei dati. Si integra perfettamente con il sistema di hook di PrestaShop per la visualizzazione nel front-office e le azioni nel back-office. Il modulo include controller admin dedicati per la gestione dei preventivi e dei registri di controllo, controller front per l'interazione con i clienti (richiesta, elenco, visualizzazione, API) e un set completo di classi helper per la logica di business, la generazione di PDF, la gestione delle email e altro ancora. Viene fornita anche un'API REST per l'integrazione di sistemi esterni.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/api.php`
    -   Nome classe: `QuoteenterpriseApiModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Gestisce le richieste API dal front-office, probabilmente per integrazioni specifiche rivolte al cliente o caricamento dinamico di contenuti.
-   `controllers/front/cron.php`
    -   Nome classe: `QuoteenterpriseCronModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Serve come endpoint per il cron job, attivando attività in background come il controllo delle scadenze dei preventivi e l'invio di email di riepilogo.
-   `controllers/front/index.php`
    -   Nome classe: `QuoteenterpriseIndexModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Probabilmente un controller di fallback o di base, o gestisce una rotta predefinita per la sezione front-office del modulo.
-   `controllers/front/list.php`
    -   Nome classe: `QuoteenterpriseListModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Visualizza un elenco di preventivi per il cliente loggato nella sua area account.
-   `controllers/front/pdf.php`
    -   Nome classe: `QuoteenterprisePdfModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Genera e serve versioni PDF dei preventivi per il download da parte dei clienti.
-   `controllers/front/quoteList.php`
    -   Nome classe: `QuoteenterpriseQuoteListModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Simile a `list.php`, potenzialmente una vista alternativa o specifica per gli elenchi di preventivi, possibilmente per il caricamento AJAX.
-   `controllers/front/request.php`
    -   Nome classe: `QuoteenterpriseRequestModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Gestisce la visualizzazione e l'invio del modulo di richiesta preventivo dalle pagine prodotto, dal carrello o dal pulsante fluttuante. Elabora i dati del modulo e crea nuove voci di preventivo.
-   `controllers/front/view.php`
    -   Nome classe: `QuoteenterpriseViewModuleFrontController` (estende `ModuleFrontController`)
    -   Responsabilità: Visualizza la vista dettagliata di un singolo preventivo per il cliente, mostrando articoli, prezzi, stato e messaggi.

#### Controller Admin Back-Office

-   `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
    -   Nome classe: `AdminQuoteEnterpriseAuditLogController` (estende `ModuleAdminController`)
    -   Nome scheda: Quote Enterprise > Registro di controllo
    -   Entità gestita: `quote_audit_log` (probabilmente un `ObjectModel` personalizzato per le voci di controllo)
    -   Responsabilità: Fornisce una vista a griglia per gli amministratori per rivedere tutte le azioni e le modifiche storiche relative ai preventivi.
-   `controllers/admin/AdminQuoteEnterpriseQuotes.php`
    -   Nome classe: `AdminQuoteEnterpriseQuotesController` (estende `ModuleAdminController`)
    -   Nome scheda: Quote Enterprise > Preventivi
    -   Entità gestita: `quote` (probabilmente un `ObjectModel` personalizzato per i preventivi)
    -   Responsabilità: L'interfaccia principale per la gestione dei preventivi, inclusi elenco, visualizzazione, modifica, conversione in ordine e invio di comunicazioni.
-   `controllers/admin/index.php`
    -   Nome classe: `QuoteenterpriseAdminIndexModuleFrontController` (estende `ModuleAdminController`)
    -   Responsabilità: Probabilmente un segnaposto o un controller admin di base, potenzialmente reindirizzando all'elenco principale dei preventivi o alla dashboard.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/index.php`: File vuoto, pratica comune per prevenire l'elenco delle directory.
-   `classes/QuoteAdmin.php`: Contiene la logica per le attività specifiche dell'amministratore, potenzialmente correlate alla configurazione del modulo o alle utilità generali dell'amministratore.
-   `classes/QuoteAdminAjax.php`: Gestisce le richieste AJAX provenienti dal back-office, come la ricerca dinamica di prodotti da aggiungere a un preventivo.
-   `classes/QuoteAdminQuoteForm.php`: Gestisce la complessa logica del modulo per la modifica e la creazione di preventivi nel back-office.
-   `classes/QuoteApi.php`: Classe principale per l'API REST del modulo, che gestisce l'autenticazione, il routing e la serializzazione dei dati.
-   `classes/QuoteApiDocumentation.php`: Fornisce metodi per generare o visualizzare la documentazione per gli endpoint API del modulo.
-   `classes/QuoteBulkActions.php`: Implementa la logica per l'esecuzione di azioni su più preventivi selezionati nell'elenco admin (es. cambio di stato di massa).
-   `classes/QuoteConverter.php`: Gestisce la logica cruciale di conversione di un preventivo accettato in un ordine PrestaShop standard.
-   `classes/QuoteDashboard.php`: Fornisce dati e logica per la vista dashboard del modulo nel back-office (se presente), riassumendo l'attività dei preventivi.
-   `classes/QuoteDuplicator.php`: Logica per la duplicazione di preventivi esistenti.
-   `classes/QuoteenterpriseModuleFrontController.php`: Classe base per i controller front-office, che fornisce metodi e proprietà comuni.
-   `classes/QuoteExpiry.php`: Gestisce la logica per il controllo della validità dei preventivi, la marcatura dei preventivi come scaduti e l'invio delle notifiche correlate.
-   `classes/QuoteExporter.php`: Gestisce l'esportazione dei dati dei preventivi (es. CSV, Excel).
-   `classes/QuoteFeeProduct.php`: Probabilmente un `ObjectModel` o un helper per la gestione di speciali prodotti "a pagamento" che possono essere aggiunti ai preventivi (es. per servizi, costi personalizzati).
-   `classes/QuoteListHelper.php`: Fornisce metodi di utilità per la visualizzazione e il filtraggio degli elenchi di preventivi sia nel front che nel back office.
-   `classes/QuoteMailer.php`: Classe centralizzata per l'invio di varie notifiche email relative ai preventivi.
-   `classes/QuoteNotifyDigest.php`: Logica per la compilazione e l'invio di riepiloghi giornalieri o periodici dell'attività dei preventivi agli amministratori.
-   `classes/QuotePdf.php`: Gestisce la generazione di fatture proforma PDF per i preventivi.
-   `classes/QuoteProductHelper.php`: Metodi di utilità per interagire con i prodotti PrestaShop nel contesto di un preventivo.
-   `classes/QuoteQtyHelper.php`: Aiuta con la gestione e la convalida delle quantità all'interno dei preventivi.
-   `classes/QuoteQuotesManager.php`: Logica di business principale per la gestione dei preventivi, inclusa la creazione, gli aggiornamenti e le modifiche di stato.
-   `classes/QuoteReference.php`: Gestisce la generazione e l'unicità dei numeri di riferimento dei preventivi.
-   `classes/QuoteRequestHelper.php`: Aiuta con l'elaborazione e la convalida delle richieste di preventivo inviate dai clienti.
-   `classes/QuoteSchema.php`: Definisce lo schema del database per le tabelle personalizzate utilizzate dal modulo (es. `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
-   `classes/QuoteSettingDescTrait.php`: Un trait PHP probabilmente utilizzato per fornire descrizioni o metadati comuni per le impostazioni del modulo.
-   `classes/QuoteTaxHelper.php`: Gestisce i calcoli fiscali specifici per i preventivi.
-   `classes/QuoteThemeCompat.php`: Contiene la logica per garantire la compatibilità con vari temi PrestaShop, potenzialmente rilevando le funzionalità del tema o fornendo override.
-   `classes/QuoteTimeline.php`: Gestisce e visualizza la cronologia degli eventi per un preventivo specifico (simile alla cronologia degli ordini).
-   `classes/QuoteValidityHelper.php`: Metodi di utilità per il calcolo e la convalida delle date di scadenza dei preventivi.
-   `classes/QuoteVisibility.php`: Controlla la visibilità degli elementi relativi ai preventivi nel front office (es. chi può richiedere un preventivo, dove appaiono i pulsanti).

### 4.4 Risorse JavaScript (`views/js/`)

-   `lib/emailTemplatesManager/js/emailTemplatesManager.js`: Logica front-end per l'editor di modelli email nel back-office.
-   `lib/searchTool/views/js/autocomplete.js`: Fornisce la funzionalità di completamento automatico per la ricerca di prodotti o clienti nell'editor di preventivi del back-office.
-   `views/js/admin-audience-picker.js`: Gestisce la logica per la selezione di gruppi di clienti o clienti specifici per la visibilità o il targeting dei preventivi nell'amministrazione.
-   `views/js/adminQuoteApi.js`: JavaScript per la schermata di configurazione dell'API admin, potenzialmente gestendo la generazione di chiavi o la visualizzazione della documentazione API.
-   `views/js/adminQuoteDashboard.js`: Script per elementi interattivi o visualizzazione dei dati nella dashboard admin.
-   `views/js/adminQuoteDetail.js`: Gestisce le interazioni dinamiche all'interno della vista dettagliata del preventivo nel back-office (es. aggiunta di prodotti, applicazione di sconti, modifiche di stato).
-   `views/js/adminQuoteEditor.js`: JavaScript principale per il modulo di creazione/modifica preventivi del back-office, inclusa la selezione dei prodotti, gli aggiornamenti delle quantità e le regolazioni dei prezzi.
-   `views/js/adminQuoteSelector.js`: Utilizzato per la selezione dei preventivi, possibilmente in una modale o in un contesto collegato.
-   `views/js/adminQuotesList.js`: Script per l'elenco dei preventivi admin, inclusi filtro, ordinamento e azioni di massa.
-   `views/js/front.js`: JavaScript generale del front-office per il modulo, che gestisce i clic sui pulsanti, i pop-up modali per le richieste di preventivo, l'invio di moduli e gli aggiornamenti dinamici.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `lib/emailTemplatesManager/css/emailTemplatesManager.css`: Stile per l'editor di modelli email nel back-office.
-   `lib/searchTool/views/css/autocomplete.css`: Stili per i risultati della ricerca con completamento automatico (es. ricerca prodotti).
-   `views/css/admin-audience-picker.css`: Stile per l'interfaccia di selezione cliente/pubblico nell'amministrazione.
-   `views/css/admin_quoteenterprise.css`: Foglio di stile principale per le interfacce del back-office del modulo (elenco preventivi, dettagli, registro di controllo).
-   `views/css/front-hummingbird.css`: Regolazioni di stile specifiche del front-office per il tema predefinito "Hummingbird" di PrestaShop.
-   `views/css/front.css`: Stile generale del front-office per pulsanti di preventivo, moduli e viste dell'account cliente. Gli sviluppatori possono sovrascrivere classi come `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` nel loro tema.

### 4.6 Struttura dei template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

-   `hook/adminOrderQuote.tpl`: Renderizza un blocco relativo al preventivo all'interno della pagina di dettaglio dell'ordine standard di PrestaShop nell'amministrazione.
-   `hook/cartQuoteButton.tpl`: Visualizza il pulsante o il link "Richiedi un preventivo" nella pagina del carrello.
-   `hook/customerAccount-hummingbird.tpl`: Renderizza il link all'elenco dei preventivi nell'area account del cliente per il tema Hummingbird.
-   `hook/customerAccount.tpl`: Renderizza il link all'elenco dei preventivi nell'area account del cliente per i temi classici.
-   `hook/productListQuote.tpl`: Visualizza un pulsante o un'opzione di preventivo nelle pagine di elenco prodotti (categoria, risultati di ricerca).
-   `hook/quoteFloatButton.tpl`: Renderizza il pulsante di preventivo fluttuante persistente nel front office.
-   `hook/quoteListModal.tpl`: Template per una finestra modale che visualizza un elenco di preventivi.
-   `hook/quoteRequestButton.tpl`: Visualizza il pulsante "Richiedi un preventivo" sulle singole pagine prodotto.
-   `hook/quoteRequestModal.tpl`: Template per la finestra modale che apre il modulo di richiesta preventivo.

#### Template admin (`views/templates/admin/`)

-   `admin/api.tpl`: Renderizza l'interfaccia di configurazione API e gestione chiavi.
-   `admin/audience-picker.tpl`: Template per lo strumento di selezione cliente/gruppo nell'amministrazione.
-   `admin/audit.tpl`: Visualizza la tabella del registro di controllo nel back-office.
-   `admin/dashboard.tpl`: Renderizza la panoramica della dashboard del modulo nel back-office.
-   `admin/notifications.tpl`: Visualizza le notifiche admin relative ai preventivi.
-   `admin/quoteDetail.tpl`: Il template completo per la visualizzazione e la modifica di un singolo preventivo nel back-office.
-   `admin/quotes.tpl`: Renderizza la tabella principale dell'elenco dei preventivi nel back-office.
-   `admin/quotesOverview.tpl`: Una sezione di riepilogo o panoramica per i preventivi, possibilmente sulla dashboard.
-   `admin/scopeSelector.tpl`: Template per la selezione dell'ambito (es. negozio, lingua) nell'amministrazione.
-   `admin/visibilityConfigurator.tpl`: Template per la configurazione delle regole di visibilità dei preventivi.
-   `admin/_api_documentation_modal.tpl`: Renderizza una finestra modale con la documentazione API per gli sviluppatori.
-   `admin/_bulk_options.tpl`: Template per i menu a discesa delle azioni di massa negli elenchi admin.

#### Template front-office (`views/templates/front/`)

-   `front/list.tpl`: Visualizza l'elenco dei preventivi del cliente nel suo account.
-   `front/request.tpl`: Il template principale per il modulo di richiesta preventivo del cliente.
-   `front/view.tpl`: Visualizza la vista dettagliata di un singolo preventivo per il cliente.
-   `front/_requestComplianceFields.tpl`: Template parziale per campi aggiuntivi relativi alla conformità nel modulo di richiesta preventivo.
-   `front/_requestLinesTable.tpl`: Template parziale per la visualizzazione delle righe di prodotto all'interno di un modulo di richiesta preventivo.

#### Template PDF (`views/templates/pdf/`)

-   `pdf/quote.tpl`: Template utilizzato per generare il contenuto della fattura proforma PDF.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo crea tabelle personalizzate, tipicamente prefissate con `ps_` (o il tuo prefisso personalizzato). Le tabelle chiave includono:

-   `ps_quote`: Memorizza i dettagli principali del preventivo (ID cliente, stato, totale, validità, riferimento, ecc.).
-   `ps_quote_product`: Memorizza i singoli prodotti e le loro quantità/prezzi associati a ciascun preventivo.
-   `ps_quote_audit_log`: Registra tutte le modifiche e le azioni eseguite sui preventivi a scopo di controllo.
-   `ps_quote_api_key`: Memorizza le chiavi API per le integrazioni esterne.
-   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE`, ecc.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Iniezione di risorse CSS/JS, meta tag o inizializzazione globale del modulo. |
| `displayRightColumn` | Nella colonna destra del tuo negozio (se abilitata dal tema). | Visualizzazione del pulsante di preventivo fluttuante o di un blocco di richiesta preventivo statico. |
| `displayLeftColumn` | Nella colonna sinistra del tuo negozio (se abilitata dal tema). | Visualizzazione del pulsante di preventivo fluttuante o di un blocco di richiesta preventivo statico. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Visualizzazione del pulsante di preventivo fluttuante o di un blocco di richiesta preventivo statico. |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "Aggiungi al carrello". | Visualizzazione del pulsante "Richiedi un preventivo" nelle pagine prodotto. |
| `displayShoppingCartFooter` | Nel riepilogo del carrello, sotto l'elenco dei prodotti. | Visualizzazione del pulsante "Richiedi un preventivo" per convertire il carrello in preventivo. |
| `displayCustomerAccount` | Nella pagina "Il mio account" del cliente. | Aggiunta di un link all'elenco dei preventivi del cliente. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potenzialmente utilizzato per collegare un preventivo all'ordine risultante o aggiornare lo stato del preventivo. |
| `actionAdminControllerSetMedia` | Quando un controller admin carica le sue risorse. | Iniezione di CSS/JS specifici del modulo per le pagine del back-office. |
| `displayAdminOrder` | Nella pagina di dettaglio dell'ordine admin di PrestaShop. | Visualizzazione di un blocco con informazioni sul preventivo se l'ordine è originato da un preventivo. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto. | Potenzialmente per aggiornare i prezzi dei preventivi se i prezzi dei prodotti cambiano (funzionalità avanzata). |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Per gestire i prodotti rimossi dai preventivi. |
| `actionObjectCustomerDeleteAfter` | Dopo l'eliminazione di un cliente. | Per gestire i preventivi associati a un cliente eliminato. |
| `displayBackOfficeHeader` | Nella `<head>` di ogni pagina del back-office. | Iniezione generale di risorse del back-office o configurazione globale del modulo admin. |
| `displayBackOfficeTop` | Nella parte superiore dell'area del contenuto del back-office. | Visualizzazione di avvisi specifici del modulo o widget della dashboard. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo al modulo Quote Enterprise.
