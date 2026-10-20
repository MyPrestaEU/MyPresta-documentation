---
title: "Cart protection pro - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Cart protection pro di MyPresta.eu."
sidebar:
  label: "Cart protection pro - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cart protection pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per le integrazioni API esterne (come CleanTalk o StopForumSpam) se scegli di abilitarle. La maggior parte degli ambienti di hosting moderni le fornisce già.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo è il pannello di controllo principale per "Cart protection pro", dove definisci come il modulo rileva e risponde all'attività sospetta del carrello.

#### Impostazioni Generali

-   **Abilitato**:

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Il modulo monitora attivamente l'attività del carrello e applica le regole di protezione scelte.
        -   *Quando disabilitato:* Il modulo è inattivo e non proteggerà il tuo negozio dagli attacchi di carrelli falsi.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Mantienilo sempre abilitato per assicurarti che il tuo negozio sia protetto. Disabilita solo per la risoluzione dei problemi o la manutenzione.
-   **Tipo di protezione**:

    -   **Cosa fa questa impostazione:** Determina il metodo che il modulo utilizza per identificare e bloccare l'attività sospetta.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando impostato su "Indirizzo IP":* Il modulo traccia i tentativi di carrello in base all'indirizzo IP del visitatore. Se un IP supera i tentativi consentiti, verrà bloccato.
        -   *Quando impostato su "Cookie":* Il modulo traccia i tentativi di carrello utilizzando un cookie del browser. Se un browser (identificato dal cookie) supera i tentativi, verrà bloccato. Questo è meno affidabile poiché i cookie possono essere cancellati.
        -   *Quando impostato su "Indirizzo IP + Cookie":* Combina entrambi i metodi per una protezione più forte. Un IP o un cookie che supera i limiti attiverà un blocco.
        -   *Quando impostato su "CleanTalk":* Utilizza il servizio anti-spam esterno CleanTalk per verificare le richieste. Richiede una chiave API CleanTalk.
        -   *Quando impostato su "StopForumSpam":* Utilizza il database esterno StopForumSpam per verificare se un IP è noto per lo spam. Richiede una chiave StopForumSpam.
    -   **Valore consigliato:** "Indirizzo IP + Cookie" per una robusta protezione locale, o "CleanTalk" / "StopForumSpam" se hai account con questi servizi per controlli esterni avanzati.
    -   **Scenario / esempio del commerciante:** Se stai riscontrando un volume elevato di carrelli falsi, inizia con "Indirizzo IP + Cookie". Se il problema persiste o desideri controlli più avanzati, considera l'integrazione con CleanTalk o StopForumSpam.
-   **Intervallo di tempo**:

    -   **Cosa fa questa impostazione:** Definisce la durata (in minuti) entro la quale il modulo conta i tentativi di carrello da una singola fonte (IP o cookie).
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Un intervallo di tempo più breve (es. 5 minuti):* Protezione più aggressiva. Un utente/bot verrà bloccato più velocemente se effettua molti tentativi in un breve lasso di tempo.
        -   *Un intervallo di tempo più lungo (es. 60 minuti):* Meno aggressivo. Consente più tentativi per un periodo più lungo prima del blocco.
    -   **Valore consigliato:** 10 minuti
    -   **Scenario / esempio del commerciante:** Se i bot stanno creando rapidamente carrelli, un intervallo di tempo più breve li catturerà più velocemente. Se scopri che utenti legittimi vengono bloccati (raro), potresti aumentarlo leggermente.
-   **Numero di tentativi**:

    -   **Cosa fa questa impostazione:** Imposta il numero massimo di aggiunte al carrello consentite da una singola fonte (IP o cookie) entro l'“Intervallo di tempo” definito prima che venga attivato un blocco.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Un numero inferiore (es. 3):* Molto aggressivo. Un utente/bot verrà bloccato dopo solo poche aggiunte al carrello.
        -   *Un numero superiore (es. 10):* Meno aggressivo. Consente più aggiunte al carrello prima del blocco.
    -   **Valore consigliato:** 5
    -   **Scenario / esempio del commerciante:** Un cliente normale raramente aggiunge più di 5 articoli al carrello entro un intervallo di 10 minuti. I bot, tuttavia, spesso cercano di aggiungerne decine o centinaia. Impostare questo valore a 5 aiuta a differenziare.
