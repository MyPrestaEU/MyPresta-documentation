---
title: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Abandoned Cart Reminder Pro – drip emails, discount codes & ROI di MyPresta.eu."
sidebar:
  label: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Abandoned Cart Reminder Pro – drip emails, discount codes & ROI su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi/)
>
> ---


# Abandoned Cart Reminder Pro – drip emails, discount codes & ROI

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5 (Il modulo è scritto pensando a PHP 5.6+, ma PrestaShop 9.x richiede PHP 8.1+ per il negozio stesso. Raccomandiamo di utilizzare la versione PHP stabile più alta compatibile con la tua installazione PrestaShop, fino a 8.5.)
- **Requisiti di hosting**: Sono richieste estensioni PHP standard come cURL, JSON e OpenSSL. Il tuo ambiente di hosting deve anche supportare i cron job (attività pianificate) affinché il modulo funzioni correttamente, poiché elabora i promemoria in background.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Abandoned Cart Reminder Pro" offre un set completo di strumenti per gestire le tue campagne. Interagirai principalmente con le sue voci di menu dedicate nel Back Office di PrestaShop.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Mentre il modulo ha schermate di amministrazione dedicate, il pulsante iniziale "Configura" dal Gestore moduli potrebbe portare a una configurazione di base o a un reindirizzamento. Il modulo sfrutta la chiave di configurazione `PS_SSL_ENABLED` di PrestaShop.

-   **Cosa fa questa impostazione:** Questa impostazione non è controllata direttamente dal modulo ma è un'impostazione fondamentale di PrestaShop che indica se il tuo negozio utilizza HTTPS (connessione sicura). Il modulo si basa su questo per generare link corretti e sicuri nelle tue email di promemoria.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando `PS_SSL_ENABLED` è SÌ:* Tutti i link generati dal modulo (es. a carrelli abbandonati, pagine di opt-out) utilizzeranno `https://`, garantendo un'esperienza sicura e affidabile per i tuoi clienti.
    -   *Quando `PS_SSL_ENABLED` è NO:* I link potrebbero essere generati utilizzando `http://`, il che è meno sicuro e può attivare avvisi del browser, riducendo potenzialmente la fiducia dei clienti e i tassi di conversione.
-   **Valore consigliato:** **SÌ**. Il tuo negozio dovrebbe sempre utilizzare SSL per motivi di sicurezza e SEO. Assicurati che l'intero negozio sia in esecuzione su HTTPS.
-   **Scenario/esempio del commerciante:** Se i tuoi clienti ricevono un'email con un link `http://` al loro carrello, il loro browser potrebbe mostrare un avviso "Non sicuro". Questo può renderli esitanti a cliccare sul link o a completare l'acquisto, anche se il tuo checkout è sicuro. Usa sempre HTTPS.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Una volta installato il modulo, troverai una nuova voce di menu nel tuo Back Office di PrestaShop, tipicamente sotto **Marketing** o una sezione dedicata per "Abandoned Cart Reminder Pro". Questo menu porterà a diverse sottosezioni:

#### 2.2.1 Campagne (Back Office > Abandoned Cart Reminder Pro > Campagne)

Qui è dove crei, gestisci e ottimizzi le tue campagne di promemoria per carrelli abbandonati.

-   **Nome schermata e posizione menu:** **Abandoned Cart Reminder Pro > Campagne**
-   **Azioni e impostazioni disponibili:**
    -   **Elenco campagne:** Una tabella che mostra tutte le tue campagne attive e inattive, inclusi il loro nome, stato e statistiche chiave.
    -   **Aggiungi nuova campagna:** Clicca per creare una nuova sequenza di email a più passaggi.
        -   **Nome campagna:** Un nome descrittivo per il tuo riferimento interno (es. "Promemoria standard a 2 passaggi", "Sconto carrello di alto valore").
        -   **Regole di targeting:**
            -   **Valore minimo del carrello:** Imposta un valore totale minimo per un carrello affinché sia idoneo a questa campagna.
                -   *Effetto:* I carrelli al di sotto di questo valore non riceveranno email da questa campagna.
                -   *Scenario del commerciante:* Crea una campagna specifica per carrelli di alto valore, magari offrendo uno sconto maggiore.
            -   **Gruppi di clienti:** Targetizza gruppi di clienti specifici (es. "Visitatori", "Clienti", "Grossisti").
                -   *Effetto:* Solo i clienti appartenenti ai gruppi selezionati riceveranno email.
                -   *Scenario del commerciante:* Invia promemoria diversi a nuovi visitatori rispetto ai clienti fedeli, o escludi i clienti B2B se hanno un processo di acquisto diverso.
            -   **Prodotti nel carrello:** Targetizza i carrelli contenenti prodotti specifici o prodotti di determinate categorie.
                -   *Effetto:* Solo i carrelli con i prodotti specificati attiveranno la campagna.
                -   *Scenario del commerciante:* Crea una campagna per i clienti che hanno abbandonato un carrello con un prodotto specifico ad alto margine.
        -   **Passaggi della campagna (Email a goccia):** Definisci la sequenza di email da inviare.
            -   **Ritardo:** Quanto tempo dopo l'abbandono del carrello dovrebbe essere inviata questa email (es. 1 ora, 24 ore, 3 giorni).
                -   *Effetto:* Controlla la tempistica del tuo follow-up.
                -   *Scenario del commerciante:* Invia un rapido promemoria dopo 1 ora, uno più forte con uno sconto dopo 24 ore e uno finale dopo 3 giorni.
            -   **Oggetto email:** L'oggetto dell'email (supporta più lingue).
            -   **Contenuto email (Costruttore email):** Progetta il corpo della tua email utilizzando un editor di testo ricco. Puoi includere segnaposto dinamici come nome cliente, link carrello, elenco prodotti e codici sconto.
            -   **Codice sconto:** Opzione per generare un codice sconto unico, una tantum per questa specifica email.
                -   *Effetto:* Viene creato un codice voucher unico e incluso nell'email, incoraggiando la conversione.
                -   *Scenario del commerciante:* Offri uno sconto del 10% nella seconda email di promemoria per incentivare il completamento.
            -   **A/B Testing:** Crea variazioni dell'oggetto o del contenuto della tua email per testare quale funziona meglio.
                -   *Effetto:* Il modulo dividerà gli invii tra le variazioni e traccerà i tassi di conversione, permettendoti di ottimizzare le tue campagne.
                -   *Scenario del commerciante:* Testa due diversi oggetti per vedere quale ottiene un tasso di apertura più alto.
    -   **Modifica/Duplica/Elimina campagne:** Gestisci le campagne esistenti. La duplicazione è utile per creare rapidamente campagne simili.
