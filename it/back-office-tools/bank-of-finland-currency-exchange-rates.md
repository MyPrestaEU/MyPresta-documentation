---
title: "Banca di Finlandia - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Banca di Finlandia - tassi di cambio valuta' di MyPresta.eu."
sidebar:
  label: "Banca di Finlandia - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank of Finland - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-finland-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bank-of-finland-currency-exchange-rates/)
>
> ---


# Banca di Finlandia - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Il tuo ambiente di hosting deve anche supportare i CRON job per gli aggiornamenti automatici.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Qui definirai come i tassi di cambio vengono aggiornati e applicati.

#### **1. URL CRON**

-   **Cosa fa questa impostazione:** Questo è un indirizzo web (URL) unico che, quando visitato, attiva il modulo per recuperare gli ultimi tassi di cambio dalla Banca di Finlandia e aggiornarli nel tuo negozio PrestaShop.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo. Questo URL è cruciale per impostare un'attività automatizzata (CRON job) sul tuo server web.
-   **Valore consigliato:** Copia questo URL esattamente come appare.
-   **Scenario / esempio del commerciante:** Fornirai questo URL al tuo provider di hosting o lo userai nel tuo pannello di controllo di hosting (es. cPanel, Plesk) per impostare un CRON job. Ciò garantisce che i tuoi tassi di cambio vengano aggiornati automaticamente, ad esempio, una volta al giorno, senza che tu debba cliccare manualmente nulla.

#### **2. Istruzioni per la configurazione del CRON job**

-   **Cosa fa questa impostazione:** Questa sezione fornisce istruzioni su come impostare il CRON job utilizzando l'URL fornito sopra. Un CRON job è uno scheduler di processi basato sul tempo nei sistemi operativi simili a Unix. Ti consente di pianificare l'esecuzione automatica di comandi o script a intervalli specificati.
-   **Effetto della modifica di questa impostazione:** Questa è una sezione informativa; non modifichi nulla qui. Seguire correttamente queste istruzioni assicura che i tuoi tassi di cambio vengano aggiornati automaticamente.
-   **Valore consigliato:** Leggi e segui attentamente queste istruzioni.
-   **Scenario / esempio del commerciante:** Il pannello di controllo del tuo provider di hosting (come cPanel) avrà una sezione "Cron Jobs" o "Attività pianificate". Tipicamente aggiungerai un nuovo cron job, specificherai la frequenza (es. una volta al giorno alle 3 del mattino) e incollerai l'URL CRON nel campo del comando, spesso preceduto da `wget -q -O /dev/null`.

#### **3. Margine (%)**

-   **Cosa fa questa impostazione:** Questo ti consente di aggiungere un margine percentuale ai tassi di cambio recuperati. Ad esempio, se il tasso ufficiale è 1 EUR = 1.10 USD, e imposti un margine del 2%, il modulo userà 1 EUR = 1.078 USD (1.10 * 0.98) o 1 EUR = 1.122 USD (1.10 * 1.02) a seconda di come il modulo applica il margine (solitamente per proteggere dalle fluttuazioni, quindi potrebbe aumentare leggermente il prezzo in valuta estera).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato a 0:* I tassi di cambio verranno aggiornati esattamente come forniti dalla Banca di Finlandia.
    -   *Quando impostato su un valore positivo (es. 2):* Il modulo regolerà il tasso di cambio di questa percentuale. Questo può aiutare a coprire le commissioni di transazione, i costi di conversione valuta, o semplicemente fornire un piccolo cuscinetto contro movimenti sfavorevoli del tasso, garantendo il mantenimento dei tuoi margini di profitto.
-   **Valore consigliato:** Inizia con 0. Se riscontri problemi di redditività a causa delle fluttuazioni valutarie o delle commissioni di conversione, considera un piccolo margine come 1-3%.
-   **Scenario / esempio del commerciante:** Se vendi un prodotto per 100 EUR e il tasso di cambio è 1 EUR = 1.10 USD, il prodotto sarebbe 110 USD. Se imposti un margine del 2%, il modulo potrebbe calcolare il tasso come 1 EUR = 1.078 USD, rendendo il prodotto 107.80 USD. Questo ti dà un piccolo cuscinetto.

#### **4. Ultimo aggiornamento**

