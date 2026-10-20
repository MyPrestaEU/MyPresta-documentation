---
title: "Feed di prodotti Pinterest - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Feed di prodotti Pinterest di MyPresta.eu."
sidebar:
  label: "Feed di prodotti Pinterest - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Pinterest products feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/pinterest-products-feed/)
>
> ---


# Feed di prodotti Pinterest

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e garantiscono il buon funzionamento dei moduli. Il tuo ambiente di hosting dovrebbe anche consentire memoria e tempo di esecuzione sufficienti per la generazione di feed di prodotti di grandi dimensioni, specialmente se hai molti prodotti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Feed di prodotti Pinterest" ha una schermata di configurazione principale e una schermata di amministrazione dedicata per la gestione dei tuoi feed di prodotti.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Configura Feed di prodotti Pinterest)

Questa è la schermata di configurazione principale dove definisci i parametri fondamentali per il tuo feed di prodotti Pinterest.

#### Scheda Impostazioni generali

Questa scheda contiene le impostazioni fondamentali per la generazione del tuo feed di prodotti.

-   **Abilita Feed Pinterest:**
    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (SÌ):* Il modulo genererà il feed di prodotti e lo renderà accessibile tramite un URL.
        *   *Quando disabilitato (NO):* Il modulo non genererà o aggiornerà il feed, e l'URL del feed diventerà inattivo.
    *   **Valore consigliato:** SÌ (una volta configurate le altre impostazioni).
    *   **Scenario / esempio commerciante:** Sei pronto per iniziare a vendere su Pinterest, quindi lo abiliti dopo aver impostato i tuoi filtri prodotto.
-   **Tipo di file del feed:**
    *   **Cosa fa questa impostazione:** Determina il formato del file del feed di prodotti. Pinterest supporta sia CSV (Comma Separated Values) che XML (Extensible Markup Language).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su CSV:* Il feed sarà un file di testo semplice con i dati del prodotto separati da virgole.
        *   *Quando impostato su XML:* Il feed sarà un file strutturato che utilizza tag XML.
    *   **Valore consigliato:** XML (generalmente più robusto per dati complessi, ma entrambi funzionano con Pinterest).
    *   **Scenario / esempio commerciante:** Pinterest spesso raccomanda XML per dati più ricchi, quindi potresti scegliere XML per una migliore compatibilità e per essere a prova di futuro.
-   **Lingua predefinita per il feed:**
    *   **Cosa fa questa impostazione:** Seleziona la lingua in cui i nomi dei prodotti, le descrizioni e altri dati testuali verranno esportati nel feed.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su Inglese:* Tutto il testo del prodotto sarà in inglese.
        *   *Quando impostato su Francese:* Tutto il testo del prodotto sarà in francese.
    *   **Valore consigliato:** La lingua principale del tuo pubblico di destinazione su Pinterest.
    *   **Scenario / esempio commerciante:** Se stai targettizzando clienti in Francia, selezioneresti Francese. Se stai targettizzando un pubblico globale di lingua inglese, selezioneresti Inglese.
-   **Valuta predefinita per il feed:**
    *   **Cosa fa questa impostazione:** Seleziona la valuta in cui i prezzi dei prodotti verranno esportati nel feed.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su USD:* Tutti i prezzi saranno in Dollari USA.
        *   *Quando impostato su EUR:* Tutti i prezzi saranno in Euro.
    *   **Valore consigliato:** La valuta principale del tuo mercato di riferimento su Pinterest.
    *   **Scenario / esempio commerciante:** Se il tuo mercato principale utilizza gli Euro, imposta questo su EUR per garantire la corretta visualizzazione dei prezzi su Pinterest.
-   **Paese predefinito per il feed:**
    *   **Cosa fa questa impostazione:** Seleziona il paese associato ai tuoi prodotti nel feed. Questo può influenzare i calcoli di spedizione e tasse da parte di Pinterest.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su Stati Uniti:* I prodotti sono associati al mercato statunitense.
        *   *Quando impostato su Francia:* I prodotti sono associati al mercato francese.
    *   **Valore consigliato:** Il tuo paese principale di operazione o mercato di riferimento.
    *   **Scenario / esempio commerciante:** Se la tua attività ha sede in Germania e vende principalmente a clienti tedeschi, selezioneresti Germania.
