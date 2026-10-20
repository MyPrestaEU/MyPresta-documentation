---
title: "Backup del database in locale e nel cloud - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Database backup locally and in cloud' di MyPresta.eu."
sidebar:
  label: "Backup del database in locale e nel cloud - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Database backup locally and in cloud su MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Backup del database in locale e nel cloud

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Risorse server sufficienti (CPU, memoria) per l'esportazione del database, specialmente per database molto grandi, anche se il modulo è progettato per mitigare questi problemi con la suddivisione in blocchi. Permessi di scrittura per la directory di backup sul tuo server.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

Il modulo "Database backup locally and in cloud" fornisce un'interfaccia completa per la gestione dei tuoi backup. Interagirai principalmente con due aree principali: la pagina di configurazione principale del modulo e la sua schermata amministrativa dedicata "My Backups".

### 2.1 Pagina di configurazione principale del modulo (Back Office > Moduli > Gestione moduli > Configura "Database backup locally and in cloud")

Questa pagina di configurazione iniziale (`mybackups/index.php` tramite `getContent()`) gestisce la configurazione di base e l'integrazione del modulo.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Queste impostazioni controllano gli aspetti fondamentali del funzionamento del modulo e della sua integrazione con il tuo ambiente PrestaShop.
-   **Effetto della modifica di questa impostazione:** La regolazione di queste impostazioni può influire sulle prestazioni, sulla sicurezza e sull'affidabilità complessiva dei tuoi backup.
-   **Valore consigliato:** In generale, attieniti ai valori predefiniti a meno che tu non abbia un motivo specifico o ti sia stato consigliato dal supporto.

#### Integrazioni di archiviazione cloud

-   **Cosa fa questa impostazione:** Questa sezione ti consente di connettere il tuo negozio PrestaShop a vari fornitori di archiviazione cloud dove verranno archiviati i tuoi backup. Ogni fornitore (Google Drive, Dropbox, FTP/FTPS, Amazon S3) avrà il proprio set di dettagli di connessione.
-   **Effetto della modifica di questa impostazione:** La connessione riuscita a un servizio cloud abilita tale servizio come destinazione di backup. Credenziali errate impediranno il caricamento dei backup su quel cloud specifico.
-   **Valore consigliato:** Connettiti ad almeno un fornitore di archiviazione cloud per i backup off-site. Google Drive e Dropbox sono spesso i più facili da configurare per la maggior parte dei commercianti.
-   **Scenario/esempio del commerciante:** Vuoi archiviare i tuoi backup su Google Drive. Faresti clic sul pulsante "Connetti a Google Drive", seguiresti i passaggi di autenticazione e concederesti al modulo il permesso di accedere a una cartella specifica nel tuo Google Drive. Ciò garantisce che, anche se il tuo server si blocca, i tuoi backup siano al sicuro nel cloud.

### 2.2 Schermata amministrativa dedicata: I miei backup (Back Office > I miei backup)

Questo è l'hub centrale per la gestione di tutti i tuoi backup del database. Troverai questa schermata sotto una nuova voce di menu, tipicamente denominata "I miei backup" o simile, aggiunta alla navigazione del tuo Back Office PrestaShop. Questa schermata è alimentata da `mybackups/controllers/admin/AdminMyBackupsController.php`.

#### Dashboard ed elenco dei backup

-   **Nome schermata e posizione menu:** Troverai "I miei backup" sotto il menu principale di PrestaShop, solitamente raggruppato con "Amministrazione" o "Parametri avanzati".
-   **Azioni e impostazioni disponibili:**
    -   **Elenco backup:** Questa tabella mostra tutti i tuoi backup del database esistenti, sia archiviati localmente che nel cloud. Ogni voce tipicamente mostra:
        -   **Data/Ora:** Quando è stato creato il backup.
        -   **Dimensione:** La dimensione del file di backup compresso.
        -   **Posizione:** Dove è archiviato il backup (Locale, Google Drive, Dropbox, FTP, S3).
        -   **Azioni:**
            -   **Scarica:** Scarica il file di backup sul tuo computer.
            -   **Ripristina:** Avvia un processo di ripristino del database utilizzando questo backup. (Fai molta attenzione con questa azione, poiché sovrascriverà il tuo database corrente!)
            -   **Elimina:** Rimuovi il file di backup dalla sua posizione di archiviazione.
    -   **Pulsante Crea nuovo backup:** Un pulsante prominente per avviare manualmente un nuovo backup del database.
    -   **Stato archiviazione cloud:** Indicatori visivi che mostrano quali servizi cloud sono attualmente connessi e disponibili.
    -   **Backup programmati:** Una sezione per visualizzare e gestire le tue attività di backup automatizzate (cron job).