-   **Cosa fa questa impostazione:** Questo visualizza la data e l'ora in cui i tassi di cambio sono stati aggiornati con successo dal modulo.
-   **Effetto della modifica di questa impostazione:** Questo è un campo informativo e non può essere modificato direttamente. Serve come verifica che il tuo CRON job stia funzionando correttamente e che il modulo stia attivamente aggiornando i tassi.
-   **Valore consigliato:** Questo dovrebbe mostrare una data e un'ora recenti, idealmente entro le ultime 24 ore se il tuo CRON job viene eseguito quotidianamente.
-   **Scenario / esempio del commerciante:** Se imposti il tuo CRON job per essere eseguito quotidianamente alle 3 del mattino, dovresti vedere il timestamp "Ultimo aggiornamento" cambiare per riflettere le 3 del mattino del giorno corrente (o poco dopo) ogni mattina. Se non si aggiorna, indica un problema con la configurazione del tuo CRON job.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL CRON | Copia esattamente | URL unico per attivare gli aggiornamenti dei tassi tramite CRON job. |
| Configurazione Modulo | Istruzioni per la configurazione del CRON job | Leggi attentamente | Guida per impostare gli aggiornamenti automatici sul tuo server. |
| Configurazione Modulo | Margine (%) | 0 (o 1-3% se necessario) | Aggiunge un buffer percentuale ai tassi di cambio per proteggere i margini di profitto. |
| Configurazione Modulo | Ultimo aggiornamento | N/A (informativo) | Mostra il timestamp dell'ultimo aggiornamento riuscito del tasso. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano. Cosa devo fare?**
R1: Questo è quasi sempre correlato alla configurazione del CRON job.
1.  **Controlla il timestamp "Ultimo aggiornamento":** Vai alla pagina di configurazione del modulo. Se questa data è vecchia, il tuo CRON job non è in esecuzione.
2.  **Verifica la configurazione del CRON job:** Accedi al tuo pannello di controllo di hosting (es. cPanel, Plesk). Naviga nella sezione "Cron Jobs" o "Attività pianificate".
    \* Assicurati che l'URL CRON che hai copiato dal modulo sia esattamente quello presente nel comando del tuo CRON job.
    \* Assicurati che il comando sia formattato correttamente (es. `wget -q -O /dev/null "IL_TUO_URL_CRON_QUI"`).
    \* Conferma che la frequenza sia impostata come desiderato (es. giornaliera).
    \* Controlla l'indirizzo email associato al CRON job (se presente) per eventuali messaggi di errore.
3.  **Esegui manualmente l'URL CRON:** Copia l'URL CRON dalla configurazione del modulo e incollalo direttamente nella barra degli indirizzi del tuo browser web. Questo dovrebbe attivare un aggiornamento. Se funziona, il problema è sicuramente con la configurazione del CRON job del tuo server. Se non funziona, potrebbe esserci un problema lato server che impedisce al modulo di recuperare i dati (es. firewall, cURL non abilitato).

**D2: I miei prezzi in valute estere sembrano leggermente sbagliati, anche dopo gli aggiornamenti.**
R2: Controlla l'impostazione "Margine (%)" nella configurazione del modulo. Se hai impostato un margine (es. 2%), il modulo regolerà intenzionalmente il tasso di cambio di quella percentuale. Se desideri tassi ufficiali esatti, imposta il margine a 0. Inoltre, assicurati che la tua valuta base in PrestaShop (Localizzazione > Valute) sia impostata correttamente su EUR se stai principalmente trattando con i tassi della Banca di Finlandia.

**D3: Questo modulo funziona con tutte le valute?**
R3: Il modulo recupera i dati di riferimento ufficiali dalla Banca di Finlandia, che fornisce principalmente tassi rispetto all'Euro. Tuttavia, calcola intelligentemente i tassi incrociati per le valute non euro. Ciò significa che se la Banca di Finlandia fornisce EUR a USD e EUR a GBP, il modulo può derivare il tasso da USD a GBP. Finché la Banca di Finlandia fornisce un tasso per una valuta rispetto all'Euro, il modulo dovrebbe essere in grado di aggiornarlo.

**D4: Devo svuotare la cache di Smarty dopo gli aggiornamenti?**
R4: No, tipicamente no. Questo modulo aggiorna i valori del database (tassi di cambio). La cache di Smarty di PrestaShop influisce principalmente sulla compilazione dei template e sui contenuti statici. Le modifiche ai tassi di cambio sono dinamiche e dovrebbero riflettersi immediatamente nei prezzi del tuo negozio senza la necessità di svuotare la cache.

