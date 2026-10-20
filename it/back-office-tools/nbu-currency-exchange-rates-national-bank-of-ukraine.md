---
title: "Tassi di cambio NBU - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tassi di cambio NBU di MyPresta.eu."
sidebar:
  label: "Tassi di cambio NBU"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo NBU Currency Exchange & Rates (National Bank of Ukraine) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbu-currency-exchange-rates-national-bank-of-ukraine.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/nbu-currency-exchange-rates-national-bank-of-ukraine/)
>
> ---


# Tassi di cambio NBU

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL) per il recupero dei dati da API esterne. La maggior parte degli ambienti di hosting moderni soddisfa questi requisiti per impostazione predefinita.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Qui definirai come i tassi NBU vengono applicati al tuo negozio.

**Nome schermata:** Configurazione Tassi di cambio NBU

**Impostazioni e Opzioni:**

1.  **URL CRON Job:**
    -   **Cosa fa questa impostazione:** Visualizza l'URL univoco che lo scheduler CRON del tuo server deve chiamare periodicamente. Quando si accede a questo URL, il modulo recupera automaticamente gli ultimi tassi di cambio NBU e li aggiorna nel tuo negozio PrestaShop.
    -   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. È generato dal modulo. Se non imposti un CRON job per chiamare questo URL, i tassi di cambio non si aggiorneranno automaticamente e dovrai attivare gli aggiornamenti manualmente (se tale opzione esiste, cosa che non è prevista per la funzione principale di questo modulo).
    -   **Valore consigliato:** Copia questo URL e impostalo nello scheduler CRON job del tuo pannello di controllo hosting.
    -   **Scenario / esempio per il commerciante:** Copi `https://yourstore.com/module/nburates/cronjob?token=YOUR_SECURE_TOKEN` e lo aggiungi ai tuoi CRON job di cPanel o Plesk per eseguirlo una volta al giorno (ad esempio, alle 3 del mattino). Questo garantisce che i tuoi prezzi in UAH siano sempre aggiornati prima che i tuoi clienti inizino a fare acquisti.

2.  **Frequenza CRON Job:**
    -   **Cosa fa questa impostazione:** Questa è una raccomandazione su quanto spesso dovresti eseguire il CRON job. La NBU di solito aggiorna i tassi una volta al giorno.
    -   **Effetto della modifica di questa impostazione:** Questo è puramente informativo. La modifica della frequenza effettiva del tuo CRON job (nel tuo pannello di hosting) influirà sulla frequenza di aggiornamento dei tassi. Eseguirlo troppo frequentemente (ad esempio, ogni minuto) è inutile e può consumare risorse del server senza beneficio, poiché i tassi NBU non cambiano così spesso. Eseguirlo troppo infrequentemente (ad esempio, una volta alla settimana) significa che i tuoi tassi potrebbero essere obsoleti.
    -   **Valore consigliato:** Una volta al giorno.
    -   **Scenario / esempio per il commerciante:** Imposti il CRON job del tuo server per l'esecuzione `0 3 * * *` (ogni giorno alle 3 del mattino) per corrispondere agli aggiornamenti giornalieri della NBU.