-   **Titolo dell'email al commerciante**:

    -   **Cosa fa questa impostazione:** Specifica l'oggetto per la notifica email inviata a te (il commerciante) quando si verifica un blocco di protezione del carrello.
    -   **Effetto del cambiamento di questa impostazione:** Cambia l'oggetto delle email di avviso che ricevi.
    -   **Valore consigliato:** "Cart Protection Pro - Avviso di Blocco!"
    -   **Scenario / esempio del commerciante:** Personalizza questo per rendere gli avvisi facilmente riconoscibili nella tua casella di posta, ad esempio, "URGENTE: Bot Bloccato su [Nome del tuo negozio]".
-   **Log**:

    -   **Cosa fa questa impostazione:** Controlla se il modulo registra i dettagli dei tentativi di carrello e dei blocchi nel tuo database PrestaShop.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Il modulo memorizza una cronologia di tutti i tentativi e i blocchi, che puoi rivedere nelle sezioni "Tentativi" e "Blocchi" del modulo. Questo è cruciale per monitorare e comprendere gli attacchi.
        -   *Quando disabilitato:* Non vengono conservati log, rendendo più difficile tracciare o risolvere i problemi.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Mantieni sempre i log abilitati. Forniscono preziose informazioni sui tipi e la frequenza degli attacchi che il tuo negozio subisce, aiutandoti a perfezionare le tue impostazioni.

#### Integrazione CleanTalk

-   **Attiva il supporto gratuito CleanTalk**:

    -   **Cosa fa questa impostazione:** Abilita l'integrazione con il servizio anti-spam CleanTalk per controlli spam in tempo reale. CleanTalk offre un piano gratuito per controlli di base.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Il modulo invierà richieste a CleanTalk per verificare se un indirizzo IP o un'email (se disponibile) è noto per lo spam prima di consentire le aggiunte al carrello.
        -   *Quando disabilitato:* I controlli CleanTalk non vengono eseguiti.
    -   **Valore consigliato:** NO (a meno che tu non abbia un account CleanTalk e una chiave API)
    -   **Scenario / esempio del commerciante:** Se utilizzi già CleanTalk per altre protezioni anti-spam (es. commenti, registrazioni) o desideri un ulteriore livello di verifica esterna, abilita questa opzione.
-   **Attiva il supporto a pagamento CleanTalk**:

    -   **Cosa fa questa impostazione:** Abilita l'integrazione con il servizio anti-spam CleanTalk, specificamente per le funzionalità disponibili con un abbonamento CleanTalk a pagamento.
    -   **Effetto del cambiamento di questa impostazione:** Simile al supporto gratuito, ma potenzialmente con controlli più avanzati se il tuo piano CleanTalk lo consente.
    -   **Valore consigliato:** NO (a meno che tu non abbia un account CleanTalk a pagamento e una chiave API)
    -   **Scenario / esempio del commerciante:** Scegli questa opzione se hai un abbonamento CleanTalk a pagamento e desideri sfruttare tutte le sue capacità per la protezione del carrello.
-   **Chiave API CleanTalk**:

    -   **Cosa fa questa impostazione:** Questa è la chiave unica fornita da CleanTalk che autentica il tuo negozio con il loro servizio.
    -   **Effetto del cambiamento di questa impostazione:** Senza una chiave API valida, l'integrazione CleanTalk non funzionerà, anche se abilitata.
    -   **Valore consigliato:** La tua effettiva chiave API CleanTalk (lascia vuoto se non utilizzi CleanTalk).
    -   **Scenario / esempio del commerciante:** Dopo esserti iscritto a CleanTalk, riceverai una chiave API. Inseriscila qui per attivare il loro servizio.

#### Integrazione StopForumSpam

-   **Attiva il supporto StopForumSpam**:

    -   **Cosa fa questa impostazione:** Abilita l'integrazione con il database StopForumSpam, che elenca IP, email e nomi utente noti per lo spamming di forum e siti web.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Il modulo interrogherà StopForumSpam per verificare se l'indirizzo IP del visitatore è elencato come spammer noto.
        -   *Quando disabilitato:* I controlli StopForumSpam non vengono eseguiti.
    -   **Valore consigliato:** NO (a meno che tu non abbia una chiave StopForumSpam)
    -   **Scenario / esempio del commerciante:** Questo è un buon livello aggiuntivo di protezione se desideri bloccare IP che sono globalmente riconosciuti come spammer, anche se non hanno ancora attivato i tuoi limiti di carrello locali.
