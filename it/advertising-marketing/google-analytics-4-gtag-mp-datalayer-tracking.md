---
title: "Google Analytics 4 - gtag, MP & dataLayer tracking - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Google Analytics 4 - gtag, MP & dataLayer tracking di MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - gtag, MP & dataLayer tracking - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google Analytics 4 - gtag, MP & dataLayer tracking su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - gtag, MP & dataLayer tracking

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard come cURL, JSON e OpenSSL sono necessarie affinché il modulo funzioni correttamente, specialmente per il tracciamento Measurement Protocol lato server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Google Analytics 4 - gtag, MP & dataLayer tracking" offre un set completo di opzioni di configurazione, accessibili tramite la sua pagina di configurazione principale e le schermate di amministrazione dedicate.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale in cui imposterai il tuo tracciamento GA4. Il modulo utilizza un'interfaccia simile a una procedura guidata per guidarti attraverso la configurazione iniziale, ma puoi sempre rivedere e modificare le impostazioni.

#### **Procedura guidata di configurazione iniziale**

Alla prima configurazione, sarai probabilmente accolto da una procedura guidata. Segui i suoi passaggi per configurare rapidamente la tua proprietà GA4 principale.

-   **Passaggio 1: Scegli la modalità di tracciamento**

    *   **Cosa fa questa impostazione:** Determina come il tuo negozio invia i dati a Google Analytics 4. Questa è una decisione cruciale basata sulla tua configurazione tecnica e sui requisiti di privacy.
    *   **Effetto della modifica di questa impostazione:**
        *   *`gtag.js` (Consigliato per la maggior parte):* Questo è il tag web standard di Google Analytics 4. Carica una libreria JavaScript (`gtag.js`) direttamente sulle pagine del tuo negozio, che poi invia i dati a GA4. È facile da implementare ma si basa sull'esecuzione del browser lato client e sul consenso ai cookie.
        *   *`dataLayer` (Per gli utenti di Google Tag Manager):* Questa modalità inserisce tutti i dati degli eventi GA4 nell'oggetto `dataLayer`, che il tuo contenitore Google Tag Manager (GTM) legge e invia a GA4. Scegli questa opzione se utilizzi già GTM per altri tag e desideri una gestione centralizzata dei tag.
        *   *`Measurement Protocol` (Avanzato, per il massimo recupero dei dati):* Questa modalità invia i dati direttamente dal tuo server PrestaShop a Google Analytics 4, bypassando completamente il browser. Questo è l'ideale per recuperare i dati quando il tracciamento `gtag.js` o `dataLayer` è bloccato da ad-blocker, impostazioni del browser o consenso ai cookie negato. È più complesso ma fornisce la raccolta dati più robusta.
    *   **Valore consigliato:** `gtag.js` per semplicità, `dataLayer` se usi GTM, `Measurement Protocol` se l'accuratezza dei dati è fondamentale e ti senti a tuo agio con una configurazione avanzata.
    *   **Scenario / esempio del commerciante:** Se vuoi iniziare rapidamente e non usi GTM, `gtag.js` è perfetto. Se hai un team di marketing dedicato che gestisce GTM, `dataLayer` si integra perfettamente. Se stai riscontrando significative discrepanze tra le tue vendite e i dati GA4, `Measurement Protocol` può aiutare a colmare tale lacuna.
-   **Passaggio 2: Inserisci il/i tuo/i ID di misurazione GA4**

    *   **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco per la tua proprietà Google Analytics 4 (ad esempio, `G-XXXXXXXXXX`). Il modulo ne ha bisogno per sapere dove inviare i tuoi dati. Puoi aggiungere più ID se tracci diverse parti del tuo negozio in proprietà GA4 separate.
    *   **Effetto della modifica di questa impostazione:** I dati verranno inviati alla proprietà GA4 specificata. ID errati significano nessun dato o dati inviati nel posto sbagliato.
    *   **Valore consigliato:** Il tuo ID di misurazione GA4 principale.
    *   **Scenario / esempio del commerciante:** Hai una proprietà GA4 principale `G-ABCDEF1234`. Inserisci questo ID. Se vuoi anche inviare dati di prodotto specifici a una proprietà separata `G-XYZW5678`, puoi aggiungerla.
-   **Passaggio 3: Configura la gestione del consenso (se applicabile)**

    *   **Cosa fa questa impostazione:** Si integra con la soluzione di consenso ai cookie del tuo negozio per garantire che il tracciamento GA4 rispetti le scelte sulla privacy dell'utente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* I tag GA4 verranno attivati solo se l'utente ha concesso il consenso per i cookie di analisi.
        *   *Disabilitato:* I tag GA4 verranno attivati indipendentemente dal consenso (non consigliato per la conformità GDPR/CCPA).
    *   **Valore consigliato:** Abilitato, e assicurati di avere un modulo di consenso ai cookie robusto installato e configurato.
    *   **Scenario / esempio del commerciante:** Un cliente visita il tuo negozio e rifiuta i cookie di analisi. Con la gestione del consenso abilitata, gli script `gtag.js` o `dataLayer` non verranno caricati, impedendo il tracciamento lato client. Se stai utilizzando il Measurement Protocol, potresti comunque inviare dati di acquisto anonimizzati lato server.

#### **Impostazioni generali (dopo la procedura guidata)**