-   **Effetto delle modifiche:** Le modifiche qui influiscono direttamente su quali clienti ricevono email di promemoria, quando le ricevono, quale contenuto vedono e se ricevono codici sconto. Campagne ben configurate possono aumentare significativamente il tasso di recupero del tuo negozio.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizia con una semplice campagna a 2 passaggi: un promemoria dopo 1-2 ore (senza sconto) e un altro dopo 24 ore (con un piccolo sconto).
    2.  Monitora la tua Dashboard (vedi 4.2.2) per vedere quali campagne stanno ottenendo i migliori risultati.
    3.  Sperimenta con l'A/B testing sugli oggetti o sugli importi degli sconti per ottimizzare i tassi di conversione.
    4.  Considera la creazione di campagne mirate per segmenti di clienti specifici o prodotti di alto valore.

#### 2.2.2 Dashboard (Back Office > Abandoned Cart Reminder Pro > Dashboard)

Questa schermata fornisce una chiara panoramica delle prestazioni del tuo modulo e delle statistiche chiave.

-   **Nome schermata e posizione menu:** **Abandoned Cart Reminder Pro > Dashboard**
-   **Azioni e impostazioni disponibili:**
    -   **Indicatori chiave di performance (KPI):** Visualizza metriche come:
        -   **Carrelli abbandonati:** Numero totale di carrelli abbandonati.
        -   **Email inviate:** Numero di email di promemoria spedite.
        -   **Carrelli recuperati:** Numero di carrelli abbandonati che hanno portato a un ordine completato dopo aver ricevuto un promemoria.
        -   **Tasso di recupero:** Percentuale di carrelli abbandonati recuperati.
        -   **Ricavi attribuiti:** Il ricavo totale generato dai carrelli recuperati.
        -   **ROI:** Ritorno sull'investimento per le tue campagne.
    -   **Ripartizione delle prestazioni della campagna:** Una rappresentazione visiva (es. grafici) di come stanno performando le singole campagne.
    -   **Attività recenti:** Uno sguardo rapido ai carrelli recentemente abbandonati, alle email inviate e agli ordini recuperati.
-   **Effetto delle modifiche:** Questa è una schermata di reporting; non apporti modifiche dirette qui, ma i dati ti aiutano a capire l'impatto delle tue campagne e guidano i tuoi sforzi di ottimizzazione nella sezione "Campagne".
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla questa dashboard regolarmente (es. settimanalmente) per identificare le tendenze, vedere quali campagne sono più efficaci e individuare eventuali problemi. Utilizza questi dati per affinare le tue strategie di campagna.

#### 2.2.3 Log (Back Office > Abandoned Cart Reminder Pro > Log)

La sezione Log fornisce una cronologia dettagliata di tutte le azioni intraprese dal modulo, aiutandoti a risolvere i problemi e a verificarne il funzionamento.

-   **Nome schermata e posizione menu:** **Abandoned Cart Reminder Pro > Log**
-   **Azioni e impostazioni disponibili:**
    -   **Griglia delle voci di log:** Una tabella ricercabile e filtrabile che visualizza:
        -   **Timestamp:** Quando si è verificato l'evento.
        -   **Cliente:** Il cliente associato all'evento.
        -   **ID carrello:** L'ID del carrello abbandonato.
        -   **Campagna/Passaggio:** Quale campagna e passaggio hanno attivato l'evento.
        -   **Tipo di evento:** (es. "Carrello abbandonato", "Email inviata", "Email aperta", "Link cliccato", "Carrello recuperato", "Sconto applicato").
        -   **Stato:** Successo o fallimento.
        -   **Dettagli:** Informazioni aggiuntive, come l'anteprima del contenuto dell'email o i messaggi di errore.
    -   **Anteprima email:** Opzione per visualizzare il contenuto esatto di un'email che è stata inviata.
-   **Effetto delle modifiche:** Questa è una schermata diagnostica e di auditing. Non apporti modifiche qui, ma è fondamentale per capire perché un cliente potrebbe non aver ricevuto un'email o se una campagna non sta funzionando come previsto.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Se un cliente segnala di non aver ricevuto un'email, o se il tuo tasso di recupero diminuisce inaspettatamente, controlla i log. Puoi vedere se le email sono state inviate con successo, se ci sono stati errori o se i clienti hanno optato per l'esclusione.

#### 2.2.4 Impostazioni (Back Office > Abandoned Cart Reminder Pro > Impostazioni)

Questa schermata contiene impostazioni globali che influenzano il comportamento generale del modulo.