-   **Chiave StopForumSpam**:

    -   **Cosa fa questa impostazione:** Questa è la chiave unica fornita da StopForumSpam che autentica il tuo negozio con il loro servizio.
    -   **Effetto del cambiamento di questa impostazione:** Senza una chiave valida, l'integrazione StopForumSpam non funzionerà, anche se abilitata.
    -   **Valore consigliato:** La tua effettiva chiave API StopForumSpam (lascia vuoto se non utilizzi StopForumSpam).
    -   **Scenario / esempio del commerciante:** Dopo esserti registrato a StopForumSpam, riceverai una chiave API. Inseriscila qui per attivare il loro servizio.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Cart Protection Pro > Tentativi (Back Office > Moduli > Cart Protection Pro > Tentativi)

-   **Nome schermata e posizione nel menu:** Puoi trovare questa schermata navigando su **Moduli > Gestione moduli**, quindi cliccando su "Configura" su "Cart protection pro", e poi selezionando la scheda "Tentativi" (o una voce di menu simile se il modulo aggiunge il proprio menu di primo livello).
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza un elenco (vista a griglia) di tutti i tentativi di carrello registrati che hanno attivato la registrazione del modulo. Mostra dettagli come:
    -   **Indirizzo IP:** L'indirizzo IP del visitatore.
    -   **ID Cookie:** L'identificatore unico del cookie (se la protezione "Cookie" è abilitata).
    -   **Tentativi:** Il numero di aggiunte al carrello effettuate da questa fonte entro l'intervallo di tempo configurato.
    -   **Timestamp:** Quando il tentativo è stato registrato.
    -   **Stato:** Se ha portato a un blocco o è stato solo un tentativo.
-   **Effetto dei cambiamenti:** Questo è un log di sola lettura. Non puoi modificare direttamente i tentativi qui. Il suo scopo è fornire trasparenza e dati per farti comprendere potenziali attacchi. Di solito puoi filtrare e ordinare l'elenco per analizzare i modelli.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questo log, specialmente se sospetti attività di bot. Cerca modelli:
    -   Molti tentativi dallo stesso IP o cookie.
    -   Tentativi concentrati in un breve periodo.
    -   Intervalli IP o posizioni geografiche insolite.
    Questi dati ti aiutano a perfezionare le impostazioni di "Intervallo di tempo" e "Numero di tentativi".

#### 2.2.2 Cart Protection Pro > Blocchi (Back Office > Moduli > Cart Protection Pro > Blocchi)

-   **Nome schermata e posizione nel menu:** Simile alla schermata Tentativi, questa è accessibile tramite **Moduli > Gestione moduli > Configura "Cart protection pro" > Blocchi** (scheda/voce di menu).
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza un elenco (vista a griglia) di tutti gli indirizzi IP o ID cookie che sono stati bloccati dal modulo. Tipicamente mostra:
    -   **Indirizzo IP:** L'IP bloccato.
    -   **ID Cookie:** Il cookie bloccato (se applicabile).
    -   **Motivo:** Perché si è verificato il blocco (es. "Troppi tentativi").
    -   **Ora inizio/fine blocco:** Quando il blocco è stato avviato e se è temporaneo.
    -   **Azioni:** Spesso include opzioni per "Sbloccare" manualmente una voce.
-   **Effetto dei cambiamenti:**
    -   *Sbloccare una voce:* Rimuove il blocco per quell'IP o cookie specifico, consentendo loro di accedere nuovamente alla funzionalità del carrello. Usa con cautela!
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Rivedi periodicamente l'elenco dei blocchi. Se noti che un indirizzo IP legittimo (es. il tuo, o un partner conosciuto) è stato accidentalmente bloccato, puoi sbloccarlo qui.
    -   Cerca indirizzi IP ricorrenti o modelli nei blocchi, che potrebbero indicare attacchi persistenti.
    -   Questa schermata è cruciale per garantire che il modulo stia bloccando efficacemente il traffico malevolo senza influenzare inavvertitamente i clienti reali.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilitato | SÌ | Interruttore principale per la funzionalità del modulo. |