-   **Effetto delle modifiche:**
    -   **Creazione di un nuovo backup:** Genera un nuovo dump SQL compresso del tuo database e lo archivia nelle posizioni configurate (locale e/o cloud).
    -   **Ripristino di un backup:** Sostituisce il tuo database live corrente con i dati del file di backup selezionato. Questa è un'azione potente e potenzialmente distruttiva; assicurati sempre di avere un backup fresco prima di tentare un ripristino.
    -   **Eliminazione di un backup:** Rimuove permanentemente il file di backup dalla sua archiviazione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Configurazione iniziale:** Connettiti ai tuoi fornitori di archiviazione cloud preferiti nella pagina di configurazione del modulo.
    2.  **Pianifica backup:** Imposta un cron job (vedi "Casi d'uso pratici" di seguito) per creare automaticamente backup giornalieri o settimanali, a seconda dell'attività del tuo negozio. Assicurati che questi backup programmati vengano inviati ad almeno una posizione cloud.
    3.  **Monitoraggio regolare:** Controlla periodicamente la dashboard "I miei backup" per assicurarti che i backup vengano creati con successo e che le tue connessioni cloud siano attive.
    4.  **Backup manuale (Opzionale):** Crea un backup manuale prima di qualsiasi modifica importante al negozio (ad esempio, installazioni di moduli, aggiornamenti del tema, importazioni di prodotti).
    5.  **Test di ripristino (CRITICO):** Occasionalmente, esegui un test di ripristino su un *ambiente di sviluppo o staging* (MAI sul tuo negozio live senza estrema cautela) per assicurarti che i tuoi backup siano validi e che il processo di ripristino funzioni come previsto.

#### Modulo di creazione backup

Quando fai clic su "Crea nuovo backup", ti verranno tipicamente presentate delle opzioni:

-   **Nome backup:**
    -   **Cosa fa questa impostazione:** Ti consente di assegnare un nome personalizzato al tuo file di backup per una facile identificazione.
    -   **Effetto della modifica di questa impostazione:** Il file di backup verrà salvato con questo nome (ad esempio, `my-store-backup-2023-10-27.sql.zip`).
    -   **Valore consigliato:** Usa un nome descrittivo, magari includendo la data o una breve nota sul motivo del backup (ad esempio, "Backup pre-aggiornamento").
-   **Posizioni di archiviazione:**
    -   **Cosa fa questa impostazione:** Seleziona dove deve essere salvato il file di backup. Le opzioni tipicamente includono "Server locale" e qualsiasi servizio cloud connesso (Google Drive, Dropbox, FTP, S3).
    -   **Effetto della modifica di questa impostazione:** Il backup verrà archiviato solo nelle posizioni selezionate.
    -   **Valore consigliato:** Seleziona sempre "Server locale" e almeno un'opzione di archiviazione cloud per la ridondanza.
-   **Escludi tabelle:**
    -   **Cosa fa questa impostazione:** Ti consente di selezionare tabelle di database specifiche che *non* devono essere incluse nel backup. Questo può essere utile per tabelle molto grandi che contengono dati non critici o facilmente rigenerabili (ad esempio, tabelle di cache, tabelle di log).
    -   **Effetto della modifica di questa impostazione:** Le tabelle selezionate verranno saltate, risultando in un file di backup più piccolo.
    -   **Valore consigliato:** Per la maggior parte dei commercianti, lascia vuoto per eseguire il backup dell'intero database. Escludi le tabelle solo se comprendi le implicazioni e stai cercando di ridurre le dimensioni del backup a causa di gravi vincoli di hosting.