-   **Nome schermata e posizione menu:** **Abandoned Cart Reminder Pro > Impostazioni**
-   **Azioni e impostazioni disponibili:**
    -   **Impostazioni generali:**
        -   **Abilita modulo:** Attiva o disattiva l'intero modulo.
            -   *Effetto:* Quando disabilitato, nessun carrello verrà tracciato e nessuna email verrà inviata.
            -   *Consigliato:* SÌ, a meno che non lo si disabiliti temporaneamente per manutenzione.
        -   **Valore minimo del carrello per il tracciamento:** Imposta un valore minimo globale del carrello affinché qualsiasi carrello sia considerato "abbandonato" e tracciato dal modulo.
            -   *Effetto:* I carrelli al di sotto di questo valore verranno ignorati da tutte le campagne.
            -   *Scenario del commerciante:* Evita di inviare promemoria per carrelli di valore molto basso dove lo sforzo di recupero potrebbe non valere la pena.
        -   **Tempo per considerare il carrello abbandonato:** Quanto tempo dopo l'ultima attività del carrello un carrello dovrebbe essere considerato abbandonato (es. 30 minuti, 1 ora).
            -   *Effetto:* Questo determina quando il modulo inizia a contare il ritardo per la prima email di promemoria.
            -   *Consigliato:* 30-60 minuti. Troppo breve potrebbe infastidire i clienti, troppo lungo potrebbe far perdere la finestra di opportunità.
        -   **Limiti anti-spam:**
            -   **Max email per cliente:** Limita il numero totale di email di carrello abbandonato che un singolo cliente può ricevere in un periodo (es. 3 email ogni 30 giorni).
                -   *Effetto:* Impedisce ai clienti di essere sopraffatti da troppe email, riducendo i tassi di disiscrizione.
                -   *Consigliato:* Imposta limiti ragionevoli per mantenere un'esperienza cliente positiva.
            -   **Tempo minimo tra le email:** Assicura un ritardo minimo tra due email inviate allo stesso cliente.
                -   *Effetto:* Impedisce l'invio di più email da diverse campagne troppo ravvicinate.
        -   **Impostazioni GDPR / Opt-Out:**
            -   **Abilita link di opt-out:** Includi un link nelle email di promemoria che consente ai clienti di disiscriversi da futuri promemoria.
                -   *Effetto:* Cruciale per la conformità al GDPR e il rispetto della privacy dei clienti.
                -   *Consigliato:* SÌ.
            -   **Contenuto pagina di opt-out:** Personalizza il testo visualizzato nella pagina di conferma dell'opt-out.
        -   **URL Cron Job:** Visualizza l'URL esatto che devi impostare come cron job sul tuo server.
            -   *Effetto:* Questo URL attiva l'elaborazione in background del modulo, inviando email e aggiornando le statistiche.
            -   *Consigliato:* Copia questo URL e configura il cron job del tuo server per eseguirlo ogni 5-15 minuti.
    -   **Impostazioni email:**
        -   **Nome e email del mittente:** Il nome e l'indirizzo email che appariranno come mittente delle tue email di promemoria.
            -   *Effetto:* Influisce sulla deliverability delle email e su come i clienti percepiscono il tuo marchio.
            -   *Consigliato:* Usa un nome di negozio riconoscibile e un indirizzo email professionale (es. `sales@tuonegozio.com`, `noreply@tuonegozio.com`).
        -   **Modello email:** Scegli un modello di base per le tue email di promemoria (se ne sono disponibili più di uno).
            -   *Effetto:* Determina il design e il layout generale delle tue email.
    -   **Impostazioni avanzate:**
        -   **Modalità debug:** Abilita per la registrazione dettagliata (per gli sviluppatori).
            -   *Effetto:* Fornisce informazioni più verbose nei log, utili per la risoluzione dei problemi.
            -   *Consigliato:* NO, a meno che non sia specificamente richiesto dal supporto.
-   **Effetto delle modifiche:** Queste impostazioni controllano il comportamento fondamentale del modulo, da quando traccia i carrelli a come rispetta la privacy dei clienti e invia le email. Impostazioni errate possono portare a opportunità mancate o a una scarsa esperienza del cliente.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi queste impostazioni durante la configurazione iniziale e periodicamente per assicurarti che siano allineate con le politiche e la strategia di marketing del tuo negozio. Presta molta attenzione alle impostazioni anti-spam e GDPR.

#### 2.2.5 index.php (cartrempro/controllers/admin/index.php)

Questo file è una pratica standard di PrestaShop per prevenire l'elenco diretto delle directory nelle cartelle di amministrazione e tipicamente non rappresenta una schermata configurabile in sé. Garantisce la sicurezza reindirizzando o visualizzando una pagina vuota se qualcuno tenta di accedere direttamente alla cartella.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | `PS_SSL_ENABLED` (Core PrestaShop) | SÌ | Garantisce link HTTPS sicuri nelle email. |
| **Campagne** | Nome campagna | Descrittivo | Identificazione interna delle tue campagne. |
| | Valore minimo carrello | 0 (o la tua soglia) | Filtra i carrelli in base al valore per campagne specifiche. |
| | Gruppi di clienti | Tutti (o specifici) | Targetizza segmenti di clienti specifici. |
| | Prodotti nel carrello | Nessuno (o specifici) | Targetizza i carrelli contenenti prodotti/categorie specifici. |
| | Ritardo passaggio campagna | 1h, 24h, 3d | Controlla la tempistica delle email di promemoria. |
| | Oggetto email | Coinvolgente | Cruciale per i tassi di apertura. |
| | Contenuto email | Personalizzato | Messaggio principale per recuperare il carrello. |
| | Codice sconto | Opzionale | Incentivo alla conversione. |
| | A/B Testing | Opzionale | Ottimizza le prestazioni della campagna. |
| **Dashboard** | Tutti i KPI | N/A (Reporting) | Fornisce una panoramica delle prestazioni e del ROI. |
| **Log** | Tutte le voci di log | N/A (Reporting) | Cronologia dettagliata per la risoluzione dei problemi e l'audit. |
| **Impostazioni** | Abilita modulo | SÌ | Attiva/disattiva il modulo. |
| | Valore minimo carrello per tracciamento | 0 (o la tua soglia) | Filtro globale per tutti i carrelli tracciati. |
| | Tempo per considerare il carrello abbandonato | 30-60 minuti | Definisce quando un carrello è "abbandonato". |
| | Max email per cliente | Limite ragionevole | Impedisce lo spam ai clienti. |
| | Tempo minimo tra le email | Limite ragionevole | Impedisce l'invio rapido di email. |
| | Abilita link di opt-out | SÌ | Conformità GDPR, scelta del cliente. |
| | URL Cron Job | Copia dal modulo | **CRITICO:** Abilita l'elaborazione in background. |
| | Nome e email del mittente | Nome del tuo negozio, email professionale | Influisce sulla deliverability e sulla fiducia nel marchio. |
| | Modalità debug | NO | Solo per la risoluzione dei problemi degli sviluppatori. |

