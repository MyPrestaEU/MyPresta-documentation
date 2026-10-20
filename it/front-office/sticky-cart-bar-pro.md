---
title: "Sticky Cart Bar PRO - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sticky Cart Bar PRO di MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Sticky Cart Bar PRO su MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo Sticky Cart Bar PRO offre un potente set di opzioni di configurazione, divise in diverse aree chiave per la gestione delle tue barre adesive e dei test A/B.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Quando clicchi per la prima volta su "Configura" sul modulo, atterrerai su una dashboard che fornisce una panoramica e l'accesso alle sezioni principali. Questa pagina funge da hub centrale.

La pagina di configurazione principale per Sticky Cart Bar PRO è strutturata con schede o sezioni per gestire diversi aspetti del modulo.

#### Impostazioni generali / Panoramica della dashboard

Questa sezione presenta tipicamente un riepilogo delle tue barre attive, dei test A/B e collegamenti rapidi alle schermate di gestione principali.

-   **Cosa fa questa sezione:** Fornisce una panoramica di alto livello dello stato del tuo modulo e una navigazione rapida per creare nuove barre, gestire quelle esistenti o impostare test A/B.
-   **Effetto della modifica di questa impostazione:** Questa è principalmente una schermata di navigazione e informativa. Le modifiche qui implicano il clic su collegamenti ad altre schermate di gestione dedicate.
-   **Valore consigliato:** Rivedi regolarmente questa dashboard per monitorare le tue barre adesive e gli esperimenti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo presenta controller di amministrazione dedicati per la gestione delle tue barre adesive e dei test A/B, offrendo un'interfaccia completa per la progettazione, il targeting e l'analisi.

#### 2.2.1 Gestione delle barre del carrello adesive (Back Office > Moduli > Sticky Cart Bar PRO > **Gestisci Barre**)

Questa schermata è dove crei, modifichi e gestisci tutte le tue barre del carrello adesive.