-   **Pulsante Avvia backup:** Avvia il processo di backup. Tipicamente vedrai una barra di avanzamento o aggiornamenti di stato mentre il backup viene creato e caricato.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Impostazioni generali | Predefinito | Controlla le operazioni fondamentali del modulo, le prestazioni e la sicurezza. |
| | Integrazione Google Drive | Connetti | Abilita Google Drive come destinazione di backup. |
| | Integrazione Dropbox | Connetti | Abilita Dropbox come destinazione di backup. |
| | Integrazione FTP/FTPS | Configura | Abilita FTP/FTPS come destinazione di backup. |
| | Integrazione Amazon S3 | Configura | Abilita Amazon S3 come destinazione di backup. |
| **Dashboard I miei backup** | Crea nuovo backup | N/A | Avvia manualmente un nuovo backup del database. |
| | Elenco backup (Scarica) | N/A | Scarica un file di backup sul tuo computer locale. |
| | Elenco backup (Ripristina) | N/A | **CRITICO:** Sovrascrive il database corrente con il backup selezionato. Usare con estrema cautela, preferibilmente in staging. |
| | Elenco backup (Elimina) | N/A | Rimuove permanentemente un file di backup dalla sua posizione di archiviazione. |
| **Modulo di creazione backup** | Nome backup | Generato automaticamente | Nome personalizzato per il file di backup. |
| | Posizioni di archiviazione | Locale + Cloud | Seleziona dove verrà salvato il backup (server locale, servizi cloud). |
| | Escludi tabelle | Nessuno | Salta le tabelle specificate dal backup per ridurre le dimensioni del file. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei backup falliscono o impiegano troppo tempo. Cosa devo fare?**
R:

-   **Controlla le risorse del server:** I database di grandi dimensioni richiedono una notevole memoria del server e tempo di esecuzione. Sebbene il modulo suddivida le esportazioni in blocchi, gli ambienti di hosting molto limitati possono comunque avere difficoltà. Contatta il tuo host per verificare i limiti di memoria PHP (`memory_limit`) e il tempo massimo di esecuzione (`max_execution_time`).
-   **Svuota la cache:** A volte, la cache di PrestaShop può interferire. Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache".
-   **Escludi tabelle:** Considera di escludere tabelle non critiche (come tabelle di cache o statistiche) dal backup se sono molto grandi. Ciò può ridurre significativamente le dimensioni e il tempo del backup.
-   **Controlla i log degli errori:** Cerca nei log degli errori di PrestaShop (solitamente `var/logs/` o `app/logs/` a seconda della versione di PS) o nei log degli errori PHP del tuo server messaggi di errore specifici.

**D: Mi sono connesso a Google Drive/Dropbox, ma non vedo i miei backup lì.**
R:

-   **Controlla lo stato della connessione:** Vai alla pagina di configurazione del modulo e verifica che il tuo servizio cloud sia visualizzato come "Connesso". In caso contrario, prova a riconnetterti.
-   **Permessi cartella:** Assicurati che il modulo abbia i permessi necessari per scrivere nella cartella specificata nel tuo archivio cloud. Per Google Drive/Dropbox, il modulo di solito crea la propria cartella.
-   **Test di caricamento manuale:** Prova a creare un piccolo backup manuale e a selezionare esplicitamente il servizio cloud come destinazione per vedere se viene caricato con successo.
-   **Controlla direttamente l'archivio cloud:** Accedi al tuo account Google Drive o Dropbox tramite il loro sito web e sfoglia manualmente le cartelle per vedere se i backup sono lì, magari in una posizione inaspettata.

**D: Come ripristino il mio database da un backup?**
R:

-   **ATTENZIONE:** Il ripristino di un database sovrascriverà il tuo database live corrente. Questa è un'azione altamente distruttiva. **Avere sempre un backup fresco del tuo database corrente prima di tentare un ripristino.**
-   Vai su **Back Office > I miei backup**.
-   Individua il file di backup che desideri ripristinare nell'elenco.
-   Fai clic sul pulsante "Ripristina" accanto a quel backup.
-   Segui le istruzioni sullo schermo. Il modulo ti guiderà attraverso il processo.
-   Se il tuo negozio è completamente inattivo, potresti dover caricare manualmente il file di backup tramite FTP e quindi utilizzare l'interfaccia del modulo o uno strumento come phpMyAdmin per importarlo. In situazioni così critiche, è meglio consultare uno sviluppatore o il tuo provider di hosting.

**D: Cosa succede se il mio server esaurisce lo spazio su disco durante un backup locale?**
R: Il processo di backup probabilmente fallirà e vedrai un messaggio di errore relativo allo spazio su disco. Assicurati di avere spazio su disco sufficiente sul tuo server, soprattutto se stai archiviando più backup locali o hai un database molto grande. Elimina regolarmente i vecchi backup locali che sono già stati caricati in sicurezza nel cloud.

