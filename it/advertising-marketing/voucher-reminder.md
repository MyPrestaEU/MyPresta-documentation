---
title: "Voucher Reminder - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Voucher Reminder di MyPresta.eu."
sidebar:
  label: "Voucher Reminder - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Voucher Reminder su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-reminder.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/voucher-reminder/)
>
> ---


# Voucher Reminder

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. L'accesso per impostare un cron job sul tuo server è essenziale per il funzionamento automatico del modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, la prima schermata che vedrai è la pagina di configurazione principale per il modulo Voucher Reminder. Questa pagina è cruciale per impostare la funzionalità principale.

**URL del Cron Job:**

- **Cosa fa questa impostazione:** Visualizza un URL unico che il cron job del tuo server deve chiamare periodicamente. Questo URL attiva il modulo per controllare i voucher in scadenza e inviare promemoria.
- **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. È generato dal modulo. Se il cron job non è impostato correttamente sul tuo server per chiamare questo URL, il modulo non invierà automaticamente alcun promemoria.
- **Valore consigliato:** Copia esattamente questo URL e usalo per impostare un cron job sul tuo server di hosting.
- **Scenario / esempio del commerciante:** Hai creato diverse regole di promemoria, ma non vengono inviate email. La prima cosa da controllare è se hai impostato correttamente il cron job sul tuo server utilizzando questo URL.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Gestione dei promemoria voucher (Back Office > Moduli > Voucher Reminder > Promemoria voucher)

Qui è dove definisci e gestisci le regole di promemoria effettive. Ogni regola specifica quando un promemoria deve essere inviato e quale template email deve utilizzare.

