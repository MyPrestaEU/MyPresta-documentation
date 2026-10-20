---
title: "Tassi di cambio e valuta NBRB (Banca Nazionale della Bielorussia) - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tassi di cambio e valuta NBRB (Banca Nazionale della Bielorussia) di MyPresta.eu."
sidebar:
  label: "Tassi di cambio e valuta NBRB (Banca Nazionale della Bielorussia) - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo NBRB Exchange Rates & Currency (National Bank of Belarus) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# Tassi di cambio e valuta NBRB (Banca Nazionale della Bielorussia)

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste e presenti sulla maggior parte degli ambienti di hosting moderni. L'accesso per impostare un CRON job è essenziale per gli aggiornamenti automatici.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Tassi di cambio e valuta NBRB" per accedere alle sue impostazioni.

#### **Abilita tassi di cambio NBRB**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo inizierà a recuperare e applicare i tassi di cambio NBRB per le conversioni di valuta BYN nel tuo negozio.
    -   *Quando disabilitato (NO):* Il modulo smetterà di recuperare i tassi e i tuoi tassi di valuta BYN torneranno a quelli impostati manualmente nella sezione "Valute" di PrestaShop o da un altro modulo di valuta attivo.
-   **Valore consigliato:** SÌ
-   **Scenario/esempio del commerciante:** Se vendi principalmente in Bielorussia, abilita questa opzione per assicurarti che tutti i prezzi BYN siano ufficiali. Se smetti temporaneamente di vendere in Bielorussia, potresti disabilitarla.

#### **URL del CRON Job**

-   **Cosa fa questa impostazione:** Visualizza l'URL univoco che devi impostare come CRON job sul tuo server. Quando si accede a questo URL, il modulo recupererà automaticamente gli ultimi tassi di cambio dalla NBRB.
-   **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione. Copia questo URL e incollalo nello scheduler del CRON job del tuo pannello di controllo dell'hosting.
-   **Valore consigliato:** Copia questo URL esattamente come mostrato.
-   **Scenario/esempio del commerciante:** Copieresti questo URL e imposteresti un CRON job per l'esecuzione, ad esempio, una volta ogni 24 ore (es. alle 3 del mattino ora locale) per assicurarti che i tuoi tassi siano sempre aggiornati. Consulta la documentazione o il supporto del tuo provider di hosting per l'impostazione dei CRON job.

#### **Regolazione del margine (%)**

-   **Cosa fa questa impostazione:** Ti consente di aggiungere un margine percentuale (markup o markdown) ai tassi di cambio NBRB recuperati. Questo è utile per coprire le commissioni di transazione, coprire piccole fluttuazioni o applicare un leggero sconto/premio.
-   **Effetto della modifica di questa impostazione:**
    -   *Inserendo un valore positivo (es. 2):* Il tasso di conversione BYN verrà aumentato del 2%, rendendo i prodotti leggermente più costosi in BYN.
    -   *Inserendo un valore negativo (es. -1):* Il tasso di conversione BYN verrà diminuito dell'1%, rendendo i prodotti leggermente più economici in BYN.
    -   *Lasciandolo a 0:* Verrà utilizzato il tasso ufficiale NBRB senza alcuna modifica.
-   **Valore consigliato:** 0 (a meno che tu non abbia una specifica ragione commerciale per regolare i tassi).
-   **Scenario/esempio del commerciante:** Se il tuo gateway di pagamento addebita una commissione dell'1,5% per le transazioni BYN, potresti impostare questo valore su "1.5" per assorbire quel costo nel tasso di cambio.

#### **Ultimo aggiornamento**

-   **Cosa fa questa impostazione:** Questo campo visualizza la data e l'ora dell'ultimo aggiornamento riuscito dei tassi di cambio da parte del modulo (manualmente o tramite CRON job).
-   **Effetto della modifica di questa impostazione:** Questo è un campo informativo di sola lettura. Ti aiuta a verificare che il tuo CRON job sia in esecuzione correttamente e che i tassi vengano aggiornati.
-   **Valore consigliato:** N/A (monitora questo per garantire aggiornamenti regolari).
-   **Scenario/esempio del commerciante:** Se noti che questa data è vecchia di diversi giorni, indica un problema con la configurazione del tuo CRON job e dovresti indagare.

