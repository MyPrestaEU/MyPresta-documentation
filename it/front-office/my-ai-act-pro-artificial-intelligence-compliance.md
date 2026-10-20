---
title: "My AI Act Pro - Conformità all'Intelligenza Artificiale - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop My AI Act Pro - Conformità all'Intelligenza Artificiale di MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Conformità all'Intelligenza Artificiale - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo My AI Act Pro - Artificial Intelligence Compliance su MyPresta.eu](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Conformità all'Intelligenza Artificiale

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.6.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Assicurati che il tuo server soddisfi i requisiti generali di PrestaShop per prestazioni ottimali.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > My AI Act Pro)

Questo è il pannello di controllo principale per il tuo modulo di conformità all'AI Act. Qui abiliterai le funzionalità, definirai le impostazioni globali e gestirai il comportamento generale delle divulgazioni AI.

#### Scheda Impostazioni Generali

-   **Abilita conformità AI Act:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutte le funzionalità del modulo (badge, banner, log, ecc.) diventeranno attive nel tuo negozio in base alle loro impostazioni individuali.
        -   *Quando disabilitato:* Il modulo smetterà di visualizzare qualsiasi contenuto relativo all'AI Act nel tuo front office e i suoi processi in background verranno sospesi.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Abilita questa opzione una volta che sei pronto a rendere operativa la tua conformità all'AI Act. Se hai bisogno di disabilitare temporaneamente tutte le divulgazioni per manutenzione, disattiva questa opzione.
-   **Visualizza badge di divulgazione AI nelle pagine prodotto:**

    -   **Cosa fa questa impostazione:** Controlla se il badge di divulgazione AI appare nelle singole pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il badge AI sarà visibile nelle pagine prodotto per i prodotti contrassegnati come generati dall'IA.
        -   *Quando disabilitato:* Il badge non verrà visualizzato nelle pagine prodotto, anche se i prodotti sono contrassegnati.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Questo è fondamentale per la trasparenza diretta del prodotto. Mantienilo abilitato per informare i clienti direttamente sul prodotto che stanno visualizzando.
-   **Visualizza badge di divulgazione AI negli elenchi di prodotti:**

    -   **Cosa fa questa impostazione:** Controlla se il badge di divulgazione AI appare nelle pagine di categoria, nei risultati di ricerca o in altre visualizzazioni di elenchi di prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un badge AI più piccolo apparirà sulle miniature dei prodotti negli elenchi.
        -   *Quando disabilitato:* Nessun badge apparirà negli elenchi di prodotti.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione fornisce una trasparenza immediata mentre i clienti navigano, aiutandoli a identificare i contenuti generati dall'IA prima di cliccare su una pagina prodotto.
-   **Posizione del badge di divulgazione AI (Pagina prodotto):**

    -   **Cosa fa questa impostazione:** Determina dove viene posizionato il badge AI nella pagina prodotto. Le opzioni includono tipicamente "Sopra l'immagine del prodotto", "Sotto l'immagine del prodotto", "Vicino al nome del prodotto", "Nella descrizione del prodotto", ecc.
    -   **Effetto della modifica di questa impostazione:** Il badge si sposterà nella posizione selezionata nella pagina prodotto.
    -   **Valore consigliato:** Sperimenta per trovare la migliore soluzione per il tuo tema, spesso "Sopra l'immagine del prodotto" o "Vicino al nome del prodotto" per la visibilità.
    -   **Scenario / esempio del commerciante:** Se le tue immagini prodotto sono molto grandi, posizionare il badge "Sotto l'immagine del prodotto" potrebbe essere meno invasivo. Se vuoi che sia immediatamente visibile, "Sopra l'immagine del prodotto" è meglio.
-   **Layout del badge di divulgazione AI:**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere uno stile visivo predefinito per il badge AI dallo "Studio di Layout".
    -   **Effetto della modifica di questa impostazione:** L'aspetto del badge AI (icona, testo, colori, forma) cambierà in base al layout selezionato.
    -   **Valore consigliato:** Seleziona un layout che si abbini al branding del tuo negozio e sia chiaramente visibile.
    -   **Scenario / esempio del commerciante:** Potresti creare un layout personalizzato con i colori del tuo marchio e un'icona specifica per garantire che il badge abbia un aspetto professionale e si integri bene.
-   **Link alla pagina della politica sull'IA:**

    -   **Cosa fa questa impostazione:** Ti consente di collegarti a una pagina CMS dedicata o a un URL esterno che spiega la politica sull'IA del tuo negozio.
    -   **Effetto della modifica di questa impostazione:** Il modulo utilizzerà questo URL quando si collega alla tua politica sull'IA da badge, banner o altri elementi di divulgazione.
    -   **Valore consigliato:** Crea una pagina CMS dettagliata (ad esempio, "La nostra politica di trasparenza sull'IA") e collegala qui.
    -   **Scenario / esempio del commerciante:** Questo link è fondamentale per fornire informazioni complete ai clienti che desiderano saperne di più sull'utilizzo dell'IA.
-   **Abilita banner di divulgazione AI:**

    -   **Cosa fa questa impostazione:** Attiva un banner a livello di sito per informare i clienti sull'utilizzo dell'IA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un banner apparirà nell'hook selezionato (ad esempio, intestazione o piè di pagina).
        -   *Quando disabilitato:* Nessun banner verrà visualizzato.
    -   **Valore consigliato:** SÌ, soprattutto per il lancio iniziale o se il tuo negozio utilizza ampiamente l'IA.
    -   **Scenario / esempio del commerciante:** Utilizza questo banner per fare una dichiarazione generale sulla politica sull'IA del tuo negozio, magari collegandoti alla tua pagina di politica dedicata.