## 3. Risoluzione dei problemi per i commercianti e domande frequenti (FAQ)

**D1: I miei clienti non ricevono le email di promemoria. Cosa dovrei controllare?**
R1:

-   **Cron Job:** Questo è il problema più comune. Assicurati che il tuo cron job sia configurato correttamente sul tuo server e che venga eseguito regolarmente (ogni 5-15 minuti). L'URL esatto si trova in **Abandoned Cart Reminder Pro > Impostazioni**.
-   **Modulo abilitato:** Controlla **Abandoned Cart Reminder Pro > Impostazioni** per assicurarti che il modulo sia abilitato globalmente.
-   **Campagne attive:** Verifica che le tue campagne siano abilitate e abbiano passaggi attivi in **Abandoned Cart Reminder Pro > Campagne**.
-   **Configurazione email:** Controlla le impostazioni email di PrestaShop (Parametri avanzati > E-mail) per assicurarti che il tuo negozio possa inviare email in generale.
-   **Filtri antispam:** Chiedi a un cliente di prova di controllare la sua cartella spam/posta indesiderata. Assicurati che il tuo indirizzo email del mittente sia professionale e non in blacklist.
-   **Log:** Vai a **Abandoned Cart Reminder Pro > Log** per vedere se le email sono in coda, inviate o se ci sono messaggi di errore.

**D2: Perché alcuni carrelli abbandonati non attivano una campagna?**
R2:

-   **Valore minimo del carrello:** Controlla il "Valore minimo del carrello per il tracciamento" globale in **Abandoned Cart Reminder Pro > Impostazioni** e il "Valore minimo del carrello" specifico per le tue campagne in **Abandoned Cart Reminder Pro > Campagne**. I carrelli al di sotto di questi valori verranno ignorati.
-   **Tempo per considerare il carrello abbandonato:** Assicurati che il tempo impostato in **Abandoned Cart Reminder Pro > Impostazioni** sia trascorso dall'ultima attività del carrello.
-   **Gruppi di clienti/Targeting prodotti:** Se la tua campagna ha un targeting specifico per gruppi di clienti o prodotti, assicurati che il carrello abbandonato soddisfi tali criteri.
-   **Limiti anti-spam:** Il cliente potrebbe aver raggiunto i limiti "Max email per cliente" o "Tempo minimo tra le email" impostati in **Abandoned Cart Reminder Pro > Impostazioni**.
-   **Opt-Out del cliente:** Il cliente potrebbe aver precedentemente scelto di non ricevere promemoria. Controlla i log.

**D3: Come faccio a essere sicuro che le email di promemoria abbiano un bell'aspetto sui dispositivi mobili?**
R3: Il modulo utilizza modelli di email responsive. Tuttavia, il contenuto che aggiungi nel costruttore di email può influire su questo.

-   **Mantienilo semplice:** Evita layout eccessivamente complessi o immagini molto larghe.
-   **Testa:** Invia sempre un'email di prova a te stesso e visualizzala su diversi dispositivi (desktop, tablet, telefono) prima di attivare una campagna.
-   **Tema PrestaShop:** Assicurati che il tuo tema PrestaShop principale sia mobile-responsive, poiché i link nelle email reindirizzeranno al tuo negozio.

**D4: Posso tradurre il contenuto dell'email e gli oggetti?**
R4: Sì! Quando modifichi un passaggio della campagna, vedrai le schede linguistiche per l'oggetto e il contenuto dell'email. Puoi fornire diverse traduzioni per ogni lingua installata nel tuo negozio PrestaShop. Questo è fondamentale per i negozi internazionali.

**D5: Ho svuotato la cache di Smarty e ora qualcosa non va. Cosa è successo?**
R5: Svuotare la cache di Smarty (sotto **Parametri avanzati > Prestazioni**) è un passaggio comune per la risoluzione dei problemi di visualizzazione. Sebbene generalmente sicuro, a volte può influire temporaneamente su come i moduli rendono il loro contenuto fino a quando la cache non viene ricostruita. Se noti problemi di visualizzazione dopo aver svuotato la cache, prova ad aggiornare la pagina più volte o a salvare nuovamente la configurazione del modulo (anche senza modificare nulla) per forzare una ricostruzione della cache per il modulo. Questo modulo utilizza i propri meccanismi di caching, quindi svuotare la cache di Smarty non dovrebbe influire direttamente sulla sua funzionalità principale, ma piuttosto sulla visualizzazione della sua interfaccia di amministrazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Abandoned Cart Reminder Pro" per sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura robusta e basata su eventi, aderendo al modello MVC di PrestaShop dove appropriato, ma sfruttando anche un contenitore di servizi personalizzato e l'autoloading per una migliore organizzazione e testabilità. Si basa fortemente sui cron job per l'elaborazione in background, garantendo che l'invio di email e il tracciamento del carrello non influiscano sulle prestazioni del front-office. I componenti chiave includono:

-   **Tracciamento del carrello:** Si aggancia a `ActionCartSave` e `ActionValidateOrder` per monitorare lo stato del carrello.
-   **Motore delle campagne:** Gestisce sequenze di email a più passaggi, targeting e generazione di sconti.
-   **Processore della coda:** Gestisce l'invio asincrono di email tramite cron.
-   **Analisi e attribuzione:** Traccia i tassi di recupero e i ricavi.
-   **Controller di amministrazione:** Controller dedicati per la gestione delle campagne, la visualizzazione dei log e la configurazione delle impostazioni.
-   **Conformità GDPR:** Include un meccanismo di opt-out.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono interazioni specifiche del front-office, principalmente per l'esecuzione del cron, il tracciamento e l'opt-out.

-   `controllers/front/cron.php`
    -   **Nome classe:** `CartRemProCronModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Questo è l'endpoint primario per il cron job del modulo. Quando viene acceduto, attiva il `CartRemProQueueProcessor` per elaborare la coda dei carrelli abbandonati, inviare le email pianificate e aggiornare le statistiche. È progettato per essere chiamato da un'attività cron lato server, non direttamente dagli utenti.
-   `controllers/front/index.php`
    -   **Nome classe:** `CartRemProIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Una pratica standard di PrestaShop per prevenire l'elenco diretto delle directory. Tipicamente reindirizza alla homepage del negozio o visualizza una pagina vuota.
-   `controllers/front/optout.php`
    -   **Nome classe:** `CartRemProOptoutModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce le richieste dei clienti di opt-out dai promemoria del carrello abbandonato. Elabora l'azione `optout`, aggiorna la preferenza del cliente e visualizza una pagina di conferma (`optout.tpl`).
-   `controllers/front/track.php`
    -   **Nome classe:** `CartRemProTrackModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Utilizzato per tracciare le aperture delle email e i clic sui link all'interno delle email di promemoria. Registra questi eventi nei log del modulo, consentendo l'analisi dell'engagement delle email.

#### Controller di amministrazione Back-Office

Questi controller gestiscono l'interfaccia del modulo nel Back Office di PrestaShop.

-   `controllers/admin/AdminCartRemProCampaignsController.php`
    -   **Nome scheda:** Abandoned Cart Reminder Pro > Campagne
    -   **Responsabilità:** Gestisce la creazione, la modifica, la duplicazione e l'eliminazione delle campagne di carrello abbandonato. Gestisce l'invio del modulo per i dettagli della campagna, i passaggi, le regole di targeting e le configurazioni di A/B testing. Interagisce con le classi `CartRemProCampaign` e `CartRemProCampaignStep`.
-   `controllers/admin/AdminCartRemProDashboardController.php`
    -   **Nome scheda:** Abandoned Cart Reminder Pro > Dashboard
    -   **Responsabilità:** Visualizza le metriche di performance del modulo, inclusi carrelli abbandonati, carrelli recuperati, ricavi attribuiti e ROI. Aggrega i dati da `CartRemProAnalytics` e `CartRemProAbandoned` per presentare una panoramica completa.
-   `controllers/admin/AdminCartRemProLogsController.php`
    -   **Nome scheda:** Abandoned Cart Reminder Pro > Log
    -   **Responsabilità:** Fornisce un log dettagliato di tutte le attività del modulo, come abbandoni di carrello, invii di email, aperture, clic e recuperi. Consente di filtrare e cercare in questi log per la risoluzione dei problemi e l'audit.
-   `controllers/admin/AdminCartRemProSettingsController.php`
    -   **Nome scheda:** Abandoned Cart Reminder Pro > Impostazioni
    -   **Responsabilità:** Gestisce le impostazioni di configurazione globali per il modulo, inclusa l'abilitazione/disabilitazione, i limiti anti-spam, le opzioni GDPR e la visualizzazione dell'URL del cron job. Interagisce con la classe `Configuration` di PrestaShop.
-   `controllers/admin/index.php`
    -   **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire l'elenco diretto delle directory.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo utilizza un ricco set di classi personalizzate per la sua logica di business, molte delle quali estendono `ObjectModel` per l'interazione con il database.

-   `classes/CartRemProAbandoned.php`
    -   **Tabella database:** `ps_cartrempro_abandoned`
    -   **Estende:** `ObjectModel`
    -   **Campi `$definition`:** `id_cart`, `id_customer`, `id_shop`, `id_lang`, `cart_value`, `date_add`, `date_upd`, `is_recovered`, `is_optout`
    -   **Metodi pubblici chiave:** Gestisce il tracciamento e lo stato dei carrelli abbandonati.
-   `classes/CartRemProAbTesting.php`
    -   **Responsabilità:** Gestisce la logica per l'A/B testing all'interno dei passaggi della campagna, inclusa la divisione del traffico e il tracciamento dei tassi di conversione per diverse varianti.
-   `classes/CartRemProAdminController.php`
    -   **Estende:** `ModuleAdminController`
    -   **Responsabilità:** Una classe base per i controller di amministrazione del modulo, che fornisce funzionalità e utilità comuni specifiche per l'interfaccia di back-office del modulo.
-   `classes/CartRemProAdminUi.php`
    -   **Responsabilità:** Classe helper per la generazione e il rendering di elementi UI comuni nel pannello di amministrazione, garantendo la coerenza.
-   `classes/CartRemProAnalytics.php`
    -   **Responsabilità:** Raccoglie ed elabora i dati per la dashboard, calcolando KPI come il tasso di recupero, i ricavi attribuiti e il ROI.
-   `classes/CartRemProAntiSpam.php`
    -   **Responsabilità:** Implementa la logica per i limiti anti-spam, garantendo che i clienti non ricevano troppe email in un dato periodo.
-   `classes/CartRemProAttribution.php`
    -   **Responsabilità:** Determina se un carrello recuperato può essere attribuito a una specifica campagna di promemoria per carrelli abbandonati.
-   `classes/CartRemProAutoload.php`
    -   **Responsabilità:** Autoloader personalizzato per le classi del modulo, garantendo che vengano caricate in modo efficiente senza entrare in conflitto con l'autoloader predefinito di PrestaShop.
