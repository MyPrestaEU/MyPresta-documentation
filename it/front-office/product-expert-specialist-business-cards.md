---
title: "Esperto di prodotto - Biglietti da visita specialistici - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Esperto di prodotto - Biglietti da visita specialistici' di MyPresta.eu."
sidebar:
  label: "Esperto di prodotto - Biglietti da visita specialistici - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product expert - Specialist Business Cards su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-expert-specialist-business-cards/)
>
> ---


# Esperto di prodotto - Biglietti da visita specialistici

## 1. Requisiti e compatibilità

Per garantire il buon funzionamento del modulo "Esperto di prodotto - Biglietti da visita specialistici", si prega di rivedere i seguenti requisiti:

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard come cURL, JSON e OpenSSL, e sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Esperto di prodotto - Biglietti da visita specialistici" offre ampie opzioni di configurazione su diverse schermate nel tuo Back Office di PrestaShop.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Configura Esperto di prodotto - Biglietti da visita specialistici)

Questa è la schermata di configurazione principale per le impostazioni generali del modulo, accessibile direttamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

-   **Abilita/Disabilita Modulo:**
    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per la funzionalità del modulo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Le funzionalità del modulo (biglietti da visita degli esperti, assegnazioni) saranno attive sul tuo front office.
        *   *Quando disabilitato:* Tutte le funzionalità del modulo saranno nascoste dal front office e i biglietti da visita degli esperti non appariranno.
    *   **Valore consigliato:** SÌ (a meno che non lo si stia temporaneamente disabilitando per manutenzione).
    *   **Scenario/esempio del commerciante:** Potresti disabilitarlo se stai eseguendo un aggiornamento importante del tema e vuoi assicurarti che non ci siano conflitti, quindi riabilitarlo una volta completato il test.
-   **Visualizza esperti sulla pagina del prodotto:**
    *   **Cosa fa questa impostazione:** Controlla se i biglietti da visita degli esperti vengono mostrati sulle singole pagine dei prodotti.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Gli esperti assegnati a prodotti, categorie, marchi o fornitori appariranno sulle pagine dei prodotti pertinenti.
        *   *Quando disabilitato:* Gli esperti non verranno visualizzati sulle pagine dei prodotti, indipendentemente dalle loro assegnazioni.
    *   **Valore consigliato:** SÌ (questa è una funzionalità fondamentale del modulo).
    *   **Scenario/esempio del commerciante:** Se desideri utilizzare gli esperti solo per richieste B2B su una pagina dedicata e non direttamente nelle schede dei prodotti, potresti disabilitare questa opzione.