| Configurazione Modulo | Tipo di protezione | Indirizzo IP + Cookie | Metodo per identificare e bloccare attività sospette (IP, Cookie, entrambi, CleanTalk, StopForumSpam). |
| Configurazione Modulo | Intervallo di tempo | 10 minuti | Durata (minuti) per il conteggio dei tentativi di carrello. |
| Configurazione Modulo | Numero di tentativi | 5 | Max aggiunte al carrello entro l'intervallo di tempo prima di un blocco. |
| Configurazione Modulo | Titolo dell'email al commerciante | Cart Protection Pro - Avviso di Blocco! | Oggetto per le email di notifica al commerciante. |
| Configurazione Modulo | Log | SÌ | Abilita/disabilita la registrazione di tentativi e blocchi. |
| Configurazione Modulo | Attiva supporto gratuito CleanTalk | NO | Attiva i controlli anti-spam gratuiti di CleanTalk. |
| Configurazione Modulo | Attiva supporto a pagamento CleanTalk | NO | Attiva i controlli anti-spam a pagamento di CleanTalk. |
| Configurazione Modulo | Chiave API CleanTalk | (vuoto) | La tua chiave API CleanTalk unica. |
| Configurazione Modulo | Attiva supporto StopForumSpam | NO | Attiva i controlli del database IP di StopForumSpam. |
| Configurazione Modulo | Chiave StopForumSpam | (vuoto) | La tua chiave API StopForumSpam unica. |
| AdminCproAttempts | Vista a griglia / Gestione | N/A | Visualizza un log di tutti i tentativi di carrello. |
| AdminCproBans | Vista a griglia / Gestione | N/A | Visualizza un elenco di tutti gli IP/cookie bloccati, con opzione di sblocco. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei clienti si lamentano di non riuscire ad aggiungere articoli al carrello, ma non vedo alcun blocco.**
R1: Innanzitutto, controlla se il modulo "Cart protection pro" è "Abilitato" nella sua configurazione. Se lo è, naviga alla sezione "Blocchi" all'interno della configurazione del modulo. Verifica se sono elencati IP di clienti legittimi. In tal caso, potresti aver impostato il "Numero di tentativi" o l'"Intervallo di tempo" in modo troppo aggressivo. Prova ad aumentare leggermente il "Numero di tentativi" (es. da 3 a 5 o 7) o ad estendere l'"Intervallo di tempo" (es. da 5 a 10-15 minuti). Inoltre, assicurati che il tuo tema o altri moduli non stiano interferendo con il processo del carrello.

**D2: Ho configurato CleanTalk/StopForumSpam, ma non sembra funzionare.**
R2: Ricontrolla quanto segue:
1.  Assicurati che "Attiva il supporto CleanTalk/StopForumSpam" sia abilitato.
2.  Verifica che la tua "Chiave API CleanTalk" o "Chiave StopForumSpam" sia inserita correttamente e sia attiva con il rispettivo servizio. Anche un singolo errore di battitura ne impedirà il funzionamento.
3.  Conferma che il tuo ambiente di hosting consenta le richieste cURL in uscita, necessarie per comunicare con questi servizi esterni. Il tuo host può confermarlo.
4.  Controlla i log "Tentativi" e "Blocchi" del modulo per eventuali voci che indicano un blocco da parte di questi servizi.

**D3: Il mio negozio riceve ancora molti carrelli falsi anche con il modulo abilitato.**
R3: Questo potrebbe indicare un bot sofisticato o che le tue impostazioni non sono abbastanza aggressive.
1.  **Rivedi le tue impostazioni:** Prova a diminuire il "Numero di tentativi" (es. da 5 a 3) e/o ad accorciare l'"Intervallo di tempo" (es. da 10 a 5 minuti).
2.  **Abilita servizi esterni:** Se non l'hai già fatto, considera di abilitare e configurare CleanTalk o StopForumSpam per un ulteriore livello di protezione.
3.  **Verifica i conflitti:** Disabilita temporaneamente altri moduli di sicurezza o di caching per vedere se c'è un conflitto.
4.  **Svuota la cache:** A volte, la cache Smarty di PrestaShop può impedire che le nuove impostazioni del modulo abbiano effetto immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache".