-   **Vettore predefinito per il feed:**
    *   **Cosa fa questa impostazione:** Specifica il vettore di spedizione predefinito da associare ai prodotti nel feed. Questo può essere utilizzato da Pinterest per stimare i costi di spedizione.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su "Il mio vettore":* Pinterest potrebbe utilizzare le regole di spedizione generali di questo vettore (se disponibili) per la visualizzazione.
    *   **Valore consigliato:** Il tuo vettore di spedizione più comunemente usato o predefinito.
    *   **Scenario / esempio commerciante:** Se spedisci principalmente con FedEx, selezioneresti FedEx qui.
-   **Includi combinazioni di prodotti (Varianti):**
    *   **Cosa fa questa impostazione:** Determina se le singole varianti di prodotto (come diverse taglie o colori di una maglietta) sono incluse come articoli separati nel feed.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (SÌ):* Ogni combinazione (es. "T-shirt Rossa - Piccola", "T-shirt Rossa - Media") sarà una voce distinta nel feed.
        *   *Quando disabilitato (NO):* Sarà incluso solo il prodotto principale, senza le singole varianti.
    *   **Valore consigliato:** SÌ (se vuoi che i clienti vedano e clicchino su varianti specifiche su Pinterest).
    *   **Scenario / esempio commerciante:** Vendi magliette in varie taglie e colori. Abilitando questa opzione, ogni combinazione unica di taglia/colore ottiene il proprio pin su Pinterest, consentendo ai clienti di trovare esattamente ciò che cercano.
-   **Esporta prodotti con attributo specifico (es. Taglia):**
    *   **Cosa fa questa impostazione:** Ti consente di specificare un attributo particolare (come "Taglia" o "Colore") che dovrebbe essere incluso nel feed di prodotti, spesso utilizzato per dati di prodotto ricchi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato (es. "Taglia"):* L'attributo taglia dei tuoi prodotti sarà esplicitamente incluso nei dati del feed.
        *   *Quando non selezionato:* Questo attributo specifico non sarà esplicitamente esportato.
    *   **Valore consigliato:** Seleziona un attributo cruciale per la differenziazione del prodotto, come "Taglia" o "Colore".
    *   **Scenario / esempio commerciante:** Se vendi abbigliamento, selezionare "Taglia" assicura che Pinterest possa visualizzare le informazioni sulla taglia direttamente sul pin, migliorando l'esperienza di acquisto.
-   **Esporta prodotti con caratteristica specifica (es. Materiale):**
    *   **Cosa fa questa impostazione:** Simile agli attributi, questo ti consente di includere una caratteristica specifica del prodotto (come "Materiale" o "Marca") nel feed.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato (es. "Materiale"):* La caratteristica materiale dei tuoi prodotti sarà esplicitamente inclusa nei dati del feed.
        *   *Quando non selezionato:* Questa caratteristica specifica non sarà esplicitamente esportata.
    *   **Valore consigliato:** Seleziona una caratteristica che aggiunge informazioni preziose per gli acquirenti, come "Materiale", "Marca" o "Stile".
    *   **Scenario / esempio commerciante:** Se vendi mobili, selezionare "Materiale" (es. "Rovere", "Pino") aiuta i clienti a filtrare e trovare prodotti in base alle loro preferenze.
-   **Esporta prodotti con etichetta personalizzata specifica (es. Bestseller):**
    *   **Cosa fa questa impostazione:** Ti consente di includere un'etichetta personalizzata (se le hai definite in PrestaShop) nel feed. Queste possono essere utilizzate per campagne di marketing specifiche su Pinterest.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato (es. "Bestseller"):* I prodotti con questa etichetta personalizzata la avranno inclusa nei loro dati del feed.
        *   *Quando non selezionato:* Le etichette personalizzate non saranno esportate.
    *   **Valore consigliato:** Utilizza se hai etichette specifiche per il marketing o la categorizzazione su Pinterest.
    *   **Scenario / esempio commerciante:** Hai contrassegnato alcuni prodotti come "Bestseller" in PrestaShop. Esportare questa etichetta ti consente di creare campagne pubblicitarie su Pinterest che targettizzano specificamente questi prodotti ad alte prestazioni.