Una volta completata la procedura guidata, vedrai un'interfaccia di configurazione più dettagliata, spesso organizzata in schede.

-   **Gestione ID di misurazione**

    *   **Cosa fa questa impostazione:** Ti consente di aggiungere, modificare o rimuovere più ID di misurazione GA4 (`G-XXXXXXXXXX`) e associarli a modalità di tracciamento specifiche.
    *   **Effetto della modifica di questa impostazione:** Determina quali proprietà GA4 ricevono dati dal tuo negozio.
    *   **Valore consigliato:** Mantieni solo le proprietà GA4 necessarie.
    *   **Scenario / esempio del commerciante:** Hai creato una nuova proprietà GA4 per una specifica campagna di marketing. Puoi aggiungere il suo ID qui per tracciare le prestazioni specifiche della campagna.
-   **Domini di collegamento (per il tracciamento cross-domain)**

    *   **Cosa fa questa impostazione:** Se il tuo negozio opera su più domini (ad esempio, `shop.example.com` e `blog.example.com`), questa impostazione aiuta Google Analytics a capire che questi fanno parte dello stesso percorso utente, impedendo l'avvio di nuove sessioni quando un utente naviga tra di essi.
    *   **Effetto della modifica di questa impostazione:** Garantisce un tracciamento accurato del percorso utente su domini correlati. Senza di essa, gli utenti che si spostano tra i tuoi domini potrebbero essere contati come nuovi utenti o nuove sessioni.
    *   **Valore consigliato:** Aggiungi tutti i domini correlati che un utente potrebbe visitare come parte del suo percorso sul tuo sito.
    *   **Scenario / esempio del commerciante:** Il tuo negozio principale è `mystore.com` e il tuo blog è `blog.mystore.com`. Aggiungi `blog.mystore.com` all'elenco dei domini di collegamento.
-   **Modalità debug**

    *   **Cosa fa questa impostazione:** Attiva una speciale visualizzazione di debug nel front office e invia eventi di debug a GA4, consentendoti di verificare che il tuo tracciamento funzioni correttamente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* Un piccolo pannello di debug appare nel front office del tuo negozio, mostrando quali eventi GA4 vengono inviati. Gli eventi appaiono anche nella DebugView di GA4.
        *   *Disabilitato:* Nessun pannello di debug, tracciamento normale.
    *   **Valore consigliato:** Abilita solo durante i test e la risoluzione dei problemi. Disabilita per i negozi in produzione.
    *   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi confermare che gli eventi `add_to_cart` vengono attivati correttamente. Abilita la modalità debug, aggiungi un prodotto al carrello e controlla il pannello di debug e la DebugView di GA4.
-   **Coach qualità dati**

    *   **Cosa fa questa impostazione:** Fornisce approfondimenti e raccomandazioni per migliorare la qualità e la completezza dei tuoi dati GA4. Controlla problemi comuni come ID prodotto mancanti, formati di valuta errati, ecc.
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento diagnostico; non modifica direttamente il comportamento del front office ma ti aiuta a identificare e risolvere problemi che potrebbero portare ad analisi imprecise.
    *   **Valore consigliato:** Rivedi regolarmente le raccomandazioni.
    *   **Scenario / esempio del commerciante:** Il coach potrebbe dirti che ad alcuni prodotti mancano i codici EAN/UPC, che sono preziosi per i dati di prodotto GA4. Puoi quindi aggiornare il tuo catalogo prodotti.
-   **Dottore del catalogo**

    *   **Cosa fa questa impostazione:** Analizza il tuo catalogo prodotti per potenziali problemi che potrebbero influire sul tracciamento GA4, come prodotti senza prezzi, immagini o categorie valide.
    *   **Effetto della modifica di questa impostazione:** Simile al Coach qualità dati, questo è uno strumento diagnostico per garantire che i tuoi dati di prodotto siano robusti per GA4.
    *   **Valore consigliato:** Esegui periodicamente questo controllo.
    *   **Scenario / esempio del commerciante:** Il dottore potrebbe segnalare prodotti esauriti ma ancora visibili, il che potrebbe confondere il tracciamento GA4 delle visualizzazioni dei prodotti.
-   **Statistiche in tempo reale**

    *   **Cosa fa questa impostazione:** Visualizza i dati degli eventi in tempo reale inviati dal tuo negozio a GA4, direttamente nel back office di PrestaShop.
    *   **Effetto della modifica di questa impostazione:** Fornisce una panoramica immediata delle recenti interazioni e degli eventi degli utenti.
    *   **Valore consigliato:** Utile per il monitoraggio, specialmente dopo aver apportato modifiche o durante i picchi di traffico.
    *   **Scenario / esempio del commerciante:** Hai appena lanciato un nuovo prodotto. Puoi guardare le statistiche in tempo reale per vedere gli eventi `view_item` e `add_to_cart` in tempo reale.
-   **Mappatura e personalizzazione degli eventi**

    *   **Cosa fa questa impostazione:** Ti consente di personalizzare come le azioni di PrestaShop si mappano agli eventi GA4 e ai loro parametri. Ad esempio, potresti voler inviare un parametro personalizzato con l'evento `purchase`.
    *   **Effetto della modifica di questa impostazione:** Affina i dati inviati a GA4, consentendo una reportistica più specifica e la creazione di segmenti di pubblico.
    *   **Valore consigliato:** Modifica solo se hai esigenze specifiche di reportistica GA4.
    *   **Scenario / esempio del commerciante:** Vuoi includere un parametro personalizzato `loyalty_program_status` con ogni evento `purchase`. Puoi configurare questa mappatura qui.