- **Nome schermata e posizione nel menu:** **Promemoria voucher** (sotto **Moduli > Voucher Reminder** nel menu principale di PrestaShop).
- **Azioni e impostazioni disponibili:**
  - **Elenco dei promemoria:** Vedrai una tabella che elenca tutte le tue regole di promemoria definite.
  - **Aggiungi nuovo promemoria:** Clicca sul pulsante "Aggiungi nuovo" per creare una nuova regola di promemoria.
    - **Ricorda (ore prima della scadenza):**
      - **Cosa fa questa impostazione:** Questa è l'impostazione più critica per una regola di promemoria. Determina quante ore *prima* della data di scadenza di un voucher deve essere inviata l'email di promemoria.
      - **Effetto della modifica di questa impostazione:**
        - *Impostato su 24:* Un'email di promemoria verrà inviata esattamente 24 ore prima della scadenza del voucher.
        - *Impostato su 72:* Un'email di promemoria verrà inviata 3 giorni (72 ore) prima della scadenza.
      - **Valore consigliato:** Dipende dalla tua strategia. I valori comuni sono 24, 48, 72 ore, o anche 168 ore (1 settimana).
      - **Scenario / esempio del commerciante:** Vuoi dare ai clienti un ultimo avviso un giorno prima della scadenza del loro voucher. Imposteresti questo valore su `24`. Se vuoi dare loro un preavviso di una settimana, lo imposteresti su `168`.
    - **Titolo:**
      - **Cosa fa questa impostazione:** Un nome descrittivo per la tua regola di promemoria, visibile solo nel Back Office. Questo ti aiuta a identificare diverse regole di promemoria.
      - **Effetto della modifica di questa impostazione:** Cambia l'etichetta per questa regola nel tuo pannello di amministrazione. Nessun impatto sul front office.
      - **Valore consigliato:** Qualcosa di chiaro e descrittivo, ad esempio, "24 ore prima della scadenza", "Settimana prima della scadenza del voucher".
      - **Scenario / esempio del commerciante:** Hai più promemoria. Chiamarli "Promemoria 1 giorno" e "Promemoria 3 giorni" rende facile la gestione.
    - **Titolo email:**
      - **Cosa fa questa impostazione:** Questa è la riga dell'oggetto dell'email che i tuoi clienti riceveranno.
      - **Effetto della modifica di questa impostazione:** Cambia direttamente la riga dell'oggetto delle email di promemoria.
      - **Valore consigliato:** Qualcosa di coinvolgente e chiaro, ad esempio, "Il tuo [Codice Voucher] sta per scadere!", "Non perdere il tuo sconto!".
      - **Scenario / esempio del commerciante:** Vuoi che l'email si distingua nella casella di posta del cliente. Un oggetto come "Ultima possibilità: il tuo sconto scade presto!" è più efficace di uno generico.
    - **File template email:**
      - **Cosa fa questa impostazione:** Specifica quale file di template email (ad esempio, `voucher_reminder.html` e `voucher_reminder.txt`) il modulo deve utilizzare per questo specifico promemoria. Questo ti consente di avere diversi design di email per diverse tempistiche di promemoria.
      - **Effetto della modifica di questa impostazione:** Determina il contenuto e il layout dell'email inviata. Se crei un template personalizzato, selezioneresti il suo nome qui.
      - **Valore consigliato:** Usa il template predefinito a meno che tu non abbia esigenze di design specifiche. Se crei template personalizzati, assicurati che siano posizionati correttamente nella directory `mails` del tuo tema.
      - **Scenario / esempio del commerciante:** Vuoi un'email di promemoria delicata una settimana prima, e un'email più urgente di "ultima possibilità" 24 ore prima. Creeresti due diversi template email e li assegneresti alle rispettive regole di promemoria.
    - **Invia promemoria:**
      - **Cosa fa questa impostazione:** Un semplice interruttore ON/OFF per abilitare o disabilitare questa specifica regola di promemoria.
      - **Effetto della modifica di questa impostazione:**
        - *Abilitato (Sì):* Il modulo invierà email secondo questa regola.
        - *Disabilitato (No):* Questa regola verrà ignorata e non verranno inviate email per essa.
      - **Valore consigliato:** "Sì" una volta che hai configurato la regola e sei pronto a usarla.
      - **Scenario / esempio del commerciante:** Stai testando una nuova regola di promemoria e vuoi assicurarti che sia perfetta prima di attivarla per tutti i clienti. La manterresti disabilitata durante i test.
  - **Pulsante Salva:** Applica tutte le modifiche apportate alla regola di promemoria.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Inizia creando una o due regole di promemoria (ad esempio, 72 ore e 24 ore prima della scadenza).
  2. Usa titoli chiari e oggetti email accattivanti.
  3. Monitora la "Cronologia promemoria voucher" per vedere se le email vengono inviate come previsto.
  4. Considera la creazione di template email personalizzati per diverse tempistiche di promemoria per personalizzare il tuo messaggio.

#### 2.2.2 Cronologia promemoria voucher (Back Office > Moduli > Voucher Reminder > Cronologia)

Questa schermata fornisce un registro di tutte le email di promemoria che sono state inviate con successo dal modulo.

- **Nome schermata e posizione nel menu:** **Cronologia** (sotto **Moduli > Voucher Reminder** nel menu principale di PrestaShop).
- **Azioni e impostazioni disponibili:**
  - **Elenco dei promemoria inviati:** Una tabella che visualizza:
    - **ID:** Identificatore unico per la voce della cronologia.
    - **Data di consegna dell'email:** Quando l'email è stata inviata.
    - **Promemoria:** Quale regola di promemoria (per titolo) ha attivato questa email.
    - **Cliente:** Il cliente che ha ricevuto il promemoria.
    - **Voucher:** Lo specifico codice voucher di cui è stato inviato il promemoria.
- **Effetto delle modifiche:** Questo è un registro di sola lettura. Non puoi apportare modifiche qui, ma è inestimabile per verificare il funzionamento del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questa cronologia per assicurarti che i promemoria vengano inviati come previsto. Se noti lacune o comportamenti inaspettati, questo registro è il tuo primo punto di riferimento per la risoluzione dei problemi.