**D4: Questo modulo rallenterà il mio negozio?**
R4: Il modulo è progettato per essere leggero. I controlli principali (IP/Cookie) sono molto veloci. Se abiliti servizi esterni come CleanTalk o StopForumSpam, ci sarà un leggero ritardo mentre il tuo server comunica con le loro API. Tuttavia, questi servizi sono ottimizzati per la velocità e l'impatto è solitamente trascurabile. Il vantaggio di prevenire il sovraccarico del server da carrelli falsi supera di gran lunga qualsiasi tempo di elaborazione minimo.

**D5: Come posso tradurre il titolo dell'email o altri testi del modulo?**
R5: Per il "Titolo dell'email al commerciante", puoi semplicemente modificare il testo direttamente nella configurazione del modulo. Per altri testi del modulo (se fossero visibili ai clienti, cosa che questo modulo generalmente non è), dovresti tipicamente andare su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Cart protection pro" per trovare e modificare le stringhe traducibili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Cart protection pro", destinata a sviluppatori e webmaster che necessitano di comprendere, debuggare o estendere le sue funzionalità.

### 4.1 Panoramica dell'architettura

Il modulo "Cart protection pro" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente gli hook per la sua funzionalità principale e i Controller Admin dedicati per la gestione del back-office. Integra servizi anti-spam esterni (CleanTalk, StopForumSpam) tramite richieste cURL. La logica del modulo è incapsulata nella sua classe principale e nelle classi helper, con la configurazione memorizzata in `ps_configuration` e i log in tabelle di database personalizzate.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questo modulo non definisce esplicitamente controller front-office personalizzati. La sua logica front-office è principalmente eseguita tramite hook all'interno del file del modulo principale `cpro.php`, intercettando le azioni del carrello prima che vengano completamente elaborate.

#### Controller Admin Back-Office

Questi controller gestiscono le schermate di amministrazione dedicate del modulo, fornendo viste a griglia per tentativi e blocchi.

-   `cpro/controllers/admin/AdminCproAttempts.php`

    -   **Nome classe e classe genitore**: `AdminCproAttemptsController` estende `ModuleAdminController`.
    -   **Responsabilità**: Gestisce la visualizzazione e l'interazione per il log "Tentativi" nel Back Office di PrestaShop. Recupera i dati dalla tabella del database `cattempt` e li rende in formato elenco, consentendo all'amministratore di visualizzare tutti i tentativi di carrello registrati. Non consente la modifica diretta dei tentativi, agendo come un visualizzatore di log di sola lettura.
-   `cpro/controllers/admin/AdminCproBans.php`

    -   **Nome classe e classe genitore**: `AdminCproBansController` estende `ModuleAdminController`.
    -   **Responsabilità**: Gestisce la visualizzazione e l'interazione per l'elenco "Blocchi" nel Back Office di PrestaShop. Recupera i dati dalla tabella del database `cban` e li presenta in un elenco. Questo controller gestisce anche azioni come "Sblocca", consentendo a un amministratore di rimuovere un IP o un cookie specifico dall'elenco dei blocchi.
-   `cpro/controllers/admin/index.php`

    -   **Nome classe e classe genitore**: Questo file serve tipicamente come misura di sicurezza in PrestaShop, contenendo `die('No direct script access');` per prevenire l'accesso diretto alla directory. Non contiene una classe controller funzionale.