-   **Escludi prodotti per categoria:**
    *   **Cosa fa questa impostazione:** Fornisce un selettore ad albero per scegliere intere categorie di prodotti che NON vuoi includere nel tuo feed di Pinterest.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando le categorie sono selezionate:* Tutti i prodotti all'interno di quelle categorie (e delle loro sottocategorie) saranno esclusi dal feed generato.
        *   *Quando nessuna categoria è selezionata:* Tutti i prodotti di tutte le categorie saranno considerati per l'esportazione (a meno che non siano esclusi da altre impostazioni).
    *   **Valore consigliato:** Escludi le categorie non adatte a Pinterest (es. servizi, download digitali o prodotti che non vuoi pubblicizzare).
    *   **Scenario / esempio commerciante:** Vendi sia prodotti fisici che carte regalo digitali. Escluderesti la categoria "Carte regalo digitali" dal feed poiché Pinterest è principalmente per prodotti fisici.
-   **Escludi prodotti specifici:**
    *   **Cosa fa questa impostazione:** Ti consente di cercare e selezionare singoli prodotti che vuoi esplicitamente escludere dal feed di Pinterest.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando i prodotti sono selezionati:* Quei prodotti specifici non appariranno nel feed generato.
        *   *Quando nessun prodotto è selezionato:* Tutti i prodotti (non esclusi per categoria) saranno considerati per l'esportazione.
    *   **Valore consigliato:** Escludi prodotti specifici che sono esauriti a tempo indeterminato, fuori produzione o per qualsiasi altro motivo non vuoi che appaiano su Pinterest.
    *   **Scenario / esempio commerciante:** Un particolare prodotto è temporaneamente non disponibile a causa di un problema con il fornitore, quindi lo escludi finché non torna in magazzino.
-   **Genera URL del feed:**
    *   **Cosa fa questa impostazione:** Visualizza l'URL unico dove è possibile accedere al tuo feed di prodotti Pinterest. Questo è l'URL che fornirai a Pinterest.
    *   **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione. L'URL cambia se modifichi il dominio del tuo negozio o le impostazioni SSL.
    *   **Valore consigliato:** Copia questo URL e incollalo nelle impostazioni del tuo account Pinterest Business quando configuri il tuo catalogo prodotti.
    *   **Scenario / esempio commerciante:** Dopo aver configurato tutte le impostazioni, copi questo URL e vai al tuo account Pinterest Business per configurare il tuo catalogo prodotti, incollando questo URL nel campo "Origine dati".
-   **Genera Feed (Pulsante):**
    *   **Cosa fa questa impostazione:** Attiva manualmente la generazione del file del feed di prodotti.
    *   **Effetto della modifica di questa impostazione:** Cliccando questo pulsante si creerà o aggiornerà immediatamente il file del feed in base alle impostazioni correnti. Questo può richiedere del tempo per cataloghi di grandi dimensioni.
    *   **Valore consigliato:** Clicca questo dopo aver apportato modifiche alle impostazioni del feed o quando vuoi forzare un aggiornamento immediato.
    *   **Scenario / esempio commerciante:** Hai appena aggiunto 50 nuovi prodotti e vuoi che appaiano su Pinterest il prima possibile, quindi clicchi "Genera Feed".

#### Scheda Impostazioni Cron Job

Questa scheda fornisce informazioni per automatizzare il processo di generazione del feed.

-   **URL Cron Job:**
    *   **Cosa fa questa impostazione:** Visualizza un URL speciale che, quando visitato, attiva automaticamente il processo di generazione del feed senza che tu debba cliccare il pulsante "Genera Feed" nel back office.
    *   **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione.
    *   **Valore consigliato:** Copia questo URL e impostalo come "cron job" sul tuo server di hosting web.
    *   **Scenario / esempio commerciante:** Vuoi che il tuo feed di Pinterest si aggiorni ogni notte alle 3 del mattino. Copi questo URL e configuri un cron job sul tuo server per visitare questo URL ogni giorno alle 3 del mattino.