-   `classes/CartRemProCampaign.php`
    -   **Tabella database:** `ps_cartrempro_campaign`
    -   **Estende:** `ObjectModel`
    -   **Campi `$definition`:** `name`, `active`, `min_cart_value`, `customer_groups`, `products`, `categories`, `date_add`, `date_upd`
    -   **Metodi pubblici chiave:** Rappresenta una campagna di carrello abbandonato, gestendo le sue impostazioni, le regole di targeting e i passaggi associati.
-   `classes/CartRemProCampaignEngine.php`
    -   **Responsabilità:** La logica principale per valutare i carrelli abbandonati rispetto alle campagne attive, determinando quale campagna (se presente) dovrebbe essere attivata e pianificando il passaggio successivo dell'email.
-   `classes/CartRemProCampaignStep.php`
    -   **Tabella database:** `ps_cartrempro_campaign_step`
    -   **Estende:** `ObjectModel`
    -   **Campi `$definition`:** `id_cartrempro_campaign`, `delay_hours`, `subject`, `content`, `discount_type`, `discount_value`, `ab_test_active`, `ab_test_variations`
    -   **Metodi pubblici chiave:** Definisce un singolo passaggio all'interno di una campagna, inclusi il contenuto dell'email, il ritardo e lo sconto.
-   `classes/CartRemProCartTracker.php`
    -   **Responsabilità:** Monitora i carrelli dei clienti, identifica quando diventano abbandonati e li registra nella tabella `ps_cartrempro_abandoned`.
-   `classes/CartRemProChannelEmail.php`
    -   **Implementa:** `CartRemProChannelInterface`
    -   **Responsabilità:** Gestisce l'invio effettivo delle email di promemoria, inclusa la renderizzazione dei modelli di email e l'integrazione con la classe Mail di PrestaShop.
-   `classes/CartRemProChannelInterface.php`
    -   **Responsabilità:** Definisce un'interfaccia comune per diversi canali di comunicazione (attualmente solo email, ma estensibile per SMS, notifiche web push).
-   `classes/CartRemProCompat.php`
    -   **Responsabilità:** Fornisce livelli di compatibilità per diverse versioni di PrestaShop (1.7, 8.x, 9.x) per garantire un funzionamento fluido nell'intervallo supportato.
-   `classes/CartRemProDiscountGenerator.php`
    -   **Responsabilità:** Crea codici sconto unici e una tantum (Regole carrello) per i clienti che ricevono un'email di promemoria con un'offerta di sconto.
-   `classes/CartRemProEmailRenderer.php`
    -   **Responsabilità:** Rende i modelli Smarty per le email di promemoria, iniettando dati dinamici come dettagli del carrello, informazioni sul cliente e codici sconto.
-   `classes/CartRemProGdpr.php`
    -   **Responsabilità:** Gestisce le funzionalità di conformità al GDPR, in particolare il meccanismo di opt-out del cliente.
-   `classes/CartRemProProductBlocks.php`
    -   **Responsabilità:** Helper per la generazione di blocchi relativi ai prodotti all'interno dei modelli di email, come elenchi di prodotti del carrello abbandonato o prodotti consigliati.
-   `classes/CartRemProQueueProcessor.php`
    -   **Responsabilità:** Il cuore del cron job. Recupera le attività pianificate dalla coda (es. invia email, controlla lo stato del carrello), le elabora e aggiorna i log.
-   `classes/CartRemProScheduleGuard.php`
    -   **Responsabilità:** Garantisce che le attività pianificate vengano eseguite una sola volta e entro i tempi previsti, prevenendo email o azioni duplicate.
-   `classes/CartRemProSegmentation.php`
    -   **Responsabilità:** Implementa la logica per la segmentazione di clienti e carrelli in base alle regole di targeting della campagna (es. valore del carrello, gruppo di clienti, prodotti).
-   `classes/CartRemProServiceContainer.php`
    -   **Responsabilità:** Un contenitore di iniezione di dipendenze personalizzato per gestire e fornire istanze dei servizi e delle classi principali del modulo, migliorando la modularità e la testabilità.
-   `classes/CartRemProStockChecker.php`
    -   **Responsabilità:** Controlla i livelli di stock dei prodotti prima di inviare i promemoria per garantire che gli articoli in un carrello abbandonato siano ancora disponibili.
-   `classes/CartRemProTabInstaller.php`
    -   **Responsabilità:** Gestisce l'installazione e la disinstallazione delle schede del menu di amministrazione del modulo nel Back Office di PrestaShop.
-   `classes/index.php`
    -   **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire l'elenco diretto delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cartrempro/devtools/crp-ab-stats-demo-console.js`
    -   **Ambito:** Back-office (strumenti per sviluppatori)
    -   **Responsabilità:** Probabilmente uno script di sviluppo per dimostrare o eseguire il debug delle statistiche di A/B testing nella console del browser. Non per uso in produzione.
-   `cartrempro/devtools/crp-dashboard-demo-console.js`
    -   **Ambito:** Back-office (strumenti per sviluppatori)
    -   **Responsabilità:** Simile a quanto sopra, per dimostrare o eseguire il debug dei dati della dashboard. Non per uso in produzione.