-   **Posizione del banner di divulgazione AI (Hook):**

    -   **Cosa fa questa impostazione:** Seleziona dove apparirà il banner (ad esempio, `displayHeader`, `displayFooter`).
    -   **Effetto della modifica di questa impostazione:** Il banner verrà renderizzato nella posizione scelta.
    -   **Valore consigliato:** `displayHeader` per la massima visibilità, o `displayFooter` per un approccio meno invasivo.
    -   **Scenario / esempio del commerciante:** Posizionarlo in `displayHeader` garantisce che ogni visitatore lo veda immediatamente all'atterraggio sul tuo sito.
-   **Contenuto del banner di divulgazione AI:**

    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo e il contenuto HTML del banner.
    -   **Effetto della modifica di questa impostazione:** Il banner visualizzerà il tuo messaggio personalizzato.
    -   **Valore consigliato:** Un messaggio conciso come "Utilizziamo l'IA per migliorare la tua esperienza di acquisto. [Scopri di più]" con un link alla tua pagina della politica.
    -   **Scenario / esempio del commerciante:** Puoi usarlo per spiegare brevemente l'utilizzo dell'IA e indirizzare i clienti alla tua politica completa.
-   **Abilita informazioni di fallback umano:**

    -   **Cosa fa questa impostazione:** Visualizza un messaggio che indica la supervisione umana o offre assistenza umana per i contenuti generati dall'IA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un messaggio configurabile apparirà nelle pagine pertinenti.
        -   *Quando disabilitato:* Nessun messaggio di fallback umano verrà visualizzato.
    -   **Valore consigliato:** SÌ, se vuoi rassicurare i clienti che è coinvolta una revisione umana o fornire un punto di contatto.
    -   **Scenario / esempio del commerciante:** Se le tue descrizioni di prodotti generate dall'IA sono sempre revisionate da un editor umano, puoi usarlo per dichiarare "Tutti i contenuti generati dall'IA sono revisionati dal nostro team. Contattaci se hai domande."
-   **Messaggio di fallback umano:**

    -   **Cosa fa questa impostazione:** Personalizza il testo per le informazioni di fallback umano.
    -   **Effetto della modifica di questa impostazione:** Il messaggio verrà visualizzato come inserito.
    -   **Valore consigliato:** Un messaggio chiaro e rassicurante.
    -   **Scenario / esempio del commerciante:** "I nostri strumenti AI sono supervisionati da esperti umani. Per qualsiasi preoccupazione, si prega di contattare il nostro servizio clienti."
-   **Abilita registro di audit:**

    -   **Cosa fa questa impostazione:** Registra tutte le azioni e le divulgazioni relative all'AI Act in un log a fini di conformità.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Ogni volta che viene effettuata una divulgazione AI o un prodotto viene contrassegnato, viene salvata una voce nel registro di audit del modulo.
        -   *Quando disabilitato:* Nessuna traccia di audit verrà mantenuta.
    -   **Valore consigliato:** SÌ, questo è fondamentale per dimostrare la conformità e la risoluzione dei problemi.
    -   **Scenario / esempio del commerciante:** Se un organismo di regolamentazione richiede una prova delle tue divulgazioni AI, il registro di audit fornisce una cronologia.

#### Scheda API e Integrazioni