**D5: Il mio tema personalizzato non mostra correttamente i prezzi aggiornati.**
R5: Il modulo aggiorna i tassi di cambio sottostanti nel database di PrestaShop. Il selettore di valuta e la logica di visualizzazione dei prezzi del tuo tema dovrebbero automaticamente rilevare questi tassi aggiornati. In caso contrario, è probabile che si tratti di un problema specifico del tema piuttosto che di un problema del modulo.
1.  **Verifica i tassi interni di PrestaShop:** Vai su **Localizzazione > Valute** nel tuo Back Office. Controlla la colonna "Tasso di cambio" per le tue valute non EUR. Se questi tassi sono aggiornati correttamente, il modulo funziona.
2.  **Contatta lo sviluppatore del tuo tema:** Se i tassi sono corretti nel Back Office ma non nel front-end, il tuo tema potrebbe avere una cache personalizzata o un modo specifico di gestire la visualizzazione della valuta che richiede l'attenzione dello sviluppatore del tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Banca di Finlandia - tassi di cambio valuta" (`sprates`) è un modulo PrestaShop leggero progettato per un singolo, critico compito: automatizzare gli aggiornamenti dei tassi di cambio valuta. Sfrutta un controller front-office per esporre un endpoint richiamabile da CRON, che, quando viene acceduto, recupera i dati XML dalla Banca di Finlandia, li analizza e aggiorna la tabella `ps_currency`. Il modulo segue un pattern MVC standard di PrestaShop per la sua configurazione e il trigger front-end.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `sprates/controllers/front/cronjob.php`
    -   **Nome classe e classe padre:** `SpratesCronjobModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è il controller principale per il processo di aggiornamento automatico. Risponde alle richieste effettuate all'URL CRON. All'esecuzione, esso:
        1.  Recupera i dati XML dal feed ufficiale dei tassi di cambio della Banca di Finlandia.
        2.  Analizza l'XML per estrarre i tassi di cambio basati sull'EUR.
        3.  Calcola i tassi incrociati per le valute non EUR se necessario.
        4.  Applica il margine configurato.
        5.  Aggiorna la colonna `exchange_rate` nella tabella `ps_currency` per tutte le valute attive in PrestaShop.
        6.  Aggiorna il timestamp `last_update` nella configurazione del modulo.
        7.  Restituisce un semplice messaggio di successo o errore (spesso soppresso da `wget -q -O /dev/null`).
-   `sprates/controllers/front/index.php`
    -   **Nome classe e classe padre:** `SpratesIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è un controller segnaposto, tipicamente usato per prevenire l'elenco delle directory o fornire un'azione predefinita se il dispatch principale del modulo non viene utilizzato. Nel contesto di questo modulo, probabilmente serve come fallback o una pratica standard di PrestaShop per i moduli con controller frontali, ma la logica principale risiede in `cronjob.php`.

#### Controller Admin Back-Office

Questo modulo non utilizza alcun controller Admin personalizzato dedicato. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce alcuna classe o modello personalizzato all'interno della directory `classes/`. Interagisce direttamente con la classe `Currency` e la classe `Configuration` di PrestaShop per gestire i tassi di cambio e le impostazioni del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `sprates/views/admin.tpl`
        -   **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza l'URL CRON, le istruzioni di configurazione, il campo di input del margine e il timestamp dell'ultimo aggiornamento. Utilizza elementi di form helper standard di PrestaShop.

### 4.7 Schema del database e Mappa degli hook

#### Tabelle del database

Il modulo non crea tabelle di database personalizzate. Interagisce con le tabelle esistenti di PrestaShop:

-   `ps_currency`: Aggiorna la colonna `exchange_rate` per le valute attive.
-   `ps_configuration`: Memorizza le impostazioni specifiche del modulo come `SP_RATES_MARGIN` (per la percentuale di margine) e `SP_RATES_LAST_UPDATE` (per il timestamp dell'ultimo aggiornamento).

#### Tabella degli hook registrati

Questo modulo non registra alcun hook di visualizzazione tradizionale (es. `displayHeader`, `displayFooter`) in quanto non ha componenti visivi nel front-office. Il suo meccanismo di "hook" primario è il CRON job, che attiva il suo controller frontale.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione. |
| (CRON job tramite Front Controller) | Pianificato dal server (es. giornaliero) | Recupera, calcola e aggiorna i tassi di cambio valuta. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Banca di Finlandia - tassi di cambio valuta", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