#### 2.2.3 Disiscrizioni (Back Office > Moduli > Voucher Reminder > Disiscrizioni)

Questa schermata elenca i clienti che hanno scelto di non ricevere promemoria voucher.

- **Nome schermata e posizione nel menu:** **Disiscrizioni** (sotto **Moduli > Voucher Reminder** nel menu principale di PrestaShop).
- **Azioni e impostazioni disponibili:**
  - **Elenco dei clienti disiscritti:** Una tabella che visualizza:
    - **ID:** Identificatore unico per la voce di disiscrizione.
    - **Email:** L'indirizzo email del cliente che si è disiscritto.
    - **IP:** L'indirizzo IP da cui è avvenuta la disiscrizione.
    - **Data di disiscrizione:** Quando il cliente si è disiscritto.
  - **Aggiungi nuova disiscrizione:** Puoi aggiungere manualmente un indirizzo email all'elenco di disiscrizione.
    - **Email del cliente:** Inserisci l'indirizzo email che desideri disiscrivere.
    - **IP:** (Opzionale) L'indirizzo IP associato alla disiscrizione.
    - **Data:** (Opzionale) La data di disiscrizione.
    - **Pulsante Salva:** Aggiunge il cliente all'elenco di disiscrizione.
- **Effetto delle modifiche:** I clienti elencati qui non riceveranno più email di promemoria voucher dal tuo negozio, anche se hanno voucher in scadenza. L'aggiunta manuale di un'email assicura che siano disattivati.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Mentre i clienti possono disiscriversi da soli, questa schermata ti consente di aggiungere manualmente i clienti se ti contattano direttamente chiedendo di essere rimossi dagli elenchi di promemoria. È anche un buon posto per monitorare le tendenze di disiscrizione.

#### 2.2.4 index.php (vreminders/controllers/admin/index.php)

Questo file è tipicamente un segnaposto o un reindirizzamento all'interno della struttura di amministrazione di PrestaShop e non rappresenta una schermata diretta e configurabile per il commerciante. Il suo scopo è solitamente quello di garantire che l'accesso diretto alla directory sia limitato o di reindirizzare alla configurazione principale del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | URL Cron Job | (URL generato) | Essenziale per impostare l'automazione lato server per inviare promemoria. |
| **Promemoria voucher** | Ricorda (ore prima della scadenza) | Varia (es. 24, 72) | Definisce la tempistica dell'email di promemoria rispetto alla scadenza del voucher. |
| | Titolo | Descrittivo (es. "Promemoria 1 giorno") | Etichetta interna per identificare le regole di promemoria nel Back Office. |
| | Titolo email | Oggetto accattivante | La riga dell'oggetto dell'email che i clienti ricevono. |
| | File template email | `voucher_reminder` | Specifica il template email utilizzato per questo promemoria. |
| | Invia promemoria | Sì | Attiva o disattiva una specifica regola di promemoria. |
| **Cronologia promemoria voucher** | (Tutti i campi) | N/A (Sola lettura) | Registro di tutte le email di promemoria inviate per verifica e risoluzione dei problemi. |
| **Disiscrizioni** | Email del cliente | N/A | Aggiungi manualmente le email dei clienti per impedire loro di ricevere promemoria. |
| | IP | N/A | (Opzionale) Indirizzo IP associato alla disiscrizione. |
| | Data | N/A | (Opzionale) Data di disiscrizione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei promemoria non vengono inviati. Cosa devo controllare per primo?**
R: La ragione più comune è un cron job configurato in modo errato.

