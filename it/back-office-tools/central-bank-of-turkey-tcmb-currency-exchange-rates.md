---
title: "Banca Centrale di Turchia (TCMB) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Banca Centrale di Turchia (TCMB) - tassi di cambio valuta' di MyPresta.eu."
sidebar:
  label: "Banca Centrale di Turchia (TCMB) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Central Bank of Turkey (TCMB) - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Banca Centrale di Turchia (TCMB) - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Il tuo ambiente di hosting dovrebbe consentire connessioni in uscita al sito web della TCMB.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### Impostazioni Generali

-   **Abilita modulo**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a recuperare i tassi di cambio e ad aggiornare i prezzi delle valute del tuo negozio in base alle altre impostazioni.
        -   *Quando disabilitato:* Il modulo cesserà tutte le operazioni. I tassi di cambio non verranno aggiornati automaticamente e i tuoi prezzi rimarranno statici fino a quando non verranno modificati manualmente o il modulo non verrà riabilitato.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta, abilitalo per iniziare a utilizzare le sue funzionalità. Se hai bisogno di interrompere temporaneamente gli aggiornamenti automatici (ad esempio, per manutenzione), puoi disabilitarlo.
-   **URL CRON**

    -   **Cosa fa questa impostazione:** Questo campo visualizza un URL unico che, quando viene acceduto, attiva il modulo per recuperare gli ultimi tassi di cambio dalla TCMB e aggiornare i prezzi delle valute del tuo negozio.
    -   **Effetto della modifica di questa impostazione:** Questo è un campo di sola lettura. Copiare e impostare questo URL nello scheduler CRON job del tuo pannello di hosting automatizzerà gli aggiornamenti dei tassi.
    -   **Valore consigliato:** Copia questo URL.
    -   **Scenario / esempio del commerciante:** Copierai questo URL e lo incollerai nel tuo pannello di controllo dell'hosting (ad esempio, cPanel, Plesk o un'interfaccia CRON job personalizzata) per pianificare aggiornamenti automatici. Ad esempio, potresti impostarlo per essere eseguito una volta ogni 24 ore per garantire l'accuratezza giornaliera dei prezzi.
-   **Margine (%)**

    -   **Cosa fa questa impostazione:** Ti consente di aggiungere un margine percentuale sui tassi di cambio ufficiali recuperati dalla TCMB. Questo può essere utilizzato per coprire commissioni di transazione, costi di conversione valuta o semplicemente per aggiustare la tua strategia di prezzo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 0:* Il tuo negozio utilizzerà i tassi di cambio ufficiali esatti forniti dalla TCMB.
        -   *Quando impostato su un valore positivo (es. 2):* Il modulo aumenterà il tasso di cambio calcolato di quella percentuale. Ad esempio, se il tasso ufficiale è 1 USD = 30 TRY e imposti un margine del 2%, il modulo utilizzerà 1 USD = 30.6 TRY per le conversioni. Ciò significa che i prodotti prezzati in USD appariranno leggermente più costosi in TRY, o viceversa, a seconda della tua valuta base.
    -   **Valore consigliato:** 0 (se desideri tassi ufficiali esatti) o una piccola percentuale positiva (es. 1-3%) per coprire i costi.
    -   **Scenario / esempio del commerciante:** Se il tuo gateway di pagamento addebita una commissione dell'1,5% per le conversioni di valuta, potresti impostare un "Margine (%)" dell'1,5 per assorbire questo costo e mantenere i tuoi margini di profitto.
-   **Ultimo aggiornamento**

    -   **Cosa fa questa impostazione:** Questo campo di sola lettura mostra la data e l'ora in cui il modulo ha recuperato e applicato con successo gli ultimi aggiornamenti dei tassi di cambio.
    -   **Effetto della modifica di questa impostazione:** Questo campo si aggiorna automaticamente dopo ogni esecuzione riuscita del CRON job o aggiornamento manuale. Ti aiuta a verificare che il modulo funzioni correttamente e quando i tassi sono stati aggiornati l'ultima volta.
    -   **Valore consigliato:** Monitora questo valore per assicurarti aggiornamenti regolari.
    -   **Scenario / esempio del commerciante:** Dopo aver impostato il tuo CRON job, puoi controllare questo campo per confermare che gli aggiornamenti automatici stiano funzionando come previsto. Se la data è vecchia, indica un problema con la configurazione del tuo CRON job.

