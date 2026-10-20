---
title: "Norges Bank - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Norges Bank - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Norges Bank - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Norges Bank - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/norges-bank-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/norges-bank-currency-exchange-rates/)
>
> ---


# Norges Bank - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Il tuo ambiente di hosting deve anche supportare i CRON job per gli aggiornamenti automatici.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali per il modulo "Norges Bank - tassi di cambio valuta". Qui è dove controlli come e quando i tuoi tassi di cambio vengono aggiornati.

#### **Impostazioni e Opzioni**

1.  **URL CRON per aggiornamenti automatici:**

    -   **Cosa fa questa impostazione:** Questo è un indirizzo web unico (URL) che, quando visitato, attiva il modulo per recuperare gli ultimi tassi di cambio dalla Norges Bank e aggiornarli nel tuo negozio PrestaShop.
    -   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo. Hai bisogno di questo URL per impostare un'attività automatizzata (un "CRON job") sul tuo server di hosting web.
    -   **Valore consigliato:** Copia questo URL esattamente come appare.
    -   **Scenario / esempio per il commerciante:** Fornirai questo URL al tuo provider di hosting o lo userai nel tuo pannello di controllo dell'hosting (come cPanel o Plesk) per programmare un'attività che visiti questo URL regolarmente (ad esempio, una volta al giorno). Questo assicura che i tuoi tassi siano sempre aggiornati senza che tu debba fare nulla manualmente.
2.  **Margine del tasso di cambio (%):**

    -   **Cosa fa questa impostazione:** Questo ti consente di aggiungere un margine percentuale ai tassi di cambio recuperati dalla Norges Bank. Ad esempio, se il tasso ufficiale è 1 EUR = 10 NOK e imposti un margine del 2%, il tuo negozio potrebbe usare 1 EUR = 9.8 NOK (o 10.2 NOK, a seconda della direzione del calcolo, tipicamente rendendo la valuta estera leggermente più costosa per il cliente per coprire i costi di conversione).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 0:* Il tuo negozio utilizza i tassi di cambio ufficiali esatti forniti dalla Norges Bank.
        -   *Quando impostato su un valore positivo (es. 2):* Il modulo regola i tassi di cambio per includere questa percentuale, fornendoti effettivamente un piccolo buffer o margine di profitto sulle conversioni di valuta. Questo può aiutare a coprire le commissioni di transazione o semplicemente aumentare la tua redditività.
    -   **Valore consigliato:** Inizia con `0` se desideri tassi esatti. Se hai bisogno di coprire i costi o aggiungere un piccolo profitto, un valore tra `0.5` e `2` percento è comune.
    -   **Scenario / esempio per il commerciante:** Se il tuo gateway di pagamento addebita una commissione dell'1% per le transazioni internazionali, impostare un margine dell'1% qui può aiutarti ad assorbire quel costo senza influire sui prezzi dei tuoi prodotti nella tua valuta base.
3.  **Ultimo aggiornamento:**

    -   **Cosa fa questa impostazione:** Questo mostra la data e l'ora dell'ultimo aggiornamento riuscito dei tassi di cambio nel tuo negozio da parte del modulo.
    -   **Effetto della modifica di questa impostazione:** Questo è un campo informativo e non può essere modificato. Ti aiuta a verificare che il tuo CRON job funzioni correttamente e che i tuoi tassi vengano aggiornati regolarmente.
    -   **Valore consigliato:** Controlla periodicamente questo campo per assicurarti che gli aggiornamenti avvengano come previsto.
    -   **Scenario / esempio per il commerciante:** Dopo aver impostato il tuo CRON job, puoi controllare questo campo il giorno successivo per confermare che il modulo è stato eseguito con successo e ha aggiornato i tassi.

#### **Pulsante di aggiornamento manuale**

-   **Cosa fa questo pulsante:** Questo pulsante ti consente di attivare manualmente un aggiornamento immediato di tutti i tassi di cambio dalla Norges Bank.
-   **Effetto del clic su questo pulsante:** Il modulo recupererà istantaneamente gli ultimi tassi e li applicherà al tuo negozio. Questo è utile per i test o se hai bisogno di un aggiornamento immediato al di fuori del tuo CRON job programmato.
-   **Uso consigliato:** Usalo per i test iniziali dopo la configurazione, o se c'è una significativa e improvvisa fluttuazione valutaria che desideri riflettere immediatamente.

#### **Istruzioni per la configurazione del CRON Job**

Sotto le impostazioni, troverai istruzioni chiare su come configurare il CRON job sul tuo server. Questo è cruciale per il funzionamento "senza manutenzione" del modulo.