3.  **Valuta da aggiornare (UAH):**
    -   **Cosa fa questa impostazione:** Questo campo ti consente di specificare l'ID della valuta Grivna Ucraina (UAH) nel tuo negozio PrestaShop. Il modulo ha bisogno di sapere quale valuta targetizzare per gli aggiornamenti.
    -   **Effetto della modifica di questa impostazione:** Se l'ID è errato o lasciato vuoto, il modulo non sarà in grado di trovare e aggiornare la valuta UAH, e i tuoi prezzi non rifletteranno i tassi NBU.
    -   **Valore consigliato:** L'ID della tua valuta UAH. Puoi trovarlo navigando su **Internazionale > Valute** nel tuo Back Office PrestaShop, modificando la valuta UAH e guardando l'URL (ad esempio, `id_currency=3` significa che l'ID è 3).
    -   **Scenario / esempio per il commerciante:** La tua valuta UAH ha un ID `3`. Inserisci `3` in questo campo. Ora, quando il CRON job viene eseguito, il modulo sa di dover aggiornare il tasso di cambio per la valuta con ID `3`.

4.  **Margine (%):**
    -   **Cosa fa questa impostazione:** Questo ti consente di aggiungere un margine percentuale (markup o markdown) ai tassi di cambio NBU recuperati. Un valore positivo aumenta il tasso (rendendo i prezzi in UAH più alti), e un valore negativo lo diminuisce (rendendo i prezzi in UAH più bassi).
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato a 0:* Il modulo utilizza il tasso NBU esatto.
        -   *Se impostato a 2:* Il tasso di cambio UAH sarà del 2% più alto del tasso ufficiale NBU. Ad esempio, se NBU dice 1 EUR = 40 UAH, con un margine del 2%, il tuo negozio userà 1 EUR = 40.8 UAH. Questo può aiutare a coprire le commissioni di transazione o fornire un leggero margine di profitto.
        -   *Se impostato a -1:* Il tasso di cambio UAH sarà dell'1% più basso del tasso ufficiale NBU. Questo potrebbe essere utilizzato per prezzi promozionali o per offrire un leggero sconto.
    -   **Valore consigliato:** Dipende dalla tua strategia aziendale. `0` per tassi NBU esatti, o una piccola percentuale positiva (ad esempio, `1` o `2`) per coprire i costi.
    -   **Scenario / esempio per il commerciante:** Vuoi compensare leggermente le commissioni del gateway di pagamento per le transazioni in UAH. Imposti il margine a `1.5`. Ora, tutti i prezzi in UAH saranno calcolati utilizzando il tasso NBU più un ulteriore 1.5%.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Configurazione modulo | URL CRON Job | N/A (Generato) | L'URL per attivare gli aggiornamenti giornalieri dei tassi. Deve essere impostato nel CRON dell'hosting. |
| Configurazione modulo | Frequenza CRON Job | Una volta al giorno | Raccomandazione informativa per la pianificazione del CRON job. |
| Configurazione modulo | Valuta da aggiornare (UAH) | ID della valuta UAH | Specifica quale valuta in PrestaShop deve essere aggiornata con i tassi NBU. Critico per la funzione del modulo. |
| Configurazione modulo | Margine (%) | 0 | Aggiunge un markup/markdown percentuale al tasso NBU per flessibilità di prezzo. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei prezzi in UAH non si aggiornano. Cosa devo fare?**
R1:
*   **Controlla il CRON Job:** La ragione più comune è un CRON job configurato in modo errato o mancante. Verifica che l'URL del CRON job dalla configurazione del modulo sia correttamente aggiunto al tuo pannello di hosting e sia programmato per l'esecuzione.
*   **Controlla l'ID della valuta UAH:** Assicurati che l'impostazione "Valuta da aggiornare (UAH)" nella configurazione del modulo corrisponda all'ID esatto della tua valuta UAH in PrestaShop (**Internazionale > Valute**).
*   **Controlla la disponibilità della NBU:** Occasionalmente, l'API della NBU potrebbe essere temporaneamente non disponibile. Attendi qualche ora e controlla di nuovo. Il modulo è progettato per utilizzare l'ultimo tasso noto se l'API è inattiva.
*   **Log del server:** Controlla i log del CRON job del tuo server (se disponibili) per eventuali errori quando viene chiamato l'URL del CRON.

**D2: Il modulo è installato, ma non vedo modifiche visive nel mio negozio.**
R2: Questo modulo funziona in background per aggiornare i tassi di cambio. Non aggiunge nuovi blocchi o elementi visivi al tuo negozio. Il suo effetto si vede nel calcolo accurato dei prezzi dei prodotti quando UAH è la valuta selezionata.

**D3: Posso aggiornare manualmente i tassi se il CRON job fallisce?**
R3: Il meccanismo principale del modulo è il CRON job. Sebbene tu possa aggiornare manualmente i tassi di cambio in PrestaShop (**Internazionale > Valute**), farlo sovrascriverebbe i tassi NBU. La migliore pratica è assicurarsi che il tuo CRON job funzioni correttamente. Se hai bisogno di un aggiornamento immediato, puoi attivare manualmente l'URL del CRON una volta visitandolo nel tuo browser (anche se questa non è la soluzione a lungo termine prevista).

**D4: Cosa succede durante le festività bancarie quando la NBU non pubblica nuovi tassi?**
R4: Il modulo è progettato per gestire questo in modo intelligente. Se la NBU non pubblica nuovi tassi in un dato giorno (ad esempio, fine settimana o festività pubbliche), il modulo manterrà tipicamente l'ultimo tasso recuperato con successo. Ciò garantisce che i tuoi prezzi in UAH rimangano stabili e coerenti.

**D5: Come posso svuotare la cache di Smarty se apporto modifiche e non le vedo?**
R5: Sebbene le modifiche di questo modulo siano principalmente basate sui dati (tassi di cambio) e meno sui modelli visivi, la pulizia della cache può talvolta aiutare. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Imposta "Compilazione dei template" su "Ricompila i template se i file sono stati aggiornati" o "Forza compilazione" e clicca su "Svuota la cache". Ricorda di tornare a "Non ricompilare mai i file dei template" per le prestazioni in produzione dopo la risoluzione dei problemi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)
Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura
Il modulo `Tassi di cambio NBU` è un modulo PrestaShop leggero progettato per integrare i tassi di cambio esterni dall'API della Banca Nazionale dell'Ucraina (NBU). Segue un semplice modello simile a MVC all'interno della struttura del modulo PrestaShop. La logica principale risiede nel file principale del modulo (`cronjob.php`), che gestisce la configurazione, l'installazione e l'esecuzione del CRON job primario. Utilizza la classe `Configuration` di PrestaShop per memorizzare le impostazioni e l'ObjectModel `Currency` per aggiornare i tassi. La funzionalità principale del modulo è esposta tramite un front controller, specificamente progettato per essere chiamato da un CRON job lato server.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    *   `nburates/controllers/front/cronjob.php`
        *   **Nome classe:** `NburatesCronjobModuleFrontController` (estende `ModuleFrontController`)
        *   **Responsabilità:** Questo è l'endpoint critico per il CRON job. Quando viene acceduto, esegue le seguenti azioni:
            1.  Convalida un token sicuro (`token`) passato nell'URL per prevenire accessi non autorizzati.
            2.  Recupera le impostazioni di configurazione del modulo (ID valuta UAH, margine).
            3.  Recupera gli ultimi tassi di cambio NBU dall'API ufficiale NBU (probabilmente `https://bank.gov.ua/NBUStatService/v1/statdirectory/exchangenew?json`).
            4.  Analizza la risposta JSON per estrarre i tassi di cambio rilevanti.
            5.  Applica il margine configurato ai tassi recuperati.
            6.  Aggiorna il tasso di cambio per la valuta UAH specificata nella tabella `ps_currency` utilizzando l'ObjectModel `Currency` di PrestaShop.
            7.  Gestisce le condizioni di errore (ad esempio, API irraggiungibile, risposta non valida) registrando o ripiegando sui tassi precedenti.
            8.  Restituisce un semplice messaggio di successo o di errore, adatto per la registrazione del CRON job.
    *   `nburates/controllers/front/index.php`
        *   **Nome classe:** `NburatesIndexModuleFrontController` (estende `ModuleFrontController`)
        *   **Responsabilità:** Questo è un front controller `index.php` standard vuoto, spesso incluso nei moduli per prevenire l'elenco delle directory o per fungere da segnaposto. Tipicamente non contiene logica specifica per la funzione principale di questo modulo.