#### Aggiornamento Manuale

-   Pulsante **Aggiorna ora**
    -   **Cosa fa questa impostazione:** Questo pulsante ti consente di attivare manualmente il processo di aggiornamento dei tassi di cambio immediatamente, senza attendere il CRON job.
    -   **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante verranno recuperati istantaneamente gli ultimi tassi dalla TCMB e verranno aggiornati i prezzi delle valute del tuo negozio. Questo è utile per test o per aggiornamenti urgenti.
    -   **Valore consigliato:** Clicca quando hai bisogno di un aggiornamento immediato o per test.
    -   **Scenario / esempio del commerciante:** Hai appena lanciato un nuovo prodotto e vuoi assicurarti che il suo prezzo sia basato sugli ultimissimi tassi di cambio prima che i clienti inizino a ordinare. Puoi cliccare su "Aggiorna ora" per aggiornare tutti i tassi istantaneamente.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita modulo | SÌ | Attiva/disattiva la funzionalità principale del modulo. |
| Configurazione Modulo | URL CRON | Copia questo URL | URL da impostare per gli aggiornamenti automatici dei tassi di cambio tramite il CRON job del tuo hosting. |
| Configurazione Modulo | Margine (%) | 0-3% | Aggiunge un margine percentuale sui tassi di cambio ufficiali della TCMB per flessibilità di prezzo. |
| Configurazione Modulo | Ultimo aggiornamento | Monitora | Visualizza la data/ora dell'ultimo aggiornamento riuscito dei tassi di cambio. |
| Configurazione Modulo | Pulsante Aggiorna ora | Clicca quando necessario | Attiva manualmente un aggiornamento immediato dei tassi di cambio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prezzi non si aggiornano, anche dopo aver configurato il modulo.**
R1: Innanzitutto, controlla se l'impostazione "Abilita modulo" è impostata su SÌ. In secondo luogo, verifica la configurazione del tuo CRON job nel pannello di hosting. Assicurati che l'URL CRON sia corretto e che il job sia pianificato per l'esecuzione. Puoi anche provare a cliccare sul pulsante "Aggiorna ora" nella configurazione del modulo per vedere se un aggiornamento manuale funziona. Se funziona, il problema è probabilmente con il tuo CRON job.

**D2: Il campo "Ultimo aggiornamento" mostra una data vecchia, ma il mio CRON job è configurato.**
R2: Questo di solito significa che il tuo CRON job non viene eseguito correttamente o che il modulo sta riscontrando un errore durante il tentativo di recuperare i dati.
-   **Controlla i log del CRON job:** Molti provider di hosting offrono log per le esecuzioni dei CRON job. Cerca eventuali errori lì.
-   **Accesso al server:** Assicurati che il tuo server abbia accesso a Internet in uscita a `www.tcmb.gov.tr` (il sito web della Banca Centrale di Turchia). Firewall o restrizioni di rete possono bloccarlo.
-   **Versione PHP:** Conferma che la tua versione PHP rientri nell'intervallo supportato (PHP 5.6 - 8.5).
-   **Reinstallazione del modulo:** Come ultima risorsa, prova a disinstallare e reinstallare il modulo (dopo aver eseguito il backup del tuo negozio) per assicurarti che tutti i file siano correttamente al loro posto.

**D3: Posso aggiornare i tassi più frequentemente di una volta al giorno?**
R3: Sì, puoi configurare il tuo CRON job per essere eseguito più frequentemente (ad esempio, ogni 6 ore, ogni ora). Tuttavia, considera l'impatto sulle risorse del tuo server e la frequenza effettiva dei cambiamenti dei tassi della TCMB. Gli aggiornamenti giornalieri sono solitamente sufficienti per la maggior parte dei negozi e-commerce, poiché i tassi ufficiali cambiano tipicamente una volta al giorno lavorativo.