-   `cartrempro/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (moduli di amministrazione)
    -   **Responsabilità:** Fornisce la funzionalità di autocompletamento per i campi di input, probabilmente utilizzata per selezionare prodotti o categorie nel targeting delle campagne. Si lega agli eventi di input ed effettua chiamate AJAX per i suggerimenti di ricerca.
-   `cartrempro/views/js/admin-common.js`
    -   **Ambito:** Back-office (amministrazione globale)
    -   **Responsabilità:** Contiene funzioni JavaScript comuni e listener di eventi utilizzati in varie schermate di amministrazione del modulo, come la gestione generale dei moduli, le funzioni di utilità AJAX e i miglioramenti dell'interfaccia utente.
-   `cartrempro/views/js/admin-dashboard.js`
    -   **Ambito:** Back-office (Dashboard)
    -   **Responsabilità:** Gestisce gli elementi interattivi e la visualizzazione dei dati sulla dashboard del modulo, potenzialmente rendendo grafici o aggiornando le statistiche dinamicamente.
-   `cartrempro/views/js/campaigns-admin.js`
    -   **Ambito:** Back-office (Campagne)
    -   **Responsabilità:** Gestisce l'interfaccia utente complessa per la creazione e la modifica delle campagne, inclusa l'aggiunta/rimozione di passaggi della campagna, la configurazione delle regole di targeting, la gestione delle opzioni di sconto e la gestione delle variazioni di A/B test. Si lega agli eventi di clic sui pulsanti, agli eventi di modifica sulle caselle di selezione e agli invii di moduli.
-   `cartrempro/views/js/email-builder.js`
    -   **Ambito:** Back-office (Campagne - Contenuto email)
    -   **Responsabilità:** Migliora l'editor di testo ricco utilizzato per il contenuto delle email, potenzialmente aggiungendo pulsanti personalizzati per segnaposto dinamici (es. `{{customer_name}}`, `{{cart_link}}`) o fornendo anteprime in tempo reale.
-   `cartrempro/views/js/logs-admin.js`
    -   **Ambito:** Back-office (Log)
    -   **Responsabilità:** Fornisce funzionalità interattive per la tabella dei log, come filtraggio, ricerca, paginazione e potenzialmente popup modali per la visualizzazione delle anteprime delle email.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cartrempro/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office (moduli di amministrazione)
    -   **Componenti UI principali:** Stila i suggerimenti a discesa dell'autocompletamento e i campi di input utilizzati nello strumento di ricerca.
    -   **Selettori di classe CSS chiave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`
-   `cartrempro/views/css/admin.css`
    -   **Ambito:** Back-office (amministrazione globale)
    -   **Componenti UI principali:** Fornisce lo stile generale per l'interfaccia di amministrazione del modulo, inclusi layout della dashboard, moduli delle campagne, tabelle dei log e stile generale di pulsanti/input.
    -   **Selettori di classe CSS chiave:** `.cartrempro-dashboard`, `.cartrempro-campaign-form`, `.cartrempro-logs-table`, `.crp-badge`, `.crp-stat-card`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

Il modulo non elenca esplicitamente i template in una directory `hook/`, suggerendo che il rendering front-office per gli hook potrebbe essere gestito direttamente all'interno del file principale del modulo o tramite specifici controller frontali.

#### Template di amministrazione (`views/templates/admin/`)

Questi template rendono l'interfaccia del Back Office del modulo.

-   `cartrempro/views/templates/admin/ab_email_preview.tpl`
    -   **Scopo:** Visualizza un'anteprima di una variazione di email di A/B test.
-   `cartrempro/views/templates/admin/campaigns.tpl`
    -   **Scopo:** Il template principale per la schermata di amministrazione "Campagne", che elenca le campagne e fornisce moduli per l'aggiunta/modifica.
-   `cartrempro/views/templates/admin/dashboard.tpl`
    -   **Scopo:** Il template principale per la schermata "Dashboard", che visualizza i KPI e i grafici delle prestazioni.
-   `cartrempro/views/templates/admin/logs.tpl`
    -   **Scopo:** Il template principale per la schermata "Log", che presenta la tabella delle attività del modulo.
-   `cartrempro/views/templates/admin/logs_email_preview.tpl`
    -   **Scopo:** Visualizza un'anteprima di un'email dai log.
-   `cartrempro/views/templates/admin/settings.tpl`
    -   **Scopo:** Il template principale per la schermata "Impostazioni", contenente le opzioni di configurazione globali.
-   `cartrempro/views/templates/admin/_partials/ab_stats.tpl`
    -   **Scopo:** Rende le statistiche per le variazioni di A/B test all'interno di una campagna.
-   `cartrempro/views/templates/admin/_partials/campaign_form.tpl`
    -   **Scopo:** Parziale riutilizzabile per il modulo di creazione/modifica della campagna, inclusi passaggi, targeting e impostazioni generali.
-   `cartrempro/views/templates/admin/_partials/campaign_list_compact.tpl`
    -   **Scopo:** Rende un elenco compatto di campagne, possibilmente per widget della dashboard o panoramiche rapide.
-   `cartrempro/views/templates/admin/_partials/campaign_targeting.tpl`
    -   **Scopo:** Rende la sezione delle regole di targeting all'interno del modulo della campagna.