-   **Cosa fa questa sezione:** Fornisce il comando esatto o il metodo che devi usare con lo scheduler CRON job del tuo provider di hosting.
-   **Effetto del seguire queste istruzioni:** Una volta configurato, il tuo server visiterà automaticamente l'URL CRON a intervalli specificati (ad esempio, una volta al giorno), assicurando che i tuoi tassi di cambio siano sempre aggiornati senza intervento manuale.
-   **Frequenza consigliata:** Gli aggiornamenti giornalieri sono solitamente sufficienti. Per valute altamente volatili o vendite internazionali ad alto volume, potresti considerare due volte al giorno.
-   **Scenario / esempio per il commerciante:** In cPanel, andresti su "Cron Jobs", selezioneresti un'impostazione comune come "Una volta al giorno" e incolleresti il comando fornito nel campo "Comando".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL CRON per aggiornamenti automatici | (URL generato) | URL per attivare gli aggiornamenti automatici dei tassi tramite CRON job. **Cruciale per l'automazione.** |
| Configurazione Modulo | Margine del tasso di cambio (%) | 0 | Aggiunge un buffer percentuale ai tassi di cambio per redditività/recupero costi. |
| Configurazione Modulo | Ultimo aggiornamento | (Data/Ora) | Campo informativo che mostra l'ultimo aggiornamento riuscito dei tassi. |
| Configurazione Modulo | Pulsante di aggiornamento manuale | N/A | Recupera e applica immediatamente gli ultimi tassi. Utile per test/aggiornamenti urgenti. |
| Configurazione Modulo | Istruzioni per la configurazione del CRON Job | N/A | Guida per impostare gli aggiornamenti automatici sul tuo server di hosting. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo fare?**
R: Questo è quasi sempre correlato alla configurazione del CRON job sul tuo server.
1.  **Verifica il CRON Job:** Ricontrolla il tuo pannello di controllo dell'hosting (cPanel, Plesk, ecc.) per assicurarti che il CRON job sia configurato correttamente con l'URL esatto fornito dal modulo e che sia programmato per essere eseguito.
2.  **Percorso CRON:** A volte il percorso PHP nel comando CRON deve essere assoluto (ad esempio, `/usr/bin/php` invece di solo `php`). Il tuo provider di hosting può confermarlo.
3.  **Controlla "Ultimo aggiornamento":** Se il campo "Ultimo aggiornamento" nella configurazione del modulo non cambia mai, conferma che il CRON job non sta eseguendo lo script di aggiornamento del modulo.
4.  **Aggiornamento manuale:** Prova a cliccare sul pulsante "Aggiornamento manuale" nella configurazione del modulo. Se funziona, conferma che il modulo stesso può recuperare i tassi, indicando definitivamente un problema con il CRON job.

**D: I tassi di cambio sembrano errati o non sono cambiati molto.**
R:
1.  **Controlla Norges Bank:** Confronta i tassi nel tuo negozio con i tassi ufficiali pubblicati dalla Norges Bank (il loro sito web è solitamente accessibile tramite una rapida ricerca).
2.  **Impostazione del margine:** Ricorda che la tua impostazione "Margine del tasso di cambio (%)" regolerà leggermente i tassi. Assicurati che sia impostata come previsto.
3.  **Ultimo aggiornamento:** Controlla il campo "Ultimo aggiornamento". Se è vecchio, il tuo CRON job non è in esecuzione.

**D: Questo modulo influisce sulla mia valuta predefinita?**
R: No, il modulo aggiorna solo i tassi di cambio per le valute non predefinite rispetto alla tua valuta predefinita. Il valore della tua valuta predefinita rimane invariato.

**D: Ho aggiornato il mio tema e ora il selettore di valuta non funziona correttamente.**
R: Questo modulo aggiorna solo i *valori* dei tassi di cambio. La visualizzazione e la funzionalità del selettore di valuta stesso sono gestite dal core di PrestaShop o dal tuo tema. Se il selettore non funziona, è probabile che sia un problema del tema o del core di PrestaShop, non direttamente correlato a questo modulo. Svuota la cache di Smarty (**Parametri avanzati > Prestazioni**) e controlla la configurazione del tuo tema.