**D: Il mio tema personalizzato non viene visualizzato correttamente dopo un ripristino.**
R: I backup del database ripristinano principalmente i tuoi dati. I file del tema, i file del modulo e le immagini sono tipicamente archiviati nel file system del tuo server, non direttamente nel database.

-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota tutte le cache (Smarty, file system, ecc.).
-   **Controlla il file system:** Assicurati che tutti i file del tuo tema, i file del modulo e le cartelle delle immagini siano presenti e abbiano i permessi corretti sul server. Un ripristino del database non influirà su questi file. Se hai ripristinato da un backup molto vecchio, alcune configurazioni del modulo potrebbero dover essere salvate nuovamente nel Back Office.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica e della codebase del modulo "Database backup locally and in cloud" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo MyBackups è progettato con una forte enfasi sulla robustezza, scalabilità e tolleranza agli errori, in particolare per la gestione di operazioni di database di grandi dimensioni e integrazioni cloud esterne. Segue un approccio modulare e orientato agli oggetti, sfruttando il pattern MVC di PrestaShop ove appropriato, ma implementando anche la propria architettura interna orientata ai servizi per la logica di backup/ripristino principale.

I principali pattern architetturali includono:

-   **Elaborazione a blocchi:** L'esportazione e l'importazione del database sono suddivise in blocchi più piccoli e gestibili per aggirare i limiti di tempo di esecuzione e memoria di PHP.
-   **Gestione dello stato:** Un robusto sistema di gestione dello stato (`MyBackupsStateManager`) tiene traccia dell'avanzamento dei lavori di backup/ripristino a lungo termine, consentendo l'esecuzione di web-cron e il recupero da interruzioni.
-   **Astrazione dell'archiviazione:** Un design basato su interfacce (`MyBackupsStorageInterface`) consente una facile integrazione di nuovi provider di archiviazione cloud senza alterare la logica di backup principale.
-   **Integrazione OAuth:** Flussi OAuth 2.0 sicuri per Google Drive e Dropbox, che gestiscono l'archiviazione e l'aggiornamento dei token.
-   **Cron/Job Runner:** Controller frontali e classi dedicate per l'attivazione e la gestione di lavori in background tramite cron o web-cron.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono utilizzati principalmente per attività in background e callback OAuth, non per il rendering di contenuti rivolti ai clienti.

-   `mybackups/controllers/front/cron.php`
    -   **Nome classe e classe genitore:** `MyBackupsCronModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller funge da punto di ingresso per i cron job programmati. Quando viene acceduto con il token corretto, attiva `MyBackupsCronRunner` per elaborare le attività di backup in sospeso. È progettato per essere chiamato esternamente da un demone cron del server o da un servizio web-cron.
-   `mybackups/controllers/front/index.php`
    -   **Nome classe e classe genitore:** `MyBackupsIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Un segnaposto o un controller frontale predefinito, spesso utilizzato per il routing del modulo o semplici reindirizzamenti se non viene richiesta alcuna azione specifica. In questo modulo, potrebbe fungere da base o fallback.
-   `mybackups/controllers/front/job.php`
    -   **Nome classe e classe genitore:** `MyBackupsJobModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Gestisce le richieste AJAX relative all'avanzamento e allo stato dei lavori di backup/ripristino in corso. Interagisce con `MyBackupsJobRunner` e `MyBackupsStateManager` per fornire aggiornamenti in tempo reale all'interfaccia utente del Back Office.
-   `mybackups/controllers/front/oauthdropbox.php`
    -   **Nome classe e classe genitore:** `MyBackupsOauthdropboxModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è l'URI di callback per il flusso OAuth 2.0 di Dropbox. Dopo che un commerciante autorizza il modulo su Dropbox, Dropbox reindirizza a questo controller, che quindi gestisce lo scambio del codice di autorizzazione per un token di accesso e lo archivia in modo sicuro.
