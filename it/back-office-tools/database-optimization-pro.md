---
title: "Database Optimization Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Database Optimization Pro di MyPresta.eu."
sidebar:
  label: "Database Optimization Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Database Optimization Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/database-optimization-pro/)
>
> ---


# Database Optimization Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. L'accesso al pannello di controllo del tuo hosting (cPanel, Plesk, ecc.) per impostare i cron job è altamente raccomandato per le capacità di automazione complete del modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale di Database Optimization Pro. Qui imposterai la pulizia automatica e otterrai le informazioni necessarie per il tuo cron job.

La pagina di configurazione è semplice e fornisce gli strumenti essenziali per gestire l'ottimizzazione del tuo database.

#### **URL del Cron Job**

-   **Cosa fa questa impostazione:** Questo è l'indirizzo web univoco (URL) che, quando visitato, attiva il processo di ottimizzazione del database. È progettato per essere chiamato da un sistema automatizzato (un cron job) piuttosto che da un essere umano che lo naviga.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL dalla configurazione del modulo. Viene generato automaticamente dal modulo.
-   **Valore consigliato:** Copia questo URL esattamente come appare. Ne avrai bisogno per impostare il tuo cron job sul tuo server di hosting.
-   **Scenario/esempio del commerciante:** Copierai questo URL e lo incollerai nell'interfaccia di configurazione del cron job fornita dal tuo web host (es. cPanel, Plesk o un gestore di cron job personalizzato). Questo dice al tuo server "ogni X ore/giorni, visita questo URL per pulire il mio database".

#### **Esegui ottimizzazione ora**

-   **Cosa fa questa impostazione:** Questo è un trigger manuale per eseguire immediatamente il processo di ottimizzazione del database. Esegue le stesse azioni di pulizia dell'URL del cron job, ma su richiesta.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando cliccato:* Il modulo inizierà immediatamente a pulire il tuo database. Vedrai un messaggio di conferma una volta completato.
-   **Valore consigliato:** Usa questo pulsante per i test iniziali dopo l'installazione, o se hai bisogno di eseguire una pulizia immediata al di fuori dei tuoi cron job programmati.
-   **Scenario/esempio del commerciante:** Hai appena installato il modulo e vuoi vederlo in azione, oppure hai apportato molte modifiche al tuo negozio (es. importato molti prodotti) e vuoi pulire immediatamente senza aspettare il prossimo cron job programmato.

#### **Impostazione del Cron Job**

Questa è la parte più cruciale per automatizzare l'ottimizzazione del tuo database. Un cron job è uno scheduler di processi basato sul tempo nei sistemi operativi simili a Unix. Ti consente di programmare comandi o script da eseguire automaticamente a un'ora o un intervallo specificato.