-   **Come impostare un Cron Job:**
    *   **Cosa fa questa impostazione:** Fornisce istruzioni su come impostare un'attività automatizzata (cron job) sul tuo server web per aggiornare regolarmente il tuo feed di prodotti.
    *   **Effetto della modifica di questa impostazione:** Questa è una sezione informativa.
    *   **Valore consigliato:** Segui queste istruzioni o forniscile al tuo webmaster/supporto hosting per assicurarti che il tuo feed sia sempre aggiornato.
    *   **Scenario / esempio commerciante:** Non sei sicuro di come impostare un cron job. Questa sezione ti fornisce i passaggi esatti o le informazioni da passare al tuo provider di hosting.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### Dashboard Feed Pinterest (Back Office > Vendi > Feed Pinterest)

Questa sezione dedicata del tuo back office PrestaShop fornisce una panoramica e un'interfaccia di gestione per i tuoi feed di prodotti Pinterest. Puoi trovarla sotto il menu "Vendi" in PrestaShop 1.7/8/9.

-   **Nome schermata e posizione menu:** Feed Pinterest (sotto "Vendi" nel menu principale).
-   **Azioni e impostazioni disponibili:**
    *   **Tabella Elenco Feed:** Questa tabella visualizza tutti i feed generati (se il modulo supporta più feed, altrimenti mostrerà quello principale). Tipicamente include:
        *   **Nome/ID Feed:** Un identificatore unico per il feed.
        *   **Lingua:** La lingua dei prodotti nel feed.
        *   **Valuta:** La valuta dei prezzi nel feed.
        *   **Ultima generazione:** La data e l'ora dell'ultimo aggiornamento del feed.
        *   **URL Feed:** Il link diretto al file del feed generato.
        *   **Azioni:** Pulsanti per visualizzare, scaricare o rigenerare il feed.
    *   **Aggiungi nuovo feed / Modifica feed:** Sebbene il modulo si concentri principalmente su un singolo feed principale, questa interfaccia potrebbe consentire future espansioni o configurazioni di feed specifiche. Per ora, riflette in gran parte le impostazioni della pagina di configurazione principale.
    *   **Vista Griglia / Gestione:** Questa schermata fornisce una chiara panoramica dello stato del tuo feed e un rapido accesso al suo URL e alle opzioni di rigenerazione.
-   **Effetto delle modifiche:**
    *   *Rigenerazione di un feed:* Aggiorna il file del feed con i dati più recenti dei prodotti dal tuo negozio, riflettendo eventuali modifiche alle informazioni sui prodotti, ai prezzi o ai livelli di stock.
    *   *Visualizzazione dell'URL del feed:* Ti consente di copiare rapidamente l'URL necessario per Pinterest.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla periodicamente questa dashboard per assicurarti che il tuo feed venga generato regolarmente (se hai impostato un cron job) e che il timestamp "Ultima generazione" sia recente.
    2.  Se apporti modifiche significative ai prodotti (es. aggiornamenti massivi dei prezzi, lancio di nuovi prodotti), potresti rigenerare manualmente il feed da questa schermata o dalla configurazione del modulo per assicurarti che Pinterest riceva i dati più recenti rapidamente.
    3.  Copia l'URL del feed da qui quando configuri inizialmente il tuo account Pinterest Business.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita Feed Pinterest | SÌ | Attiva/disattiva la generazione del feed. |