1. Vai su **Moduli > Voucher Reminder > Configura**.
2. Copia esattamente l'"URL del Cron Job".
3. Accedi al pannello di controllo del tuo hosting (cPanel, Plesk, ecc.) e vai alla sezione "Cron Jobs".
4. Crea un nuovo cron job che chiami questo URL ogni 5-15 minuti. Il comando di solito assomiglia a `wget -q -O /dev/null "IL_TUO_URL_CRON_JOB_QUI"` o `curl -s "IL_TUO_URL_CRON_JOB_QUI" > /dev/null`.
5. Inoltre, assicurati che le singole regole di promemoria siano abilitate ("Invia promemoria" sia impostato su "Sì") sotto **Moduli > Voucher Reminder > Promemoria voucher**.

**D: I clienti si lamentano di non ricevere promemoria, ma la cronologia mostra che sono stati inviati.**
R: Questo di solito indica problemi di consegna delle email.

1. **Controlla le cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
2. **Configurazione del server email:** Assicurati che le impostazioni email del tuo negozio PrestaShop (sotto **Parametri avanzati > E-mail**) siano configurate correttamente e che il tuo server non sia in blacklist. L'utilizzo di un server SMTP (come SendGrid, Mailgun, ecc.) è spesso più affidabile della funzione `mail()` di PHP.
3. **Problemi con il template email:** Assicurati che i tuoi template email siano HTML/testo validi e non contengano link o immagini interrotte che potrebbero attivare i filtri antispam.

**D: Posso personalizzare i template email?**
R: Sì!

1. Il modulo utilizza template email standard di PrestaShop. Puoi trovare i file del template predefinito in `modules/vreminders/mails/en/` (o nella cartella della tua lingua).
2. **Migliore pratica:** Copia questi file nella directory `mails/en/` del tuo tema attivo (ad esempio, `themes/il_tuo_tema/mails/en/`). In questo modo, le tue personalizzazioni non verranno sovrascritte quando il modulo viene aggiornato.
3. Modifica i file `.html` e `.txt` per adattarli al tuo branding e al tuo messaggio. Puoi utilizzare le variabili Smarty disponibili nei template email di PrestaShop.
4. Se crei file di template completamente nuovi (ad esempio, `il_mio_promemoria_personalizzato.html`), dovrai selezionare `il_mio_promemoria_personalizzato` nell'impostazione "File template email" per la tua regola di promemoria.

**D: Come posso testare i promemoria senza inviarli a clienti reali?**
R:

1. Crea un account cliente di prova nel tuo negozio.
2. Crea manualmente un codice voucher per questo cliente di prova con una data di scadenza tra qualche ora o giorno.
3. Imposta una regola di promemoria con un "Ricorda (ore prima della scadenza)" breve (ad esempio, 1 ora).
4. Invece di aspettare il cron job, puoi attivare manualmente l'URL del cron nel tuo browser (anche se questo non è raccomandato per la produzione).
5. Controlla la "Cronologia promemoria voucher" e la casella di posta del cliente di prova.
6. Una volta soddisfatto, elimina il voucher di prova e la regola di promemoria, e imposta le tue regole di produzione.