-   `mybackups/controllers/front/oauthgdrive.php`
    -   **Nome classe e classe genitore:** `MyBackupsOauthgdriveModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Simile a `oauthdropbox.php`, questo è l'URI di callback per il flusso OAuth 2.0 di Google Drive. Elabora il codice di autorizzazione da Google e ottiene/archivia i token di accesso e di aggiornamento necessari.

#### Controller amministrativi Back-Office

Questi controller gestiscono l'interfaccia del modulo all'interno del Back Office di PrestaShop.

-   `mybackups/controllers/admin/AdminMyBackupsController.php`
    -   **Nome classe e classe genitore:** `AdminMyBackupsController` che estende `ModuleAdminController`.
    -   **Nome scheda ed entità gestita:** Questo è il controller amministrativo principale per la dashboard "I miei backup". Gestisce l'elenco, la creazione, il download, il ripristino e l'eliminazione dei file di backup. Orchesta le interazioni con `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter` e le varie classi di archiviazione.
-   `mybackups/controllers/admin/index.php`
    -   **Nome classe e classe genitore:** File `index.php` standard di PrestaShop per le directory dei controller amministrativi.
    -   **Responsabilità:** Impedisce l'elenco diretto delle directory e garantisce l'accesso sicuro ai controller amministrativi.

### 4.3 Classi e modelli principali (`classes/`)

-   `mybackups/classes/index.php`: `index.php` vuoto standard per impedire l'elenco delle directory.
-   `mybackups/classes/MyBackupsAdminAjax.php`: Gestisce varie richieste AJAX dall'interfaccia di amministrazione, come il recupero degli elenchi di backup, l'avvio di azioni specifiche o l'aggiornamento degli elementi dell'interfaccia utente.
-   `mybackups/classes/MyBackupsAdminForms.php`: Probabilmente responsabile del rendering e dell'elaborazione dei moduli di configurazione del modulo nel Back Office, incluse le impostazioni di integrazione cloud.
-   `mybackups/classes/MyBackupsCatalog.php`: Gestisce il catalogo dei file di backup, sia locali che nel cloud. Fornisce metodi per elencare, filtrare e recuperare informazioni sui backup esistenti.
-   `mybackups/classes/MyBackupsCloudUi.php`: Aiuta a generare gli elementi dell'interfaccia utente e la logica per l'integrazione dell'archiviazione cloud all'interno del Back Office (ad esempio, pulsanti di connessione, indicatori di stato).
-   `mybackups/classes/MyBackupsCronRunner.php`: La logica principale per l'esecuzione dei job di backup programmati. Controlla le attività in sospeso e avvia `MyBackupsJobRunner` per ciascuna.
-   `mybackups/classes/MyBackupsDumpVerifier.php`: Responsabile della verifica dell'integrità e della validità dei file di dump SQL, potenzialmente controllando errori comuni o dump incompleti.
-   `mybackups/classes/MyBackupsExporter.php`: Gestisce il processo di esportazione del database effettivo, inclusa la suddivisione del dump SQL in blocchi, il filtraggio delle tabelle e la compressione.
-   `mybackups/classes/MyBackupsImporter.php`: Gestisce il processo di importazione (ripristino) del database, analizzando il dump SQL ed eseguendo query in blocchi.
-   `mybackups/classes/MyBackupsJobLock.php`: Implementa un meccanismo di blocco per impedire l'esecuzione simultanea di più job di backup/ripristino, garantendo la coerenza dei dati e prevenendo la contesa delle risorse.
-   `mybackups/classes/MyBackupsJobRunner.php`: Orchesta l'intero job di backup o ripristino, gestendo la sequenza di passaggi (esportazione, compressione, caricamento/download, importazione) e interagendo con `MyBackupsStateManager`.
-   `mybackups/classes/MyBackupsMemoryGuard.php`: Una classe utility per monitorare e gestire l'utilizzo della memoria PHP durante operazioni intensive, aiutando a prevenire errori di memoria insufficiente.
-   `mybackups/classes/MyBackupsOAuthReturn.php`: Gestisce i passaggi finali del processo di callback OAuth, elaborando il codice di autorizzazione restituito e gestendo l'archiviazione dei token.
-   `mybackups/classes/MyBackupsOAuthState.php`: Gestisce il parametro di stato durante i flussi OAuth per prevenire attacchi CSRF.
-   `mybackups/classes/MyBackupsPaths.php`: Fornisce una gestione centralizzata dei percorsi e delle directory dei file utilizzati dal modulo (ad esempio, la directory di archiviazione dei backup).
-   `mybackups/classes/MyBackupsStateManager.php`: Cruciale per i lavori a lungo termine. Archivia e recupera lo stato corrente di un'operazione di backup/ripristino, consentendo di mettere in pausa e riprendere i lavori su più richieste HTTP (ad esempio, durante l'esecuzione di cron o gli aggiornamenti di avanzamento basati sul web).
-   `mybackups/classes/MyBackupsTableFilter.php`: Implementa la logica per il filtraggio delle tabelle del database durante l'esportazione, in base alle selezioni dell'utente.
-   `mybackups/classes/MyBackupsTimeBudget.php`: Aiuta a gestire i limiti di tempo di esecuzione per i processi a lungo termine, consentendo al modulo di arrestarsi e salvare lo stato in modo elegante prima di raggiungere `max_execution_time`.
-   `mybackups/classes/MyBackupsTokenCrypto.php`: Gestisce la crittografia e la decrittografia di token OAuth sensibili e chiavi API per un'archiviazione sicura.
-   `mybackups/classes/MyBackupsZip.php`: Gestisce la compressione e la decompressione dei file di backup in archivi ZIP.

#### Sottoclassi di archiviazione (`classes/storage/`)

Questa directory contiene classi che implementano `MyBackupsStorageInterface` per vari backend di archiviazione.

-   `mybackups/classes/storage/index.php`: `index.php` vuoto standard.
-   `mybackups/classes/storage/MyBackupsCloudUploader.php`: Una classe generica per la gestione del processo di caricamento nell'archiviazione cloud, potenzialmente gestendo caricamenti a blocchi e il monitoraggio dell'avanzamento.
-   `mybackups/classes/storage/MyBackupsDropboxStorage.php`: Implementa `MyBackupsStorageInterface` per interagire con l'API di Dropbox.
-   `mybackups/classes/storage/MyBackupsFtpStorage.php`: Implementa `MyBackupsStorageInterface` per interagire con i server FTP/FTPS.
-   `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php`: Implementa `MyBackupsStorageInterface` per interagire con l'API di Google Drive.
-   `mybackups/classes/storage/MyBackupsHttp.php`: Una classe utility per effettuare richieste HTTP, probabilmente utilizzata dalle classi di archiviazione cloud per le chiamate API.
-   `mybackups/classes/storage/MyBackupsLocalStorage.php`: Implementa `MyBackupsStorageInterface` per archiviare e recuperare i backup sul file system del server locale.
-   `mybackups/classes/storage/MyBackupsS3Storage.php`: Implementa `MyBackupsStorageInterface` per interagire con Amazon S3.
-   `mybackups/classes/storage/MyBackupsStorageFactory.php`: Una classe con pattern factory responsabile dell'istanza della classe di archiviazione corretta in base alla configurazione.
-   `mybackups/classes/storage/MyBackupsStorageInterface.php`: Definisce il contratto (metodi) che tutte le classi di archiviazione devono implementare (ad esempio, `upload`, `download`, `delete`, `list_files`).

### 4.4 Risorse JavaScript (`views/js/`)

-   `mybackups/lib/searchTool/views/js/autocomplete.js`:
    -   **Ambito:** Probabilmente Back-office.
    -   **Dettagli:** Fornisce funzionalità di completamento automatico, possibilmente per la ricerca tra le tabelle del database durante la configurazione delle esclusioni o per il filtraggio degli elenchi di backup.
-   `mybackups/views/js/mybackups-cloud.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce le interazioni lato client per la configurazione dell'archiviazione cloud. Ciò include chiamate AJAX per connettersi/disconnettersi dai servizi, aggiornare l'interfaccia utente in base allo stato della connessione e potenzialmente gestire la navigazione delle cartelle all'interno dei servizi cloud.
-   `mybackups/views/js/mybackups-job.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce la visualizzazione dell'avanzamento in tempo reale per i lavori di backup e ripristino. Utilizza AJAX per interrogare il controller frontale `job.php` per gli aggiornamenti sullo stato del lavoro, aggiornando le barre di avanzamento, i messaggi di stato e gestendo le notifiche di completamento o fallimento del lavoro.
-   `mybackups/views/js/mybackups-table-picker.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Fornisce l'interfaccia interattiva per la selezione o l'esclusione delle tabelle del database durante la creazione del backup, potenzialmente includendo funzionalità di ricerca e selezione multipla.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `mybackups/lib/searchTool/views/css/autocomplete.css`:
    -   **Ambito:** Stile di amministrazione del Back-office.
    -   **Dettagli:** Stili per i campi di input di completamento automatico e gli elenchi di suggerimenti utilizzati nel Back Office.