| | Tipo di file del feed | XML | Imposta il formato di output per il feed (CSV o XML). |
| | Lingua predefinita per il feed | La tua lingua principale | Lingua per nomi/descrizioni dei prodotti. |
| | Valuta predefinita per il feed | La tua valuta principale | Valuta per i prezzi dei prodotti. |
| | Paese predefinito per il feed | Il tuo paese principale | Associazione del paese per i prodotti. |
| | Vettore predefinito per il feed | Il tuo vettore predefinito | Vettore di spedizione per le stime di Pinterest. |
| | Includi combinazioni di prodotti | SÌ | Esporta le singole varianti di prodotto. |
| | Esporta prodotti con attributo specifico | Seleziona l'attributo pertinente (es. Taglia) | Include attributi specifici del prodotto nel feed. |
| | Esporta prodotti con caratteristica specifica | Seleziona la caratteristica pertinente (es. Materiale) | Include caratteristiche specifiche del prodotto nel feed. |
| | Esporta prodotti con etichetta personalizzata specifica | Seleziona l'etichetta pertinente (es. Bestseller) | Include etichette personalizzate per il marketing. |
| | Escludi prodotti per categoria | Seleziona le categorie da escludere | Impedisce ai prodotti delle categorie scelte di apparire nel feed. |
| | Escludi prodotti specifici | Seleziona i singoli prodotti da escludere | Impedisce a prodotti specifici di apparire nel feed. |
| | Genera URL del feed | (Solo visualizzazione) | L'URL da fornire a Pinterest per recuperare il tuo feed. |
| | Genera Feed (Pulsante) | Clicca dopo le modifiche | Attiva manualmente la generazione immediata del feed. |
| **Scheda Impostazioni Cron Job** | URL Cron Job | (Solo visualizzazione) | URL per la generazione automatica del feed tramite cron del server. |
| | Come impostare un Cron Job | Segui le istruzioni | Guida per l'impostazione degli aggiornamenti automatici del feed. |
| **Dashboard Feed Pinterest** | Tabella Elenco Feed | (Visualizza) | Panoramica dei feed generati, stato e URL. |
| | Rigenera Feed (Azione) | Clicca quando necessario | Aggiorna il feed con i dati più recenti del negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prodotti non appaiono su Pinterest dopo aver configurato il feed. Cosa devo fare?**
R1: Innanzitutto, assicurati che l'impostazione "Abilita Feed Pinterest" nella configurazione del modulo sia impostata su SÌ. Quindi, clicca manualmente il pulsante "Genera Feed" per creare il file del feed iniziale. Successivamente, ricontrolla di aver copiato e incollato correttamente l'"URL Genera Feed" nelle impostazioni del catalogo prodotti del tuo account Pinterest Business. Pinterest può impiegare del tempo (fino a 24-48 ore) per elaborare un nuovo feed. Inoltre, controlla il tuo account Pinterest Business per eventuali messaggi di errore relativi al feed.

**D2: I prezzi o i livelli di stock su Pinterest sono obsoleti. Come posso risolvere questo problema?**
R2: Questo di solito significa che il tuo feed non si sta aggiornando regolarmente. Assicurati di aver impostato il cron job sul tuo server di hosting utilizzando l'"URL Cron Job" fornito nel modulo. Se il cron job è impostato, verifica che funzioni correttamente (il tuo provider di hosting può aiutarti in questo). Puoi anche rigenerare manualmente il feed cliccando il pulsante "Genera Feed" nella configurazione del modulo per forzare un aggiornamento immediato.

**D3: Alcuni dei miei prodotti mancano dal feed di Pinterest.**
R3: Vai alla pagina di configurazione del modulo e controlla le impostazioni "Escludi prodotti per categoria" ed "Escludi prodotti specifici". Potresti aver inavvertitamente escluso categorie o singoli prodotti. Inoltre, assicurati che i prodotti abbiano immagini valide, prezzi e siano impostati su "attivo" e "disponibile per l'ordine" nel tuo negozio PrestaShop, poiché il modulo tipicamente esporta solo prodotti attivi e acquistabili.

**D4: Il processo di generazione del feed richiede molto tempo o va in timeout.**
R4: Se hai un catalogo molto grande (migliaia di prodotti), la generazione del feed può essere intensiva in termini di risorse.
\* **Soluzione 1:** Aumenta le impostazioni `memory_limit` e `max_execution_time` di PHP nel file `php.ini` del tuo server. Il tuo provider di hosting può aiutarti in questo.
\* **Soluzione 2:** Assicurati che il tuo cron job sia impostato per essere eseguito durante le ore di minor traffico per minimizzare l'impatto sulle prestazioni del negozio.
\* **Soluzione 3:** Considera di escludere categorie o prodotti meno importanti se la dimensione del feed è costantemente un problema.