**D: Cosa succede se un cliente usa il suo voucher dopo che è stato inviato un promemoria ma prima che scada?**
R: Il modulo è progettato per inviare promemoria solo per i voucher *non utilizzati*. Se un cliente usa il suo voucher, non sarà più considerato "attivo" e "non utilizzato", quindi non verranno inviati ulteriori promemoria per quel voucher specifico.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Voucher Reminder" segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC. La sua funzionalità principale ruota attorno a un cron job che controlla periodicamente i voucher in scadenza e invia email in base alle regole configurate. Utilizza `ObjectModel` di PrestaShop per la gestione delle sue entità personalizzate (promemoria, cronologia, disiscrizioni) e meccanismi email standard per la comunicazione. La logica principale del modulo risiede in `cronjob.php` (che funge da classe principale del modulo) e nei controller di amministrazione dedicati per le operazioni CRUD sui suoi dati personalizzati.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/CronJob.php`
    - **Nome classe e classe padre**: `VremindersCronJobModuleFrontController` estende `ModuleFrontController`.
    - **Responsabilità**: Questo controller è il punto di ingresso per il cron job del modulo. Quando si accede all'URL del cron (generato nella configurazione del modulo), questo controller viene eseguito. Contiene la logica per recuperare i voucher in scadenza, controllare le regole di promemoria configurate e inviare le email. Tipicamente non produce alcun output visivo ma esegue l'elaborazione in background.
  - `controllers/front/index.php`
    - **Nome classe e classe padre**: Non è una classe, tipicamente un file vuoto o un semplice `die('No direct script access allowed')` per impedire l'elenco o l'accesso diretto alla directory.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminVoucherReminders.php`
    - **Nome scheda ed entità gestita**: Gestisce l'elenco e i moduli "Promemoria voucher" nel Back Office. Gestisce le operazioni CRUD per l'entità `VoucherReminder` (che mappa alla tabella `ps_vr`).
  - `controllers/admin/AdminVoucherRemindersHistory.php`
    - **Nome scheda ed entità gestita**: Gestisce l'elenco "Cronologia promemoria voucher" nel Back Office. Visualizza un registro di sola lettura dei promemoria inviati, mappando all'entità `VoucherReminderHistory` (che mappa alla tabella `ps_vr_history`).
  - `controllers/admin/AdminVRemindersUnsub.php`
    - **Nome scheda ed entità gestita**: Gestisce l'elenco e i moduli "Disiscrizioni" nel Back Office. Gestisce le operazioni CRUD per l'entità `VoucherReminderUnsub` (che mappa alla tabella `ps_vr_vunsub`).
  - `controllers/admin/index.php`
    - **Nome classe e classe padre**: Non è una classe, tipicamente un file vuoto o un semplice `die('No direct script access allowed')` per impedire l'elenco o l'accesso diretto alla directory.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica una directory `classes/` esplicita. Ciò implica che le classi `ObjectModel` principali sono probabilmente definite direttamente all'interno del file principale del modulo (`cronjob.php`) o all'interno dei rispettivi file del controller di amministrazione. Basandosi sulla tipica struttura dei moduli PrestaShop e sulle entità identificate, si prevede che le seguenti classi `ObjectModel` siano presenti, probabilmente definite all'interno di `cronjob.php` o `AdminVoucherReminders.php`, `AdminVoucherRemindersHistory.php`, `AdminVRemindersUnsub.php`:

- **`VoucherReminder` (o simile)**

  - **Tabella del database**: `ps_vr` (o `_vreminders_vr`)
  - **Estende `ObjectModel`**: Sì.
  - **Campi `$definition`**: I campi previsti includono `id_vr`, `remind_hours`, `title`, `email_title`, `email_template`, `active`.
  - **Metodi pubblici chiave**: Metodi per aggiungere, aggiornare, eliminare le regole di promemoria e potenzialmente metodi per recuperare le regole attive.
- **`VoucherReminderHistory` (o simile)**

  - **Tabella del database**: `ps_vr_history` (o `_vreminders_vr_history`)
  - **Estende `ObjectModel`**: Sì.
  - **Campi `$definition`**: I campi previsti includono `id_vr_history`, `id_vr`, `id_customer`, `id_cart_rule`, `date_add`.
  - **Metodi pubblici chiave**: Metodi per la registrazione dei promemoria inviati.
- **`VoucherReminderUnsub` (o simile)**

  - **Tabella del database**: `ps_vr_vunsub` (o `_vreminders_vr_vunsub`)
  - **Estende `ObjectModel`**: Sì.
  - **Campi `$definition`**: I campi previsti includono `id_vunsub`, `email`, `ip`, `date_add`.
  - **Metodi pubblici chiave**: Metodi per la gestione delle disiscrizioni, inclusa l'aggiunta e il controllo delle email disiscritte.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript. Ciò suggerisce che il modulo si basa interamente sulle funzionalità JavaScript principali di PrestaShop per i suoi moduli e elenchi del Back Office, o che qualsiasi JS minimo è incorporato direttamente nei template.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS. Ciò suggerisce che il modulo si basa interamente sul CSS principale del Back Office di PrestaShop per le sue interfacce di amministrazione, e qualsiasi stile front-office (per le email) è gestito all'interno dei template email stessi.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template di amministrazione (`views/templates/admin/`)**:

  - `vreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    - **Scopo**: Questo template è probabilmente utilizzato da `AdminVoucherRemindersController` per renderizzare il modulo di aggiunta/modifica per le singole regole di promemoria voucher. Contenerebbe i campi di input per "Ricorda (ore prima della scadenza)", "Titolo", "Titolo email", "File template email" e "Invia promemoria".