-   `cartrempro/views/templates/admin/_partials/copy_box.tpl`
    -   **Scopo:** Un componente riutilizzabile per visualizzare testo che può essere facilmente copiato (es. l'URL del cron job).
-   `cartrempro/views/templates/admin/_partials/empty_state.tpl`
    -   **Scopo:** Visualizza un messaggio quando un elenco o una sezione è vuota (es. "Nessuna campagna trovata").
-   `cartrempro/views/templates/admin/_partials/icon_duplicate.tpl`
    -   **Scopo:** Rende un'icona di duplicazione.
-   `cartrempro/views/templates/admin/_partials/icon_edit.tpl`
    -   **Scopo:** Rende un'icona di modifica.
-   `cartrempro/views/templates/admin/_partials/icon_trash.tpl`
    -   **Scopo:** Rende un'icona di cestino/eliminazione.
-   `cartrempro/views/templates/admin/_partials/page_header.tpl`
    -   **Scopo:** Rende un'intestazione coerente per le pagine di amministrazione all'interno del modulo.
-   `cartrempro/views/templates/admin/_partials/status_badge.tpl`
    -   **Scopo:** Rende un badge visivo che indica lo stato (es. "Attivo", "Inattivo").
-   `cartrempro/views/templates/admin/_partials/stat_card.tpl`
    -   **Scopo:** Rende una singola scheda statistica per la dashboard (es. "Carrelli recuperati").
-   `cartrempro/views/templates/admin/_partials/step_subject_lang.tpl`
    -   **Scopo:** Rende il campo di input dell'oggetto con schede linguistiche per i passaggi della campagna.
-   `cartrempro/views/templates/admin/_partials/toggle_row.tpl`
    -   **Scopo:** Rende una riga con un interruttore (es. per abilitare/disabilitare un'impostazione).

#### Template front-office (`views/templates/front/`)

-   `cartrempro/views/templates/front/optout.tpl`
    -   **Scopo:** Visualizza la pagina di conferma dopo che un cliente ha scelto di non ricevere più promemoria di carrello abbandonato.

#### Template email (`views/templates/email/`)

-   `cartrempro/views/templates/email/default_recovery.tpl`
    -   **Scopo:** Il template di base predefinito per le email di promemoria del carrello abbandonato. Include segnaposto per contenuti dinamici come nome cliente, link carrello, elenco prodotti e codici sconto. Gli sviluppatori possono personalizzare questo template o crearne di nuovi per diversi design di email.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo crea le seguenti tabelle personalizzate durante l'installazione:

-   `ps_cartrempro_abandoned`: Memorizza i dettagli dei carrelli abbandonati.
    -   `id_cartrempro_abandoned` (PK)
    -   `id_cart` (FK a `ps_cart`)
    -   `id_customer` (FK a `ps_customer`)
    -   `id_shop` (FK a `ps_shop`)
    -   `id_lang` (FK a `ps_lang`)
    -   `cart_value` (decimale)
    -   `date_add` (datetime)
    -   `date_upd` (datetime)
    -   `is_recovered` (tinyint)
    -   `is_optout` (tinyint)
-   `ps_cartrempro_campaign`: Memorizza i dettagli di ogni campagna di promemoria.
    -   `id_cartrempro_campaign` (PK)
    -   `name` (varchar)
    -   `active` (tinyint)
    -   `min_cart_value` (decimale)
    -   `customer_groups` (text - array serializzato)
    -   `products` (text - array serializzato)
    -   `categories` (text - array serializzato)
    -   `date_add` (datetime)
    -   `date_upd` (datetime)
-   `ps_cartrempro_campaign_step`: Memorizza i dettagli di ogni passaggio all'interno di una campagna.
    -   `id_cartrempro_campaign_step` (PK)
    -   `id_cartrempro_campaign` (FK a `ps_cartrempro_campaign`)
    -   `delay_hours` (int)
    -   `subject` (text - multi-lingua)
    -   `content` (text - multi-lingua)
    -   `discount_type` (varchar)
    -   `discount_value` (decimale)
    -   `ab_test_active` (tinyint)
    -   `ab_test_variations` (text - array serializzato)
-   `ps_cartrempro_log`: Memorizza i log dettagliati delle attività del modulo.
    -   `id_cartrempro_log` (PK)
    -   `id_cart`
    -   `id_customer`
    -   `id_cartrempro_campaign`
    -   `id_cartrempro_campaign_step`
    -   `event_type` (varchar)
    -   `details` (text)
    -   `date_add` (datetime)
-   `ps_cartrempro_queue`: Memorizza le attività pianificate per il cron job.
    -   `id_cartrempro_queue` (PK)
    -   `id_cart`
    -   `id_cartrempro_campaign`
    -   `id_cartrempro_campaign_step`
    -   `task_type` (varchar)
    -   `scheduled_at` (datetime)
    -   `processed_at` (datetime)
    -   `status` (varchar)
    -   `error_message` (text)

#### Tabella degli hook registrati

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `ActionObjectCartUpdateAfter` | Dopo l'aggiornamento di un oggetto `Cart` (es. prodotto aggiunto/rimosso, quantità modificata). | Utilizzato per tracciare le modifiche ai carrelli dei clienti e identificare potenziali abbandoni. |
| `actionDispatcher` | Prima che un controller venga spedito. | Potenzialmente utilizzato per il routing, la riscrittura degli URL o l'inizializzazione precoce. |
| `ActionCronJob` | Quando viene eseguito il cron job nativo di PrestaShop (se configurato). | Attiva il controller `cron.php` del modulo per elaborare la coda. |
| `ActionFrontControllerInit` | Prima dell'inizializzazione di qualsiasi controller frontale. | Utilizzato per la configurazione iniziale, come la registrazione delle risorse del modulo o il routing specifico. |
| `moduleRoutes` | Durante la generazione del routing URL. | Consente al modulo di definire URL personalizzati e amichevoli per i suoi controller frontali (es. `/cartrempro/optout`). |
| `displayModuleRoutes` | Simile a `moduleRoutes`, spesso utilizzato per visualizzare o eseguire il debug delle rotte. | Meno comune per la logica funzionale, più per il debug. |
| `ActionCartSave` | Dopo il salvataggio di un carrello nel database. | Cruciale per tracciare l'attività del carrello e identificare quando un carrello viene abbandonato. |
| `ActionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Utilizzato per contrassegnare un carrello abbandonato come "recuperato" se porta a un acquisto completato. |
| `ActionCustomerAccountAdd` | Dopo la creazione di un nuovo account cliente. | Potenzialmente utilizzato per la segmentazione o il tracciamento iniziale del cliente, sebbene meno critico per la logica principale del carrello abbandonato. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a fornire assistenza tempestiva e a garantire che il tuo modulo funzioni senza intoppi.

-   **MyPresta.eu Cronologia ordini e download:** <https://mypresta.eu/my-account/orders/>
-   **Contatto supporto:** [support@mypresta.eu](mailto:support@mypresta.eu)