-   **Regole multi-proprietà**

    *   **Cosa fa questa impostazione:** Definisce le regole per l'invio di eventi o dati specifici a diverse proprietà GA4. Ad esempio, potresti inviare tutti gli eventi alla tua proprietà principale ma solo gli eventi "acquisto" per una categoria specifica a una proprietà separata.
    *   **Effetto della modifica di questa impostazione:** Abilita la segmentazione avanzata dei tuoi dati analitici su più proprietà GA4.
    *   **Valore consigliato:** Utilizza se hai requisiti di tracciamento complessi che coinvolgono più proprietà GA4.
    *   **Scenario / esempio del commerciante:** Hai una proprietà GA4 principale per l'intero negozio, ma hai anche una proprietà separata per la tua linea di "Prodotti Premium". Puoi impostare una regola per inviare gli eventi `purchase` per i prodotti nella categoria "Prodotti Premium" a entrambe le proprietà.

### 2.2 Schermate di amministrazione dedicate e visualizzazioni del controller

Il modulo fornisce anche schermate dedicate per una gestione e una diagnostica più avanzate.

#### **AdminMyanalyticsAjaxController (Back Office > Moduli > Google Analytics 4 > [Varie schede])**

Questo controller gestisce molti degli elementi interattivi e delle visualizzazioni dei dati all'interno della configurazione del modulo, in particolare per gli strumenti diagnostici e le statistiche in tempo reale. Non navigherai direttamente a questo controller; esso alimenta il contenuto dinamico nella pagina di configurazione principale.

-   **Nome schermata e posizione menu:** Questo controller non è una voce di menu autonoma. Serve le richieste AJAX per le varie schede e sezioni all'interno della pagina di configurazione principale del modulo (ad esempio, "Coach qualità dati", "Dottore del catalogo", "Statistiche in tempo reale").
-   **Azioni e impostazioni disponibili:**
    *   **Griglia Coach qualità dati:** Visualizza una tabella dei problemi di qualità dei dati rilevati, spesso con suggerimenti per la risoluzione.
    *   **Report Dottore del catalogo:** Mostra un report sull'integrità dei dati del prodotto.
    *   **Flusso eventi in tempo reale:** Un feed in tempo reale degli eventi inviati a GA4.
    *   **Passaggi della procedura guidata:** Gestisce l'avanzamento e l'invio dei dati per la procedura guidata di configurazione iniziale.
-   **Effetto delle modifiche:** L'interazione con questi elementi (ad esempio, cliccando su "Esegui controllo" per il Coach qualità dati) attiva processi in background che analizzano i dati del tuo negozio e aggiornano le informazioni visualizzate. Ti aiuta a diagnosticare e risolvere i problemi, ma non modifica direttamente il comportamento del front office.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente le schede "Coach qualità dati" e "Dottore del catalogo" per assicurarti che i tuoi dati GA4 rimangano accurati. Monitora le "Statistiche in tempo reale" durante periodi critici o dopo importanti modifiche al negozio.

#### **index.php (Back Office > Moduli > Google Analytics 4)**

Questo è il punto di ingresso principale per la configurazione del modulo nel back office. Sebbene sia chiamato `index.php`, è il cuore del metodo `getContent()` che renderizza l'intera interfaccia di configurazione, incluse tutte le schede e le impostazioni descritte nella sezione 4.1.

-   **Nome schermata e posizione menu:** **Moduli > Gestione moduli > Google Analytics 4 - gtag, MP & dataLayer tracking > Configura**.
-   **Azioni e impostazioni disponibili:** Tutte le impostazioni, le schede e i passaggi della procedura guidata menzionati nella sezione 4.1 vengono renderizzati e gestiti tramite questa visualizzazione di configurazione principale.
-   **Effetto delle modifiche:** Qualsiasi modifica salvata su questa schermata influisce direttamente su come viene implementato il tuo tracciamento GA4 e quali dati vengono inviati a Google Analytics.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Qui configurerai inizialmente il modulo e tornerai per eventuali modifiche importanti alle tue proprietà GA4, modalità di tracciamento o regole avanzate.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Visualizzazione | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Config. principale | **Modalità di tracciamento** | `gtag.js` | Definisce come vengono inviati i dati (lato client, GTM o lato server). Cruciale per l'accuratezza dei dati e la privacy. |
| Config. principale | **ID di misurazione** | Il tuo ID GA4 (`G-XXXXXXXXXX`) | Specifica quale proprietà GA4 riceve i dati. ID errati significano nessun dato. |
| Config. principale | **Gestione del consenso** | Abilitato (se si usa un modulo di consenso) | Garantisce che il tracciamento GA4 rispetti le scelte sulla privacy dell'utente. |
| Config. principale | **Domini di collegamento** | Vuoto (aggiungi se cross-domain) | Abilita il tracciamento accurato degli utenti su più domini correlati. |
| Config. principale | **Modalità debug** | Disabilitato (abilita per i test) | Mostra un pannello di debug nel front office e invia eventi di debug a GA4. |
| Config. principale | **Coach qualità dati** | N/A (strumento diagnostico) | Identifica e suggerisce correzioni per i problemi di qualità dei dati GA4. |
| Config. principale | **Dottore del catalogo** | N/A (strumento diagnostico) | Analizza il catalogo prodotti per la prontezza al tracciamento GA4. |
| Config. principale | **Statistiche in tempo reale** | N/A (strumento di monitoraggio) | Visualizza gli eventi GA4 in tempo reale nel back office. |
| Config. principale | **Mappatura eventi** | Predefinito (modifica per esigenze personalizzate) | Personalizza come le azioni di PrestaShop si mappano agli eventi e ai parametri GA4. |
| Config. principale | **Regole multi-proprietà** | Nessuna (aggiungi per tracciamento avanzato) | Definisce le regole per l'invio di dati specifici a diverse proprietà GA4. |
| AdminMyanalyticsAjaxController | (Varie visualizzazioni basate su AJAX) | N/A | Alimenta il contenuto dinamico per gli strumenti diagnostici e le statistiche in tempo reale. |
| index.php | (Pagina di configurazione principale) | N/A | Renderizza l'intera interfaccia di configurazione del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho installato il modulo, ma non vedo alcun dato nella mia proprietà Google Analytics 4.**