-   **Visualizza esperti nell'hook:**
    *   **Cosa fa questa impostazione:** Ti consente di selezionare un hook PrestaShop specifico in cui verranno visualizzati i biglietti da visita degli esperti. Gli hook comuni includono `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
    *   **Effetto della modifica di questa impostazione:** I biglietti da visita degli esperti verranno renderizzati nella posizione scelta sulle pagine dei prodotti o su altre pagine in cui l'hook è attivo.
    *   **Valore consigliato:** `displayProductExtraContent` o `displayProductButtons` sono spesso buone scelte per le pagine dei prodotti, in quanto sono solitamente prominenti. Sperimenta per trovare la soluzione migliore per il tuo tema.
    *   **Scenario/esempio del commerciante:** Se il tuo tema ha una scheda o una sezione dedicata ai "contenuti extra", `displayProductExtraContent` potrebbe essere l'ideale. Se desideri gli esperti vicino al pulsante "Aggiungi al carrello", `displayProductButtons` potrebbe funzionare.
-   **Abilita modulo di contatto:**
    *   **Cosa fa questa impostazione:** Determina se è disponibile un modulo di contatto per i clienti per inviare messaggi direttamente agli esperti.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un pulsante o un link "Contatta esperto" apparirà sul biglietto da visita dell'esperto, aprendo un modulo per i clienti per inviare un messaggio.
        *   *Quando disabilitato:* L'opzione del modulo di contatto verrà rimossa dai biglietti da visita degli esperti.
    *   **Valore consigliato:** SÌ (altamente raccomandato per il coinvolgimento dei clienti).
    *   **Scenario/esempio del commerciante:** L'abilitazione di questa opzione consente ai clienti di porre domande specifiche su un prodotto direttamente all'esperto, portando a acquisti più informati.
-   **Conformità GDPR per il modulo di contatto:**
    *   **Cosa fa questa impostazione:** Se il modulo di contatto è abilitato, questa impostazione aggiunge una casella di controllo per i clienti per acconsentire al trattamento dei dati, fondamentale per la conformità al GDPR.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Una casella di controllo obbligatoria apparirà sul modulo di contatto, richiedendo il consenso del cliente prima di inviare un messaggio.
        *   *Quando disabilitato:* Non verrà mostrata alcuna casella di controllo per il consenso al GDPR.
    *   **Valore consigliato:** SÌ (essenziale per la conformità legale in molte regioni).
    *   **Scenario/esempio del commerciante:** Abilita sempre questa opzione se il tuo pubblico di destinazione si trova nell'UE o in qualsiasi regione con leggi sulla protezione dei dati simili.
-   **Layout predefinito del biglietto da visita dell'esperto:**
    *   **Cosa fa questa impostazione:** Ti consente di selezionare un layout predefinito o personalizzato per la visualizzazione dei singoli biglietti da visita degli esperti. Ciò include opzioni per il posizionamento della foto, l'allineamento del testo e il design generale del biglietto.
    *   **Effetto della modifica di questa impostazione:** Modifica l'aspetto visivo di tutti i biglietti da visita degli esperti nel tuo negozio, a meno che non sia sovrascritto dalle impostazioni di un esperto specifico.
    *   **Valore consigliato:** Scegli un layout che si adatti meglio all'estetica del tuo negozio. Puoi visualizzare in anteprima diverse opzioni.
    *   **Scenario/esempio del commerciante:** Potresti scegliere un layout "Moderno" per un negozio elegante e minimalista, o un layout "Classico" per un'atmosfera più tradizionale.
-   **Layout predefinito dell'elenco esperti:**
    *   **Cosa fa questa impostazione:** Determina come vengono disposti più biglietti da visita degli esperti quando ne viene visualizzato più di uno (ad esempio, in una griglia, elenco o carosello).
    *   **Effetto della modifica di questa impostazione:** Controlla la presentazione generale di più esperti su una pagina.
    *   **Valore consigliato:** "Griglia" per una visualizzazione compatta, "Carosello" per un risparmio di spazio e una navigazione interattiva, o "Elenco" per una visualizzazione più dettagliata e impilata.
    *   **Scenario/esempio del commerciante:** Se hai molti esperti per una categoria, un "Carosello" può far risparmiare spazio. Se ne hai solo uno o due, una "Griglia" potrebbe apparire più pulita.
-   **Mostra strumento di ricerca esperti:**
    *   **Cosa fa questa impostazione:** Abilita una barra di ricerca che consente ai clienti di trovare esperti per nome o specialità.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Apparirà un campo di input di ricerca, solitamente vicino ai biglietti da visita degli esperti, consentendo ai clienti di filtrare gli esperti.
        *   *Quando disabilitato:* Lo strumento di ricerca esperti non sarà visibile.
    *   **Valore consigliato:** SÌ (migliora l'usabilità, specialmente con molti esperti).
    *   **Scenario/esempio del commerciante:** Se hai un grande team di specialisti, abilitare lo strumento di ricerca aiuta i clienti a trovare rapidamente la persona giusta.
-   **Hook strumento di ricerca esperti:**
    *   **Cosa fa questa impostazione:** Specifica dove verrà visualizzato lo strumento di ricerca esperti nel tuo front office.
    *   **Effetto della modifica di questa impostazione:** La barra di ricerca apparirà nella posizione dell'hook scelta.
    *   **Valore consigliato:** `displayTop` o `displayNav` per visibilità globale, o `displayLeftColumn`/`displayRightColumn` se lo desideri insieme ad altri filtri.
    *   **Scenario/esempio del commerciante:** Posizionarlo in `displayTop` lo rende facilmente accessibile da qualsiasi pagina, simile a una ricerca di prodotti.

### 2.2 Schermata di amministrazione dedicata: Esperti (Back Office > Esperto di prodotto > Esperti)

Questa schermata è dove gestisci i profili dei singoli esperti, crei nuovi esperti e modifichi quelli esistenti.

-   **Nome schermata e posizione menu:** **Esperto di prodotto > Esperti**
-   **Azioni e impostazioni disponibili:**
    *   **Elenco esperti (Vista a griglia):** Visualizza una tabella di tutti gli esperti creati. Puoi vedere il loro nome, ruolo, stato (attivo/inattivo) e azioni come "Modifica" o "Elimina".
    *   **Pulsante "Aggiungi nuovo esperto":** Cliccando su questo pulsante si accede a un modulo per creare un nuovo profilo esperto.
    *   **Azioni Modifica/Elimina:** Per ogni esperto nell'elenco, puoi cliccare su "Modifica" per modificare i loro dettagli o su "Elimina" per rimuoverli.
    *   **Azioni di massa:** Consente di selezionare più esperti ed eseguire azioni come "Abilita", "Disabilita" o "Elimina" contemporaneamente.
-   **Modulo di creazione/modifica esperto:**
    *   **Nome:** Il nome completo del tuo esperto.
    *   **Ruolo/Titolo:** Il loro titolo professionale o ruolo (ad esempio, "Responsabile vendite senior", "Specialista supporto tecnico", "Consulente di moda").
    *   **Breve biografia:** Una breve descrizione della loro esperienza o background. Questo aiuta i clienti a comprendere le loro qualifiche.
    *   **Foto:** Carica una foto professionale dell'esperto. Questo è cruciale per costruire fiducia e connessione personale.
    *   **Link di contatto:**
        *   **Email:** Indirizzo email dell'esperto.
        *   **Telefono:** Numero di telefono dell'esperto.
        *   **WhatsApp:** Numero WhatsApp (genererà un link di chat diretto).
        *   **LinkedIn:** Link al loro profilo LinkedIn.
        *   **Altri link personalizzati:** Puoi aggiungere altri link personalizzati con icone (ad esempio, un link al loro blog personale, un portfolio prodotti specifico).
    *   **Attivo:** Un interruttore per abilitare o disabilitare l'esperto.
        *   *Quando abilitato:* L'esperto sarà disponibile per l'assegnazione e la visualizzazione.
        *   *Quando disabilitato:* L'esperto non apparirà nel front office, anche se assegnato.
    *   **Sovrascrittura layout biglietto da visita esperto:** Consente di selezionare un layout di biglietto specifico per *questo singolo esperto*, sovrascrivendo il valore predefinito globale impostato nella configurazione del modulo. Questo è utile per evidenziare determinati esperti o per abbinare il loro marchio personale.
    *   **Assegnazioni (Prodotti, Categorie, Marche, Fornitori):** Qui si collegano gli esperti a specifiche entità del negozio.
        *   **Prodotti:** Cerca e seleziona i singoli prodotti a cui è associato questo esperto.
        *   **Categorie:** Seleziona le categorie in cui il biglietto da visita di questo esperto dovrebbe apparire sui prodotti all'interno di tali categorie.
        *   **Marche:** Seleziona le marche specifiche in cui questo esperto è specializzato.
        *   **Fornitori:** Seleziona i fornitori i cui prodotti questo esperto può consigliare.
        *   *Effetto delle modifiche:* Quando un cliente visualizza un prodotto che corrisponde a una di queste assegnazioni, verrà visualizzato il biglietto da visita dell'esperto. Se sono assegnati più esperti, tutti gli esperti pertinenti verranno mostrati in base al layout dell'elenco.
-   **Effetto delle modifiche:**
    *   L'aggiunta di un nuovo esperto lo rende disponibile per l'assegnazione a prodotti, categorie, ecc.
    *   La modifica di un esperto aggiorna le informazioni visualizzate e i dettagli di contatto in tutto il negozio.
    *   L'eliminazione di un esperto lo rimuove e le sue assegnazioni dal tuo negozio.
    *   La modifica delle assegnazioni influisce immediatamente su quali biglietti da visita degli esperti appaiono su quali pagine dei prodotti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Crea nuovi esperti:** Quando un nuovo membro del team si unisce o è necessaria una nuova specializzazione, crea il loro profilo qui.
    2.  **Assegna esperti:** Rivedi regolarmente il tuo catalogo prodotti e assegna esperti pertinenti a nuovi prodotti, categorie o marchi.
    3.  **Aggiorna profili:** Mantieni aggiornate le foto, le biografie e i dettagli di contatto degli esperti.
    4.  **Disattiva/Riattiva:** Usa l'interruttore "Attivo" per nascondere temporaneamente un esperto (ad esempio, se è in congedo) senza eliminare il suo profilo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita/Disabilita Modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Visualizza esperti sulla pagina del prodotto | SÌ | Mostra i biglietti da visita degli esperti sulle pagine dei prodotti. |
| | Visualizza esperti nell'hook | `displayProductExtraContent` | Scegli dove appaiono i biglietti da visita degli esperti sulle pagine dei prodotti. |
| | Abilita modulo di contatto | SÌ | Consenti ai clienti di inviare messaggi direttamente agli esperti. |
| | Conformità GDPR per il modulo di contatto | SÌ | Aggiungi la casella di controllo del consenso al modulo di contatto. |
| | Layout predefinito del biglietto da visita dell'esperto | (Scegli in base al tema) | Stile visivo dei singoli biglietti da visita degli esperti. |
| | Layout predefinito dell'elenco esperti | Griglia / Carosello | Come sono disposti più biglietti da visita degli esperti. |
| | Mostra strumento di ricerca esperti | SÌ | Abilita una barra di ricerca per gli esperti. |
| | Hook strumento di ricerca esperti | `displayTop` / `displayNav` | Dove appare lo strumento di ricerca esperti. |
| **Esperto di prodotto > Esperti** | Aggiungi nuovo esperto | N/A | Crea nuovi profili esperti. |
| | Modifica esperto | N/A | Modifica i dettagli dell'esperto (nome, ruolo, biografia, foto, contatti). |
| | Attivo (Stato esperto) | SÌ | Abilita/disabilita la visibilità del singolo esperto. |
| | Sovrascrittura layout biglietto da visita esperto | N/A | Sovrascrivi il layout globale del biglietto per un esperto specifico. |
| | Assegna a prodotti | N/A | Collega l'esperto a prodotti specifici. |
| | Assegna a categorie | N/A | Collega l'esperto a prodotti all'interno di categorie specifiche. |
| | Assegna a marche | N/A | Collega l'esperto a prodotti di marche specifiche. |
| | Assegna a fornitori | N/A | Collega l'esperto a prodotti di fornitori specifici. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

Ecco alcune domande comuni e suggerimenti per la risoluzione dei problemi per i proprietari di negozi che utilizzano il modulo "Esperto di prodotto - Biglietti da visita specialistici":

**D1: I miei biglietti da visita degli esperti non vengono visualizzati sulla pagina del prodotto.**

-   **R:** Per prima cosa, controlla se il modulo è **abilitato** in **Moduli > Gestione moduli**.
-   **R:** Successivamente, vai alla pagina di configurazione del modulo e assicurati che "Visualizza esperti sulla pagina del prodotto" sia impostato su **SÌ**.
-   **R:** Verifica di aver effettivamente **assegnato** un esperto al prodotto specifico, alla sua categoria, marca o fornitore in **Esperto di prodotto > Esperti > [Modifica esperto] > Assegnazioni**.
-   **R:** Controlla l'interruttore "Attivo" per il singolo esperto in **Esperto di prodotto > Esperti**. Se sono inattivi, non verranno visualizzati.
-   **R:** Svuota la cache di PrestaShop: vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" in alto a destra. A volte, i vecchi contenuti memorizzati nella cache impediscono la visualizzazione di nuovi elementi del modulo.

**D2: I biglietti da visita degli esperti hanno un aspetto strano o non corrispondono al design del mio tema.**

-   **R:** Il modulo fornisce un "Layout predefinito del biglietto da visita dell'esperto" e un "Layout predefinito dell'elenco esperti" nella sua configurazione. Sperimenta diverse opzioni per vedere quale si integra meglio con il tuo tema.
-   **R:** Se hai un tema personalizzato, potrebbe avere CSS specifici che entrano in conflitto con lo stile del modulo. Potrebbe essere necessario un web developer per ispezionare il CSS e apportare piccole modifiche.
-   **R:** Assicurati che il tuo tema sia aggiornato. I temi obsoleti a volte possono causare problemi di visualizzazione con i moduli più recenti.

**D3: Il modulo di contatto non invia email.**

-   **R:** Per prima cosa, assicurati che "Abilita modulo di contatto" sia impostato su **SÌ** nella configurazione del modulo.
-   **R:** Verifica che l'indirizzo email dell'esperto sia inserito correttamente nel suo profilo (**Esperto di prodotto > Esperti > [Modifica esperto]**).
-   **R:** Controlla le impostazioni email di PrestaShop (**Parametri avanzati > E-mail**). Invia un'email di prova da PrestaShop per assicurarti che la configurazione email del tuo negozio funzioni correttamente. Se PrestaShop non può inviare email, nemmeno il modulo può farlo.
-   **R:** Controlla i log di posta del tuo server per eventuali errori. Questo potrebbe richiedere l'assistenza del tuo provider di hosting.

**D4: Come posso tradurre il testo del modulo in altre lingue?**

-   **R:** Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   **R:** Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona il modulo "Esperto di prodotto - Biglietti da visita specialistici".
-   **R:** Puoi quindi tradurre tutte le stringhe del modulo nelle lingue desiderate. Ricorda di salvare le modifiche.

**D5: Voglio visualizzare gli esperti in una posizione diversa dagli hook disponibili.**

-   **R:** Il modulo fornisce una selezione di hook PrestaShop standard. Se hai bisogno di visualizzare gli esperti in una posizione molto specifica e non standard (ad esempio, all'interno di una scheda personalizzata o di una sezione unica del template della tua pagina prodotto), ciò richiederà uno sviluppo del tema personalizzato. Un web developer dovrebbe richiamare manualmente la funzione hook del modulo direttamente nei file `.tpl` del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica e della codebase del modulo "Esperto di prodotto - Biglietti da visita specialistici", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Esperto di prodotto - Biglietti da visita specialistici" segue un modello MVC (Model-View-Controller) standard di PrestaShop, sfruttando pesantemente `ObjectModel` per la persistenza dei dati. Introduce controller amministrativi personalizzati per la gestione degli esperti e delle loro assegnazioni, e controller front-end per le interazioni AJAX e la visualizzazione delle informazioni degli esperti. Il modulo utilizza una robusta struttura di classi per la gestione dei layout, degli stili e della logica di presentazione dei biglietti da visita degli esperti, consentendo un'elevata personalizzazione. Si integra con vari hook di PrestaShop per iniettare dinamicamente il suo contenuto nel front office.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    *   **Nome classe:** `ProductexpertAjaxModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Gestisce le richieste AJAX dal front office. Questo include tipicamente l'elaborazione delle sottomissioni del modulo di contatto dell'esperto, il caricamento dinamico dei dati dell'esperto o qualsiasi altro elemento interattivo che richiede la comunicazione lato server senza un ricaricamento completo della pagina. Restituisce risposte JSON.
-   `controllers/front/index.php`
    *   **Nome classe:** `ProductexpertIndexModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Un controller front-end segnaposto o predefinito. In molti moduli, questo potrebbe gestire una pagina di modulo dedicata se ne esiste una, o semplicemente reindirizzare se la sua funzione principale è tramite hook o AJAX. Per questo modulo, il suo ruolo principale è probabilmente minimo, con `ajax.php` che gestisce la maggior parte delle interazioni front-end.

#### Controller Admin Back-Office

-   `controllers/admin/AdminProductExpertController.php`
    *   **Nome classe:** `AdminProductExpertController` (estende `ModuleAdminController`)
    *   **Nome scheda:** "Esperti" sotto il menu "Esperto di prodotto".
    *   **Entità gestita:** `ProductExpertExpert` (tramite `classes/ProductExpertExpert.php`).
    *   **Responsabilità:** Questo è il controller di amministrazione principale per la gestione dei profili dei singoli esperti. Gestisce l'elenco degli esperti (utilizzando `HelperList`) e i moduli di creazione/modifica per gli esperti (utilizzando `HelperForm`). Gestisce le operazioni CRUD per i dati degli esperti, inclusi nome, ruolo, biografia, foto, link di contatto e, soprattutto, le loro assegnazioni a prodotti, categorie, marchi e fornitori. Gestisce anche le sovrascritture del layout per i singoli biglietti da visita degli esperti.
-   `controllers/admin/index.php`
    *   **Nome classe:** (Nessuna classe specifica, spesso un reindirizzamento o una misura di sicurezza)
    *   **Responsabilità:** Questo file è tipicamente una misura di sicurezza per prevenire l'elenco diretto delle directory o l'accesso. Spesso contiene un semplice `header('Location: ../../index.php'); exit;` o simile per reindirizzare al pannello di amministrazione principale. Non gestisce un'entità o un modulo specifico.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo ha un ricco set di classi per la gestione delle sue complesse funzionalità, in particolare per quanto riguarda i layout e le configurazioni dei biglietti da visita degli esperti.

-   `classes/ProductExpertExpert.php`
    *   **Tabella database:** `ps_productexpert_expert`
    *   **Estende:** `ObjectModel`
    *   **Campi `$definition`:** Definisce lo schema per i profili degli esperti (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Gestisce i campi multilingue se applicabile.
    *   **Metodi pubblici chiave:** Metodi per salvare, recuperare ed eliminare i dati degli esperti. Include la logica per la gestione dei caricamenti di foto e delle associazioni.
-   `classes/ProductExpertExpertLinks.php`
    *   **Tabella database:** `ps_productexpert_expert_link`
    *   **Estende:** `ObjectModel`
    *   **Campi `$definition`:** Definisce lo schema per i link di contatto degli esperti (id\_expert\_link, id\_expert, type, value, icon, position).
    *   **Metodi pubblici chiave:** Gestisce i vari link di contatto (email, telefono, WhatsApp, LinkedIn, personalizzati) associati a un esperto.
-   `classes/ProductExpertExpertPhoto.php`
    *   **Tabella database:** `ps_productexpert_expert_photo`
    *   **Estende:** `ObjectModel`
    *   **Campi `$definition`:** Gestisce i dettagli della foto dell'esperto (id\_photo, filename, mime\_type, size).
    *   **Metodi pubblici chiave:** Gestisce l'archiviazione e il recupero delle immagini del profilo dell'esperto.
-   `classes/ProductExpertConfig.php`
    *   **Tabella database:** `ps_configuration` (memorizza i valori di configurazione)
    *   **Estende:** (Probabilmente non `ObjectModel`, ma una classe di utilità)
    *   **Metodi pubblici chiave:** Fornisce metodi statici per ottenere e impostare i valori di configurazione specifici del modulo (ad esempio, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
-   `classes/ProductExpertResolver.php`
    *   **Estende:** (Probabilmente una classe personalizzata)
    *   **Metodi pubblici chiave:** Contiene la logica principale per determinare quali esperti devono essere visualizzati per un dato prodotto in base alla sua categoria, marca, fornitore e assegnazioni dirette del prodotto. Risolve l'elenco degli esperti per il front office.
-   `classes/ProductExpertListPresenter.php`
    *   **Estende:** (Probabilmente una classe personalizzata)
    *   **Metodi pubblici chiave:** Responsabile della preparazione dei dati degli esperti risolti in un formato adatto per la visualizzazione nei template Smarty, applicando i layout di elenco selezionati (griglia, carosello, elenco).
-   `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
    *   **Estende:** (Probabilmente classi personalizzate)
    *   **Responsabilità:** Un complesso set di classi dedicate alla gestione del design visivo e della struttura dei biglietti da visita degli esperti. Ciò include la definizione di elementi di layout, stili, sfumature e la gestione dei preset integrati, nonché dei layout personalizzati salvati dall'utente. Questo è il cuore della funzionalità "Visual Business Card Designer".
