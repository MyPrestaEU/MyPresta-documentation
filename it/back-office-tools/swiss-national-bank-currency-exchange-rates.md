---
title: "Banca Nazionale Svizzera - tassi di cambio - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Banca Nazionale Svizzera - tassi di cambio di MyPresta.eu."
sidebar:
  label: "Banca Nazionale Svizzera - tassi di cambio"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Swiss National Bank - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/swiss-national-bank-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/swiss-national-bank-currency-exchange-rates/)
>
> ---


# Banca Nazionale Svizzera - tassi di cambio

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Il tuo ambiente di hosting deve anche supportare i CRON job per gli aggiornamenti automatici.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alla pagina delle impostazioni principali del modulo. Qui definirai come il modulo recupera e applica i tassi di cambio.

#### **1. URL CRON**

-   **Cosa fa questa impostazione:** Visualizza l'URL unico che devi impostare come CRON job sul tuo server web. Quando questo URL viene richiamato, il modulo recupererà automaticamente i tassi di cambio più recenti dalla Banca Nazionale Svizzera e li aggiornerà nel tuo negozio PrestaShop.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. È generato dal modulo.
    *   *Se correttamente impostato come CRON job:* I tuoi tassi di cambio verranno aggiornati automaticamente alla frequenza che definisci (es. giornalmente, orariamente).
    *   *Se NON impostato come CRON job:* I tuoi tassi di cambio non verranno aggiornati automaticamente e dovrai attivare manualmente l'aggiornamento visitando questo URL nel tuo browser, il che vanifica lo scopo dell'automazione.
-   **Valore consigliato:** Copia questo URL e impostalo come CRON job sul tuo server di hosting.
-   **Scenario / esempio del commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni mattina alle 3. Copi questo URL e lo aggiungi allo scheduler dei CRON job del tuo pannello di controllo hosting, impostato per essere eseguito quotidianamente alle 3.

#### **2. Margine del Tasso di Cambio (%)**

-   **Cosa fa questa impostazione:** Ti permette di aggiungere un margine percentuale ai tassi di cambio recuperati dalla Banca Nazionale Svizzera. Questo margine viene applicato in aggiunta al tasso base.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato a 0 (predefinito):* I tassi di cambio verranno aggiornati esattamente come forniti dalla BNS.
    *   *Se impostato su un valore positivo (es. 2):* Il tasso di cambio verrà aumentato di quella percentuale. Ad esempio, se il tasso BNS è 1 EUR = 1.10 CHF, e imposti un margine del 2%, il tuo negozio userà 1 EUR = 1.122 CHF (1.10 \* 1.02). Ciò significa che i prodotti prezzati in CHF appariranno leggermente più costosi se convertiti in EUR.
-   **Valore consigliato:** Inizia con 0. Aumenta solo se hai bisogno di tenere conto delle commissioni del gateway di pagamento, dei costi di conversione valuta o per costruire un piccolo margine di profitto nella tua strategia di prezzo internazionale.
-   **Scenario / esempio del commerciante:** Il tuo processore di pagamento addebita una commissione dell'1.5% per le conversioni di valuta internazionali. Per coprire questo costo, imposti il "Margine del Tasso di Cambio" all'1.5%. Questo assicura che i tuoi margini di profitto non vengano erosi dalle commissioni di conversione.

#### **3. Pulsante Salva**

-   **Cosa fa questa impostazione:** Questo pulsante salva tutte le modifiche apportate all'impostazione "Margine del Tasso di Cambio".
-   **Effetto della modifica di questa impostazione:** Cliccando su "Salva" si applica l'impostazione del margine. L'URL CRON è statico e non richiede salvataggio.
-   **Valore consigliato:** Clicca sempre su "Salva" dopo aver regolato il margine.
-   **Scenario / esempio del commerciante:** Hai deciso di aggiungere un margine dell'1%. Dopo aver digitato "1" nel campo del margine, clicchi su "Salva" per assicurarti che questa impostazione venga applicata per i futuri aggiornamenti dei tassi.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | CRON URL | Generato dal modulo | URL per attivare l'aggiornamento automatico dei tassi di cambio tramite CRON job. |
| Pagina di configurazione del modulo | Margine del Tasso di Cambio (%) | 0 | Aggiunge una percentuale ai tassi di cambio recuperati per coprire costi o margini. |
| Pagina di configurazione del modulo | Pulsante Salva | Clicca dopo le modifiche | Salva le impostazioni del modulo. |

## 3. Domande Frequenti (FAQ)

**D: Il modulo supporta tutte le valute?**
R: Il modulo recupera i tassi di cambio dalla Banca Nazionale Svizzera. La BNS fornisce tassi per le principali valute internazionali rispetto al Franco Svizzero (CHF). Il modulo aggiornerà solo le valute attive nel tuo negozio per le quali la BNS fornisce un tasso.

**D: Qual è la valuta base utilizzata per i calcoli?**
R: Il modulo utilizza il Franco Svizzero (CHF) come valuta base per recuperare i tassi dalla BNS. Tutti i tassi di cambio nel tuo negozio verranno aggiornati in relazione al CHF.

**D: Posso impostare tassi di cambio diversi per valute diverse?**
R: Il modulo applica un unico "Margine del Tasso di Cambio" percentuale a *tutti* i tassi recuperati dalla BNS. Non è possibile impostare margini diversi per singole valute tramite questo modulo.