-   **R:** Innanzitutto, assicurati di aver inserito l'ID di misurazione GA4 corretto (che inizia con `G-`) nella configurazione del modulo.
-   **R:** Controlla la "DebugView" della tua proprietà GA4 (in Google Analytics, vai su Amministrazione > DebugView) mentre navighi nel tuo negozio. Se vedi eventi lì, i dati vengono inviati.
-   **R:** Svuota la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).
-   **R:** Se stai utilizzando `gtag.js` o `dataLayer`, controlla la console per sviluppatori del tuo browser (F12) per eventuali errori JavaScript. Inoltre, assicurati di aver accettato i cookie di analisi se hai un modulo di consenso.
-   **R:** Se utilizzi il Measurement Protocol, assicurati che il tuo server abbia `cURL` abilitato e che non ci siano regole del firewall che bloccano le connessioni in uscita ai server di Google.

**D2: I miei dati di acquisto GA4 non corrispondono ai dati degli ordini di PrestaShop.**

-   **R:** Questo è un problema comune, spesso dovuto a ad-blocker, impostazioni sulla privacy del browser o utenti che rifiutano il consenso ai cookie.
-   **R:** **Considera fortemente l'abilitazione del Measurement Protocol per gli eventi di acquisto.** Questo invia i dati di acquisto direttamente dal tuo server, bypassando i problemi del browser lato client.
-   **R:** Utilizza il "Coach qualità dati" e il "Dottore del catalogo" del modulo per identificare eventuali incongruenze nei dati che potrebbero causare problemi.
-   **R:** Assicurati che la pagina di conferma dell'ordine sia sempre raggiunta dai clienti dopo un acquisto riuscito. Se i clienti vengono reindirizzati altrove o chiudono il browser troppo presto, gli eventi di acquisto lato client potrebbero non essere attivati.

**D3: Il pannello di debug del modulo non viene visualizzato o non vedo eventi nella DebugView di GA4.**

-   **R:** Assicurati che la "Modalità debug" sia esplicitamente abilitata nella configurazione del modulo.
-   **R:** Svuota la cache del browser e la cache Smarty di PrestaShop.
-   **R:** Assicurati di essere loggato come amministratore nel back office di PrestaShop e di navigare nel front office nella stessa sessione del browser.
-   **R:** Controlla la console per sviluppatori del tuo browser per eventuali errori JavaScript che potrebbero impedire il caricamento del pannello di debug.

**D4: Come mi assicuro che il modulo rispetti il mio modulo di consenso ai cookie?**

-   **R:** Il modulo è progettato per integrarsi con i meccanismi standard di consenso ai cookie. Nella configurazione del modulo, dovrebbe esserci un'impostazione per la "Gestione del consenso". Assicurati che sia abilitata.
-   **R:** Verifica che il tuo modulo di consenso ai cookie stia correttamente categorizzando i cookie di analisi e che le scelte degli utenti vengano memorizzate e rispettate. Il modulo GA4 caricherà quindi i tag lato client (`gtag.js`, `dataLayer`) solo se viene dato il consenso.
-   **R:** Per il massimo recupero dei dati, considera l'utilizzo del Measurement Protocol per eventi critici come `purchase`, poiché spesso può bypassare i problemi di consenso lato client (anche se dovresti comunque informare gli utenti sull'elaborazione dei dati).

**D5: Voglio tracciare eventi o parametri personalizzati non coperti dalla configurazione predefinita.**

-   **R:** Il modulo include una sezione "Mappatura e personalizzazione degli eventi". Qui puoi definire come le azioni di PrestaShop si mappano agli eventi GA4 e aggiungere parametri personalizzati.
-   **R:** Per un tracciamento personalizzato altamente complesso, specialmente con `dataLayer`, potresti dover combinare le capacità di questo modulo con script personalizzati nel tuo contenitore Google Tag Manager.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `myanalytics` per PrestaShop è progettato per fornire un'integrazione robusta e flessibile con Google Analytics 4. Segue un approccio modulare e orientato agli oggetti, sfruttando il pattern MVC e il sistema di hook di PrestaShop.

