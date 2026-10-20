---
title: "Banca d'Italia - tassi di cambio valuta - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Banca d'Italia - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Banca d'Italia - tassi di cambio valuta - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank of Italy (Banca dItalia) - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Banca d'Italia - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione API esterna, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca sul pulsante "Configura" accanto al nome del modulo in Gestione moduli. Questo ti porterà alla schermata di configurazione principale per il modulo "Banca d'Italia - tassi di cambio valuta".

#### Impostazioni generali

- **Cosa fa questa impostazione:** Questa sezione ti permette di controllare come il modulo aggiorna i tuoi tassi di cambio valuta e di gestire la sua funzionalità principale.
- **Effetto della modifica di questa impostazione:** Queste impostazioni influenzano direttamente l'accuratezza e la frequenza dei tassi di cambio del tuo negozio.

#### Impostazioni e opzioni specifiche:

1.  **Pulsante "Aggiorna tassi"**

    - **Cosa fa questa impostazione:** Questo è un trigger manuale per recuperare immediatamente gli ultimi tassi di cambio dalla Banca d'Italia e applicarli alle valute del tuo negozio.
    - **Effetto della modifica di questa impostazione:**
      - *Quando cliccato:* Il modulo si connetterà alla fonte dati della Banca d'Italia, recupererà i tassi di riferimento Euro più recenti e aggiornerà tutte le valute attive nel tuo negozio PrestaShop (eccetto la tua valuta predefinita, che di solito è EUR). Questo è utile per testare o per un aggiornamento immediato al di fuori dei tuoi cron job programmati.
    - **Valore consigliato:** Clicca su questo pulsante dopo la configurazione iniziale per assicurarti che i tuoi tassi siano aggiornati. Usalo manualmente ogni volta che hai bisogno di un aggiornamento immediato.
    - **Scenario / esempio per il commerciante:** Hai appena aggiunto una nuova valuta al tuo negozio, o c'è stata una significativa fluttuazione del mercato, e vuoi assicurarti che i tuoi prezzi siano immediatamente aggiornati prima di una grande vendita.
2.  **Campo "URL CRON per aggiornamenti automatici"**

    - **Cosa fa questa impostazione:** Questo campo visualizza un URL unico che puoi utilizzare con il servizio "cron job" del tuo provider di hosting. Un cron job è un'attività programmata che viene eseguita automaticamente a intervalli specificati (ad esempio, una volta al giorno, ogni ora).
    - **Effetto della modifica di questa impostazione:**
      - *Quando configurato con il tuo provider di hosting:* I tassi di cambio del tuo negozio verranno aggiornati automaticamente alla frequenza che definisci nelle impostazioni del tuo cron job, senza che tu debba cliccare manualmente alcun pulsante. Questo assicura che i tuoi tassi siano sempre freschi.
      - *Quando non configurato:* Dovrai cliccare manualmente sul pulsante "Aggiorna tassi" per aggiornare i tuoi tassi di cambio.
    - **Valore consigliato:** Copia questo URL e imposta un cron job sul tuo server per eseguirlo almeno una volta ogni 24 ore. Un aggiornamento giornaliero è solitamente sufficiente per la maggior parte dei negozi e-commerce.
    - **Scenario / esempio per il commerciante:** Vuoi che i tassi di cambio del tuo negozio vengano aggiornati ogni mattina alle 3 del mattino, assicurando che tutti i prezzi siano aggiornati per l'inizio della giornata lavorativa, senza che tu debba ricordarti di farlo.
3.  **Campo "Aggiungi margine ai tassi di cambio (%)"**

    - **Cosa fa questa impostazione:** Questo ti permette di aggiungere un margine percentuale ai tassi di cambio recuperati. Ad esempio, se il tasso ufficiale è 1 EUR = 1.10 USD, e imposti un margine del 2%, il modulo utilizzerà 1 EUR = 1.078 USD (1.10 \* 0.98) o 1 EUR = 1.122 USD (1.10 \* 1.02) a seconda della direzione di conversione. Questo aiuta a coprire potenziali commissioni di transazione, costi di conversione valuta, o semplicemente a darti un leggero cuscinetto.
    - **Effetto della modifica di questa impostazione:**
      - *Quando impostato su un valore positivo (ad esempio, 2):* Il modulo regolerà i tassi di cambio recuperati di quella percentuale. Questo di solito significa che otterrai leggermente più valuta locale per i tuoi prodotti basati sull'Euro, o leggermente meno Euro per i prodotti in valuta locale, aiutando a proteggere i tuoi margini di profitto.
      - *Quando impostato su 0 (o vuoto):* Il modulo utilizzerà i tassi di cambio esatti forniti dalla Banca d'Italia senza alcuna regolazione.
    - **Valore consigliato:** Inizia con 0. Se riscontri problemi di redditività a causa delle fluttuazioni valutarie o delle commissioni di transazione, considera l'aggiunta di un piccolo margine (ad esempio, 1-3%).
    - **Scenario / esempio per il commerciante:** Il tuo gateway di pagamento addebita una commissione dell'1,5% per le transazioni internazionali. Impostando un margine del 2%, puoi assorbire questo costo e assicurarti che la tua redditività non venga erosa dalle conversioni di valuta.