### 4.3 Classi Core e Modelli (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. La logica principale per la gestione dei tentativi e dei blocchi, incluse le interazioni con il database, è probabilmente gestita direttamente all'interno del file del modulo principale `cpro.php` o tramite chiamate dirette a `Db::getInstance()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript personalizzati. Qualsiasi comportamento dinamico nel back office è probabilmente gestito dal JS core di PrestaShop o da script inline all'interno dei template.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS personalizzati. Lo stile per le schermate del back-office si baserà sul tema amministrativo predefinito di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `cpro/views/templates/admin/main.tpl`
        -   **Scopo**: Questo template è probabilmente utilizzato per la pagina di configurazione principale del modulo, renderizzata dal metodo `getContent()` in `cpro.php`. Contiene la struttura HTML per tutte le impostazioni descritte nella Sezione 4.1, inclusi i campi del modulo per "Tipo di protezione", "Intervallo di tempo", "Numero di tentativi", chiavi API e l'interruttore "Abilitato". Potrebbe anche includere schede di navigazione o collegamenti ai controller `AdminCproAttempts` e `AdminCproBans`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_cattempt`: Memorizza i log dei tentativi di carrello.
        -   `id_cattempt` (Chiave Primaria)
        -   `ip_address` (VARCHAR): Indirizzo IP del visitatore.
        -   `cookie_id` (VARCHAR): Identificatore unico dal cookie del browser.
        -   `attempts` (INT): Numero di aggiunte al carrello.
        -   `date_add` (DATETIME): Timestamp del tentativo.
        -   `status` (TINYINT): Stato, es. 0 per tentativo, 1 per bloccato.
    -   `ps_cban`: Memorizza i record di IP/cookie bloccati.
        -   `id_cban` (Chiave Primaria)
        -   `ip_address` (VARCHAR): Indirizzo IP bloccato.
        -   `cookie_id` (VARCHAR): ID cookie bloccato.
        -   `reason` (TEXT): Motivo del blocco (es. "Troppi tentativi").
        -   `date_add` (DATETIME): Quando il blocco è stato avviato.
        -   `date_expire` (DATETIME): Se il blocco è temporaneo.
    -   **Record di configurazione (in `ps_configuration`)**:
        -   `CPRO_PTYPE_5`: Impostazione del tipo di protezione (es. IP, Cookie, CleanTalk).
        -   `CPRO_CTALK_APIKEY`: Chiave API CleanTalk.
        -   `CPRO_CTALK`: Supporto gratuito CleanTalk abilitato/disabilitato.
        -   `CPRO_CTALK_PAID`: Supporto a pagamento CleanTalk abilitato/disabilitato.
        -   `CPRO_ATMPT`: Numero di tentativi consentiti.
        -   `CPRO_TIME`: Intervallo di tempo in minuti.
        -   `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4`: Flag interni per i tipi di protezione.
        -   `CPRO_SFS`: Supporto StopForumSpam abilitato/disabilitato.
        -   `CPRO_SFS_KEY`: Chiave API StopForumSpam.
        -   `CPRO_MTITLE`: Titolo dell'email per le notifiche al commerciante.
        -   `CPRO_LOGS`: Registrazione abilitata/disabilitata.
        -   `mypresta_updates`, `update_`, `updatev_`: Chiavi interne per gli aggiornamenti del modulo.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionObjectCartAddAfter` | Dopo che un oggetto carrello è stato aggiunto/aggiornato nel database. | Potenzialmente utilizzato per registrare aggiunte al carrello riuscite o per la post-elaborazione dopo il salvataggio di un carrello. |
| `actionCartSave` | Dopo che un carrello è stato salvato (inserito o aggiornato). | Simile a `actionObjectCartAddAfter`, utilizzato per monitorare o registrare le modifiche al carrello. |
| `actionFrontControllerInitBefore` | Prima che il controller frontale si inizializzi. | Punto di intercettazione precoce per controllare IP/cookie bloccati prima che qualsiasi contenuto della pagina venga renderizzato, potenzialmente reindirizzando o visualizzando un messaggio di blocco. |
| `actionObjectCartAddBefore` | Prima che un oggetto carrello venga aggiunto/aggiornato nel database. | **CRITICO**: Questo è l'hook principale per intercettare e convalidare le aggiunte al carrello. Il modulo eseguirà i suoi controlli (IP, cookie, CleanTalk, StopForumSpam) qui e può impedire l'aggiunta al carrello se i limiti vengono superati o viene rilevato un blocco. |
| `displayHeader` | Nella sezione `<head>` delle pagine front-office. | Potrebbe essere utilizzato per iniettare JavaScript necessario (anche se non rilevato) o CSS, o per impostare cookie per il tracciamento. |
| `actionDispatcherBefore` | Prima che il dispatcher elabori la richiesta. | Un altro punto di intercettazione precoce, simile a `actionFrontControllerInitBefore`, che consente al modulo di eseguire controlli e potenzialmente bloccare le richieste prima che raggiungano un controller specifico. |

### 4.8 Integrazioni API Esterne

-   **CleanTalk**: Utilizza cURL per inviare indirizzi IP e potenzialmente altri dati all'API di CleanTalk per la verifica dello spam.
-   **StopForumSpam**: Utilizza cURL per interrogare il database StopForumSpam con indirizzi IP per verificare la presenza di spammer noti.

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo "Cart protection pro", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e che il tuo negozio rimanga sicuro.