Componenti architettonici chiave:

-   **Classe principale del modulo (`Myanalytics`):** Gestisce l'installazione, la disinstallazione, la registrazione degli hook e il metodo `getContent()` primario per la configurazione del back-office.
-   **Fabbrica di tracker (`MyanalyticsTrackerFactory`):** Istanzia dinamicamente il meccanismo di tracciamento appropriato (`gtag.js`, `dataLayer` o `Measurement Protocol`) in base alla configurazione del modulo.
-   **Classi di tracker dedicate:** Ogni metodo di tracciamento (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implementa `MyanalyticsTrackerInterface` e incapsula la logica per l'invio di eventi GA4 tramite il suo metodo specifico.
-   **Mappatura degli eventi e gestione del Data Layer:** Classi come `MyanalyticsEvents` e `MyanalyticsDataLayerTracker` sono responsabili della traduzione delle azioni di PrestaShop (ad esempio, visualizzazione prodotto, aggiunta al carrello) in nomi di eventi e parametri conformi a GA4.
-   **Strumenti diagnostici:** Classi come `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor` e `MyanalyticsHealthScore` forniscono approfondimenti nel back-office sull'integrità dei dati e sulla salute del tracciamento.
-   **Controller di amministrazione:** Gestiscono le richieste AJAX per il contenuto dinamico nel back-office (ad esempio, statistiche in tempo reale, report diagnostici).
-   **Controller frontali:** Utilizzati principalmente per gli endpoint AJAX, specialmente per il fallback del Measurement Protocol o azioni relative al consenso.
-   **Template Smarty:** Utilizzati per il rendering sia delle visualizzazioni di configurazione del back-office che degli script di tracciamento del front-office iniettati tramite hook.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    *   **Nome classe e classe genitore:** `MyanalyticsAjaxModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce le richieste AJAX dal front office. Questo potrebbe includere l'invio di eventi del Measurement Protocol in scenari specifici (ad esempio, quando il tracciamento lato client è bloccato), l'aggiornamento dello stato del consenso o altre interazioni dinamiche che non richiedono un ricaricamento completo della pagina. Tipicamente restituisce risposte JSON.
-   `controllers/front/index.php`
    *   **Nome classe e classe genitore:** `MyanalyticsIndexModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller potrebbe fungere da fallback o da endpoint specifico per determinate funzionalità del modulo, sebbene spesso la classe principale del modulo gestisca la maggior parte dell'iniezione di script nel front office tramite hook. Potrebbe essere utilizzato per reindirizzamenti specifici o elaborazione dati se necessario.

#### Controller di amministrazione Back-Office

-   `controllers/admin/AdminMyanalyticsAjaxController.php`
    *   **Nome classe e classe genitore:** `AdminMyanalyticsAjaxController` estende `AdminController`.
    *   **Nome scheda ed entità gestita:** Questo controller non è direttamente accessibile come scheda di menu. Serve le richieste AJAX dalla pagina di configurazione principale del modulo (`getContent()`). Gestisce gli aggiornamenti dinamici per sezioni come il Coach qualità dati, il Dottore del catalogo, le Statistiche in tempo reale e i passaggi della procedura guidata di configurazione.
    *   **Responsabilità:** Elabora le richieste per report diagnostici, dati di eventi in tempo reale e invii di passaggi della procedura guidata, restituendo dati JSON per aggiornare l'interfaccia utente del back-office.
-   `controllers/admin/index.php`
    *   **Nome classe e classe genitore:** `AdminMyanalyticsIndexController` estende `AdminController`.
    *   **Nome scheda ed entità gestita:** Simile ad `AdminMyanalyticsAjaxController`, questo è probabilmente un controller interno o un segnaposto. La configurazione principale del back-office è gestita dal metodo `getContent()` della classe principale del modulo `Myanalytics`.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/autoload.php`: File di autoload standard di PrestaShop per le classi del modulo.
-   `classes/index.php`: File vuoto, pratica comune per prevenire l'elenco delle directory.
-   `classes/MyanalyticsCatalogDoctor.php`
    *   **Cosa fa:** Analizza il catalogo prodotti di PrestaShop per problemi di qualità dei dati rilevanti per il tracciamento GA4 (ad esempio, prezzi mancanti, immagini, categorie non valide).
    *   **Metodi pubblici chiave:** Metodi per eseguire controlli e recuperare report sullo stato del catalogo.
-   `classes/MyanalyticsConsent.php`
    *   **Cosa fa:** Gestisce e interagisce con i meccanismi di consenso ai cookie, determinando se il tracciamento analitico è consentito in base alle scelte dell'utente.
    *   **Metodi pubblici chiave:** Metodi per controllare lo stato del consenso, impostare il consenso e potenzialmente integrarsi con moduli di consenso di terze parti.
-   `classes/MyanalyticsCurrencyHelper.php`
    *   **Cosa fa:** Fornisce funzioni di utilità per la gestione della formattazione e della conversione della valuta, garantendo che GA4 riceva i dati della valuta nel formato corretto.
-   `classes/MyanalyticsDataLayerTracker.php`
    *   **Cosa fa:** Implementa `MyanalyticsTrackerInterface` per il tracciamento `dataLayer`. Inserisce i dati degli eventi GA4 nell'array JavaScript `dataLayer`, rendendoli disponibili per Google Tag Manager.
    *   **Metodi pubblici chiave:** Metodi per aggiungere eventi al dataLayer, gestire eventi e-commerce specifici (ad esempio, `add_to_cart`, `purchase`).
-   `classes/MyanalyticsDataQualityCoach.php`
    *   **Cosa fa:** Fornisce uno strumento diagnostico per identificare e segnalare potenziali problemi di qualità dei dati nel flusso di eventi GA4 o nella configurazione.
    *   **Metodi pubblici chiave:** Metodi per eseguire controlli di qualità dei dati e generare report.
-   `classes/MyanalyticsEventId.php`
    *   **Cosa fa:** Probabilmente una classe di utilità per generare ID evento univoci, che possono essere utili per la deduplicazione in GA4, specialmente con il Measurement Protocol.
-   `classes/MyanalyticsEventMap.php`
    *   **Cosa fa:** Definisce la mappatura tra azioni/dati di PrestaShop e nomi e parametri di eventi GA4 standard.
    *   **Metodi pubblici chiave:** Metodi per recuperare definizioni di eventi e mappature di parametri.
-   `classes/MyanalyticsEvents.php`
    *   **Cosa fa:** Una classe centrale per l'attivazione e la gestione degli eventi GA4 all'interno del modulo. Orchesta quale tracker (gtag, datalayer, MP) dovrebbe gestire quale evento.
    *   **Metodi pubblici chiave:** Metodi come `trackPageView()`, `trackAddToCart()`, `trackPurchase()`, ecc.
-   `classes/MyanalyticsGtagTracker.php`
    *   **Cosa fa:** Implementa `MyanalyticsTrackerInterface` per il tracciamento `gtag.js`. Genera e inietta il codice JavaScript necessario per inviare eventi direttamente a GA4 tramite `gtag()`.
    *   **Metodi pubblici chiave:** Metodi per generare chiamate `gtag()` per vari eventi GA4.
-   `classes/MyanalyticsHealthScore.php`
    *   **Cosa fa:** Calcola e visualizza un "punteggio di salute" per l'integrazione GA4, basato su vari controlli e migliori pratiche.
-   `classes/MyanalyticsLiveStats.php`
    *   **Cosa fa:** Raccoglie e fornisce statistiche in tempo reale sugli eventi inviati a GA4, visualizzate nel back office.
-   `classes/MyanalyticsMpClient.php`
    *   **Cosa fa:** Gestisce le effettive richieste HTTP per l'invio di dati a Google Analytics 4 tramite il Measurement Protocol.
    *   **Metodi pubblici chiave:** Metodi per costruire e inviare payload del Measurement Protocol.
-   `classes/MyanalyticsMpTracker.php`
    *   **Cosa fa:** Implementa `MyanalyticsTrackerInterface` per il tracciamento `Measurement Protocol`. Prepara i dati degli eventi e utilizza `MyanalyticsMpClient` per inviarli lato server.
    *   **Metodi pubblici chiave:** Metodi per formattare e inviare eventi lato server.
-   `classes/MyanalyticsProductIdResolver.php`
    *   **Cosa fa:** Risolve vari identificatori di prodotto (ID, riferimento, EAN, UPC) per garantire che i dati di prodotto coerenti vengano inviati a GA4.
-   `classes/MyanalyticsPropertyRules.php`
    *   **Cosa fa:** Gestisce la logica per il tracciamento multi-proprietà, definendo le regole per quali eventi vanno a quali proprietà GA4.
-   `classes/MyanalyticsTrackerFactory.php`
    *   **Cosa fa:** Una classe con pattern factory responsabile della creazione e restituzione dell'implementazione corretta di `MyanalyticsTrackerInterface` in base alla configurazione del modulo (gtag, datalayer o MP).
-   `classes/MyanalyticsTrackerInterface.php`
    *   **Cosa fa:** Definisce l'interfaccia comune che tutte le classi di tracker GA4 devono implementare, garantendo coerenza nel modo in cui gli eventi vengono gestiti.
-   `classes/MyanalyticsUserData.php`
    *   **Cosa fa:** Raccoglie e formatta i dati specifici dell'utente (ad esempio, ID utente, dati demografici) per il tracciamento GA4, rispettando le impostazioni sulla privacy.

### 4.4 Risorse JavaScript (`views/js/`)

-   `myanalytics/views/js/myanalytics-admin.js`
    *   **Ambito:** Back-office.
    *   **Cosa fa:** Fornisce funzionalità interattive per le pagine di configurazione del back-office del modulo. Ciò include la gestione degli invii di moduli, le chiamate AJAX per gli strumenti diagnostici (Coach qualità dati, Dottore del catalogo), l'aggiornamento delle statistiche in tempo reale e la gestione delle regole multi-proprietà.
-   `myanalytics/views/js/myanalytics-debug.js`
    *   **Ambito:** Front-office (quando la modalità debug è abilitata).
    *   **Cosa fa:** Inietta un pannello di debug nel front office, visualizzando gli eventi GA4 man mano che vengono attivati. Ascolta le chiamate `gtag()` o gli eventi `dataLayer.push()` e li renderizza per una facile verifica.
-   `myanalytics/views/js/myanalytics-ghost.js`
    *   **Ambito:** Front-office.
    *   **Cosa fa:** Questo script potrebbe essere correlato al tracciamento "fantasma" o "ombra", potenzialmente per il fallback del Measurement Protocol o per catturare eventi che altrimenti potrebbero essere persi. Potrebbe comportare l'ascolto di eventi DOM specifici e l'attivazione di chiamate lato server.
-   `myanalytics/views/js/myanalytics-live.js`
    *   **Ambito:** Back-office.
    *   **Cosa fa:** Alimenta la funzione "Statistiche in tempo reale" nel back office. Probabilmente utilizza AJAX per recuperare periodicamente gli eventi GA4 recenti dal server e aggiorna la visualizzazione in tempo reale.
-   `myanalytics/views/js/myanalytics-wizard.js`
    *   **Ambito:** Back-office.
    *   **Cosa fa:** Fornisce la logica interattiva per la procedura guidata di configurazione del modulo, guidando l'utente attraverso i passaggi di configurazione iniziali, convalidando gli input e inviando i dati tramite AJAX.
-   `myanalytics/views/js/myanalytics.js`
    *   **Ambito:** Front-office.
    *   **Cosa fa:** Il file JavaScript principale del front-office. Gestisce la logica di tracciamento GA4 lato client, inclusa:
        *   Inizializzazione di `gtag.js` o `dataLayer`.
        *   Ascolto di eventi DOM (ad esempio, clic sui pulsanti "Aggiungi al carrello", visualizzazioni di immagini di prodotti).
        *   Raccolta di dati rilevanti su prodotti e utenti.
        *   Invio di eventi a `dataLayer` o chiamate a comandi `gtag()`.
        *   Potenziale gestione dell'integrazione del consenso ai cookie.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `myanalytics/views/css/myanalytics-admin.css`
    *   **Ambito:** Stile del modulo di amministrazione del back-office.
    *   **Cosa fa:** Stila la pagina di configurazione del modulo, incluse schede, campi di input, pulsanti, report diagnostici e visualizzazioni delle statistiche in tempo reale, garantendo un'interfaccia coerente e intuitiva all'interno del back office di PrestaShop.
-   `myanalytics/views/css/myanalytics-debug.css`
    *   **Ambito:** Stile del cliente del front-office (quando la modalità debug è abilitata).
    *   **Cosa fa:** Stila il pannello di debug del front-office, rendendolo visivamente distinto e leggibile per sviluppatori e amministratori.

### 4.6 Struttura dei template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `myanalytics/views/templates/hook/debug.tpl`
    *   **Hook:** Probabilmente iniettato tramite `displayHeader` o `displayFooter` condizionalmente quando la modalità debug è attiva.
    *   **Output:** La struttura HTML per il pannello di debug del front-office.
-   `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
    *   **Hook:** `displayOrderConfirmation`.
    *   **Output:** Il codice JavaScript necessario o i push `dataLayer` per l'evento `purchase`, tipicamente inclusi i dettagli della transazione, le informazioni sul prodotto e potenzialmente i parametri del Measurement Protocol.
-   `myanalytics/views/templates/hook/ghost.tpl`
    *   **Hook:** Potrebbe essere `displayHeader` o `displayFooter`.
    *   **Output:** Codice JavaScript relativo al tracciamento "fantasma", potenzialmente per il fallback del Measurement Protocol o la cattura avanzata degli eventi.
-   `myanalytics/views/templates/hook/header.tpl`
    *   **Hook:** `displayHeader`.
    *   **Output:** Lo script di inizializzazione principale `gtag.js` o `dataLayer`, inclusi gli ID di misurazione GA4 e qualsiasi impostazione di configurazione globale. Questo è cruciale per il tracciamento iniziale delle visualizzazioni di pagina.
-   `myanalytics/views/templates/hook/mp-pageview.tpl`
    *   **Hook:** Probabilmente `displayHeader` o `displayFooter` (condizionalmente per il Measurement Protocol).
    *   **Output:** Codice renderizzato lato server per inviare un evento `page_view` tramite Measurement Protocol, particolarmente utile quando il tracciamento lato client è bloccato o il consenso è negato.
-   `myanalytics/views/templates/hook/payment.tpl`
    *   **Hook:** `displayPaymentTop` o hook simili relativi al pagamento.
    *   **Output:** Push JavaScript o `dataLayer` per gli eventi `add_payment_info` o `begin_checkout`, catturando la selezione del metodo di pagamento.
-   `myanalytics/views/templates/hook/product-details.tpl`
    *   **Hook:** `displayProductButtons`, `displayProductExtraContent` o hook simili della pagina prodotto.
    *   **Output:** Push JavaScript o `dataLayer` per gli eventi `view_item` e `add_to_cart`, incluse informazioni dettagliate sul prodotto.

#### Template di amministrazione (`views/templates/admin/`)

-   `myanalytics/views/templates/admin/doctor.tpl`: Renderizza l'interfaccia per il Dottore del catalogo, visualizzando report e raccomandazioni.
-   `myanalytics/views/templates/admin/dq.tpl`: Renderizza l'interfaccia per il Coach qualità dati, mostrando i problemi di qualità dei dati.
-   `myanalytics/views/templates/admin/health.tpl`: Visualizza il punteggio di salute complessivo e le metriche correlate per l'integrazione GA4.
-   `myanalytics/views/templates/admin/linker-domains.tpl`: Renderizza il campo di input e l'elenco per la gestione dei domini di collegamento cross-domain.
-   `myanalytics/views/templates/admin/live-maintain.tpl`: Probabilmente un sotto-template per le statistiche in tempo reale, possibilmente per messaggi di manutenzione o controlli.
-   `myanalytics/views/templates/admin/live.tpl`: Renderizza l'interfaccia principale per la funzione Statistiche in tempo reale, mostrando i dati degli eventi in tempo reale.
-   `myanalytics/views/templates/admin/measurement-ids.tpl`: Renderizza la sezione per la gestione di più ID di misurazione GA4.
-   `myanalytics/views/templates/admin/mode-context.tpl`: Fornisce informazioni contestuali o spiegazioni per la modalità di tracciamento scelta.
-   `myanalytics/views/templates/admin/mode-note-datalayer.tpl`: Note o istruzioni specifiche per la modalità di tracciamento `dataLayer`.
-   `myanalytics/views/templates/admin/mode-note-gtag.tpl`: Note o istruzioni specifiche per la modalità di tracciamento `gtag.js`.
-   `myanalytics/views/templates/admin/mode-note-mp.tpl`: Note o istruzioni specifiche per la modalità di tracciamento `Measurement Protocol`.
-   `myanalytics/views/templates/admin/mode-picker.tpl`: Renderizza i pulsanti radio o il menu a discesa per la selezione della modalità di tracciamento GA4.
-   `myanalytics/views/templates/admin/properties-list.tpl`: Visualizza un elenco delle proprietà GA4 configurate.
-   `myanalytics/views/templates/admin/recent-events.tpl`: Un sotto-template per la visualizzazione di un elenco di eventi recenti, spesso utilizzato nelle statistiche in tempo reale o nelle visualizzazioni di debug.
-   `myanalytics/views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per la pagina di configurazione del modulo.
-   `myanalytics/views/templates/admin/tag-chips.tpl`: Visualizza "chip" o etichette visive per i tag/proprietà GA4 configurati.
-   `myanalytics/views/templates/admin/wizard.tpl`: Renderizza la struttura complessiva e i passaggi della procedura guidata di configurazione del modulo.

#### Template front-office (`views/templates/front/`)

Il modulo non sembra avere template di pagina front-office autonomi dedicati, affidandosi invece all'iniezione di script e dati tramite hook.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   Il modulo memorizza principalmente la sua configurazione nella tabella `ps_configuration` di PrestaShop.
    *   Potrebbe anche creare tabelle personalizzate per:
        *   `ps_myanalytics_events`: Per registrare eventi del Measurement Protocol o altri dati di eventi interni per il debug/statistiche in tempo reale.
        *   `ps_myanalytics_properties`: Per memorizzare i dettagli su più proprietà GA4 e le loro regole associate.
        *   `ps_myanalytics_consent`: Per memorizzare lo stato del consenso o integrarsi con i moduli di consenso.
        *   `ps_myanalytics_health_log`: Per memorizzare i risultati dei controlli di integrità e dei report sulla qualità dei dati.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta script di inizializzazione `gtag.js` o `dataLayer`, configurazione GA4 globale e potenzialmente eventi `page_view`. |
| `displayFooter` | Prima del tag di chiusura `</body>` di ogni pagina. | Inietta script di tracciamento aggiuntivi, pannelli di debug o chiamate di fallback del Measurement Protocol. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Invia l'evento cruciale `purchase` a GA4, inclusi i dettagli della transazione e i dati del prodotto. Questo è spesso il punto in cui viene utilizzato il Measurement Protocol. |
| `displayProductButtons` | Vicino ai pulsanti di azione del prodotto (ad esempio, "Aggiungi al carrello") nella pagina del prodotto. | Inietta JavaScript per catturare gli eventi `add_to_cart`. |
| `displayProductExtraContent` | Nella sezione del contenuto extra della pagina del prodotto. | Inietta JavaScript per gli eventi `view_item` o altre interazioni con i dettagli del prodotto. |
| `displayPaymentTop` | Prima delle opzioni di pagamento nella pagina di checkout. | Cattura gli eventi `begin_checkout` e `add_payment_info`. |
| `actionFrontControllerSetMedia` | Quando un controller frontale sta impostando le sue risorse multimediali. | Inserisce in coda file JS/CSS specifici del modulo per il front office. |
| `actionAdminControllerSetMedia` | Quando un controller di amministrazione sta impostando le sue risorse multimediali. | Inserisce in coda file JS/CSS specifici del modulo per il back office. |
| `actionValidateOrder` | Dopo che un ordine è stato validato con successo. | Attiva eventi `purchase` del Measurement Protocol lato server, garantendo l'acquisizione dei dati anche se il lato client fallisce. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente attiva controlli del dottore del catalogo o aggiorna le cache interne dei dati del prodotto. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto esistente. | Simile a `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Pulisce eventuali dati di tracciamento o cache associati. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più recente e compatibile del modulo "Google Analytics 4 - gtag, MP & dataLayer tracking", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu fornisce supporto dedicato per tutti i suoi moduli, garantendo che l'integrazione analitica del tuo negozio rimanga robusta e aggiornata con gli ultimi standard GA4 e le versioni di PrestaShop.