4.  **Interruttore "Verifica aggiornamenti modulo"**

    - **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo verifica periodicamente su MyPresta.eu la presenza di versioni più recenti del modulo.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Il modulo si connetterà occasionalmente a MyPresta.eu per vedere se è disponibile una versione più recente. Se viene trovato un aggiornamento, vedrai una notifica nel tuo back office di PrestaShop, che ti inviterà a scaricare e installare l'ultima versione. Questo ti aiuta a rimanere aggiornato con correzioni di bug, nuove funzionalità e aggiornamenti di compatibilità.
      - *Quando disabilitato (NO):* Il modulo non cercherà aggiornamenti e non sarai avvisato di nuove versioni. Dovrai controllare manualmente il tuo account MyPresta.eu per gli aggiornamenti.
    - **Valore consigliato:** **SÌ**. Mantenere i tuoi moduli aggiornati è fondamentale per la sicurezza, le prestazioni e la compatibilità con le future versioni di PrestaShop.
    - **Scenario / esempio per il commerciante:** Vuoi essere informato automaticamente quando viene rilasciata una nuova versione del modulo, in modo da poter beneficiare degli ultimi miglioramenti e garantire che il tuo negozio rimanga sicuro e funzionale.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Pulsante "Aggiorna tassi" | Clicca dopo la configurazione / manualmente se necessario | Recupera e applica immediatamente gli ultimi tassi di cambio dalla Banca d'Italia. |
| Pagina di configurazione del modulo | "URL CRON per aggiornamenti automatici" | Copia e configura sull'hosting | Automatizza gli aggiornamenti giornalieri/orari dei tassi di cambio, garantendo una precisione costante. |
| Pagina di configurazione del modulo | "Aggiungi margine ai tassi di cambio (%)" | 0 (o 1-3% se necessario) | Aggiunge un buffer percentuale ai tassi di cambio per coprire commissioni o proteggere i margini di profitto. |
| Pagina di configurazione del modulo | "Verifica aggiornamenti modulo" | SÌ | Ti avvisa delle nuove versioni del modulo per correzioni di bug, funzionalità e compatibilità. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo fare?**
R1: Questo è quasi sempre correlato alla configurazione del cron job.
- **Controlla il tuo hosting:** Accedi al pannello di controllo del tuo hosting (cPanel, Plesk, ecc.) e verifica che il cron job per l'URL del modulo sia configurato correttamente e in esecuzione agli intervalli specificati. Assicurati che l'URL copiato dalla configurazione del modulo sia esatto.
- **Testa l'URL manualmente:** Copia l'"URL CRON per aggiornamenti automatici" dalla configurazione del modulo e incollalo direttamente nel tuo browser web. Se viene eseguito con successo, dovresti vedere un semplice messaggio "OK" o simile. Se vedi un errore, potrebbe esserci un problema lato server o un problema con l'URL stesso.
- **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato nel tuo back office di PrestaShop.

**D2: Ho cliccato su "Aggiorna tassi" ma i miei prezzi in altre valute non sono cambiati.**
R2:
- **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** nel tuo back office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). PrestaShop spesso memorizza nella cache le conversioni di valuta.
- **Verifica le valute attive:** Assicurati che le valute che ti aspetti vengano aggiornate siano effettivamente abilitate in **Internazionale > Valute**. Il modulo aggiorna solo le valute attive.
- **Controlla la valuta predefinita:** Il modulo aggiorna le *altre* valute rispetto alla tua valuta predefinita (solitamente EUR). Se la tua valuta predefinita non è EUR, il modulo recupererà comunque i tassi EUR e convertirà da lì. Assicurati che la tua valuta predefinita sia impostata correttamente.

**D3: Posso impostare margini diversi per valute diverse?**
R3: No, l'impostazione "Aggiungi margine ai tassi di cambio (%)" applica un unico margine percentuale uniforme a *tutti* i tassi di cambio recuperati dal modulo. Se hai bisogno di margini altamente specifici per valuta, avresti bisogno di una soluzione di sviluppo personalizzata o di un modulo di gestione valuta più avanzato.