-   **Abilita API REST:**

    -   **Cosa fa questa impostazione:** Attiva un endpoint API REST per consentire a sistemi esterni di interagire con il modulo (ad esempio, contrassegnare i prodotti come generati dall'IA).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* L'API diventa attiva, consentendo l'interazione programmatica.
        -   *Quando disabilitato:* L'API è inattiva.
    -   **Valore consigliato:** NO, a meno che tu non abbia una specifica esigenza tecnica di integrazione con strumenti o sistemi AI esterni.
    -   **Scenario / esempio del commerciante:** Se utilizzi un servizio esterno di generazione di immagini AI, potresti utilizzare l'API per contrassegnare automaticamente le immagini come generate dall'IA in PrestaShop.
-   **Gestione chiavi API:**

    -   **Cosa fa questa impostazione:** Ti consente di generare e gestire chiavi API per un accesso sicuro all'API REST del modulo.
    -   **Effetto della modifica di questa impostazione:** Possono essere create nuove chiavi, quelle esistenti revocate, controllando chi può accedere all'API.
    -   **Valore consigliato:** Genera una chiave forte e unica per ogni integrazione.
    -   **Scenario / esempio del commerciante:** Crea una chiave API specifica per il tuo generatore di immagini AI e un'altra per il tuo scrittore di contenuti AI, revocandole se un'integrazione non è più necessaria.
-   **Abilita CRON per filigrana:**

    -   **Cosa fa questa impostazione:** Attiva un'attività pianificata (CRON job) per applicare automaticamente filigrane alle immagini generate dall'IA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il CRON job verrà eseguito periodicamente, applicando una filigrana configurabile alle immagini contrassegnate.
        -   *Quando disabilitato:* Non verrà eseguita alcuna filigrana automatica.
    -   **Valore consigliato:** NO, a meno che tu non richieda specificamente la filigrana per le immagini AI.
    -   **Scenario / esempio del commerciante:** Se desideri un indicatore visivo direttamente sull'immagine stessa (ad esempio, un piccolo logo "AI") per tutte le immagini di prodotti generate dall'IA, abilita questa opzione.
-   **Immagine/Testo filigrana:**

    -   **Cosa fa questa impostazione:** Definisce la filigrana da applicare (ad esempio, un file immagine o una stringa di testo).
    -   **Effetto della modifica di questa impostazione:** Il CRON job utilizzerà questa filigrana.
    -   **Valore consigliato:** Un indicatore sottile e chiaro, se utilizzato.
    -   **Scenario / esempio del commerciante:** Carica una piccola immagine semi-trasparente "AI Generated" o inserisci "AI" come testo.

#### Scheda Shortcode

-   **Elenco e utilizzo degli shortcode:**
    -   **Cosa fa questa impostazione:** Fornisce un elenco di shortcode disponibili che possono essere inseriti nelle descrizioni dei prodotti, nelle pagine CMS o in altre aree di testo.
    -   **Effetto della modifica di questa impostazione:** Nessuna modifica diretta, ma l'utilizzo di questi shortcode nel tuo contenuto visualizzerà gli elementi di divulgazione AI corrispondenti.
    -   **Valore consigliato:** Utilizza questi shortcode per incorporare divulgazioni specifiche dove le impostazioni globali potrebbero non essere sufficienti.
    -   **Scenario / esempio del commerciante:** Potresti avere un prodotto in cui solo un paragrafo specifico della descrizione è stato generato dall'IA. Puoi racchiudere quel paragrafo con uno shortcode per visualizzare un piccolo badge accanto ad esso.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AI Act > Gestione prodotti in blocco (AdminMyAiActBulkController)

-   **Nome schermata e posizione menu:** Nel tuo Back Office di PrestaShop, naviga su **AI Act > Gestione prodotti in blocco**.
-   **Azioni e impostazioni disponibili:** Questa schermata fornisce una potente vista a griglia per gestire lo stato AI Act di più prodotti contemporaneamente.
    -   **Elenco prodotti:** Visualizza un elenco di tutti i tuoi prodotti con colonne per il nome del prodotto, l'ID e, soprattutto, il loro stato AI Act.
    -   **Filtri e ricerca:** Ti consente di filtrare i prodotti in base a vari criteri (ad esempio, categoria, fornitore, stato AI Act) per trovare rapidamente elementi specifici.
    -   **Azioni in blocco:**
        -   **Contrassegna come generato dall'IA:** Seleziona più prodotti e applica loro contemporaneamente il flag "generato dall'IA".
        -   **Rimuovi contrassegno come generato dall'IA:** Rimuovi il flag "generato dall'IA" dai prodotti selezionati.
        -   **Applica tag AI Act specifici:** Assegna tag o regole personalizzate (se configurati) a più prodotti.
-   **Effetto delle modifiche:**
    -   Quando contrassegni i prodotti come generati dall'IA, i badge e le divulgazioni del front-office appariranno per questi prodotti in base alle impostazioni generali del tuo modulo.
    -   La rimozione del contrassegno dai prodotti rimuove queste divulgazioni.
    -   L'applicazione di tag consente un controllo più granulare su tipi o messaggi di divulgazione specifici.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Dopo aver importato nuovi prodotti o generato contenuti con l'IA, utilizza i filtri per individuare rapidamente questi prodotti.
    2.  Seleziona tutti i prodotti pertinenti utilizzando le caselle di controllo.
    3.  Utilizza l'azione in blocco "Contrassegna come generato dall'IA" per applicare il flag.
    4.  Controlla periodicamente i prodotti per assicurarti che il loro stato AI Act sia accurato.

#### 2.2.2 AI Act > Registri di audit (AdminMyAiActLogsController)

-   **Nome schermata e posizione menu:** Nel tuo Back Office di PrestaShop, naviga su **AI Act > Registri di audit**.
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza un registro dettagliato di tutti gli eventi e le divulgazioni relativi all'AI Act, a condizione che l'impostazione "Abilita registro di audit" sia attiva.
    -   **Voci di registro:** Ogni voce include tipicamente:
        -   **Timestamp:** Quando si è verificato l'evento.
        -   **Azione/Evento:** Cosa è successo (ad esempio, "Prodotto X contrassegnato come AI", "Badge AI visualizzato per Prodotto Y").
        -   **Utente/Sistema:** Chi ha avviato l'azione (ad esempio, "Utente amministratore Z", "CRON Job", "Visitatore Front Office").
        -   **ID prodotto/Contesto:** Quale prodotto o entità è stata interessata.
        -   **Dettagli:** Qualsiasi informazione aggiuntiva pertinente.
    -   **Filtri e ricerca:** Ti consente di filtrare le voci di registro per intervallo di date, tipo di evento o prodotto per indagare su incidenti specifici.
-   **Effetto delle modifiche:** Questa schermata è solo per la visualizzazione; non puoi apportare modifiche dirette qui. Serve come registro storico.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Rivedi regolarmente i registri di audit, soprattutto dopo aver apportato modifiche significative alle impostazioni dell'AI Act o ai dati dei prodotti, per assicurarti che tutto funzioni come previsto.
    2.  In caso di audit di conformità o richiesta del cliente, utilizza questo registro per recuperare eventi di divulgazione specifici.

#### 2.2.3 AI Act > Studio di Layout (AdminMyAiActLayoutsController - *Dedotto da template e descrizione*)

-   **Nome schermata e posizione menu:** Nel tuo Back Office di PrestaShop, naviga su **AI Act > Studio di Layout** (o simile, in base alla struttura del menu del modulo).
-   **Azioni e impostazioni disponibili:** Questa schermata è dove progetti e gestisci l'aspetto visivo dei tuoi badge di divulgazione AI e altri elementi.
    -   **Elenco layout:** Una tabella che mostra tutti i layout di badge esistenti.
    -   **Aggiungi nuovo layout / Modifica layout:**
        -   **Nome layout:** Un nome descrittivo per il tuo layout.
        -   **Tipo di badge:** Scegli tra solo icona, solo testo o icona + testo.
        -   **Selettore icone:** Seleziona da un catalogo di icone o carica la tua.
        -   **Contenuto testuale:** Inserisci il testo da visualizzare sul badge (ad esempio, "Generato dall'IA").
        -   **Opzioni di stile:**
            -   **Colori:** Colore di sfondo, colore del testo, colore dell'icona.
            -   **Bordi:** Stile del bordo, larghezza, colore.
            -   **Ombre:** Effetti di ombreggiatura.
            -   **Sfumature:** Opzioni di sfumatura dello sfondo.
            -   **Padding e margini:** Spaziatura intorno al badge.
            -   **Impostazioni font:** Dimensione del font, peso.
        -   **Anteprima:** Un'anteprima in tempo reale del tuo badge mentre lo progetti.
-   **Effetto delle modifiche:**
    -   La creazione di nuovi layout ti offre più opzioni per l'aspetto delle tue divulgazioni AI.
    -   La modifica di un layout esistente aggiornerà immediatamente l'aspetto di tutti i badge che utilizzano quel layout in tutto il tuo negozio.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizia con un layout predefinito e personalizzalo per abbinarlo all'estetica del tuo marchio.
    2.  Crea layout diversi per diversi tipi di divulgazioni AI, se necessario (ad esempio, uno per le immagini AI, un altro per il testo AI).
    3.  Testa i layout su vari dispositivi per assicurarti che siano visibili e abbiano un bell'aspetto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita conformità AI Act | SÌ | Interruttore principale per tutte le funzionalità del modulo. |
| | Visualizza badge di divulgazione AI nelle pagine prodotto | SÌ | Mostra badge nelle pagine di dettaglio del prodotto. |
| | Visualizza badge di divulgazione AI negli elenchi di prodotti | SÌ | Mostra badge nelle pagine di categoria/ricerca. |
| | Posizione del badge di divulgazione AI (Pagina prodotto) | *Dipendente dal tema* | Controlla il posizionamento del badge nelle pagine prodotto. |
| | Layout del badge di divulgazione AI | *Personalizzabile* | Stile visivo del badge AI. |
| | Link alla pagina della politica sull'IA | *URL della tua pagina CMS* | Link alla politica sull'IA del tuo negozio. |
| | Abilita banner di divulgazione AI | SÌ | Attiva un banner informativo a livello di sito. |
| | Posizione del banner di divulgazione AI (Hook) | `displayHeader` | Posizionamento del banner (ad es. parte superiore/inferiore della pagina). |
| | Contenuto del banner di divulgazione AI | *Testo/HTML personalizzabile* | Messaggio visualizzato nel banner. |
| | Abilita informazioni di fallback umano | SÌ | Visualizza un messaggio sulla supervisione umana. |
| | Messaggio di fallback umano | *Testo personalizzabile* | Contenuto del messaggio di fallback umano. |
| | Abilita registro di audit | SÌ | Registra tutte le azioni relative all'AI Act per la conformità. |
| | Abilita API REST | NO | Attiva l'API per integrazioni esterne. |
| | Gestione chiavi API | *N/A* | Genera/gestisci chiavi API per un accesso sicuro. |
| | Abilita CRON per filigrana | NO | Applica automaticamente filigrane alle immagini generate dall'IA. |
| | Immagine/Testo filigrana | *N/A* | Definisce il contenuto della filigrana. |
| | Elenco e utilizzo degli shortcode | *N/A* | Fornisce shortcode per la divulgazione granulare dei contenuti. |
| **AI Act > Gestione prodotti in blocco** | Contrassegna come generato dall'IA (Azione in blocco) | N/A | Contrassegna più prodotti come generati dall'IA. |
| | Rimuovi contrassegno come generato dall'IA (Azione in blocco) | N/A | Rimuove il flag "generato dall'IA" dai prodotti. |
| | Applica tag AI Act specifici (Azione in blocco) | N/A | Assegna tag di divulgazione personalizzati ai prodotti. |
| **AI Act > Registri di audit** | Visualizza voci di registro | N/A | Fornisce una cronologia degli eventi AI Act. |
| **AI Act > Studio di Layout** | Crea/Modifica layout | N/A | Progetta stili visivi personalizzati per i badge AI. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho configurato il modulo, ma non vedo badge o banner AI nel mio negozio. Cosa c'è che non va?**
R1:

-   **Controlla l'interruttore principale:** Innanzitutto, assicurati che "Abilita conformità AI Act" sia impostato su SÌ nella configurazione principale del modulo.
-   **Interruttori delle singole funzionalità:** Verifica che "Visualizza badge di divulgazione AI nelle pagine prodotto", "Visualizza badge di divulgazione AI negli elenchi di prodotti" e "Abilita banner di divulgazione AI" siano anch'essi impostati su SÌ se desideri che tali funzionalità siano attive.
-   **Stato del prodotto:** Affinché i badge appaiano, i prodotti devono essere esplicitamente contrassegnati come "generati dall'IA". Controlla questo nella pagina di modifica del prodotto (sotto una scheda dedicata) o tramite "AI Act > Gestione prodotti in blocco".
-   **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser. A volte, viene visualizzato contenuto vecchio.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Controlla la console per sviluppatori del tuo browser per errori JavaScript.

**D2: Il badge AI appare, ma non si adatta bene al design del mio tema. Come posso cambiarne l'aspetto?**
R2:

-   **Studio di Layout:** Naviga su **AI Act > Studio di Layout** nel tuo Back Office. Qui puoi creare e modificare i layout dei badge. Hai ampie opzioni per colori, icone, testo, ombre e sfumature.
-   **Seleziona Layout:** Dopo aver creato o modificato un layout, torna alla configurazione principale del modulo e seleziona il layout desiderato sotto "Layout del badge di divulgazione AI".
-   **Sovrascritture CSS (Avanzato):** Se lo Studio di Layout non offre sufficiente personalizzazione, un webmaster può utilizzare CSS personalizzati nel tuo tema per sovrascrivere gli stili predefiniti del modulo (vedi Sezione 7.5 per le posizioni dei file CSS).

**D3: Come posso contrassegnare i prodotti come generati dall'IA in modo efficiente, soprattutto se ne ho molti?**
R3:

-   **Gestione prodotti in blocco:** Vai su **AI Act > Gestione prodotti in blocco**. Questa schermata ti consente di filtrare i tuoi prodotti e selezionare più elementi per contrassegnarli o rimuovere il contrassegno come generati dall'IA in un'unica operazione. Questo è il metodo più efficiente per cataloghi di grandi dimensioni.
-   **Pagina prodotto individuale:** Per i singoli prodotti, troverai una scheda dedicata (ad esempio, "Conformità AI Act") durante la modifica di un prodotto nel Back Office, dove puoi attivare o disattivare il suo stato AI.

**D4: Voglio fornire una spiegazione dettagliata della mia politica sull'IA. Dove dovrei metterla?**
R4:

-   **Pagina CMS dedicata:** Crea una nuova pagina CMS (Design > Pagine) intitolata qualcosa come "La nostra politica di trasparenza sull'IA" o "Come utilizziamo l'IA". Scrivi qui la tua politica completa.
-   **Link nel modulo:** Nella configurazione principale del modulo, imposta il "Link alla pagina della politica sull'IA" sull'URL della tua pagina CMS appena creata. Questo link verrà quindi utilizzato da banner e badge per indirizzare i clienti alla tua politica.

**D5: Il CRON job per la filigrana non funziona. Cosa dovrei controllare?**
R5:

-   **Abilita CRON per filigrana:** Assicurati che "Abilita CRON per filigrana" sia impostato su SÌ nella configurazione del modulo.
-   **Configurazione del CRON job:** Verifica che il CRON job stesso sia configurato correttamente sul tuo server. Il modulo di solito fornisce la riga di comando esatta da aggiungere al gestore CRON del tuo pannello di hosting. Se non sei sicuro, contatta il tuo provider di hosting o un webmaster.
-   **Permessi:** Assicurati che il modulo e le cartelle delle immagini abbiano i permessi di scrittura corretti.
-   **Log degli errori:** Controlla i log degli errori PHP del tuo server e la modalità di debug di PrestaShop per eventuali errori correlati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "My AI Act Pro" segue l'architettura MVC (Model-View-Controller) standard di PrestaShop. Sfrutta `ObjectModel` per le interazioni con il database, registra vari hook per la visualizzazione del front-office e include controller admin dedicati per la configurazione e la gestione dei dati. Il modulo introduce diverse classi personalizzate per incapsulare la logica di business specifica relativa alla conformità all'AI Act, come la gestione delle API, la gestione del layout dei badge e la registrazione degli audit. Include anche controller frontali per l'esecuzione di API e CRON job, consentendo integrazioni esterne e attività pianificate.

### 4.2 Controller (`controllers/`)

#### Controller del Front-Office

-   `controllers/front/api.php`
    -   **Nome classe e classe genitore:** `MyaiactproApiModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller gestisce gli endpoint API REST del modulo. Elabora le richieste in entrata (ad esempio, per contrassegnare i prodotti come generati dall'IA, recuperare lo stato AI) e restituisce risposte JSON. È responsabile della convalida della chiave API e dell'invio delle richieste ai metodi appropriati della classe `AiActApi`.
-   `controllers/front/cron.php`
    -   **Nome classe e classe genitore:** `MyaiactproCronModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller funge da endpoint per i CRON job del modulo, in particolare per l'applicazione della filigrana. Quando viene acceduto tramite un'attività pianificata, attiva il processo di filigrana per le immagini generate dall'IA.
-   `controllers/front/index.php`
    -   **Nome classe e classe genitore:** `MyaiactproIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Un controller frontale segnaposto o predefinito. In molti moduli, questo potrebbe gestire una rotta predefinita o un reindirizzamento. Per questo modulo, potrebbe essere un fallback o utilizzato per interazioni front-office specifiche e semplici non coperte da `api.php` o `cron.php`.

#### Controller Admin del Back-Office

-   `controllers/admin/AdminMyAiActBulkController.php`
    -   **Nome scheda ed entità gestita:** Accessibile tramite **AI Act > Gestione prodotti in blocco**. Gestisce indirettamente l'entità `product` consentendo aggiornamenti in blocco al loro stato AI Act.
    -   **Responsabilità:** Fornisce un'interfaccia a griglia per elencare i prodotti e applicare azioni in blocco relative alla conformità all'AI Act (ad esempio, contrassegnare i prodotti come generati dall'IA, applicare tag). Gestisce l'invio di moduli per gli aggiornamenti in blocco.
-   `controllers/admin/AdminMyAiActLogsController.php`
    -   **Nome scheda ed entità gestita:** Accessibile tramite **AI Act > Registri di audit**. Gestisce l'entità `aiact_audit_log`.
    -   **Responsabilità:** Visualizza un elenco paginato di voci del registro di audit, fornendo una cronologia degli eventi relativi all'AI Act. Gestisce il filtraggio e la visualizzazione dei dettagli del registro.
-   `controllers/admin/index.php`
    -   **Nome classe e classe genitore:** `MyaiactproAdminIndexModuleAdminController` estende `ModuleAdminController`.
    -   **Nome scheda ed entità gestita:** Tipicamente un controller admin predefinito o introduttivo per la voce di menu principale del modulo.
    -   **Responsabilità:** Può fungere da reindirizzamento alla configurazione principale o a una dashboard per il modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   `classes/AiActApi.php`
    -   **Tabella database:** Nessuna interazione diretta con la tabella, ma interagisce con `AiActApiKey` e `AiActAuditLog`.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Gestisce l'analisi delle richieste API, l'autenticazione e l'invio di azioni per aggiornare lo stato AI del prodotto.
-   `classes/AiActApiDocumentation.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Genera e fornisce documentazione per l'API REST del modulo, tipicamente per la visualizzazione nel Back Office.
-   `classes/AiActApiKey.php`
    -   **Tabella database:** `ps_myaiactpro_api_key`
    -   **Estende `ObjectModel`:** Sì.
    -   **Campi `$definition`:** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
    -   **Metodi pubblici chiave:** Gestisce la creazione, il recupero, la convalida e l'eliminazione delle chiavi API per un accesso sicuro all'API.
-   `classes/AiActAuditLog.php`
    -   **Tabella database:** `ps_myaiactpro_audit_log`
    -   **Estende `ObjectModel`:** Sì.
    -   **Campi `$definition`:** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
    -   **Metodi pubblici chiave:** Registra e recupera le voci del registro di audit per le azioni di conformità all'AI Act.
-   `classes/AiActBadgeLayout.php`
    -   **Tabella database:** `ps_myaiactpro_badge_layout`
    -   **Estende `ObjectModel`:** Sì.
    -   **Campi `$definition`:** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
    -   **Metodi pubblici chiave:** Gestisce la creazione, l'archiviazione e il recupero di layout visivi personalizzati per i badge di divulgazione AI.
-   `classes/AiActConfigureUi.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Classe helper per la costruzione e il rendering dei moduli di configurazione del modulo nel Back Office, astraendo gli elementi dell'interfaccia utente.
-   `classes/AiActDisplayResolver.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Determina quali divulgazioni AI Act (badge, banner, ecc.) devono essere visualizzate nel front office in base alle impostazioni del modulo, allo stato del prodotto e al contesto attuale.
-   `classes/AiActFlag.php`
    -   **Tabella database:** `ps_myaiactpro_product_flag` (o simile, che collega i prodotti allo stato AI)
    -   **Estende `ObjectModel`:** Sì (probabilmente, o una classe personalizzata che gestisce le relazioni stato prodotto-AI).
    -   **Campi `$definition`:** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
    -   **Metodi pubblici chiave:** Gestisce lo stato generato dall'IA dei singoli prodotti e i loro layout di badge associati.
-   `classes/AiActIconCatalog.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Fornisce un elenco o un catalogo di icone disponibili per l'uso nei layout dei badge, spesso integrandosi con Font Awesome o librerie di icone simili.
-   `classes/AiActShortcode.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Elabora e renderizza shortcode personalizzati incorporati nel contenuto, sostituendoli con elementi di divulgazione AI.
-   `classes/AiActTagRule.php`
    -   **Tabella database:** `ps_myaiactpro_tag_rule` (o simile per tag/regole personalizzate)
    -   **Estende `ObjectModel`:** Sì.
    -   **Campi `$definition`:** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
    -   **Metodi pubblici chiave:** Gestisce regole o tag personalizzati che possono essere applicati ai prodotti per divulgazioni AI più specifiche oltre a un semplice flag "generato dall'IA".
-   `classes/index.php`
    -   **Tabella database:** Nessuna.
    -   **Estende `ObjectModel`:** No.
    -   **Metodi pubblici chiave:** Tipicamente un file vuoto per impedire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (probabilmente per la ricerca di prodotti nella gestione in blocco).
    -   **Descrizione:** Fornisce la funzionalità di completamento automatico per i campi di input, tipicamente utilizzata nei moduli di amministrazione per la ricerca di prodotti, categorie o altre entità.
-   `views/js/admin_api.js`
    -   **Ambito:** Back-office (scheda API e integrazioni).
    -   **Descrizione:** Gestisce le interazioni lato client per l'interfaccia di gestione delle chiavi API, inclusa la generazione di nuove chiavi, la revoca delle chiavi e la visualizzazione dei modali di documentazione API.
-   `views/js/admin_icon_picker.js`
    -   **Ambito:** Back-office (Studio di Layout).
    -   **Descrizione:** Gestisce l'interfaccia di selezione delle icone all'interno dello Studio di Layout, consentendo agli amministratori di sfogliare e selezionare le icone per i badge.
-   `views/js/admin_layouts.js`
    -   **Ambito:** Back-office (Studio di Layout).
    -   **Descrizione:** Alimenta l'interfaccia dello Studio di Layout, gestendo gli aggiornamenti dell'anteprima in tempo reale, le regolazioni dello stile (colori, ombre, sfumature) e l'invio dei moduli per i layout dei badge.
-   `views/js/front.js`
    -   **Ambito:** Front-office.
    -   **Descrizione:** Contiene la logica lato client per la visualizzazione e l'interazione con gli elementi di divulgazione AI nel front office. Ciò potrebbe includere:
        -   Inizializzazione di tooltip o popover dei badge.
        -   Gestione degli eventi di clic sui badge per rivelare maggiori informazioni o navigare alla pagina della politica AI.
        -   Garantire la reattività mobile degli elementi di divulgazione.
-   `views/js/tinymce_ai_button.js`
    -   **Ambito:** Back-office (editor prodotto/CMS).
    -   **Descrizione:** Integra un pulsante personalizzato nell'editor TinyMCE (utilizzato per le descrizioni dei prodotti e le pagine CMS) per inserire facilmente gli shortcode dell'AI Act.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Stili per i campi di input di ricerca con completamento automatico e i loro risultati a discesa, utilizzati nei moduli di amministrazione.
-   `views/css/admin.css`
    -   **Ambito:** Stile dei moduli di amministrazione del Back-office.
    -   **Descrizione:** Contiene regole di stile generali per le interfacce del Back Office del modulo, inclusa la pagina di configurazione, la gestione in blocco, i registri di audit e lo studio di layout. Gli sviluppatori possono sovrascrivere classi come `.myaiactpro-admin-form`, `.myaiactpro-layout-preview`, ecc.
-   `views/css/front.css`
    -   **Ambito:** Stile del cliente del Front-office.
    -   **Descrizione:** Fornisce lo stile predefinito per i badge di divulgazione AI, i banner e altri elementi del front-office. I selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema includono:
        -   `.myaiactpro-badge` (per il contenitore principale del badge)
        -   `.myaiactpro-badge-icon` (per l'icona all'interno del badge)
        -   `.myaiactpro-badge-text` (per il testo all'interno del badge)
        -   `.myaiactpro-banner` (per il banner di divulgazione a livello di sito)
        -   `.myaiactpro-additional-info` (per blocchi di informazioni aggiuntive)
        -   `.myaiactpro-human-fallback` (per messaggi di fallback umano)

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `hook/additional_info.tpl`
    -   **Hook:** Potenzialmente `displayProductExtraContent` o hook personalizzato.
    -   **Output:** Renderizza un blocco di informazioni aggiuntive nella pagina del prodotto, spesso utilizzato per divulgazioni AI dettagliate o link alla politica.
-   `hook/ai_badge.tpl`
    -   **Hook:** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock`, o hook personalizzati.
    -   **Output:** Renderizza il badge di divulgazione AI nelle pagine o negli elenchi dei prodotti, utilizzando il layout selezionato.
-   `hook/banner.tpl`
    -   **Hook:** `displayHeader`, `displayFooter`.
    -   **Output:** Renderizza il banner di divulgazione AI a livello di sito.
-   `hook/human_fallback.tpl`
    -   **Hook:** Potenzialmente `displayProductExtraContent` o hook personalizzato.
    -   **Output:** Renderizza il messaggio di fallback umano nelle pagine pertinenti.
-   `hook/shortcode_badge.tpl`
    -   **Hook:** Renderizzato dinamicamente dalla classe `AiActShortcode`.
    -   **Output:** Renderizza un badge AI specifico quando uno shortcode viene utilizzato nel contenuto.

#### Template di amministrazione (`views/templates/admin/`)

-   `admin/api.tpl`
    -   **Scopo:** Renderizza il pannello di configurazione API e integrazioni, inclusa la gestione delle chiavi API e la documentazione.
-   `admin/bulk_intro.tpl`
    -   **Scopo:** Fornisce un messaggio introduttivo o istruzioni per la schermata di gestione dei prodotti in blocco.
-   `admin/configure.tpl`
    -   **Scopo:** Il template di configurazione principale per il modulo, renderizzato da `getContent()`, contenente impostazioni generali, interruttori delle funzionalità e link ad altre schermate di amministrazione.
-   `admin/configure_shell.tpl`
    -   **Scopo:** Un template wrapper o shell per la pagina di configurazione principale, fornendo un layout coerente.
-   `admin/cron_box.tpl`
    -   **Scopo:** Visualizza le informazioni relative alla configurazione del CRON job, incluso il comando CRON.
-   `admin/layouts_form.tpl`
    -   **Scopo:** Renderizza il modulo per la creazione o la modifica di un layout di badge AI all'interno dello Studio di Layout.
-   `admin/layouts_list.tpl`
    -   **Scopo:** Visualizza l'elenco dei layout di badge AI esistenti nello Studio di Layout.
-   `admin/mass_settings.tpl`
    -   **Scopo:** Renderizza l'interfaccia per l'applicazione di impostazioni o azioni di massa ai prodotti, utilizzata nel controller di gestione in blocco.
-   `admin/overrides_entity.tpl`
    -   **Scopo:** Probabilmente per la gestione di override o eccezioni specifiche per le regole dell'AI Act su base per entità (ad esempio, per categoria, per produttore).
-   `admin/overrides_fields.tpl`
    -   **Scopo:** Renderizza i campi del modulo per la definizione delle regole di override.
-   `admin/overrides_list.tpl`
    -   **Scopo:** Visualizza un elenco di regole di override configurate.
-   `admin/partials/gradient_editor.tpl`
    -   **Scopo:** Un template parziale per il selettore/editor di colori sfumati utilizzato nello Studio di Layout.
-   `admin/partials/icon_picker.tpl`
    -   **Scopo:** Un template parziale per l'interfaccia di selezione delle icone utilizzata nello Studio di Layout.
-   `admin/partials/shadow_editor.tpl`
    -   **Scopo:** Un template parziale per l'editor di effetti ombra utilizzato nello Studio di Layout.
-   `admin/product_tab.tpl`
    -   **Scopo:** Renderizza il contenuto della scheda dedicata "Conformità AI Act" all'interno della pagina di modifica del prodotto di PrestaShop.
-   `admin/shortcodes.tpl`
    -   **Scopo:** Visualizza l'elenco degli shortcode disponibili e le loro istruzioni per l'uso.
-   `admin/_api_documentation_modal.tpl`
    -   **Scopo:** Renderizza il contenuto per un popup modale che visualizza la documentazione API.

#### Template del Front-office (`views/templates/front/`)

-   Nessuno esplicitamente elencato come template di pagina autonomi, indicando che il contenuto del front-office è principalmente renderizzato tramite hook.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_myaiactpro_api_key`: Memorizza le chiavi API per l'API REST del modulo.
    -   `id_myaiactpro_api_key` (PK)
    -   `key_value` (VARCHAR)
    -   `description` (TEXT)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_myaiactpro_audit_log`: Registra gli eventi relativi all'AI Act.
    -   `id_myaiactpro_audit_log` (PK)
    -   `id_employee` (INT)
    -   `id_customer` (INT)
    -   `id_product` (INT)
    -   `action` (VARCHAR)
    -   `details` (TEXT)
    -   `ip_address` (VARCHAR)
    -   `date_add` (DATETIME)
-   `ps_myaiactpro_badge_layout`: Memorizza layout visivi personalizzati per i badge AI.
    -   `id_myaiactpro_badge_layout` (PK)
    -   `name` (VARCHAR)
    -   `type` (VARCHAR)
    -   `icon_class` (VARCHAR)
    -   `text_content` (VARCHAR)
    -   `styles_json` (TEXT)
    -   `active` (TINYINT)
-   `ps_myaiactpro_product_flag`: Collega i prodotti al loro stato generato dall'IA e al layout del badge scelto.
    -   `id_product` (PK, INT)
    -   `is_ai_generated` (TINYINT)
    -   `id_myaiactpro_badge_layout` (INT, FK a `ps_myaiactpro_badge_layout`)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_myaiactpro_tag_rule`: Memorizza regole di tag AI Act personalizzate.
    -   `id_myaiactpro_tag_rule` (PK)
    -   `name` (VARCHAR)
    -   `description` (TEXT)
    -   `badge_layout_id` (INT, FK a `ps_myaiactpro_badge_layout`)
    -   `active` (TINYINT)
-   Record di configurazione in `ps_configuration`: Le impostazioni del modulo sono memorizzate qui (ad esempio, `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico | Template renderizzati |
| --- | --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS/JS, renderizza il banner superiore. | `hook/banner.tpl` (se configurato) |
| `displayFooter` | In fondo a ogni pagina. | Renderizza il banner inferiore, inietta JS. | `hook/banner.tpl` (se configurato) |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, solitamente sotto la descrizione. | Visualizza informazioni aggiuntive sulla divulgazione AI. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | Negli elenchi di prodotti, vicino al nome/immagine del prodotto. | Visualizza il badge AI sulle miniature dei prodotti. | `hook/ai_badge.tpl` |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Visualizza il badge AI nella pagina del prodotto. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto del Back Office. | Aggiungi una scheda dedicata per le impostazioni dell'AI Act. | `admin/product_tab.tpl` |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Aggiorna i flag/stato dell'AI Act per il prodotto. | N/A |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Pulisci i dati associati all'AI Act. | N/A |
| `actionFrontControllerSetMedia` | Prima che il controller frontale renderizzi il contenuto. | Registra CSS/JS del front-office. | N/A |
| `actionAdminControllerSetMedia` | Prima che il controller admin renderizzi il contenuto. | Registra CSS/JS del back-office. | N/A |
| `actionRegisterShortcode` | All'installazione/aggiornamento del modulo. | Registra shortcode personalizzati per l'analisi del contenuto. | N/A |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina admin. | Inietta CSS/JS admin. | N/A |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante il modulo "My AI Act Pro - Conformità all'Intelligenza Artificiale".