#### **Pulsante Aggiorna tassi manualmente**

-   **Cosa fa questa impostazione:** Questo pulsante ti consente di attivare manualmente un aggiornamento immediato dei tassi di cambio dalla NBRB, al di fuori della pianificazione del CRON job.
-   **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante si recupereranno istantaneamente gli ultimi tassi e li si aggiornerà nel tuo negozio PrestaShop. Il campo "Ultimo aggiornamento" rifletterà la nuova ora.
-   **Valore consigliato:** Utilizzare secondo necessità per aggiornamenti immediati o test.
-   **Scenario/esempio del commerciante:** Se c'è un evento economico significativo e vuoi assicurarti che i tuoi tassi siano assolutamente attuali prima del tuo prossimo CRON job programmato, puoi cliccare su questo pulsante.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita tassi di cambio NBRB | SÌ | Attiva/disattiva il recupero e l'applicazione dei tassi del modulo. |
| Configurazione modulo | URL del CRON Job | N/A (copia e incolla) | URL per impostare gli aggiornamenti automatici dei tassi sul tuo server. |
| Configurazione modulo | Regolazione del margine (%) | 0 | Aggiunge un markup/markdown percentuale ai tassi NBRB recuperati. |
| Configurazione modulo | Ultimo aggiornamento | N/A (sola lettura) | Mostra il timestamp dell'ultimo aggiornamento riuscito dei tassi. |
| Configurazione modulo | Pulsante Aggiorna tassi manualmente | N/A (clicca per attivare) | Attiva un aggiornamento immediato e manuale dei tassi di cambio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prezzi BYN non si aggiornano o sembrano errati.**
R:

1.  **Controlla "Abilita tassi di cambio NBRB":** Assicurati che questa impostazione sia su "SÌ" nella configurazione del modulo.
2.  **Verifica il CRON Job:** Assicurati che il tuo CRON job sia configurato correttamente sul tuo server utilizzando l'URL fornito e che sia in esecuzione regolarmente. Controlla il timestamp "Ultimo aggiornamento" nel modulo.
3.  **Aggiorna manualmente:** Prova a cliccare sul pulsante "Aggiorna tassi manualmente". Se questo funziona, il problema è probabilmente nella configurazione del tuo CRON job.
4.  **Controlla lo stato della valuta BYN:** Vai su **Internazionale > Valute** e assicurati che "Rublo Bielorusso (BYN)" sia abilitato e che il suo codice ISO sia `BYN`.
5.  **Svuota la cache:** A volte la cache di PrestaShop può contenere valori vecchi. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".

**D: Cosa succede nei giorni festivi o nei fine settimana quando la NBRB non pubblica nuovi tassi?**
R: Il modulo è progettato per gestire questo in modo intelligente. Se l'API NBRB non fornisce nuovi tassi per un dato giorno (es. a causa di un fine settimana o di una festività pubblica), il modulo continuerà a utilizzare l'ultimo tasso recuperato con successo. Si aggiornerà solo quando saranno disponibili nuovi tassi ufficiali.

**D: Posso usare questo modulo con altri moduli di conversione valuta?**
R: Generalmente non è consigliato eseguire più moduli di conversione valuta contemporaneamente, poiché possono entrare in conflitto e portare a risultati imprevedibili. Questo modulo si concentra specificamente sui tassi NBRB per BYN. Se hai bisogno di altre valute, assicurati che questo modulo sia la fonte primaria per BYN e che altri moduli gestiscano valute diverse senza sovrapposizioni.

**D: Ho impostato un margine, ma i prezzi non sembrano rifletterlo.**
R:

1.  **Salva le modifiche:** Assicurati di aver salvato la configurazione del modulo dopo aver impostato il margine.
2.  **Aggiorna i tassi:** Il margine viene applicato quando i tassi vengono recuperati. Attendi la prossima esecuzione del CRON job o clicca su "Aggiorna tassi manualmente".
3.  **Svuota la cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
4.  **Controlla la valuta di base:** Il margine viene applicato alla conversione dalla valuta di base del tuo negozio a BYN. Assicurati che la tua valuta di base sia impostata correttamente in PrestaShop.

**D: Ricevo un errore quando cerco di installare o configurare il modulo.**
R:

1.  **Versione PrestaShop:** Assicurati di aver scaricato il file ZIP del modulo corretto per la tua specifica versione di PrestaShop (1.6, 1.7, 8.x, 9.x).
2.  **Compatibilità PHP:** Verifica che la versione PHP del tuo server rientri nell'intervallo supportato (PHP 5.6 - 8.5).
3.  **Log del server:** Controlla i log degli errori PHP del tuo server (spesso presenti nel tuo pannello di controllo dell'hosting) per messaggi di errore più dettagliati. Questo può aiutare a individuare il problema esatto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Tassi di cambio e valuta NBRB è un modulo PrestaShop leggero, focalizzato principalmente su un singolo compito critico: recuperare e aggiornare il tasso di cambio del Rublo Bielorusso (BYN) dall'API della Banca Nazionale della Repubblica di Bielorussia (NBRB). Sfrutta l'oggetto `Currency` di PrestaShop per aggiornare il `conversion_rate` per BYN. Il modulo utilizza un CRON job per gli aggiornamenti automatici e fornisce un trigger manuale nel back office. Aderisce al pattern MVC di PrestaShop per la sua configurazione e l'esecuzione del cronjob nel front-office.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe genitore:** `NbrbratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo controller è progettato per essere chiamato da un CRON job esterno. Quando viene acceduto, attiva la logica di recupero dei tassi del modulo (`$this->module->updateRates()`). Restituisce un semplice messaggio di successo/fallimento, rendendolo adatto all'esecuzione automatizzata senza un browser. Non renderizza una pagina completa.
    -   `controllers/front/index.php`
        -   **Nome classe e classe genitore:** `NbrbratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è un controller segnaposto, spesso incluso nei moduli per prevenire l'elenco delle directory o fornire una pagina "vuota" predefinita se il controller frontale del modulo viene acceduto direttamente senza azioni specifiche. Nel contesto di questo modulo, probabilmente serve come fallback e non ha una logica di business specifica.
-   **Controller Admin Back-Office**:

    -   Questo modulo non utilizza controller Admin dedicati. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce alcuna classe personalizzata nella directory `classes/`. La sua logica principale per il recupero e l'aggiornamento dei tassi è incapsulata all'interno del file principale del modulo `nbrbrates/cronjob.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile per la pagina di configurazione dell'amministrazione è tipicamente gestito dal CSS predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `nbrbrates/views/admin.tpl`
        -   **Scopo:** Questo template viene renderizzato dal metodo `getContent()` nel file principale del modulo (`nbrbrates/cronjob.php`). Definisce la struttura e la visualizzazione del modulo di configurazione del modulo nel Back Office di PrestaShop. Include campi di input per abilitare/disabilitare il modulo, la regolazione del margine, la visualizzazione dell'URL del CRON job, l'ora dell'ultimo aggiornamento e il pulsante di aggiornamento manuale.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione principali includono:
        -   `Nbrbrates_ENABLED`: (int) 1 se abilitato, 0 se disabilitato.
        -   `Nbrbrates_MARGIN`: (float) Il margine percentuale da applicare.
        -   `Nbrbrates_LAST_UPDATE`: (datetime) Timestamp dell'ultimo aggiornamento riuscito dei tassi.
-   **Tabella degli hook registrati**:
    Questo modulo non registra esplicitamente hook che visualizzano contenuti nel front office (come `displayHeader`, `displayRightColumn`, `displayFooter`). La sua interazione principale con PrestaShop avviene tramite:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Eseguito quando il modulo è installato. | Inizializza i valori di configurazione predefiniti in `ps_configuration`. |
| `actionModuleUninstall` | Eseguito quando il modulo è disinstallato. | Pulisce i valori di configurazione da `ps_configuration`. |
| `actionUpdateCurrency` | (Implicito) Attivato quando una valuta viene aggiornata. | Il metodo `updateRates()` del modulo modifica direttamente il `conversion_rate` dell'oggetto valuta BYN, agendo efficacemente sugli aggiornamenti di valuta. |

Il controller `cronjob.php` del front-office agisce come un punto di ingresso esterno, non un tradizionale hook di PrestaShop.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo Tassi di cambio e valuta NBRB, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o all'integrazione del modulo.