**D: Cosa succede se il CRON job non funziona?**
R: Se il CRON job non funziona, i tassi di cambio nel tuo negozio non verranno aggiornati automaticamente. Dovrai attivarli manualmente visitando l'URL CRON nel tuo browser, oppure risolvere il problema con la configurazione del CRON job sul tuo server di hosting.

**D: Il modulo influisce sulle prestazioni del mio negozio?**
R: Il modulo esegue il suo compito in background tramite un CRON job. L'impatto sulle prestazioni del front-office è minimo o nullo, poiché l'aggiornamento avviene in un processo separato e non durante la navigazione dei clienti.

**D: Posso disattivare l'aggiornamento automatico e aggiornare manualmente?**
R: Sì, puoi scegliere di non impostare il CRON job. In questo caso, per aggiornare i tassi, dovrai visitare manualmente l'URL CRON nel tuo browser ogni volta che desideri un aggiornamento. Tuttavia, questo vanifica lo scopo dell'automazione del modulo.

**D: Come posso verificare se i tassi di cambio sono stati aggiornati?**
R: Dopo che il CRON job è stato eseguito (o dopo aver visitato manualmente l'URL CRON), puoi andare su **Localizzazione > Valute** nel tuo Back Office di PrestaShop. Vedrai la colonna "Tasso di conversione" aggiornata per le valute interessate.

**D: Il modulo è compatibile con i temi personalizzati?**
R: Sì, il modulo opera in background e non ha componenti visivi nel front-office. Pertanto, è compatibile con qualsiasi tema PrestaShop, inclusi quelli personalizzati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura modulare PrestaShop minimalista. La sua funzione principale è recuperare periodicamente i tassi di cambio da un'API esterna (Banca Nazionale Svizzera) e aggiornare la tabella `currency` nel database di PrestaShop. La logica principale risiede nel file del modulo principale (`snbrates/cronjob.php`) ed è attivata da un controller frontale, progettato per essere richiamato da un CRON job. Utilizza la classe `Configuration` di PrestaShop per memorizzare le impostazioni e l'ObjectModel `Currency` per aggiornare i tassi.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questi controller sono progettati per essere accessibili esternamente, principalmente tramite CRON job.

    -   `controllers/front/cronjob.php`

        -   **Nome classe e classe padre:** `SnbratesCronjobModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è il punto di ingresso principale per l'aggiornamento automatico dei tassi. Quando l'URL di questo controller viene richiamato (es. `iltuonegozio.com/module/snbrates/cronjob`), esegue la logica per:
            1.  Recuperare i tassi di cambio più recenti dall'endpoint API della BNS configurato.
            2.  Applicare il margine configurato (se presente).
            3.  Aggiornare il `conversion_rate` per ogni valuta attiva nel database di PrestaShop, utilizzando CHF come base.
            4.  Non produce alcun output visivo al browser, tipicamente restituendo un semplice messaggio di successo/fallimento o reindirizzando.
    -   `controllers/front/index.php`

        -   **Nome classe e classe padre:** `SnbratesIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è un controller segnaposto, spesso incluso nei moduli ma non direttamente utilizzato per la funzionalità principale di questo specifico modulo. Potrebbe essere utilizzato per semplici reindirizzamenti o per prevenire l'elenco delle directory se acceduto direttamente, ma non contiene logica di business specifica per gli aggiornamenti dei tassi.
-   **Controller Amministrativi Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non introduce classi o ObjectModels personalizzati nella directory `classes/`. Sfrutta direttamente l'ObjectModel `Currency` di PrestaShop per gestire i dati delle valute e `Configuration` per le impostazioni del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Nessuno. Il modulo non utilizza JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessuno. Il modulo non utilizza CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template amministrativi (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Scopo:** Questo template viene renderizzato dal metodo `getContent()` del file del modulo principale (`snbrates/snbrates.php`) per visualizzare il modulo di configurazione del modulo nel Back Office di PrestaShop.
        -   **Contenuto:** Tipicamente include i campi del modulo per l'"URL CRON" (solo visualizzazione) e il "Margine del Tasso di Cambio (%)" (campo di input), insieme al pulsante "Salva". Utilizza le funzioni helper standard di PrestaShop per il rendering del modulo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Interagisce con la tabella core di PrestaShop `ps_currency`, aggiornando specificamente la colonna `conversion_rate` per le valute attive.
    -   Memorizza le sue impostazioni di configurazione (es. `SNBRATES_MARGIN`) nella tabella `ps_configuration`.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook di visualizzazione del front-office (come `displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductButtons`, ecc.) poiché la sua funzione principale è l'elaborazione dei dati in background. I "Front-Office Hooks: Header, Columns, Product, or Footer" menzionati nel prompt potrebbero riferirsi a una capacità generale o a un malinteso, poiché la funzione principale del modulo non implica il rendering di contenuti in queste aree.

    Il modulo utilizza implicitamente quanto segue:

    | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
    |---|---|---|
    | `actionModuleInstall` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti. |
    | `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione. |
    | (Interno) `ModuleFrontController` dispatch | Quando si accede all'URL CRON | Attiva la logica di aggiornamento dei tassi. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più recente e compatibile del modulo "Banca Nazionale Svizzera - tassi di cambio", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