**D4: Ho più valute. Questo modulo le aggiornerà tutte?**
R4: Sì, il modulo recupera i tassi di cambio ufficiali per la Lira Turca (TRY) rispetto ad altre valute principali. Utilizza quindi questi tassi per ricalcolare e aggiornare i prezzi per tutte le valute attive nel tuo negozio PrestaShop in base alla tua valuta base e ai tassi TRY recuperati.

**D5: Cosa succede se il sito web della TCMB è inattivo o irraggiungibile?**
R5: Se il modulo non riesce a connettersi al sito web della TCMB, in genere non riuscirà ad aggiornare i tassi. I tuoi tassi di cambio esistenti rimarranno invariati fino a quando non sarà possibile stabilire una connessione e un aggiornamento riusciti. Il campo "Ultimo aggiornamento" non cambierà, indicando un problema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `tcmbrates` è progettato come un modulo PrestaShop standard, sfruttando principalmente la classe `Module` per la sua funzionalità principale. Il suo scopo principale è recuperare dati esterni (tassi di cambio TCMB) e aggiornare i tassi di valuta interni di PrestaShop. Utilizza un controller frontale per l'esecuzione del CRON job, consentendogli di essere attivato esternamente senza interazione diretta con il Back Office. La configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, visualizzando un semplice modulo per le impostazioni e un trigger di aggiornamento manuale.

### 4.2 Controller (`controllers/`)

Il modulo include controller frontali per la gestione delle richieste esterne, in particolare per il CRON job.

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre:** `TcmbratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo controller è progettato per essere chiamato da uno scheduler CRON job esterno. Quando viene acceduto, attiva la logica principale del modulo per recuperare gli ultimi tassi di cambio dalla Banca Centrale di Turchia e aggiornare i tassi di valuta nel database di PrestaShop. In genere restituisce un messaggio di successo o fallimento.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre:** `TcmbratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è un segnaposto o un controller frontale predefinito, spesso incluso nei moduli ma non sempre utilizzato attivamente per funzionalità specifiche. Nel contesto di questo modulo, probabilmente serve come fallback o un semplice punto di ingresso se non viene richiesto nessun altro controller frontale specifico. La sua funzione principale è solitamente quella di reindirizzare o visualizzare un messaggio generico.
-   **Controller Amministrativi Back-Office**: Nessuno. Tutta l'amministrazione è gestita tramite il metodo `getContent()` del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce classi personalizzate che estendono `ObjectModel`. La sua logica principale risiede all'interno del file principale del modulo (`cronjob.php`).

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è incluso in questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è incluso in questo modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty per la sua interfaccia di configurazione del Back Office.

-   **Template amministrativi (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Scopo:** Questo template viene renderizzato dal metodo `getContent()` del file principale del modulo (`cronjob.php`). Visualizza il modulo di configurazione del modulo nel Back Office di PrestaShop, inclusi i campi per abilitare il modulo, impostare il margine, visualizzare l'URL CRON e fornire un pulsante di aggiornamento manuale.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione (ad esempio, `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) nella tabella standard `ps_configuration`. Interagisce direttamente con la tabella `ps_currency` di PrestaShop per aggiornare i tassi di cambio.
-   **Tabella degli hook registrati**: Il modulo non si registra esplicitamente a hook di visualizzazione standard come `displayHeader` o `displayFooter` per il contenuto del front-office. La sua interazione principale con il sistema PrestaShop avviene tramite la sua logica interna attivata dal CRON job o dall'aggiornamento manuale, che poi modifica i dati di valuta esistenti.

  | Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `install()` | Installazione del modulo | Crea voci di configurazione in `ps_configuration`. |
  | `uninstall()` | Disinstallazione del modulo | Elimina le voci di configurazione da `ps_configuration`. |
  | (Nessun hook di visualizzazione esplicito per il front-office) | N/A | Il modulo opera in background per aggiornare i dati, non per visualizzare contenuti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Banca Centrale di Turchia (TCMB) - tassi di cambio valuta", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