-   `mybackups/views/css/admin.css`:
    -   **Ambito:** Stile di amministrazione del Back-office.
    -   **Dettagli:** Contiene lo stile principale per l'interfaccia del Back Office del modulo, inclusi la dashboard, l'elenco dei backup, i moduli, le barre di avanzamento e le sezioni di integrazione cloud. Gli sviluppatori possono sovrascrivere questi stili nel loro tema amministrativo personalizzato o aggiungendo CSS personalizzato tramite un hook, se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   `mybackups/lib/searchTool/views/scripts.tpl`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Probabilmente include risorse JavaScript e CSS per lo strumento di ricerca/completamento automatico, potenzialmente agganciato a `displayBackOfficeHeader` o simili.
-   `mybackups/views/templates/admin/backups.tpl`:
    -   **Ambito:** Template amministrativo.
    -   **Dettagli:** Il template principale per la visualizzazione dell'elenco dei backup esistenti, incluse le colonne per data, dimensione, posizione e pulsanti di azione (scarica, ripristina, elimina). Questo è il cuore della visualizzazione di `AdminMyBackupsController`.
-   `mybackups/views/templates/admin/configure.tpl`:
    -   **Ambito:** Template amministrativo.
    -   **Dettagli:** Renderizza il modulo di configurazione principale del modulo, tipicamente accessibile tramite `getContent()` nel file principale del modulo. Questo include le impostazioni generali e la configurazione iniziale per le integrazioni dei servizi cloud.
