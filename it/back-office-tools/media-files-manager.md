---
title: "Media / Files Manager - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Media / Files Manager di MyPresta.eu."
sidebar:
  label: "Media / Files Manager - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Media / Files Manager su MyPresta.eu](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/media-files-manager/)
>
> ---


# Media / Files Manager

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Il modulo richiede permessi di scrittura per le directory che gestisce, il che è standard per le installazioni PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, verrai indirizzato alla pagina di configurazione del modulo. Questa pagina serve principalmente a integrare il gestore file nel tuo back office PrestaShop e a gestire le sue impostazioni principali.

La schermata di configurazione principale mostrerà direttamente l'interfaccia del gestore file. Questa interfaccia è un browser di file completo, simile a quello che vedresti sul tuo computer, ma che opera sui file del tuo server.

**Aree chiave e funzionalità all'interno dell'interfaccia del gestore file:**

1.  **Pannello di navigazione (barra laterale sinistra):**

    -   **Cosa fa:** Mostra una struttura ad albero delle directory del tuo server, tipicamente a partire dalla cartella radice di PrestaShop. Puoi cliccare sulle cartelle per navigare al loro interno.
    -   **Effetto dell'utilizzo:** Ti consente di passare rapidamente tra diverse parti della tua installazione PrestaShop (es. `img/p` per le immagini dei prodotti, `themes/yourtheme/css` per i fogli di stile).
    -   **Valore consigliato:** Usalo per navigare nella cartella specifica dove vuoi gestire i file.
2.  **Area di elencazione file (pannello principale):**

    -   **Cosa fa:** Visualizza il contenuto (file e sottocartelle) della cartella attualmente selezionata. Vedrai nomi di file, dimensioni, tipi e date di modifica.
    -   **Effetto dell'utilizzo:** Qui eseguirai la maggior parte delle operazioni sui file.
    -   **Valore consigliato:** Familiarizza con le icone e le informazioni presentate per ogni file.