**D: Posso usare questo modulo con altri moduli di valuta?**
R: Generalmente non è consigliabile eseguire più moduli che tentano di aggiornare i tassi di cambio, poiché potrebbero entrare in conflitto o sovrascrivere i dati l'uno dell'altro. Questo modulo è progettato per essere una soluzione autonoma per i tassi della Norges Bank. Se hai bisogno di tassi da una fonte diversa, dovresti disabilitare questo modulo e usarne l'altro.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Norges Bank - tassi di cambio valuta" (`nbrates`) è un modulo PrestaShop leggero, focalizzato principalmente su un singolo, critico compito: recuperare e aggiornare i tassi di cambio valuta. Sfrutta la classe `Module` di PrestaShop per l'installazione e la configurazione e utilizza un controller frontale per esporre un endpoint CRON per gli aggiornamenti automatici. La logica principale prevede l'esecuzione di una richiesta HTTP all'API della Norges Bank, l'analisi della risposta XML, il calcolo dei tassi incrociati e l'aggiornamento della tabella `ps_currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe**: `NbratesCronjobModuleFrontController`
        -   **Classe padre**: `ModuleFrontController`
        -   **Responsabilità**: Questo controller gestisce l'esecuzione del CRON job. Quando viene acceduto tramite il suo URL (fornito nella configurazione del modulo), attiva il metodo `cronjob()` all'interno della classe principale del modulo `nbrates`. È progettato per essere chiamato da uno scheduler esterno (CRON) e restituisce un semplice messaggio di successo/fallimento. Non renderizza alcun contenuto visivo per l'utente.
    -   `controllers/front/index.php`
        -   **Nome classe**: `NbratesIndexModuleFrontController`
        -   **Classe padre**: `ModuleFrontController`
        -   **Responsabilità**: Questo è un controller segnaposto, spesso incluso nei moduli ma non attivamente utilizzato nella funzionalità principale di questo modulo specifico. Tipicamente serve come punto di ingresso predefinito se un modulo ha una pagina front-office dedicata. In questo modulo, il suo scopo principale è probabilmente quello di prevenire l'elenco delle directory se `cronjob.php` viene acceduto direttamente senza un'azione specifica.
-   **Controller Admin Back-Office**:

    -   Nessuno. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuno. La logica principale del modulo è autocontenuta nel file principale `nbrates/cronjob.php`. Questo è comune per moduli più semplici che non richiedono strutture dati complesse o interazioni estese con il database oltre la configurazione standard.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo non include alcun JavaScript personalizzato per la funzionalità front-office o back-office.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non include alcun foglio di stile CSS personalizzato. La configurazione del back-office si basa sullo stile predefinito del pannello di amministrazione di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` della classe principale del modulo (`nbrates/cronjob.php`) per visualizzare il modulo di configurazione del modulo nel Back Office di PrestaShop.
        -   **Contenuto**: Tipicamente contiene la struttura HTML per la visualizzazione dell'URL CRON, il campo di input del margine del tasso di cambio, le informazioni "Ultimo aggiornamento", il pulsante di aggiornamento manuale e le istruzioni per la configurazione del CRON job. Utilizza gli helper e lo stile standard dei moduli di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Interagisce con la tabella standard `ps_configuration` di PrestaShop per memorizzare le sue impostazioni (ad esempio, `NBS_LAST_UPDATE`, `NBS_MARGIN`).
    -   Aggiorna la tabella `ps_currency`, in particolare la colonna `conversion_rate` per le valute non predefinite.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` del Back Office. | Utilizzato per includere eventuali CSS/JS necessari per la pagina di configurazione del modulo (anche se nessuno è utilizzato in questo modulo). |
| `actionAdminControllerSetMedia` | Chiamato prima di renderizzare un controller admin. | Utilizzato per registrare risorse (JS/CSS) per le pagine admin. |
| `actionCronJob` | Hook personalizzato, attivato dal controller frontale `cronjob`. | L'hook principale in cui viene eseguita la logica di aggiornamento della valuta del modulo. |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` del front office. | (Non esplicitamente utilizzato da questo modulo per l'output, ma spesso registrato dai moduli). |
| `displayLeftColumn` | Renderizza il contenuto nella colonna sinistra del front office. | (Non esplicitamente utilizzato da questo modulo per l'output). |
| `displayRightColumn` | Renderizza il contenuto nella colonna destra del front office. | (Non esplicitamente utilizzato da questo modulo per l'output). |
| `displayFooter` | Renderizza il contenuto nel piè di pagina del front office. | (Non esplicitamente utilizzato da questo modulo per l'output). |
| `displayProductExtraContent` | Renderizza il contenuto nella pagina del prodotto. | (Non esplicitamente utilizzato da questo modulo per l'output). |

*Nota: Sebbene la descrizione del modulo menzioni hook Front-Office come Header, Colonne, Prodotto o Footer, l'inventario del codice fornito non mostra alcun template o logica specifica per il rendering del contenuto in questi hook. È possibile che questi siano hook generici registrati durante l'installazione ma non attivamente utilizzati per l'output visivo da questo modulo specifico, poiché la sua funzione è puramente la sincronizzazione dei dati di backend.*

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Norges Bank - tassi di cambio valuta", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Puoi scaricare le versioni più recenti dalla cronologia degli ordini e accedere alle risorse di supporto direttamente dalla piattaforma MyPresta.eu.