-   `mybackups/views/templates/admin/dashboard.tpl`:
    -   **Ambito:** Template amministrativo.
    -   **Dettagli:** Il template della dashboard generale per la sezione "I miei backup", che combina elementi come l'elenco dei backup, il pulsante "Crea nuovo backup", gli indicatori di stato del cloud e potenzialmente le informazioni sui backup programmati.
-   `mybackups/views/templates/admin/job-progress.tpl`:
    -   **Ambito:** Template amministrativo.
    -   **Dettagli:** Visualizza la barra di avanzamento e i messaggi di stato per i lavori di backup o ripristino in corso, aggiornati dinamicamente da `mybackups-job.js`.
-   `mybackups/views/templates/admin/table-picker.tpl`:
    -   **Ambito:** Template amministrativo.
    -   **Dettagli:** Renderizza l'interfaccia per la selezione o l'esclusione delle tabelle del database durante la creazione del backup.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate per archiviare i dati di backup stessi, poiché i backup sono file.
    -   Memorizzerà i valori di configurazione nella tabella `ps_configuration` di PrestaShop, come:
        -   Chiavi/segreti API cloud (crittografati).
        -   Token OAuth (crittografati).
        -   Impostazioni specifiche del modulo (ad esempio, posizioni di backup predefinite, token cron).
        -   Informazioni sullo stato del lavoro per `MyBackupsStateManager`.
-   **Tabella degli hook registrati**:
    Il modulo utilizza principalmente hook del Back Office e controller frontali per la sua funzionalità. Gli hook front-office elencati (Header, Columns, Product, Footer) sono probabilmente *non* utilizzati da questo modulo, poiché la sua funzionalità è puramente amministrativa e focalizzata sul backend. Se fossero utilizzati, sarebbe per scopi molto specifici e non visibili, come il caricamento di risorse o l'esecuzione di controlli in background.

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` delle pagine del Back Office. | Utilizzato per iniettare CSS (`admin.css`) e JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) specifici del modulo nel pannello di amministrazione. |
| `displayAdminProductsExtra` (o simile) | Potenzialmente per aggiungere un'opzione di backup nella pagina di modifica del prodotto, anche se improbabile per questo modulo. | (Se utilizzato) Per aggiungere un'azione di backup specifica o informazioni relative ai dati del prodotto. |
| `actionModuleInstall` | Eseguito quando il modulo viene installato. | Crea le directory necessarie, imposta i valori di configurazione predefiniti, registra le schede del menu amministrativo e potenzialmente imposta le istruzioni iniziali del cron job. |
| `actionModuleUninstall` | Eseguito quando il modulo viene disinstallato. | Pulisce i valori di configurazione, rimuove le schede del menu amministrativo ed elimina le directory specifiche del modulo (anche se spesso lascia i file di backup per sicurezza). |
| `actionAdminControllerSetMedia` | Eseguito prima che un controller amministrativo renderizzi la sua pagina. | Utilizzato per aggiungere risorse CSS/JS specifiche solo alle pagine amministrative del modulo (`AdminMyBackupsController`). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Database backup locally and in cloud", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema tecnico o domanda che possiate avere riguardo alla funzionalità e alla configurazione del modulo.