3.  **Barra degli strumenti (parte superiore dell'area di elencazione file):**

    -   **Cosa fa:** Contiene vari pulsanti e strumenti per le operazioni sui file. Gli strumenti comuni includono:
        -   **Carica:** Carica file dal tuo computer alla cartella corrente del server.
        -   **Nuova cartella:** Crea una nuova directory.
        -   **Nuovo file:** Crea un nuovo file vuoto (es. un file `.txt`, `.html` o `.css`).
        -   **Copia, Taglia, Incolla:** Manipolazione standard dei file.
        -   **Rinomina:** Cambia il nome di un file o di una cartella.
        -   **Elimina:** Rimuovi file o cartelle (usa con estrema cautela!).
        -   **Modifica:** Apre un editor di testo per i file di testo selezionati (es. `.php`, `.css`, `.js`, `.html`).
        -   **Anteprima:** Visualizza immagini o altri tipi di file supportati direttamente.
        -   **Cerca:** Trova file all'interno della directory corrente o ricorsivamente.
        -   **Opzioni di visualizzazione:** Cambia il modo in cui i file vengono visualizzati (elenco, icone, ecc.).
    -   **Effetto dell'utilizzo di questi strumenti:** Manipola direttamente file e cartelle sul tuo server.
    -   **Valore consigliato:** Controlla sempre due volte le tue selezioni prima di eseguire azioni come "Elimina" o "Rinomina".
4.  **Menu contestuale (tasto destro del mouse):**

    -   **Cosa fa:** Cliccando con il tasto destro su un file o una cartella spesso si apre un menu contestuale con accesso rapido a operazioni comuni come "Apri", "Modifica", "Rinomina", "Elimina", "Scarica", "Ottieni informazioni", ecc.
    -   **Effetto dell'utilizzo:** Fornisce un modo più veloce per eseguire azioni su singoli elementi.
    -   **Valore consigliato:** Esplora le opzioni del tasto destro per diversi tipi di file.

**Impostazioni specifiche (se presenti, basate su `mypresta_updates`, `update_`, `updatev_`):**

Il metodo `getContent()` del modulo renderizza principalmente l'interfaccia del gestore file stesso. Le chiavi di configurazione `mypresta_updates`, `update_` e `updatev_` sono chiavi interne standard utilizzate dai moduli MyPresta.eu per gestire le notifiche di aggiornamento e i controlli di versione. Queste non sono impostazioni con cui tipicamente interagisci direttamente come commerciante.

-   **Cosa fanno queste impostazioni:** Sono flag interni che aiutano il modulo a comunicare con il server di aggiornamento di MyPresta.eu per verificare nuove versioni e visualizzare notifiche nel tuo back office PrestaShop se è disponibile un aggiornamento.
-   **Effetto della modifica di queste impostazioni:** Non puoi modificarle direttamente. Sono gestite automaticamente dal modulo. Se dovessero essere alterate manualmente (cosa non raccomandata), ciò potrebbe influire sulla capacità del modulo di notificarti le nuove versioni.
-   **Valore consigliato:** Lasciale così come sono. Sono per la gestione interna del modulo.
-   **Scenario / esempio per il commerciante:** Non devi preoccuparti di queste. Il modulo ti informerà automaticamente se viene rilasciata una nuova versione, invitandoti a scaricarla e installarla dal tuo account MyPresta.eu.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non introduce schermate di amministrazione dedicate aggiuntive o controller personalizzati oltre alla sua pagina di configurazione principale. L'intera funzionalità di gestione dei file è incorporata direttamente nell'interfaccia di configurazione del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista          | Impostazione / Opzione                               | Predefinito / Consigliato | Scopo e impatto                                                              |
| :------------------------ | :--------------------------------------------------- | :------------------------ | :--------------------------------------------------------------------------- |
| Pagina di configurazione del modulo | **Pannello di navigazione**                          | N/A                       | Sfoglia le directory del server.                                             |
| Pagina di configurazione del modulo | **Area di elencazione file**                         | N/A                       | Visualizza e interagisci con file/cartelle.                                  |
| Pagina di configurazione del modulo | **Barra degli strumenti (Carica, Nuova cartella, Modifica, Elimina, ecc.)** | N/A                       | Esegui operazioni sui file (carica, crea, modifica, elimina).                |
| Pagina di configurazione del modulo | **Menu contestuale (tasto destro del mouse)**        | N/A                       | Accesso rapido alle operazioni sui file.                                     |
| Pagina di configurazione del modulo | `mypresta_updates`                                   | Interno                   | Flag interno per le notifiche di aggiornamento.                              |
| Pagina di configurazione del modulo | `update_`                                            | Interno                   | Flag interno per le notifiche di aggiornamento.                              |
| Pagina di configurazione del modulo | `updatev_`                                           | Interno                   | Flag interno per le notifiche di aggiornamento.                              |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho caricato un'immagine, ma non viene visualizzata sulla mia pagina prodotto.**
R:

-   **Controlla il percorso:** Assicurati di aver caricato l'immagine nella directory corretta che PrestaShop si aspetta (solitamente `img/p/` seguito da sottocartelle).
-   **Svuota la cache:** A volte la cache di PrestaShop (o la cache del tuo browser) potrebbe impedire la visualizzazione immediata delle nuove immagini. Vai su **Parametri Avanzati > Prestazioni** nel tuo back office e clicca su "Svuota la cache". Prova anche a svuotare la cache del tuo browser.
-   **Permessi:** Assicurati che la cartella in cui hai caricato l'immagine abbia i permessi di scrittura corretti (solitamente 755 o 775). Sebbene il modulo di solito gestisca questo, a volte le configurazioni del server possono essere rigide.

**D: Ho modificato un file CSS, ma il design del mio negozio non è cambiato.**
R:

-   **Svuota la cache:** Questa è la ragione più comune. Vai su **Parametri Avanzati > Prestazioni** e svuota la cache di PrestaShop. Inoltre, svuota la cache del tuo browser (Ctrl+F5 o Cmd+R di solito forza un aggiornamento completo).
-   **File corretto:** Ricontrolla di aver modificato il file CSS corretto che il tuo tema sta effettivamente caricando. Alcuni temi utilizzano CSS compilati o più fogli di stile.
-   **Errori di sintassi:** Se hai introdotto un errore di sintassi nel tuo CSS, potrebbe impedire il caricamento corretto del foglio di stile. Usa gli strumenti per sviluppatori del tuo browser (F12) per controllare gli errori CSS.

**D: Ho accidentalmente eliminato un file/cartella. Posso recuperarlo?**
R:

-   **Ripristina immediatamente da backup:** Questo è il motivo per cui i backup regolari sono cruciali. Se hai un backup recente dei file del tuo server, ripristina l'elemento eliminato da lì.
-   **Contatta il provider di hosting:** Alcuni provider di hosting mantengono backup giornalieri e potrebbero essere in grado di ripristinare singoli file per te.
-   **Attenzione:** Il modulo stesso non ha una funzione "cestino" o "annulla". L'eliminazione è permanente.

**D: Il gestore file sembra rotto o non si carica correttamente.**
R:

-   **Controlla la console del browser:** Apri gli strumenti per sviluppatori del tuo browser (F12) e cerca eventuali errori nella scheda "Console". Questo può indicare conflitti JavaScript o problemi lato server.
-   **Conflitti di moduli:** Prova a disabilitare altri moduli installati di recente per vedere se c'è un conflitto.
-   **Log degli errori del server:** Controlla i log degli errori PHP del tuo server per eventuali errori correlati.
-   **Permessi:** Assicurati che i file e le cartelle del modulo stesso abbiano i permessi di lettura/scrittura corretti.

**D: Posso limitare l'accesso a determinate cartelle per diversi utenti amministratori?**
R:

-   Questo modulo, nella sua versione attuale, fornisce un'unica interfaccia di gestione file con accesso completo. Il sistema di permessi nativo di PrestaShop per i moduli concede tipicamente accesso completo o nessun accesso alla configurazione del modulo. I permessi granulari a livello di cartella per diversi utenti del back office non sono una funzionalità integrata di questo modulo specifico. Avresti bisogno di uno sviluppo personalizzato per implementare tale funzionalità.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Media / Files Manager" (`fmpro`) è costruito attorno al popolare file manager open-source **elFinder**. Integra elFinder direttamente nel back office di PrestaShop, principalmente tramite il metodo `getContent()` del modulo. Ciò significa che la logica di gestione dei file e l'interfaccia utente sono gestite dal robusto backend JavaScript e PHP di elFinder, con il modulo PrestaShop che funge da wrapper e punto di ingresso.

Il modulo stesso è un modulo PrestaShop standard, che estende `Module`. Non introduce tabelle di database personalizzate (oltre a `ps_configuration` per le proprie impostazioni interne) o complesse strutture `ObjectModel`. La sua funzione principale è quella di istanziare e configurare la libreria elFinder all'interno del contesto di amministrazione di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati nel senso tradizionale di PrestaShop (cioè, file in `controllers/front/` o `controllers/admin/`).
La libreria elFinder stessa ha il proprio connettore backend (tipicamente uno script PHP) che gestisce le operazioni sui file. Questo connettore è probabilmente integrato o chiamato direttamente dal file principale del modulo `fmpro.php` o da uno script PHP separato all'interno della directory `fmpro/php/`, agendo come gestore lato server per le richieste AJAX di elFinder.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi o modelli personalizzati all'interno di una directory `classes/`. La logica principale per la gestione dei file è gestita dalla libreria elFinder integrata.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo si basa fortemente su JavaScript per la sua interfaccia front-end, principalmente la libreria elFinder. Tutti i file JS si trovano in `fmpro/js/`.

-   `fmpro/js/elfinder.full.js`: Questo è il file principale della libreria elFinder, contenente tutte le funzionalità core per l'interfaccia utente del gestore file, le interazioni e la comunicazione AJAX con il backend. È uno script completo che alimenta l'intera interfaccia.
-   `fmpro/js/extras/editors.default.js`: Fornisce la funzionalità di editor di testo predefinita all'interno di elFinder, consentendo agli utenti di modificare direttamente i file basati su testo.
-   `fmpro/js/extras/quicklook.googledocs.js`: Migliora la funzione "quick look" integrandosi con Google Docs per l'anteprima di alcuni tipi di documenti.
-   `fmpro/js/i18n/elfinder.*.js`: Una vasta collezione di file di internazionalizzazione (i18n), che forniscono traduzioni per l'interfaccia elFinder in varie lingue (es. `elfinder.fr.js` per il francese, `elfinder.es.js` per lo spagnolo). Questi vengono caricati in base all'impostazione della lingua dell'utente.
-   `fmpro/js/i18n/help/*.html.js`: Contiene contenuti di aiuto localizzati per l'interfaccia elFinder, incorporati come stringhe JavaScript.
-   `fmpro/js/proxy/elFinderSupportVer1.js`: Probabilmente un livello di compatibilità o uno script proxy per versioni più vecchie di elFinder o configurazioni server specifiche.
-   `fmpro/js/worker/calcfilehash.js`: Uno script web worker per il calcolo degli hash dei file, potenzialmente utilizzato per controlli di integrità o caching.
-   `fmpro/js/worker/quicklook.tiff.js`: Uno script web worker specifico per la gestione delle anteprime di immagini TIFF.
-   `fmpro/js/worker/quicklook.unzip.js`: Uno script web worker per la gestione delle anteprime o dell'elenco dei contenuti dei file ZIP.

**Note per gli sviluppatori:**

-   La libreria elFinder è autonoma. Gli sviluppatori che estendono il modulo interagirebbero principalmente con l'API di elFinder se avessero bisogno di personalizzare il suo comportamento o integrarlo con altri componenti.
-   Per lo stile, il CSS personalizzato è generalmente preferito rispetto alla modifica di questi file JS core.
-   Per la localizzazione, assicurarsi che il file `elfinder.LANG.js` corretto sia caricato in base alla lingua del back office di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include file CSS per stilizzare l'interfaccia elFinder. Questi si trovano in `fmpro/css/`.

-   `fmpro/css/elfinder.full.css`: Questo è il foglio di stile principale per l'interfaccia elFinder, che definisce il layout, le icone, i colori e l'aspetto visivo generale del gestore file.
-   `fmpro/css/theme.css`: Questo file contiene probabilmente stili aggiuntivi o override per integrare elFinder più facilmente con il tema del back office di PrestaShop, o per fornire specifiche regolazioni del tema per elFinder stesso.

**Note per gli sviluppatori:**

-   Per personalizzare l'aspetto del gestore file, gli sviluppatori dovrebbero creare il proprio file CSS e caricarlo *dopo* `elfinder.full.css` e `theme.css` per sovrascrivere stili specifici.
-   I selettori di classe CSS chiave sono tipicamente prefissati con `elfinder-` (es. `.elfinder-navbar`, `.elfinder-cwd-wrapper`).

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non elenca esplicitamente alcun file `.tpl` in una directory `views/templates/` nell'inventario fornito. Ciò suggerisce che l'interfaccia elFinder viene renderizzata direttamente tramite JavaScript e HTML generato all'interno del metodo `getContent()` del file principale `fmpro.php`, o che il meccanismo di templating di elFinder viene utilizzato internamente, senza esporre i file `.tpl` nella struttura `views/templates/` del modulo.

Il metodo `getContent()` probabilmente produrrà il contenitore HTML necessario (`<div>`) dove il JavaScript di elFinder inizializzerà e renderizzerà il gestore file.

### 4.7 Schema del database e mappa degli hook

**Tabelle del database**:
Il modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione interne (come `mypresta_updates`, `update_`, `updatev_`) nella tabella standard `ps_configuration` di PrestaShop.

-   `ps_configuration`:
    -   `name`: `MYPRESTA_UPDATES_FMPRO` (o simile, per i controlli di aggiornamento)
    -   `name`: `UPDATE_FMPRO` (o simile, per i controlli di aggiornamento)
    -   `name`: `UPDATEV_FMPRO` (o simile, per i controlli di aggiornamento)

**Tabella degli hook registrati**:
La funzione principale del modulo è fornire uno strumento amministrativo, quindi non registra tipicamente molti hook front-office. La descrizione del modulo menziona "Front-Office Hooks: Header, Columns, Product, or Footer" ma questa è probabilmente un'affermazione generica per i moduli MyPresta.eu e non specifica per l'implementazione effettiva di questo modulo, in quanto è uno strumento di amministrazione.

Data la sua natura di strumento di amministrazione, il modulo interagirebbe principalmente con gli hook del back-office, se presenti, per aggiungere voci di menu o integrarsi in pagine di amministrazione esistenti. Tuttavia, le informazioni fornite non elencano esplicitamente alcun hook registrato. Il punto di integrazione più comune per un tale modulo è direttamente attraverso il suo metodo `getContent()`, a cui si accede cliccando su "Configura" nel Gestore moduli.

Se dovesse registrare degli hook, quelli comuni per gli strumenti di amministrazione potrebbero includere:

-   `displayBackOfficeHeader`: Per includere le sue risorse CSS/JS nel back office.
-   `displayAdminProductsExtra`: (Meno probabile per un gestore file generale, ma possibile per caricamenti di file specifici relativi ai prodotti).
-   `actionAdminControllerSetMedia`: Per caricare le risorse per la sua pagina di configurazione.

Dato il design del modulo, il suo punto di ingresso principale è la sua pagina di configurazione, dove viene inizializzata l'istanza di elFinder.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Media / Files Manager", si prega di fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo e all'integrazione con il tuo negozio PrestaShop.