-   **Nome schermata e posizione nel menu:** La trovi sotto **Moduli > Sticky Cart Bar PRO > Gestisci Barre** (o una voce di menu simile direttamente nella configurazione del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco delle barre:** Visualizza tutte le barre adesive create con informazioni chiave come nome, stato (attivo/inattivo) ed esperimenti assegnati.
        -   *Effetto:* Fornisce una visione organizzata di tutte le tue barre adesive.
        -   *Consigliato:* Mantieni i nomi delle barre descrittivi per una facile identificazione.
    -   **Pulsante Aggiungi Nuova Barra:** Avvia il processo di creazione di una nuova barra adesiva.
        -   *Effetto:* Apre il "Layout Studio" dove progetti la tua barra.
        -   *Consigliato:* Inizia con un obiettivo chiaro in mente per la tua nuova barra (es. "Barra inferiore pagina prodotto - Spedizione gratuita").
    -   **Pulsante Modifica (per barre esistenti):** Ti consente di modificare una barra adesiva esistente.
        -   *Effetto:* Riapre il Layout Studio con le impostazioni attuali della barra.
        -   *Consigliato:* Rivedi e aggiorna regolarmente le barre in base alle prestazioni o alle promozioni.
    -   **Pulsante Duplica:** Crea una copia esatta di una barra esistente.
        -   *Effetto:* Risparmia tempo quando crei barre simili o varianti per i test A/B.
        -   *Consigliato:* Usalo per creare rapidamente una nuova barra basata su un design di successo, quindi apporta piccole modifiche.
    -   **Attiva/Disattiva Stato:** Un interruttore per abilitare o disabilitare una barra senza eliminarla.
        -   *Effetto:* Una barra attiva apparirà sul tuo front office secondo le sue regole di targeting; una barra inattiva non lo farà.
        -   *Consigliato:* Disabilita le barre stagionali o non più pertinenti, piuttosto che eliminarle, nel caso ne avessi bisogno di nuovo.
    -   **Pulsante Elimina:** Rimuove permanentemente una barra adesiva.
        -   *Effetto:* La barra non apparirà più nel tuo negozio.
        -   *Consigliato:* Elimina solo le barre che sei certo di non utilizzare mai più.
    -   **Layout Studio (quando aggiungi/modifica una barra):** Questa è l'interfaccia di progettazione principale.
        -   **Editor Drag-and-Drop:** Ti consente di costruire visivamente la tua barra adesiva aggiungendo e organizzando gli elementi.
            -   *Effetto:* Puoi personalizzare il layout, il contenuto e l'aspetto della tua barra senza codificare.
            -   *Consigliato:* Sperimenta diverse combinazioni di elementi per trovare ciò che funziona meglio per i tuoi prodotti e il tuo pubblico.
        -   **Opzioni Elemento:** Ogni elemento (es. "Pulsante Aggiungi al carrello", "Immagine prodotto", "Timer conto alla rovescia", "Testo personalizzato") ha le proprie impostazioni per stile, contenuto e comportamento.
            -   *Effetto:* Affina l'aspetto e la funzionalità di ogni parte della tua barra.
            -   *Consigliato:* Presta attenzione a colori, font e dimensioni per abbinarli al branding del tuo negozio.
        -   **Preset:** Scegli da una libreria di layout di barre adesive pre-progettati.
            -   *Effetto:* Inizia rapidamente con una barra dall'aspetto professionale.
            -   *Consigliato:* Usa i preset come punto di partenza e poi personalizzali per adattarli alle tue esigenze specifiche.
        -   **Regole di Targeting:** Definisci *dove* e *a chi* la barra adesiva deve essere visualizzata.
            -   *Effetto:* Assicura che la tua barra sia mostrata solo ai clienti pertinenti su pagine specifiche.
            -   *Consigliato:* Targetizza categorie di prodotti, marchi o gruppi di clienti specifici per il massimo impatto. Esempi:
                -   *Visualizza su:* Tutte le pagine prodotto, ID prodotto specifici, categorie specifiche.
                -   *Gruppi di clienti:* Solo clienti loggati, nuovi visitatori, gruppi di clienti specifici.
                -   *Posizione geografica:* Solo clienti di determinati paesi.
                -   *Tipo di dispositivo:* Desktop, mobile o entrambi.
        -   **Posizione di Visualizzazione:** Scegli se la barra appare in alto o in basso nello schermo.
            -   *Effetto:* Controlla il posizionamento visivo della barra adesiva.
            -   *Consigliato:* Le barre inferiori sono spesso meno intrusive, mentre quelle superiori possono essere più prominenti. Prova entrambe!
        -   **Impostazioni di Visibilità:** Controlla quando la barra appare (es. dopo aver scorrendo una certa distanza, dopo un ritardo).
            -   *Effetto:* Impedisce che la barra appaia troppo presto o troppo tardi, ottimizzando l'esperienza utente.
            -   *Consigliato:* Un leggero ritardo o una soglia di scorrimento possono rendere la barra meno aggressiva.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Pianifica:** Decidi lo scopo della tua nuova barra adesiva (es. promuovere un prodotto specifico, offrire spedizione gratuita, ridurre l'abbandono del carrello).
    2.  **Crea:** Usa il pulsante "Aggiungi Nuova Barra" e il Layout Studio per progettare la tua barra. Inizia con un preset se non sei sicuro.
    3.  **Targetizza:** Imposta attentamente le regole di targeting per assicurarti che la barra appaia al pubblico giusto sulle pagine giuste.
    4.  **Attiva:** Imposta la barra su "Attiva" una volta che sei soddisfatto del suo design e del targeting.
    5.  **Monitora:** Usa la dashboard di analisi (vedi sezione successiva) per monitorarne le prestazioni.
    6.  **Ottimizza:** In base alle analisi, modifica la barra per migliorarne l'efficacia.

#### 2.2.2 Gestione dei test A/B (Back Office > Moduli > Sticky Cart Bar PRO > **Test A/B**)

Questa schermata ti consente di impostare e gestire i test A/B per le tue barre adesive, confrontando diverse versioni per vedere quale funziona meglio.

-   **Nome schermata e posizione nel menu:** La trovi sotto **Moduli > Sticky Cart Bar PRO > Test A/B**.
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco degli esperimenti:** Mostra tutti i tuoi test A/B attivi e completati, inclusi il loro stato, le date di inizio/fine e le metriche di performance.
        -   *Effetto:* Fornisce una panoramica dei tuoi sforzi di testing.
        -   *Consigliato:* Controlla regolarmente lo stato dei tuoi esperimenti.
    -   **Pulsante Aggiungi Nuovo Esperimento:** Avvia il processo di creazione di un nuovo test A/B.
        -   *Effetto:* Ti guida nella selezione di una barra di controllo e di una o più barre varianti.
        -   *Consigliato:* Prepara almeno due barre adesive (una di controllo, una variante) prima di iniziare un esperimento.
    -   **Configurazione dell'esperimento (quando aggiungi/modifica):**
        -   **Nome:** Un nome descrittivo per il tuo test A/B.
            -   *Effetto:* Ti aiuta a identificare l'esperimento in seguito.
            -   *Consigliato:* Usa nomi come "Barra inferiore pagina prodotto - Test colore pulsante" o "Barra superiore vs. Barra inferiore".
        -   **Barra di controllo:** La barra adesiva originale o predefinita che vuoi testare.
            -   *Effetto:* Questa è la tua base di riferimento per il confronto.
            -   *Consigliato:* Scegli la tua barra attualmente più performante o un design standard.
        -   **Barre varianti:** Una o più barre adesive alternative che vuoi testare.
            -   *Effetto:* Queste sono le versioni con modifiche che ritieni possano migliorare le prestazioni.
            -   *Consigliato:* Concentrati sul test di una modifica importante per variante (es. colore del pulsante diverso, messaggio diverso, posizione diversa).
        -   **Distribuzione del traffico:** Definisci quale percentuale del tuo pubblico vede ogni barra (controllo vs. varianti).
            -   *Effetto:* Assicura un confronto equo distribuendo il traffico in modo uniforme o come desiderato.
            -   *Consigliato:* Inizia con una distribuzione uniforme (es. 50/50 per due barre, 33/33/33 per tre).
        -   **Obiettivo:** Definisci la metrica che vuoi ottimizzare (es. clic "Aggiungi al carrello", tasso di conversione, entrate).
            -   *Effetto:* Il modulo traccerà questa metrica per ogni barra.
            -   *Consigliato:* Scegli un obiettivo chiaro e misurabile direttamente correlato al tuo obiettivo aziendale.
        -   **Regole di Targeting:** Simili al targeting delle barre, ma per l'esperimento stesso. Assicura che il test A/B venga eseguito solo per segmenti specifici.
            -   *Effetto:* Ti consente di eseguire esperimenti mirati senza influenzare l'intero pubblico.
            -   *Consigliato:* Se stai testando una barra per una categoria specifica, applica lo stesso targeting all'esperimento.
    -   **Pulsante Visualizza Analisi:** Accede a dati di performance dettagliati per un esperimento specifico.
        -   *Effetto:* Mostra quale barra ha performato meglio in base all'obiettivo definito.
        -   *Consigliato:* Lascia che gli esperimenti durino abbastanza a lungo da raccogliere dati statisticamente significativi prima di prendere decisioni.
    -   **Pulsante Interrompi Esperimento:** Termina un test A/B attivo.
        -   *Effetto:* Il modulo smetterà di mostrare le barre varianti e potrai scegliere di rendere permanente la barra vincente.
        *Consigliato:* Interrompi un esperimento una volta identificato un vincitore chiaro o se non sta producendo risultati utili.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Ipotizza:** Identifica un'area di miglioramento (es. "Credo che un pulsante 'Aggiungi al carrello' rosso avrà prestazioni migliori di uno verde").
    2.  **Crea Varianti:** Duplica la tua barra adesiva esistente e apporta la modifica specifica che vuoi testare (es. cambia il colore del pulsante).
    3.  **Imposta l'Esperimento:** Vai alla schermata Test A/B, clicca su "Aggiungi Nuovo Esperimento" e configura il tuo controllo, le varianti, il traffico e l'obiettivo.
    4.  **Avvia e Monitora:** Avvia l'esperimento e controlla regolarmente la dashboard di analisi per i progressi.
    5.  **Analizza e Implementa:** Una volta che l'esperimento si conclude o emerge un vincitore chiaro, implementa la barra vincente come predefinita.

#### 2.2.3 Dashboard di analisi (Back Office > Moduli > Sticky Cart Bar PRO > **Analisi**)

Questa schermata fornisce metriche di performance dettagliate per le tue barre adesive e i test A/B.

-   **Nome schermata e posizione nel menu:** La trovi sotto **Moduli > Sticky Cart Bar PRO > Analisi**.
-   **Azioni e impostazioni disponibili:**
    -   **Vista Dashboard:** Visualizza grafici e diagrammi che mostrano metriche chiave come impressioni, clic, tassi di click-through (CTR) e conversioni per le tue barre adesive.
        -   *Effetto:* Ti offre una chiara rappresentazione visiva di come stanno performando le tue barre.
        -   *Consigliato:* Usa questi dati per capire quali barre sono efficaci e quali necessitano di miglioramenti.
    -   **Opzioni di filtro:** Filtra i dati per intervallo di date, barra adesiva specifica o esperimento.
        -   *Effetto:* Ti consente di approfondire periodi specifici o confrontare le prestazioni delle singole barre.
        -   *Consigliato:* Confronta le prestazioni prima e dopo una modifica importante o una promozione.
    -   **Risultati test A/B:** Per esperimenti attivi o completati, questa sezione mostrerà chiaramente quale variante sta performando meglio rispetto al controllo, spesso con indicatori di significatività statistica.
        -   *Effetto:* Fornisce le prove necessarie per prendere decisioni basate sui dati riguardo ai design delle tue barre adesive.
        -   *Consigliato:* Non prendere decisioni basate su campioni di piccole dimensioni; attendi la significatività statistica.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Revisione regolare:** Controlla la dashboard di analisi settimanalmente o mensilmente per comprendere le tendenze generali delle prestazioni.
    2.  **Approfondimento:** Se una barra sta sottoperformando, usa i filtri per indagare periodi specifici o confrontarla con altre barre.
    3.  **Processo decisionale:** Usa i risultati dei test A/B per scegliere con sicurezza i design vincenti e implementarli in tutto il tuo negozio.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

Questo controller gestisce gli esperimenti di test A/B. Gestisce la creazione, la modifica, l'elenco e l'eliminazione delle entità `stickycartbar_experiment`.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

Questo controller gestisce le singole barre del carrello adesive. Gestisce la creazione, la modifica, l'elenco e l'eliminazione delle entità `stickycartbar_bar`, incluso l'accesso al Layout Studio per la progettazione.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

Questo è un file segnaposto, tipicamente utilizzato per prevenire l'elenco diretto delle directory e non rappresenta una schermata configurabile di per sé.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Gestisci Barre** | Nome Barra | Descrittivo | Identifica la barra nel back office. |
|  | Layout Studio | N/A | Editor drag-and-drop per il contenuto e lo stile della barra. |
|  | Opzioni Elemento | Varia | Personalizza i singoli elementi (pulsanti, testo, immagini). |
|  | Preset | N/A | Modelli di avvio rapido per il design della barra. |
|  | Regole di Targeting | Tutte le Pagine Prodotto | Definisce dove e a chi viene mostrata la barra. |
|  | Posizione di Visualizzazione | Inferiore | Controlla se la barra è in alto o in basso nello schermo. |
|  | Impostazioni di Visibilità | Dopo lo scroll | Controlla quando la barra appare (ritardo, scroll). |
|  | Stato (Attivo/Inattivo) | Inattivo (inizialmente) | Abilita/disabilita la visualizzazione della barra nel front office. |
| **Test A/B** | Nome Esperimento | Descrittivo | Identifica il test A/B. |
|  | Barra di Controllo | Barra Esistente | La barra di riferimento per il confronto. |
|  | Barre Varianti | Nuova/e Barra/e Modificata/e | Le versioni alternative in fase di test. |
|  | Distribuzione del Traffico | Suddivisione equa | Come il pubblico è diviso tra le barre. |
|  | Obiettivo | Clic Aggiungi al Carrello | La metrica da ottimizzare (es. clic, conversioni). |
|  | Regole di Targeting | Tutte le Pagine Prodotto | Definisce dove viene eseguito l'esperimento. |
|  | Stato (Attivo/Interrotto) | Attivo | Controlla se l'esperimento è in esecuzione. |
| **Analisi** | Filtro Intervallo Date | Ultimi 30 giorni | Filtra i dati di performance per periodo. |
|  | Filtro Barra/Esperimento | Tutti | Filtra i dati per barre o test specifici. |
|  | Visualizzazione Metriche | Impressioni, Clic, CTR | Mostra i dati di performance per barre/esperimenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La mia barra adesiva non viene visualizzata sulle pagine prodotto. Cosa devo controllare?**
**R1:**

-   **La barra è "Attiva"?** Vai su **Moduli > Sticky Cart Bar PRO > Gestisci Barre** e assicurati che l'interruttore per la tua barra sia impostato su "Attiva".
-   **Controlla le Regole di Targeting:** Modifica la tua barra e rivedi le "Regole di Targeting". Assicurati che sia impostata per essere visualizzata sulle pagine corrette (es. "Tutte le Pagine Prodotto" o categorie/prodotti specifici) e per i gruppi di clienti corretti.
-   **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce che le nuove modifiche del modulo appaiano immediatamente.
-   **Posizione del Modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo di solito gestisca questo, se lo hai sganciato manualmente, non apparirà. Controlla **Design > Posizioni** e cerca "Sticky Cart Bar PRO" per assicurarti che sia agganciato a `displayHeader` o `displayFooter` (a seconda della posizione della tua barra).

**D2: La barra adesiva ha un aspetto strano o non corrisponde al design del mio tema.**
**R2:**

-   **Stile Layout Studio:** Vai su **Moduli > Sticky Cart Bar PRO > Gestisci Barre**, modifica la tua barra e usa le opzioni di stile del Layout Studio. Puoi personalizzare colori, font, dimensioni, padding e altro per ogni elemento e per la barra stessa.
-   **Conflitti con il Tema:** A volte, il CSS del tuo tema personalizzato potrebbe sovrascrivere lo stile del modulo. Se le opzioni di stile di base nel Layout Studio non risolvono il problema, potresti aver bisogno di un webmaster per ispezionare il CSS (vedi sezione Sviluppatore).
-   **Compatibilità del Modulo:** Assicurati di aver scaricato la versione corretta del modulo per la tua versione di PrestaShop.

**D3: Come posso tradurre il testo nella mia barra adesiva in altre lingue?**
**R3:**

-   **Traduzioni del Modulo:** Per i testi statici all'interno del modulo (come le etichette dei pulsanti se non personalizzate), vai su **Internazionale > Traduzioni**. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, seleziona "Sticky Cart Bar PRO" e poi la lingua in cui vuoi tradurre.
-   **Elementi di Testo Personalizzati:** Se hai aggiunto elementi di testo personalizzati usando il Layout Studio, dovrai modificare la barra per ogni lingua. Durante la modifica della barra, dovresti vedere un'opzione per cambiare le lingue per gli input di testo, permettendoti di inserire le traduzioni direttamente all'interno del Layout Studio.

**D4: Il mio test A/B non mostra risultati chiari o sembra bloccato.**
**R4:**

-   **Durata e Traffico:** I test A/B necessitano di tempo e traffico sufficienti per raccogliere dati statisticamente significativi. Assicurati che il tuo esperimento sia in esecuzione da abbastanza tempo (almeno qualche settimana) e abbia ricevuto abbastanza visitatori per trarre conclusioni.
-   **Obiettivo Chiaro:** Ricontrolla che il tuo test A/B abbia un "Obiettivo" chiaramente definito (es. clic "Aggiungi al carrello"). Senza un obiettivo, il modulo non può misurare il successo.
-   **Nessuna Modifica Importante al Negozio:** Evita di apportare modifiche significative al tuo negozio (es. nuovo tema, promozioni importanti) mentre un test A/B è in corso, poiché ciò può distorcere i risultati.

**D5: Posso avere più barre adesive attive contemporaneamente?**
**R5:** Sì, puoi creare e attivare più barre adesive. Tuttavia, devi configurare attentamente le loro **Regole di Targeting** per evitare conflitti. Ad esempio, potresti avere una barra per "Tutte le Pagine Prodotto" in basso e un'altra barra specifica per "Prodotti Categoria X" in alto. Il modulo darà priorità alle barre in base alla loro specificità e logica interna, ma è buona pratica assicurarsi che le tue regole di targeting non si sovrappongano in modo tale da causare la visualizzazione di due barre nella stessa posizione sulla stessa pagina.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente riservata a sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Sticky Cart Bar PRO segue una robusta architettura PrestaShop MVC (Model-View-Controller), sfruttando pesantemente `ObjectModel` per la persistenza dei dati e `ModuleFrontController`/`AdminController` per la gestione delle richieste. Impiega un sistema sofisticato per la costruzione del layout, i test A/B e l'analisi, con classi dedicate per la configurazione, lo stile, il targeting e la risoluzione degli esperimenti. Il modulo utilizza un approccio modulare, separando le preoccupazioni in classi distinte per una migliore manutenibilità ed estensibilità. Il rendering del front-office è principalmente basato su hook, con AJAX per le interazioni dinamiche.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    -   **Nome Classe:** `StickyCartBarProAjaxModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce tutte le richieste AJAX dal front-office della barra adesiva. Questo include:
        -   Tracciamento impressioni e clic per l'analisi.
        -   Aggiornamento dinamico delle informazioni del carrello (es. aggiunta prodotti, modifica quantità).
        -   Risoluzione di quale variante della barra adesiva visualizzare per i test A/B.
        -   Recupero dei dati del prodotto per i selettori di varianti o i suggerimenti di cross-selling.
        -   Restituisce risposte JSON.
-   `controllers/front/index.php`
    -   **Nome Classe:** `StickyCartBarProIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Un controller frontale segnaposto. Tipicamente, potrebbe essere utilizzato per una pagina predefinita del modulo, ma in questo modulo, il rendering del front-office è principalmente gestito tramite hook e AJAX. Potrebbe servire come fallback o come base per future funzionalità.

#### Controller Admin Back-Office

-   `controllers/admin/AdminStickyCartBarAbController.php`
    -   **Nome Classe:** `AdminStickyCartBarAbController` (estende `AdminController`)
    -   **Nome Tab:** Test A/B (all'interno del menu principale del modulo)
    -   **Entità Gestita:** `StickyCartBarExperiment` (mappata alla tabella `ps_stickycartbar_experiment`).
    -   **Responsabilità:** Gestisce le operazioni CRUD per gli esperimenti di test A/B. Questo include:
        -   Elenco di tutti gli esperimenti in un `HelperList`.
        -   Fornitura di un `HelperForm` per la creazione e la modifica dei dettagli dell'esperimento (nome, barra di controllo, barre varianti, distribuzione del traffico, obiettivo, regole di targeting).
        -   Gestione dell'attivazione/disattivazione dell'esperimento e della visualizzazione dei risultati.
-   `controllers/admin/AdminStickyCartBarProController.php`
    -   **Nome Classe:** `AdminStickyCartBarProController` (estende `AdminController`)
    -   **Nome Tab:** Gestisci Barre (all'interno del menu principale del modulo)
    -   **Entità Gestita:** `StickyCartBarLayout` (mappata alla tabella `ps_stickycartbar_bar`).
    -   **Responsabilità:** Gestisce le operazioni CRUD per le singole barre del carrello adesive. Questo controller si integra con il "Layout Studio" per la progettazione visiva.
        -   Elenco di tutte le barre adesive in un `HelperList`.
        -   Fornitura dell'interfaccia per il Layout Studio drag-and-drop, inclusa la configurazione degli elementi, lo stile e le regole di targeting.
        -   Gestisce il salvataggio e il caricamento delle configurazioni delle barre, inclusa la struttura HTML, il CSS e le impostazioni JavaScript.
-   `controllers/admin/index.php`
    -   **Nome Classe:** N/A (file segnaposto)
    -   **Responsabilità:** Impedisce l'elenco diretto delle directory per motivi di sicurezza.

### 4.3 Classi e Modelli Core (`classes/`)

-   `classes/index.php`: File segnaposto per impedire l'elenco delle directory.
-   `classes/ScbpCompatibility.php`: Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (es. differenze di `Context`, metodi helper specifici).
-   `classes/StickyCartBarAdminUi.php`: Classe utility per la generazione di elementi UI comuni o la gestione di logiche UI specifiche all'interno del pannello di amministrazione.
-   `classes/StickyCartBarAnalytics.php`: Gestisce la raccolta, l'archiviazione e il recupero dei dati analitici per le barre adesive e i test A/B (impressioni, clic, conversioni).
-   `classes/StickyCartBarConfig.php`: Gestisce le impostazioni di configurazione specifiche del modulo memorizzate in `ps_configuration` (es. abilitazione/disabilitazione globale del modulo, impostazioni predefinite).
-   `classes/StickyCartBarElementStyles.php`: Gestisce le proprietà di stile e la generazione di CSS per i singoli elementi all'interno di una barra adesiva.
-   `classes/StickyCartBarExperiment.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `ps_stickycartbar_experiment`
    -   **Campi `$definition`:** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
    -   **Metodi Pubblici Chiave:** Operazioni CRUD, metodi per recuperare barre di controllo/varianti, calcolare i risultati dell'esperimento.
-   `classes/StickyCartBarExperimentMatcher.php`: Determina se le regole di targeting di un dato esperimento corrispondono al contesto attuale (cliente, pagina, dispositivo).
-   `classes/StickyCartBarExperimentResolver.php`: Dato un set di esperimenti attivi, determina quale barra adesiva (controllo o variante) deve essere visualizzata al visitatore corrente in base alla distribuzione del traffico e alle regole dell'esperimento.
-   `classes/StickyCartBarExperimentRule.php`: Rappresenta una singola regola di targeting all'interno di un esperimento.
-   `classes/StickyCartBarExperimentVariant.php`: Rappresenta una barra adesiva variante all'interno di un test A/B.
-   `classes/StickyCartBarLayout.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `ps_stickycartbar_bar`
    -   **Campi `$definition`:** `id_stickycartbar_bar`, `name`, `content` (JSON per elementi, stili, impostazioni), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
    -   **Metodi Pubblici Chiave:** Operazioni CRUD, metodi per renderizzare la barra, recuperare i suoi elementi, applicare stili.
-   `classes/StickyCartBarLayoutInstances.php`: Gestisce le istanze dei layout delle barre adesive, potenzialmente per la cache o l'accesso in fase di esecuzione.
-   `classes/StickyCartBarLayoutPreset.php`: Rappresenta un singolo layout di barra adesiva pre-progettato.
-   `classes/StickyCartBarLayoutPresets.php`: Gestisce la collezione di preset di layout disponibili.
-   `classes/StickyCartBarLayoutPresetsBuiltin.php`: Contiene le definizioni per i preset di layout predefiniti e integrati del modulo.
-   `classes/StickyCartBarListPresenter.php`: Classe helper per la formattazione e la presentazione dei dati negli elenchi di amministrazione (es. `HelperList`).
-   `classes/StickyCartBarMatcher.php`: Determina se le regole di targeting di una barra adesiva (per una barra non sperimentale) corrispondono al contesto attuale.
-   `classes/StickyCartBarRule.php`: Rappresenta una singola regola di targeting per una barra adesiva.
-   `classes/StickyCartBarTargeting.php`: Classe centrale per la valutazione di tutte le regole di targeting (sia per le barre che per gli esperimenti) rispetto al contesto attuale del front-office.

### 4.4 Risorse JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`: Fornisce la funzionalità di autocompletamento, probabilmente utilizzata nell'amministrazione per selezionare prodotti, categorie o produttori per le regole di targeting.
-   `views/js/admin-ab-dashboard.js`: Gestisce gli elementi interattivi e la visualizzazione dei dati nella dashboard dei test A/B nel back office.
-   `views/js/admin-analytics-dashboard.js`: Gestisce grafici, filtri e visualizzazione dei dati nella dashboard di analisi.
-   `views/js/admin-audience-picker.js`: Alimenta l'interfaccia interattiva per la definizione delle regole di targeting del pubblico (es. selezione di gruppi di clienti, paesi).
-   `views/js/admin-element-editor.js`: Fornisce la logica JavaScript per la modifica dei singoli elementi all'interno del Layout Studio (es. apertura di modali per l'input di testo, selettori di colore).
-   `views/js/admin-layout-builder.js`: Il JavaScript principale per il Layout Studio drag-and-drop, che gestisce il posizionamento, il ridimensionamento e l'interazione degli elementi.
-   `views/js/admin-layout-preview.js`: Gestisce l'anteprima in tempo reale della barra adesiva all'interno del Layout Studio.
-   `views/js/admin-layout-studio.js`: Orchesta tutti i componenti del Layout Studio, combinando le funzionalità di builder, editor e anteprima.
-   `views/js/admin.js`: JavaScript generico per le pagine del back-office del modulo, inclusi listener di eventi globali, invii di moduli e chiamate AJAX.
-   `views/js/front.js`: Il JavaScript principale del front-office per la barra adesiva.
    -   **Ambito:** Front-office.
    -   **Listener di eventi:** Scroll (per rilevare quando mostrare/nascondere la barra), clic sui pulsanti "Aggiungi al carrello" all'interno della barra, clic sui selettori di varianti, invii di moduli.
    -   **Manipolazione del DOM:** Inserisce l'HTML della barra adesiva nel DOM, aggiorna le quantità del carrello, cambia le varianti del prodotto, mostra/nasconde elementi (es. timer FOMO).
    -   **Chiamate AJAX:** Comunica con `controllers/front/ajax.php` per tracciare eventi, aggiornare il carrello e recuperare contenuti dinamici.
    -   **SDK di terze parti:** Nessuno esplicitamente elencato, ma potrebbe potenzialmente integrarsi con piattaforme di analisi se configurato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`: Stili per lo strumento di ricerca con autocompletamento nell'amministrazione.
-   `views/css/admin-audience-picker.css`: Stili per l'interfaccia di targeting del pubblico nell'amministrazione.
-   `views/css/admin-bars-list.css`: Stili per l'elenco delle barre adesive nell'amministrazione.
-   `views/css/admin-config.css`: Stili generali per la pagina di configurazione principale del modulo.
-   `views/css/admin-dashboard.css`: Stili per la dashboard principale del modulo e potenzialmente per le panoramiche di analisi/test A/B.
-   `views/css/admin-element-editor.css`: Stili per i modali/pannelli di modifica degli elementi all'interno del Layout Studio.
-   `views/css/admin-layout-builder.css`: Stili principali per l'interfaccia del builder di layout drag-and-drop.
-   `views/css/admin-layout-preview.css`: Stili per l'area di anteprima in tempo reale nel Layout Studio.
-   `views/css/admin-layout-studio.css`: Stili complessivi per il Layout Studio, che combinano tutti i suoi componenti.
-   `views/css/admin-searchtool.css`: Stili specifici per lo strumento di ricerca utilizzato nell'amministrazione.
-   `views/css/front-classic.css`: Stili front-office specifici per il tema "Classic" di PrestaShop.
    -   **Componenti UI principali:** Sovrascrive o aggiunge stili per garantire che la barra adesiva si integri bene con gli elementi predefiniti del tema Classic.
    -   **Selettori di classi CSS chiave:** `.scbp-bar`, `.scbp-button`, `.scbp-product-info`, ecc., potenzialmente con sovrascritture specifiche del tema.
-   `views/css/front-hummingbird.css`: Stili front-office specifici per il tema "Hummingbird" di PrestaShop (PrestaShop 8.1+).
    -   **Componenti UI principali:** Simile a `front-classic.css` ma adattato alla struttura e al design del tema Hummingbird.
    -   **Selettori di classi CSS chiave:** `.scbp-bar`, `.scbp-button`, ecc., con aggiustamenti specifici per Hummingbird.
-   `views/css/front.css`: Stili front-office generali per la barra adesiva, applicati a tutti i temi.
    -   **Componenti UI principali:** Stile di base per il contenitore della barra adesiva, i suoi elementi (pulsanti, testo, immagini, timer) e il posizionamento (fisso in alto/basso).
    -   **Selettori di classi CSS chiave:** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Gli sviluppatori possono sovrascrivere queste classi nel CSS personalizzato del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `sticky-cart-bar-classic.tpl`: Renderizza la barra adesiva specificamente per il tema Classic. Questo template probabilmente include una struttura HTML o nomi di classi specifici del tema per garantire un'integrazione perfetta.
    -   **Hook:** `displayHeader` o `displayFooter` (a seconda della posizione della barra e della logica interna del modulo).
    -   **Output:** La struttura HTML principale per la barra adesiva, inclusi i segnaposto per i contenuti dinamici.
-   `sticky-cart-bar-element-inner.tpl`: Renderizza il contenuto interno di un singolo elemento all'interno della barra adesiva. Questo è un parziale riutilizzabile.
    -   **Hook:** N/A (incluso da altri template).
    -   **Output:** HTML per un tipo di elemento specifico (es. nome prodotto, prezzo, input quantità).
-   `sticky-cart-bar-element.tpl`: Renderizza un singolo elemento (es. pulsante, immagine, blocco di testo) della barra adesiva, avvolgendo `sticky-cart-bar-element-inner.tpl` con wrapper di elementi comuni.
    -   **Hook:** N/A (incluso da altri template).
    -   **Output:** HTML per un singolo componente della barra adesiva stilizzato.
-   `sticky-cart-bar-hummingbird.tpl`: Renderizza la barra adesiva specificamente per il tema Hummingbird. Simile a `sticky-cart-bar-classic.tpl` ma adattato per il tema più recente.
    -   **Hook:** `displayHeader` o `displayFooter`.
    -   **Output:** La struttura HTML principale per la barra adesiva, ottimizzata per Hummingbird.
-   `sticky-cart-bar-inner.tpl`: Renderizza il contenuto interno dell'intera barra adesiva, contenente tutti i singoli elementi.
    -   **Hook:** N/A (incluso da `sticky-cart-bar.tpl`).
    -   **Output:** L'HTML combinato di tutti gli elementi configurati per una barra adesiva.
-   `sticky-cart-bar.tpl`: Il template principale responsabile del rendering della barra del carrello adesiva nel front office. Determina quale template specifico del tema (classic/hummingbird) includere o utilizza una struttura generica.
    -   **Hook:** `displayHeader` o `displayFooter` (il modulo si registra a questi hook).
    -   **Output:** La barra del carrello adesiva completa e renderizzata, inclusi il suo contenitore, gli elementi e gli attributi di dati necessari per JavaScript.

#### Template Admin (`views/templates/admin/`)

-   `ab-test-dashboard.tpl`: Renderizza la dashboard principale per i test A/B, mostrando elenchi di esperimenti e dati riassuntivi.
-   `ab-tests-tab.tpl`: Renderizza il contenuto per la scheda "Test A/B" all'interno della configurazione del modulo.
-   `analytics-dashboard.tpl`: Renderizza la dashboard di analisi con grafici e metriche di performance.
-   `audience-picker.tpl`: Renderizza l'HTML per l'interfaccia di selezione del targeting del pubblico (es. selettori di paese, gruppo di clienti).
-   `bars-tab.tpl`: Renderizza il contenuto per la scheda "Gestisci Barre", inclusa la lista delle barre adesive.
-   `configure.tpl`: Il template di configurazione principale per il modulo, che funge da wrapper per tutti gli altri template e schede di amministrazione.
-   `country-priority-picker.tpl`: Renderizza un componente UI specifico per la selezione e la prioritizzazione dei paesi nelle regole di targeting.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_stickycartbar_bar`: Memorizza la configurazione per ogni singola barra del carrello adesiva.
    -   `id_stickycartbar_bar` (PK, INT)
    -   `name` (VARCHAR)
    -   `content` (TEXT, codificato JSON: contiene elementi, stili, posizione, impostazioni di visibilità)
    -   `targeting_rules` (TEXT, codificato JSON: condizioni per la visualizzazione)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_experiment`: Memorizza la configurazione per ogni esperimento di test A/B.
    -   `id_stickycartbar_experiment` (PK, INT)
    -   `name` (VARCHAR)
    -   `id_control_bar` (INT, FK a `ps_stickycartbar_bar`)
    -   `id_variant_bars` (TEXT, array codificato JSON di FK a `ps_stickycartbar_bar`)
    -   `traffic_distribution` (TEXT, codificato JSON: percentuale per ogni barra)
    -   `goal` (VARCHAR: es. 'add\_to\_cart', 'conversion')
    -   `targeting_rules` (TEXT, codificato JSON)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_analytics`: Memorizza i dati analitici (impressioni, clic, conversioni) per barre ed esperimenti.
    -   `id_stickycartbar_analytics` (PK, INT)
    -   `id_stickycartbar_bar` (INT, FK)
    -   `id_stickycartbar_experiment` (INT, FK, NULLABLE)
    -   `type` (VARCHAR: 'impression', 'click', 'add\_to\_cart', 'conversion')
    -   `id_customer` (INT, NULLABLE)
    -   `id_guest` (INT, NULLABLE)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: Memorizza le impostazioni globali del modulo (es. `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Tabella degli hook registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta file CSS e JavaScript per la barra adesiva e potenzialmente la struttura HTML iniziale se la barra è posizionata in alto. |
| `displayFooter` | Prima del tag di chiusura `</body>` su ogni pagina. | Inietta la struttura HTML per le barre adesive posizionate in basso e qualsiasi inizializzazione JavaScript necessaria. |
| `actionFrontControllerSetMedia` | Dopo che un controller frontale ha impostato le sue risorse multimediali. | Consente al modulo di aggiungere condizionatamente il suo JS/CSS in base al contesto della pagina corrente (es. solo sulle pagine prodotto). |
| `actionProductUpdate` | Dopo che un prodotto viene aggiornato nel back office. | Potenzialmente utilizzato per svuotare la cache relativa ai dati del prodotto che potrebbero essere visualizzati nelle barre adesive. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Simile a `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto esistente. | Simile a `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Potenzialmente utilizzato per pulire eventuali riferimenti al prodotto eliminato nelle configurazioni delle barre adesive. |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato. | Utilizzato per tracciare gli eventi "Aggiungi al carrello" per l'analisi e gli obiettivi dei test A/B. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Utilizzato per tracciare gli eventi di conversione per l'analisi e gli obiettivi dei test A/B. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Inietta CSS e JavaScript per le interfacce di amministrazione del modulo (Layout Studio, dashboard). |
| `moduleRoutes` | Durante l'inizializzazione del routing URL. | Registra rotte front-office personalizzate per i controller AJAX, se necessario. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Sticky Cart Bar PRO, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