-   `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
    *   **Estende:** (Probabilmente classi personalizzate)
    *   **Responsabilità:** Classi helper per il rendering degli elementi UI complessi nei moduli di configurazione del Back Office, in particolare per lo studio di layout e le impostazioni generali del modulo.
-   `classes/PeCompatibility.php`
    *   **Estende:** (Probabilmente una classe di utilità)
    *   **Metodi pubblici chiave:** Fornisce metodi per gestire i problemi di compatibilità tra diverse versioni di PrestaShop (ad esempio, differenze nei nomi degli hook, nelle chiamate API o nelle funzioni deprecate).
-   `classes/ProductExpertInstallSamples.php`
    *   **Estende:** (Probabilmente una classe di utilità)
    *   **Metodi pubblici chiave:** Contiene la logica per l'installazione di dati di esempio (ad esempio, esperti di esempio, layout) durante l'installazione del modulo per fornire un avvio rapido ai commercianti.

### 4.4 Asset JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Fornisce la funzionalità di completamento automatico per lo strumento di ricerca esperti, suggerendo nomi o specialità di esperti mentre l'utente digita.
-   `lib/searchTool/views/pe-searchtool-init.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Inizializza lo strumento di ricerca esperti, associando i listener di eventi all'input di ricerca e integrando la funzionalità di completamento automatico.
-   `views/js/admin-element-editor.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Alimenta l'editor visivo per i singoli elementi all'interno di un layout di biglietto da visita esperto (ad esempio, campi di testo, immagini, icone). Gestisce il drag-and-drop, il ridimensionamento e le regolazioni delle proprietà di stile.
-   `views/js/admin-expert-photo.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Gestisce la funzionalità di caricamento e anteprima delle foto per i profili degli esperti nel pannello di amministrazione.
-   `views/js/admin-layout-studio.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Il JavaScript principale per il "Visual Business Card Designer". Gestisce la tela di layout generale, la gestione degli elementi, il salvataggio/caricamento dei layout e l'applicazione degli stili.
-   `views/js/admin-list-layout-studio.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Gestisce lo studio per la progettazione di come vengono visualizzati più biglietti da visita degli esperti (griglia, carosello, elenco), incluse le opzioni per la reattività e la navigazione.
-   `views/js/front.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Contiene il JavaScript generale del front-office per il modulo, inclusi:
        *   Listener di eventi per l'invio del modulo di contatto (chiamate AJAX a `ajax.php`).
        *   Logica per la visualizzazione e la chiusura del modale del modulo di contatto.
        *   Inizializzazione di qualsiasi funzionalità di carosello o slider per gli elenchi di esperti.
        *   Miglioramenti generali dell'interfaccia utente per i biglietti da visita degli esperti.

### 4.5 Fogli di stile CSS (`views/css/`)

#### CSS Front-Office

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili per i suggerimenti a discesa del completamento automatico nello strumento di ricerca esperti.
-   `views/css/front.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili generali del front-office per il modulo, inclusi layout di base, tipografia e reattività per i biglietti da visita e gli elenchi degli esperti.
-   `views/css/pe-expert-card-front.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili specifici per i singoli biglietti da visita degli esperti, applicando il layout scelto e gli stili degli elementi.
-   `views/css/pe-front-contact.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili per il modulo di contatto dell'esperto, inclusa la presentazione modale, i campi di input e i pulsanti.
-   `views/css/pe-front-experts.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili per la visualizzazione complessiva di più esperti, come layout a griglia, layout a elenco o navigazione a carosello.

#### CSS Back-Office

-   `views/css/admin-config.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stile generale per la pagina di configurazione principale del modulo nel pannello di amministrazione.
-   `views/css/admin-element-editor.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per l'editor visivo degli elementi all'interno dello studio di layout.
-   `views/css/admin-expert-card-studio.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** CSS principale per l'interfaccia dello studio di layout dei biglietti da visita degli esperti.
-   `views/css/admin-expert-photo.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per l'area di caricamento e anteprima delle foto degli esperti nei moduli di amministrazione.
-   `views/css/admin-experts-list.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per la vista elenco degli esperti in `AdminProductExpertController`.
-   `views/css/admin-layout-builder.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili relativi ai componenti di costruzione del layout.
-   `views/css/admin-layout-studio.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili generali per l'interfaccia dello studio di layout.
-   `views/css/admin-list-layout-studio.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per l'interfaccia dello studio di layout dell'elenco.
-   `views/css/admin-pe-overrides.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Sovrascritture o aggiustamenti CSS specifici per gli stili di amministrazione predefiniti di PrestaShop per garantire la coerenza dell'interfaccia utente del modulo.
-   `views/css/admin-searchtool.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per lo strumento di ricerca all'interno del pannello di amministrazione (se applicabile, ad esempio, per la ricerca di prodotti/categorie durante l'assegnazione).

### 4.6 Struttura del template Smarty (`views/templates/`)

-   `lib/searchTool/views/scripts.tpl`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Probabilmente include il JavaScript e il CSS necessari per lo strumento di ricerca, spesso agganciato a `displayHeader` o `displayFooter` per caricare gli asset.
-   `views/templates/admin/configure.tpl`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Il template principale per la pagina di configurazione del modulo (metodo `getContent()`), che renderizza il modulo delle impostazioni generali.
-   `views/templates/admin/list-layout.tpl`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Template per lo studio di layout dell'elenco nell'amministrazione, che consente la configurazione di come vengono visualizzati più biglietti da visita degli esperti.
-   `views/templates/admin/product-tab.tpl`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Questo template è probabilmente utilizzato per iniettare una scheda o una sezione personalizzata nella pagina di modifica del prodotto di PrestaShop, consentendo l'assegnazione diretta degli esperti a un prodotto dalla sua schermata di modifica.
-   `views/templates/hook/product-experts.tpl`
    *   **Ambito:** Front-office.
    *   **Hook:** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (come configurato).
    *   **Descrizione:** Il template principale responsabile del rendering del blocco di biglietti da visita degli esperti nel front office. Itera attraverso gli esperti risolti e include `_pe-expert-card-element.tpl` per ciascuno.
-   `views/templates/hook/_pe-expert-card-element.tpl`
    *   **Ambito:** Front-office.
    *   **Hook:** Incluso da `product-experts.tpl`.
    *   **Descrizione:** Renderizza un singolo biglietto da visita esperto, applicando il layout scelto e visualizzando la foto, il nome, il ruolo, la biografia e i link di contatto dell'esperto. Probabilmente include `_pe-expert-card-row.tpl` per il contenuto strutturato.
-   `views/templates/hook/_pe-expert-card-row.tpl`
    *   **Ambito:** Front-office.
    *   **Hook:** Incluso da `_pe-expert-card-element.tpl`.
    *   **Descrizione:** Renderizza una singola riga o sezione all'interno di un biglietto da visita esperto, utilizzata per strutturare gli elementi di contenuto (ad esempio, una riga per le icone di contatto, una riga per nome e ruolo).

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_productexpert_expert`: Memorizza le informazioni principali del profilo dell'esperto (nome, ruolo, biografia, ID foto, stato attivo, preset di layout).
-   `ps_productexpert_expert_lang`: Memorizza i campi multilingue per gli esperti (se presenti, ad esempio, biografia).
-   `ps_productexpert_expert_link`: Memorizza i singoli link di contatto per ogni esperto (tipo, valore, icona).
-   `ps_productexpert_expert_photo`: Memorizza i metadati per le immagini del profilo dell'esperto.
-   `ps_productexpert_expert_product`: Tabella di relazione molti-a-molti che collega gli esperti ai prodotti.
-   `ps_productexpert_expert_category`: Tabella di relazione molti-a-molti che collega gli esperti alle categorie.
-   `ps_productexpert_expert_manufacturer`: Tabella di relazione molti-a-molti che collega gli esperti ai marchi (produttori).
-   `ps_productexpert_expert_supplier`: Tabella di relazione molti-a-molti che collega gli esperti ai fornitori.
-   `ps_productexpert_layout_preset`: Memorizza le definizioni dei layout personalizzati dei biglietti da visita degli esperti creati dal commerciante.
-   `ps_productexpert_list_layout`: Memorizza le definizioni dei layout personalizzati degli elenchi di esperti (griglia, carosello, ecc.).
-   `ps_configuration`: Memorizza le impostazioni di configurazione globali del modulo (ad esempio, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Carica gli asset CSS e JS del modulo per il front-office. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office. | Carica gli asset CSS e JS del modulo per le schermate di amministrazione. |
| `displayModuleConfigureExtraButtons` | Nella pagina di gestione dei moduli, accanto al pulsante "Configura". | Aggiungi collegamenti rapidi a "Gestisci esperti" o "Studio di layout". |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Inietta la scheda/sezione di assegnazione degli esperti per i prodotti. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" nelle pagine dei prodotti. | Visualizza i biglietti da visita degli esperti in un'area prominente specifica del prodotto. |
| `displayProductExtraContent` | In una sezione/scheda dedicata nelle pagine dei prodotti. | Visualizza i biglietti da visita degli esperti come contenuto aggiuntivo del prodotto. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine applicabili. | Visualizza i biglietti da visita degli esperti o lo strumento di ricerca esperti nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra delle pagine applicabili. | Visualizza i biglietti da visita degli esperti o lo strumento di ricerca esperti nella colonna destra. |
| `displayFooter` | Nella sezione del piè di pagina di tutte le pagine. | Visualizza i biglietti da visita degli esperti o un link a una pagina degli esperti nel piè di pagina. |
| `displayTop` | Nella sezione superiore del negozio (intestazione). | Visualizza lo strumento di ricerca esperti per l'accesso globale. |
| `displayNav` | Nella barra di navigazione (spesso sopra `displayTop`). | Visualizza lo strumento di ricerca esperti per l'accesso globale. |
| `actionFrontControllerSetMedia` | Prima del rendering del controller front-end, per l'aggiunta di asset. | Aggiungi dinamicamente JS/CSS specifici del front-office in base al contesto. |
| `actionAdminControllerSetMedia` | Prima del rendering del controller admin, per l'aggiunta di asset. | Aggiungi dinamicamente JS/CSS specifici del back-office in base al contesto. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente attiva la logica di assegnazione degli esperti o la pulizia della cache. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto. | Potenzialmente attiva la logica di assegnazione degli esperti o la pulizia della cache. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Pulisci eventuali assegnazioni di esperti relative al prodotto eliminato. |
| `actionObjectCategoryUpdateAfter` | Dopo l'aggiornamento di una categoria. | Svuota la cache relativa alle assegnazioni di esperti basate sulla categoria. |
| `actionObjectManufacturerUpdateAfter` | Dopo l'aggiornamento di un produttore (marca). | Svuota la cache relativa alle assegnazioni di esperti basate sulla marca. |
| `actionObjectSupplierUpdateAfter` | Dopo l'aggiornamento di un fornitore. | Svuota la cache relativa alle assegnazioni di esperti basate sul fornitore. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico ufficiale, si prega di fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team è dedicato a fornire assistenza completa e a garantire che il modulo funzioni senza problemi.

-   **MyPresta.eu Cronologia ordini e download:** <https://mypresta.eu/my-account/orders/>
-   **Supporto MyPresta.eu:** Accedi al nostro portale di supporto tramite il tuo account per assistenza diretta.