**D5: Gli stili del mio tema personalizzato non vengono applicati all'interfaccia di amministrazione del modulo.**
R5: L'interfaccia di amministrazione del modulo utilizza i propri CSS (`admin-app.css`, `admin-theme.css`). Questi sono separati dal tuo tema front-office. Se desideri personalizzare l'aspetto delle pagine di back-office del modulo, dovresti sovrascrivere questi file CSS specifici o aggiungere CSS personalizzati al tuo back office PrestaShop. Questo è tipicamente un compito per uno sviluppatore web.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Feed di prodotti Pinterest" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `pinterestfeed` segue un modello MVC (Model-View-Controller) standard di PrestaShop, con controller frontali dedicati per la generazione del feed e l'esecuzione del cron, e controller di amministrazione per la configurazione e la gestione. Sfrutta `ObjectModel` per la potenziale persistenza dei dati (sebbene si concentri principalmente sulla generazione dinamica del feed) e utilizza i template Smarty per il rendering sia della configurazione del back-office che delle viste informative. La logica centrale per la generazione del feed secondo le specifiche di Pinterest è incapsulata in classi helper dedicate.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono le richieste rivolte al pubblico, principalmente per il feed stesso e l'esecuzione del cron job.

-   `controllers/front/cron.php`
    *   **Nome classe e classe padre:** `PinterestFeedCronModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job lato server. Quando viene acceduto, attiva la classe `PinterestFeedGenerator` per rigenerare il feed di prodotti in base alla configurazione corrente del modulo. Tipicamente restituisce un semplice messaggio di successo/fallimento o registra il processo. Non renderizza una pagina visiva.
-   `controllers/front/feed.php`
    *   **Nome classe e classe padre:** `PinterestFeedFeedModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller serve il file del feed di prodotti effettivo. Quando viene acceduto tramite l'"URL Genera Feed", legge il file del feed pre-generato (o lo genera se non esiste/è obsoleto, a seconda dell'implementazione) e ne restituisce il contenuto (CSV o XML) con le appropriate intestazioni HTTP (`Content-Type`).

#### Controller di amministrazione Back-Office

Questi controller gestiscono la configurazione del modulo e forniscono interfacce amministrative.

-   `controllers/admin/AdminExportProductsFeedPinterest.php`
    *   **Nome classe e classe padre:** `AdminExportProductsFeedPinterestController` che estende `ModuleAdminController`.
    *   **Nome scheda ed entità gestita:** Questo controller è responsabile della dashboard "Feed Pinterest" che si trova sotto il menu "Vendi". Gestisce la visualizzazione e le azioni relative ai feed di prodotti generati. Non gestisce direttamente una specifica entità `ObjectModel` ma piuttosto orchestra la generazione e la visualizzazione dei dati relativi al feed.
    *   **Chiavi di configurazione chiave utilizzate:** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (per i valori predefiniti nei moduli), `pm_pinterestfeed_products`, `pm_export_size_attribute` (per le impostazioni specifiche del modulo). Utilizza anche `pf_tree` per la selezione delle categorie e `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` per la selezione della lingua nei moduli.