- **Template hook (`views/templates/hook/`)**:

  - `vreminders/views/templates/hook/form.tpl`
    - **Scopo**: Questo template potrebbe essere un template di modulo generico o uno specifico per un hook che visualizza un modulo. Data la natura del modulo, è meno probabile che sia un modulo front-office visibile e più probabile che sia un componente interno o un hook legacy. Senza ulteriore contesto, la sua esatta posizione nel front-office non è chiara, ma potrebbe essere per un modulo di disiscrizione o simile.
  - `vreminders/views/templates/hook/header.tpl`
    - **Scopo**: Questo template viene renderizzato nell'hook `displayHeader`. Viene tipicamente utilizzato per includere file CSS o JavaScript, meta tag o altri elementi che devono essere caricati nella sezione `<head>` del documento HTML. Per questo modulo, potrebbe essere utilizzato per includere qualsiasi JS necessario per il cron job o per impostare meta tag specifici, anche se il dossier non indica file JS/CSS. Potrebbe anche essere un segnaposto.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_vr` (o `_vreminders_vr`): Memorizza la configurazione per ogni regola di promemoria voucher.
    - `id_vr` (PK, INT)
    - `remind_hours` (INT)
    - `title` (VARCHAR)
    - `email_title` (VARCHAR)
    - `email_template` (VARCHAR)
    - `active` (TINYINT)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_vr_history` (o `_vreminders_vr_history`): Registra ogni email di promemoria inviata.
    - `id_vr_history` (PK, INT)
    - `id_vr` (FK a `ps_vr.id_vr`, INT)
    - `id_customer` (FK a `ps_customer.id_customer`, INT)
    - `id_cart_rule` (FK a `ps_cart_rule.id_cart_rule`, INT)
    - `date_add` (DATETIME)
  - `ps_vr_vunsub` (o `_vreminders_vr_vunsub`): Memorizza gli indirizzi email dei clienti che si sono disiscritti dai promemoria.
    - `id_vunsub` (PK, INT)
    - `email` (VARCHAR)
    - `ip` (VARCHAR)
    - `date_add` (DATETIME)
- **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere eventuali risorse necessarie (JS/CSS) o meta tag per il modulo. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per creare tabelle del database e configurazione predefinita. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per rimuovere tabelle del database e configurazione. |
| `displayAdminProductsExtra` (o simile) | Potenzialmente sulle pagine dei prodotti nel BO. | Se il modulo avesse impostazioni di promemoria specifiche per il prodotto, ma non indicato dal dossier. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Per includere JS/CSS specifici dell'amministrazione o contesto per la configurazione del modulo. |
| `moduleRoutes` | Durante l'inizializzazione della riscrittura URL. | Per definire URL amichevoli personalizzati per i controller front-end (ad esempio, URL del cron job, URL di disiscrizione). |

La logica principale del modulo per l'invio dei promemoria è attivata dal controller front-end `CronJob.php`, che viene chiamato tramite un cron job lato server, non direttamente da un hook di PrestaShop.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il tuo modulo "Voucher Reminder", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire un supporto completo e a garantire che il tuo modulo funzioni senza problemi.