**D4: Il modulo dice che recupera i tassi dalla Banca d'Italia. È affidabile?**
R4: Sì, la Banca d'Italia è una banca centrale all'interno del Sistema Europeo di Banche Centrali (SEBC) e fornisce tassi di riferimento ufficiali dell'Euro. Questi tassi sono altamente affidabili e ampiamente utilizzati per le transazioni finanziarie in tutta Europa.

**D5: Dopo aver aggiornato il modulo, il mio negozio appare un po' strano o vedo errori.**
R5:
- **Svuota cache:** Svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni**) dopo qualsiasi aggiornamento del modulo.
- **Cache del browser:** Svuota la cache e i cookie del tuo browser web, oppure prova ad accedere al tuo negozio in modalità incognito/privata.
- **Ripristina (se necessario):** Se il problema persiste, potrebbe essere necessario disabilitare o disinstallare temporaneamente il modulo e ripristinare un backup precedente del tuo negozio. Quindi, contatta il supporto MyPresta.eu con i dettagli del problema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Banca d'Italia - tassi di cambio valuta" (`birates`) è un modulo PrestaShop leggero progettato per automatizzare gli aggiornamenti dei tassi di valuta. Segue un modello MVC standard di PrestaShop ove applicabile, concentrandosi principalmente su una singola interfaccia di configurazione e un front controller per l'esecuzione del cron job. Sfrutta l'`ObjectModel` `Currency` di PrestaShop per aggiornare i tassi di cambio. La logica principale risiede nel file del modulo principale, gestendo l'installazione, la disinstallazione, la configurazione e il processo di recupero dei tassi.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre**: `BiratesCronjobModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è progettato per essere chiamato da un cron job esterno. Il suo metodo `initContent()` (o logica simile all'interno di `postProcess()`) attiva il metodo `updateRates()` del modulo principale `birates`. Non renderizza alcun contenuto visivo all'utente; il suo scopo è puramente quello di eseguire la logica di aggiornamento dei tassi in background. Tipicamente restituisce un semplice messaggio di successo o uno stato.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `BiratesIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller frontale segnaposto o di fallback. In molti moduli, i controller `index.php` vengono utilizzati per definire una rotta predefinita o gestire i casi in cui non viene fornita un'azione specifica. Per questo modulo, probabilmente serve come punto di ingresso di base, ma la funzionalità principale per gli aggiornamenti dei tassi è gestita da `cronjob.php`. Potrebbe reindirizzare o semplicemente visualizzare una pagina minima.
-   **Controller Admin Back-Office**:

    -   Nessun controller admin dedicato è presente in questo modulo. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale `birates.php`.

### 4.3 Classi e modelli principali (`classes/`)

Nessuna classe personalizzata o definizione di `ObjectModel` è presente nella directory `classes/`. Il modulo interagisce direttamente con l'`ObjectModel` `Currency` di PrestaShop per aggiornare i tassi di cambio delle valute esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è presente nel modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è presente nel modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:

    -   `birates/views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` del file del modulo principale `birates.php`. Visualizza l'intero modulo di configurazione per il modulo nel back office di PrestaShop.
        -   **Contenuto**: Include il pulsante "Aggiorna tassi", il campo URL CRON, l'input "Aggiungi margine ai tassi di cambio (%)" e l'interruttore "Verifica aggiornamenti modulo". Utilizza gli helper e lo stile standard dei moduli di PrestaShop.
-   **Template Hook (`views/templates/hook/`)**: Nessuno.
-   **Template Front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione (ad esempio, `mypresta_updates`, `update_`, `updatev_`, `currency_`) nella tabella `ps_configuration` (o `_configuration` a seconda del prefisso della tua tabella). Queste chiavi sono tipicamente prefissate con il nome del modulo o un identificatore unico.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Non utilizzato direttamente per l'output visivo, ma potrebbe essere utilizzato per caricare risorse (anche se nessuna è presente). |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Non utilizzato per l'output visivo. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | Non utilizzato per l'output visivo. |
| `displayFooter` | Nella parte inferiore di ogni pagina del front-office. | Non utilizzato per l'output visivo. |
| `displayProductExtraContent` | Sulla pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Non utilizzato per l'output visivo. |
| `actionUpdateCurrency` | Dopo che una valuta è stata aggiornata. | Il modulo stesso *attiva* gli aggiornamenti delle valute, ma non si aggancia esplicitamente a questo per la propria logica. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Utilizzato per impostare i valori di configurazione predefiniti e registrare gli hook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Utilizzato per pulire i valori di configurazione e deregistrare gli hook. |

*Nota: La funzione principale del modulo (aggiornamento dei tassi) è avviata dal suo front controller `cronjob.php`, che viene chiamato esternamente, piuttosto che tramite un hook standard di PrestaShop.*

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti e per scaricare l'ultima versione del modulo "Banca d'Italia - tassi di cambio valuta", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