-   `controllers/admin/index.php`
    *   **Nome classe e classe padre:** Questo file probabilmente funge da segnaposto o da semplice reindirizzamento/punto di ingresso per la sezione amministrativa, piuttosto che da un controller completo. In PrestaShop, i file `index.php` nelle sottocartelle spesso impediscono l'elenco diretto delle directory. Il suo ruolo principale è garantire la sicurezza impedendo l'accesso diretto ai contenuti della directory.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/index.php`
    *   **Scopo:** File di sicurezza standard di PrestaShop per impedire l'elenco diretto delle directory.
-   `classes/PinterestFeedGenerator.php`
    *   **Responsabilità:** Questa è la classe logica principale per la costruzione del feed di prodotti.
    *   **Interazione con il database:** Interagisce con varie tabelle core di PrestaShop (es. `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`) per recuperare i dati dei prodotti.
    *   **Estensione ObjectModel:** Non estende `ObjectModel` direttamente, poiché il suo scopo è l'aggregazione e la formattazione dei dati piuttosto che la persistenza di una singola entità.
    *   **Metodi pubblici chiave:** Contiene metodi per recuperare i prodotti, gestire le combinazioni, applicare filtri (categorie, prodotti specifici), formattare i dati secondo le specifiche di Pinterest e scrivere l'output nel tipo di file scelto (CSV/XML).
-   `classes/PinterestFeedSpec.php`
    *   **Responsabilità:** Questa classe probabilmente definisce i campi richiesti e opzionali per la specifica del feed di prodotti Pinterest. Agisce come un livello di mappatura o validazione per garantire che il feed generato aderisca alle linee guida di Pinterest.
    *   **Interazione con il database:** Nessuna direttamente.
    *   **Estensione ObjectModel:** Non estende `ObjectModel`.
    *   **Metodi pubblici chiave:** Potrebbe contenere metodi per recuperare l'elenco dei campi richiesti/opzionali, i loro tipi di dati e qualsiasi regola di formattazione specifica.

### 4.4 Risorse JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Back-office.
    *   **Scopo:** Fornisce la funzionalità di completamento automatico, probabilmente per la ricerca e la selezione di prodotti o categorie nei moduli di configurazione amministrativa (es. per "Escludi prodotti specifici").
    *   **Listener di eventi:** Si lega agli eventi `keyup` o `input` dei campi di input per attivare le ricerche AJAX.
    *   **Manipolazione del DOM:** Visualizza i risultati della ricerca in un elenco a discesa, consente la selezione e aggiorna i campi di input nascosti.
-   `views/js/admin-app.js`
    *   **Ambito:** Back-office.
    *   **Scopo:** JavaScript principale per la configurazione del back-office e la dashboard del modulo. Gestisce l'invio dei moduli, gli aggiornamenti dinamici e potenzialmente le chiamate AJAX per lo stato di generazione del feed.
    *   **Listener di eventi:** Si lega agli eventi `submit` dei moduli, agli eventi `click` dei pulsanti (es. "Genera Feed") e potenzialmente agli eventi `change` delle caselle di selezione.
    *   **Manipolazione del DOM:** Gestisce la visualizzazione delle schede di configurazione, aggiorna i messaggi di stato e interagisce con il componente di completamento automatico.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Styling del modulo di amministrazione del back-office.
    *   **Scopo:** Stila l'input di ricerca con completamento automatico e i suoi risultati a discesa, garantendo un aspetto e una sensazione coerenti all'interno del back office di PrestaShop.
    *   **Selettori di classe CSS chiave:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `views/admin-theme.css`
    *   **Ambito:** Styling del modulo di amministrazione del back-office.
    *   **Scopo:** Fornisce uno stile generale per le pagine di configurazione del back-office del modulo, garantendo che si integri bene con il tema di amministrazione di PrestaShop.
    *   **Selettori di classe CSS chiave:** `.panel`, `.form-group`, `.control-label`, `.help-block`.
-   `views/css/admin-app.css`
    *   **Ambito:** Styling del modulo di amministrazione del back-office.
    *   **Scopo:** Styling specifico per gli elementi e il layout personalizzati del modulo all'interno dell'interfaccia di amministrazione, come la navigazione a schede, i pulsanti personalizzati o i blocchi informativi unici.
    *   **Selettori di classe CSS chiave:** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: La descrizione del modulo non elenca esplicitamente i template hook, suggerendo che la sua presenza nel front-office sia principalmente tramite l'URL del feed, non la visualizzazione diretta. Se presenti, sarebbero per blocchi informativi.
-   **Template admin (`views/templates/admin/`)**:
    *   `views/templates/admin/dashboard.tpl`: Probabilmente il template principale per la dashboard "Feed Pinterest", che visualizza l'elenco dei feed, il loro stato e le azioni.
    *   `views/templates/admin/feeds.tpl`: Potrebbe essere un template parziale utilizzato all'interno di `dashboard.tpl` per renderizzare la tabella dei feed.
    *   `views/templates/admin/form-chrome.tpl`: Un template wrapper generico per i moduli di amministrazione, che fornisce il pannello e la struttura del modulo standard di PrestaShop.
    *   `views/templates/admin/layout.tpl`: Il template di layout principale per la sezione amministrativa del modulo, che definisce la struttura complessiva inclusi l'intestazione, le schede e l'area del contenuto.
-   **Template di configurazione e utilità (`views/`)**:
    *   `views/categories-fancybox.tpl`: Template per un modale Fancybox utilizzato per la selezione delle categorie (es. per l'esclusione).
    *   `views/custom-labels.tpl`: Template per la visualizzazione o la gestione delle etichette personalizzate.
    *   `views/exclude-products.tpl`: Template per l'interfaccia di ricerca e selezione dell'esclusione dei prodotti.
    *   `views/google_lang_links.tpl`: Potenzialmente per la visualizzazione di link o informazioni specifiche per la lingua, sebbene il suo uso diretto in un modulo di feed di Pinterest potrebbe essere a scopo informativo.
    *   `views/returnAlert.tpl`: Un template generico per la visualizzazione di avvisi di successo o errore nel back office.
    *   `views/script-fancybox.tpl`: Contiene JavaScript per l'inizializzazione e la gestione dei modali Fancybox.
    *   `views/script.tpl`: Snippet JavaScript generali o script di inizializzazione per le pagine di amministrazione del modulo.
    *   `lib/searchTool/views/scripts.tpl`: Contiene JavaScript per lo strumento di ricerca con completamento automatico.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non sembra creare le proprie tabelle SQL personalizzate in base all'inventario fornito.
    *   Si basa fortemente sulle tabelle core esistenti di PrestaShop: `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (per le impostazioni del modulo come `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE`, ecc.).