-   **Controller Admin Back-Office**:
    *   Nessuno. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)
-   Nessuno. Il modulo interagisce direttamente con l'ObjectModel `Currency` e la classe `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)
-   Nessuno. Il modulo non utilizza alcun JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)
-   Nessuno. Il modulo non utilizza alcun CSS personalizzato. La pagina di configurazione dell'amministratore si basa sullo stile predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    *   `nburates/views/admin.tpl`
        *   **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop.
        *   **Contenuto:** Visualizza l'URL del CRON job, la raccomandazione sulla frequenza del CRON, i campi di input per l'ID della valuta UAH e la percentuale di margine. Tipicamente utilizza gli helper di modulo e lo stile standard di PrestaShop.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non crea tabelle di database personalizzate.
    *   Interagisce con la tabella `ps_configuration` per memorizzare le sue impostazioni (ad esempio, `NBU_RATES_UAH_CURRENCY_ID`, `NBU_RATES_MARGIN`, `NBU_RATES_SECURE_TOKEN`).
    *   Aggiorna la tabella `ps_currency`, in particolare la colonna `conversion_rate` per la valuta UAH.

-   **Tabella degli hook registrati**:
    Il modulo non registra alcun hook di visualizzazione tradizionale (`displayHeader`, `displayFooter`, ecc.) che renderizzano contenuto nel front office. Il suo "hook" principale è l'azione che esegue quando il suo front controller viene chiamato dal CRON job.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `actionModuleInstall` | Durante l'installazione del modulo | Crea voci di configurazione, genera token sicuro. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce le voci di configurazione. |
| (Implicito) `ModuleFrontController::initContent()` per `NburatesCronjobModuleFrontController` | Quando si accede all'URL del CRON | Recupera i tassi NBU, applica il margine, aggiorna il tasso di cambio UAH. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, correzioni di bug e supporto per sviluppatori per il modulo "Tassi di cambio NBU", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e a garantire la compatibilità del modulo con le ultime versioni di PrestaShop.