**Passaggi per impostare un cron job (guida generale - i passaggi specifici possono variare a seconda dell'host):**

1.  **Accedi al tuo Pannello di Controllo Hosting:** Questo è solitamente cPanel, Plesk o un pannello di controllo personalizzato fornito dal tuo host.
2.  **Trova "Cron Jobs" o "Attività pianificate":** Cerca una sezione relativa ai cron job, spesso sotto "Avanzate" o "Strumenti".
3.  **Aggiungi un nuovo Cron Job:**
    -   Di solito dovrai specificare la frequenza (es. una volta al giorno, una volta alla settimana). Un buon punto di partenza è una volta al giorno o una volta ogni pochi giorni.
    -   Dovrai fornire il "Comando" o "URL da chiamare". Qui incollerai l'**URL del Cron Job** che hai copiato dalla pagina di configurazione del modulo.
    -   Il formato del comando spesso assomiglia a questo:

    Terminal window

    ```
    wget -q -O /dev/null "IL_TUO_URL_CRON_JOB_QUI"
    ```

    Sostituisci `"IL_TUO_URL_CRON_JOB_QUI"` con l'URL esatto del modulo. Il comando `wget` recupera l'URL, e `-q -O /dev/null` assicura che venga eseguito silenziosamente senza salvare l'output, il che è ideale per le attività in background.
4.  **Salva il Cron Job:** Conferma le tue impostazioni per attivare l'attività pianificata.

**Esempi di frequenze di Cron Job:**

-   **Una volta al giorno (es. 3 AM):**
    `0 3 * * * wget -q -O /dev/null "IL_TUO_URL_CRON_JOB_QUI"`
-   **Una volta alla settimana (es. ogni domenica alle 4 AM):**
    `0 4 * * 0 wget -q -O /dev/null "IL_TUO_URL_CRON_JOB_QUI"`

Scegli un orario in cui il tuo negozio ha tipicamente poco traffico per minimizzare qualsiasi potenziale (anche se solitamente trascurabile) impatto sulle prestazioni durante la pulizia.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | URL del Cron Job | (Generato automaticamente) | L'URL da chiamare dal sistema cron job del tuo hosting per attivare l'ottimizzazione automatica del database. Copialo esattamente. |
| Configurazione modulo | Esegui ottimizzazione ora | Clicca per eseguire | Attiva manualmente una pulizia immediata del database. Utile per test o ottimizzazione su richiesta. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho impostato il cron job, ma non vedo alcuna differenza nella velocità del mio negozio.**
R: L'ottimizzazione del database fornisce miglioramenti incrementali. Se il tuo negozio era già relativamente veloce, il cambiamento potrebbe non essere drammatico.
-   **Controlla il tuo cron job:** Assicurati che sia configurato correttamente sul tuo host e che sia in esecuzione. Alcuni host forniscono log per l'esecuzione dei cron job.
-   **Esegui manualmente:** Clicca su "Esegui ottimizzazione ora" nella configurazione del modulo. Se funziona, il problema è probabilmente nella configurazione del tuo cron job.
-   **Svuota la cache di Smarty:** A volte le modifiche visive o i miglioramenti di velocità richiedono lo svuotamento della cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Svuota cache" e clicca su "Svuota cache".

**D: Quali dati pulisce effettivamente questo modulo?**
R: Il modulo mira a vari tipi di dati temporanei e obsoleti che si accumulano nel tuo database, come:
-   Vecchi carrelli ospiti che non sono mai stati convertiti in ordini.
-   Sessioni scadute.
-   Vecchie voci di log (log di accesso, log di pagina non trovata).
-   File temporanei e dati della cache memorizzati nel database.
NON elimina dati dei clienti, ordini, prodotti o qualsiasi informazione essenziale del negozio.

**D: Questo modulo può danneggiare il mio negozio?**
R: Questo modulo è progettato per rimuovere in sicurezza solo dati non essenziali, temporanei o obsoleti. Non tocca dati critici del negozio come prodotti, ordini, clienti o categorie. Tuttavia, come per qualsiasi modulo che interagisce con il tuo database, è sempre consigliabile avere un backup recente prima dell'installazione e della configurazione.

**D: Il mio provider di hosting non supporta i cron job, o ho problemi a configurarli.**
R: Se non riesci a impostare un cron job, puoi comunque utilizzare il modulo cliccando manualmente sul pulsante "Esegui ottimizzazione ora" nella pagina di configurazione del modulo ogni volta che ritieni che il tuo negozio abbia bisogno di una pulizia (es. una volta alla settimana o una volta al mese). Sebbene non sia automatico, fornisce comunque i vantaggi dell'ottimizzazione del database. Contatta il supporto del tuo provider di hosting per assistenza con la configurazione dei cron job; di solito sono molto disponibili con questa attività comune.

**D: Questo modulo influisce sulla mia SEO?**
R: Indirettamente, sì. Tempi di caricamento delle pagine più veloci sono un fattore di ranking positivo per i motori di ricerca come Google. Migliorando la velocità del tuo sito, questo modulo contribuisce a una migliore esperienza utente, che può influenzare positivamente le tue prestazioni SEO.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Database Optimization Pro` è uno strumento di amministrazione leggero focalizzato principalmente sulla manutenzione del database. La sua funzionalità principale ruota attorno all'esecuzione di una serie di query SQL per pulire i dati non essenziali. L'aspetto "Pro" introduce un meccanismo automatizzato tramite un controller front-office progettato per essere attivato da un cron job, consentendo un'ottimizzazione programmata e non presidiata. Aderisce alla struttura del modulo di PrestaShop, utilizzando un file di modulo principale per l'installazione/configurazione e un controller frontale dedicato per l'esecuzione del cron.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/CronCleaner.php`
        -   **Nome classe**: `DboptimizationproCronCleanerModuleFrontController`
        -   **Classe genitore**: `ModuleFrontController`
        -   **Responsabilità**: Questo è il controller critico per la funzionalità del cron job. Quando viene acceduto, esegue la logica di pulizia del database. È progettato per essere chiamato esternamente (es. da `wget` tramite un cron job) e non renderizza una pagina visibile all'utente. Esegue le query di ottimizzazione del database effettive.
    -   `controllers/front/index.php`
        -   **Nome classe**: (Non una classe, tipicamente un file vuoto o un reindirizzamento)
        -   **Responsabilità**: Questo file è spesso incluso nei moduli PrestaShop per prevenire l'elenco delle directory quando si naviga `iltuonegozio.com/modules/dboptimizationpro/controllers/front/`. Tipicamente contiene un semplice `header('Location: ../../../index.php'); exit;` o simile per reindirizzare alla homepage, garantendo la sicurezza.
-   **Controller Admin Back-Office**:

    -   Non sono presenti controller admin dedicati. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Non sono presenti classi personalizzate o definizioni di `ObjectModel` nella directory `classes/`. La logica del modulo è incapsulata all'interno del file del modulo principale (`dboptimizationpro/cronjob.php`) e del controller frontale `CronCleaner`. Le interazioni con il database sono probabilmente query SQL dirette eseguite tramite `Db::getInstance()->execute()`.

### 4.4 Risorse JavaScript (`views/js/`)

Non sono presenti file JavaScript personalizzati nell'archivio del modulo. La funzionalità del modulo è lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Non sono presenti file CSS personalizzati nell'archivio del modulo. La pagina di configurazione del modulo utilizza lo stile standard del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Non sono presenti file di template Smarty (`.tpl`) personalizzati nell'archivio del modulo. Il modulo di configurazione del modulo viene renderizzato direttamente all'interno del metodo `getContent()` del file del modulo principale utilizzando i moduli helper di PrestaShop o HTML grezzo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Interagisce con le tabelle esistenti di PrestaShop per eliminare i dati obsoleti (es. `ps_cart`, `ps_connections`, `ps_log`, `ps_guest`, `ps_pagenotfound`).
    -   Le impostazioni di configurazione (come l'URL del cron job o un flag che indica l'ultima esecuzione) sono memorizzate nella tabella `ps_configuration`, tipicamente con chiavi prefissate da `DBOPTIMIZATIONPRO_`.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook front-office (es. `displayHeader`, `displayRightColumn`, `displayFooter`) per visualizzare il contenuto. La sua interazione principale con il sistema di hook di PrestaShop è per l'installazione/disinstallazione del modulo e potenzialmente per l'integrazione del menu del back-office (anche se non esplicitamente elencato come controller admin, il modulo stesso appare nell'elenco dei Moduli).

    La funzionalità principale del modulo viene attivata da:

    -   Accesso al metodo `getContent()` nel back office per la configurazione e l'esecuzione manuale.
    -   Accesso al controller frontale `CronCleaner` tramite un cron job esterno.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Database Optimization Pro", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