-   **Tabella degli hook registrati**:
    La funzione principale del modulo è la generazione del feed, che viene tipicamente attivata dall'accesso diretto al controller (URL del feed, URL del cron) o da azioni amministrative. Sebbene la descrizione del modulo menzioni "Hook Front-Office: Header, Colonne, Prodotto o Footer", l'inventario dei file e la descrizione delle funzionalità forniti suggeriscono che questi non sono attivamente utilizzati per la visualizzazione visiva da *questo specifico modulo*. Invece, il modulo probabilmente registra hook per processi interni o potenziali estensioni future.

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Ad ogni caricamento di pagina nel front office. | Potenzialmente per aggiungere JS/CSS personalizzati se il modulo avesse un componente front-office, o per il tracciamento interno. (Improbabile che venga utilizzato per l'output visivo da questo modulo). |
| `displayRightColumn` | Nella colonna destra del front office. | (Improbabile che venga utilizzato per l'output visivo da questo modulo). |
| `displayLeftColumn` | Nella colonna sinistra del front office. | (Improbabile che venga utilizzato per l'output visivo da questo modulo). |
| `displayFooter` | Nel footer di ogni pagina del front office. | (Improbabile che venga utilizzato per l'output visivo da questo modulo). |
| `displayProductExtraContent` | Nella pagina del prodotto, sotto il contenuto principale. | (Improbabile che venga utilizzato per l'output visivo da questo modulo). |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel back office. | Potenzialmente per contrassegnare il feed come bisognoso di rigenerazione o per attivare un aggiornamento parziale. |
| `actionProductAdd` | Dopo l'aggiunta di un nuovo prodotto. | Simile a `actionProductUpdate`. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Simile a `actionProductUpdate`. |
| `actionUpdateQuantity` | Dopo la modifica della quantità di stock del prodotto. | Potenzialmente per attivare la rigenerazione del feed se le modifiche allo stock sono critiche per il feed. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per creare voci di configurazione e potenzialmente il file del feed iniziale. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per pulire le voci di configurazione e i file generati. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel back office. | Potrebbe essere utilizzato per aggiungere una scheda o un campo specifico relativo alle impostazioni del feed di Pinterest per i singoli prodotti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo "Feed di prodotti Pinterest", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e ti aiuti a raggiungere i tuoi obiettivi di e-commerce.

-   **MyPresta.eu Cronologia ordini e download:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Contatto supporto:** <https://mypresta.eu/contact>
