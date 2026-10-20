---
title: "Tassi di cambio dalla Česká národní banka (CNB) - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tassi di cambio dalla Česká národní banka (CNB) di MyPresta.eu."
sidebar:
  label: "Tassi di cambio dalla Česká národní banka (CNB) - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Currency rates from Česká národní banka (CNB) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Tassi di cambio dalla Česká národní banka (CNB)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Questa è la schermata di configurazione principale e unica per il modulo.

#### **Impostazioni e Opzioni**

**1. `mypresta_updates` (Aggiornamenti MyPresta.eu)**

-   **Cosa fa questa impostazione:** Questa è un'impostazione standard presente in molti moduli MyPresta.eu. Controlla se il modulo verifica la presenza di aggiornamenti da MyPresta.eu e visualizza le notifiche nel tuo back office di PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo verificherà periodicamente la presenza di nuove versioni disponibili su MyPresta.eu. Se viene trovato un aggiornamento, potresti vedere una notifica nel pannello di amministrazione di PrestaShop, che ti inviterà a scaricare e installare la versione più recente. Questo ti aiuta a rimanere aggiornato con correzioni di bug e nuove funzionalità.
    -   *Quando disabilitato (NO):* Il modulo non verificherà la presenza di aggiornamenti. Non riceverai alcuna notifica sulle nuove versioni, il che significa che dovrai controllare manualmente il tuo account MyPresta.eu per gli aggiornamenti.
-   **Valore consigliato:** **SÌ**. È sempre consigliabile mantenere i moduli aggiornati per sicurezza, compatibilità e nuove funzionalità.
-   **Scenario / esempio del commerciante:** Vuoi assicurarti che il tuo modulo stia sempre eseguendo l'ultima versione più stabile senza dover controllare costantemente manualmente. Abilitando questa opzione riceverai un avviso quando un aggiornamento è disponibile.

**2. `update_` (Frequenza di aggiornamento)**

-   **Cosa fa questa impostazione:** Questa impostazione determina la frequenza con cui il modulo tenta di recuperare e aggiornare i tassi di cambio dal feed della CNB.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un intervallo più breve (ad esempio, "Ogni ora"):* I tuoi tassi di cambio verranno aggiornati più frequentemente, garantendo che i tuoi prezzi siano molto attuali, il che è vantaggioso nei mercati volatili. Tuttavia, potrebbe aumentare leggermente il carico del server (anche se tipicamente trascurabile per questo tipo di operazione).
    -   *Quando impostato su un intervallo più lungo (ad esempio, "Una volta al giorno"):* I tassi vengono aggiornati meno frequentemente. Questo è generalmente sufficiente poiché la CNB fornisce tipicamente tassi giornalieri. Riduce il carico del server.
-   **Valore consigliato:** **Una volta al giorno**. La CNB di solito pubblica i tassi giornalieri, quindi aggiornare più frequentemente di una volta al giorno è spesso inutile e non fornisce dati più recenti.
-   **Scenario / esempio del commerciante:** Gestisci un negozio internazionale dove le fluttuazioni dei tassi di cambio possono influire sui tuoi margini di profitto. Impostando questa opzione su "Una volta al giorno" ti assicuri di avere sempre gli ultimi tassi ufficiali senza sovraccaricare il tuo server.

**3. `updatev_` (Metodo di aggiornamento)**

-   **Cosa fa questa impostazione:** Questa impostazione definisce come il modulo attiva il processo di aggiornamento dei tassi di cambio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Cron Job":* Il modulo si aspetta che tu imposti un cron job lato server (un'attività pianificata) che chiamerà periodicamente un URL specifico fornito dal modulo. Questo è il metodo più affidabile e consigliato in quanto garantisce che gli aggiornamenti avvengano esattamente quando pianificato, anche se nessuno visita il tuo negozio.
    -   *Quando impostato su "Al caricamento della pagina":* Il modulo tenterà di aggiornare i tassi quando un cliente o un amministratore visita qualsiasi pagina del tuo negozio. Questo è meno affidabile in quanto gli aggiornamenti avvengono solo quando il traffico raggiunge il tuo sito, e se il tuo sito ha poco traffico, gli aggiornamenti potrebbero essere ritardati. Può anche rallentare leggermente il primo caricamento della pagina per un visitatore se un aggiornamento è dovuto.
-   **Valore consigliato:** **Cron Job**. Questo è il metodo più robusto ed efficiente per le attività pianificate. Il modulo ti fornirà l'URL esatto da utilizzare per il tuo cron job.
-   **Scenario / esempio del commerciante:** Vuoi garantire che i tassi di cambio vengano aggiornati ogni mattina alle 3:00, indipendentemente dal traffico del sito web. Impostando questa opzione su "Cron Job" e configurando il cron del tuo server, otterrai questo in modo affidabile.

**4. `currency_` (Valute da aggiornare)**

-   **Cosa fa questa impostazione:** Ti consente di selezionare quali valute specifiche nel tuo negozio PrestaShop devono avere i loro tassi di cambio aggiornati dal feed della CNB.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando vengono selezionate valute specifiche:* Solo le valute scelte avranno i loro tassi di cambio aggiornati dal modulo. Altre valute (se ne hai) manterranno i loro tassi impostati manualmente o il meccanismo di aggiornamento predefinito di PrestaShop (se attivo). Questo ti offre un controllo granulare.
    -   *Quando non vengono selezionate valute (o tutte sono selezionate):* Il modulo tenterà di aggiornare tutte le valute attive nel tuo negozio che sono presenti nel feed della CNB.
-   **Valore consigliato:** Seleziona **tutte le valute che utilizzi attivamente per le transazioni e che sono supportate dal feed della CNB**. Tipicamente, questo include EUR, USD, GBP e altre valute principali.
-   **Scenario / esempio del commerciante:** Il tuo negozio accetta pagamenti in EUR, USD e CZK. Vuoi che i tassi EUR e USD siano aggiornati dalla CNB, ma CZK è la tua valuta predefinita e non necessita di aggiornamenti esterni. Selezioneresti EUR e USD da questo elenco.

#### **URL del Cron Job (Visualizzato dopo il salvataggio delle impostazioni)**

-   **Cosa fa:** Dopo aver configurato e salvato le impostazioni del modulo, specialmente se scegli "Cron Job" come metodo di aggiornamento, il modulo visualizzerà un URL unico. Questo URL è ciò che il cron job del tuo server deve chiamare per attivare il processo di aggiornamento.
-   **Effetto dell'utilizzo di questo URL:** Quando questo URL viene acceduto (dal cron job del tuo server o manualmente in un browser), il modulo esegue la sua logica per recuperare gli ultimi tassi di cambio dalla CNB e li aggiorna nel database di PrestaShop.
-   **Azione consigliata:** Copia questo URL e impostalo come cron job sul tuo server di hosting. Consulta la documentazione o il supporto del tuo provider di hosting per sapere come impostare un cron job. Un tipico cron job potrebbe assomigliare a `wget -q -O /dev/null "IL_TUO_URL_CRON_QUI"`.
-   **Scenario / esempio del commerciante:** Hai impostato la frequenza di aggiornamento su "Una volta al giorno" e il metodo su "Cron Job". Il modulo visualizza `https://iltuonegozio.com/module/cnbrates/cronjob?token=IL_TUO_TOKEN_UNICO`. Configureresti quindi il cron del tuo server per eseguire `wget -q -O /dev/null "https://iltuonegozio.com/module/cnbrates/cronjob?token=IL_TUO_TOKEN_UNICO"` una volta ogni 24 ore.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Aggiornamenti MyPresta.eu | SÌ | Controlla le notifiche di aggiornamento da MyPresta.eu. |
| Configurazione Modulo | Frequenza di aggiornamento | Una volta al giorno | Quanto spesso il modulo recupera nuovi tassi dalla CNB. |
| Configurazione Modulo | Metodo di aggiornamento | Cron Job | Come viene attivato il processo di aggiornamento (attività pianificata vs. caricamento pagina). |
| Configurazione Modulo | Valute da aggiornare | Seleziona tutte le pertinenti | Specifica quali valute nel tuo negozio vengono aggiornate dalla CNB. |
| Configurazione Modulo | URL del Cron Job | (Visualizzato dopo il salvataggio) | L'URL da utilizzare per i cron job lato server per attivare gli aggiornamenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano. Cosa devo controllare per primo?**
R: La ragione più comune è un problema con il cron job.

1.  Vai su **Moduli > Gestione moduli > Configura** per il modulo Tassi CNB.
2.  Controlla l'impostazione "Metodo di aggiornamento". Se è "Cron Job", assicurati di aver configurato correttamente il cron job sul tuo server di hosting utilizzando l'URL fornito. Contatta il supporto del tuo provider di hosting se non sei sicuro di come farlo.
3.  Se è selezionato "Al caricamento della pagina", assicurati che il tuo negozio riceva traffico regolare. In caso contrario, passa a "Cron Job" per aggiornamenti più affidabili.
4.  Inoltre, verifica che le valute che ti aspetti vengano aggiornate siano selezionate nell'elenco "Valute da aggiornare".

**D: Questo modulo funziona se la valuta predefinita del mio negozio non è CZK?**
R: Sì, assolutamente! Il modulo è progettato per funzionare anche se la tua valuta predefinita non è CZK. Recupera i tassi dalla CNB, che fornisce tassi di cambio per varie valute rispetto alla CZK. Il modulo quindi converte intelligentemente questi tassi per aggiornare le valute non predefinite del tuo negozio rispetto alla tua valuta predefinita effettiva.

**D: Con quale frequenza la CNB aggiorna i suoi tassi?**
R: La Česká národní banka (CNB) pubblica tipicamente i suoi tassi di cambio ufficiali una volta al giorno, di solito nei giorni lavorativi. Pertanto, impostare la "Frequenza di aggiornamento" del tuo modulo su "Una volta al giorno" è generalmente sufficiente per acquisire i dati più recenti disponibili.

**D: Ho aggiornato il modulo, ma non vedo alcun cambiamento. Cosa posso fare?**
R: A volte, il sistema di caching di PrestaShop può impedire la visualizzazione immediata delle modifiche.

1.  Vai su **Parametri avanzati > Prestazioni** nel back office di PrestaShop.
2.  Clicca su "Svuota cache" (o "Svuota cache Smarty" se disponibile).
3.  Aggiorna il tuo browser (Ctrl+F5 o Cmd+R) per assicurarti di non visualizzare una versione in cache della pagina.

**D: Posso attivare manualmente un aggiornamento?**
R: Sì, se il tuo "Metodo di aggiornamento" è impostato su "Cron Job", puoi visitare manualmente l'URL del cron job (visualizzato nella configurazione del modulo) nel tuo browser web. Questo attiverà un aggiornamento immediato. Tuttavia, questo è solo per test/risoluzione dei problemi; per gli aggiornamenti regolari, affidati al cron job automatizzato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Tassi di cambio dalla Česká národní banka (CNB)" è un modulo PrestaShop leggero progettato per un singolo compito mirato: recuperare e aggiornare i tassi di cambio. Sfrutta principalmente un controller front-office per esporre un endpoint cron job, consentendo aggiornamenti programmati e automatizzati. Il modulo non introduce nuove tabelle di database o complesse strutture `ObjectModel`, affidandosi invece alla classe `Currency` esistente di PrestaShop e a `Configuration` per le sue impostazioni. Segue una struttura di modulo PrestaShop di base, integrandosi con i metodi `install()` e `uninstall()` per la configurazione e la pulizia.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre**: `CnbratesCronjobModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è il cuore dell'automazione del modulo. Risponde alle richieste all'URL del cron job (ad esempio, `iltuonegozio.com/module/cnbrates/cronjob?token=...`). Il suo metodo `initContent()` (o metodo del ciclo di vita simile) contiene la logica per:
            1.  Validare il parametro `token` rispetto alla configurazione memorizzata per prevenire accessi non autorizzati.
            2.  Recuperare gli ultimi tassi di cambio dal feed XML della CNB (tipicamente `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
            3.  Analizzare i dati XML.
            4.  Iterare attraverso le valute configurate in PrestaShop.
            5.  Per ogni valuta selezionata, calcolare il suo nuovo tasso di cambio basato sui dati della CNB (che di solito è relativo a CZK) e alla valuta predefinita del negozio.
            6.  Aggiornare il campo `exchange_rate` per l'oggetto `Currency` corrispondente nella tabella `ps_currency`.
            7.  Restituisce un semplice messaggio di successo o errore, principalmente per la registrazione del cron job.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `CnbratesIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller segnaposto o di fallback. In molti moduli, un controller frontale `index.php` funge da punto di ingresso predefinito se non viene richiesta alcuna azione specifica. Per questo modulo, la sua funzione principale è probabilmente quella di reindirizzare alla homepage o visualizzare un semplice messaggio, poiché la funzionalità principale è gestita da `cronjob.php`. Non contiene una logica di business significativa per gli aggiornamenti delle valute.
-   **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita interamente all'interno di `cnbrates.php` tramite `getContent()`.

### 4.3 Classi e Modelli Core (`classes/`)

Non ci sono classi personalizzate o definizioni `ObjectModel` all'interno della directory `classes/` per questo modulo. Il modulo interagisce direttamente con la classe `Currency` e la classe `Configuration` di PrestaShop per la gestione dei dati.

### 4.4 Risorse JavaScript (`views/js/`)

Non ci sono file JavaScript personalizzati in questo modulo. Tutte le funzionalità sono PHP lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Non ci sono file CSS personalizzati in questo modulo. Il modulo non introduce alcun elemento visivo front-office o stile back-office complesso oltre agli elementi di modulo standard di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**: Nessuno. Il modulo non visualizza contenuti tramite hook.
-   **Template Admin (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` in `cnbrates.php` per visualizzare il modulo di configurazione del modulo nel back office di PrestaShop.
        -   **Contenuto**: Contiene la struttura HTML per le impostazioni descritte nella Sezione 4.1, inclusi i campi di input per la frequenza di aggiornamento, il metodo di aggiornamento, la selezione della valuta e la visualizzazione dell'URL del cron job. Utilizza gli helper e lo stile standard dei moduli di PrestaShop.
-   **Template Front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo **non** crea alcuna tabella SQL personalizzata.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione principali includono:
        -   `CNBRATES_UPDATE_FREQUENCY`
        -   `CNBRATES_UPDATE_METHOD`
        -   `CNBRATES_CURRENCIES` (probabilmente un elenco di ID valuta separati da virgola)
        -   `CNBRATES_CRON_TOKEN` (un token unico per la sicurezza del cron job)
        -   `MYPRESTA_UPDATES_CNBRATES` (per i controlli di aggiornamento di MyPresta.eu)
    -   Aggiorna la colonna `exchange_rate` nella tabella `ps_currency` per le valute selezionate.
-   **Tabella degli hook registrati**:
    Il modulo registra i seguenti hook, principalmente per la propria gestione del ciclo di vita e potenzialmente per i controlli di aggiornamento, piuttosto che per la visualizzazione di contenuti:

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Ad ogni caricamento di pagina nel front office (prima dell'output HTML). | Spesso utilizzato per l'inclusione di JS/CSS, o in questo caso, potenzialmente per il metodo di aggiornamento "Al caricamento della pagina" se configurato, o per i controlli di aggiornamento di MyPresta.eu. |
| `displayRightColumn` | Renderizza il contenuto nella colonna destra del front office. | Non utilizzato per la visualizzazione di contenuti da questo modulo, probabilmente una registrazione di hook legacy o per controlli interni. |
| `displayLeftColumn` | Renderizza il contenuto nella colonna sinistra del front office. | Non utilizzato per la visualizzazione di contenuti da questo modulo, probabilmente una registrazione di hook legacy o per controlli interni. |
| `displayFooter` | Renderizza il contenuto nel piè di pagina del front office. | Non utilizzato per la visualizzazione di contenuti da questo modulo, probabilmente una registrazione di hook legacy o per controlli interni. |
| `displayBackOfficeHeader` | Ad ogni caricamento di pagina nel back office. | Utilizzato per includere CSS/JS specifici del modulo per la pagina di configurazione, o per visualizzare le notifiche di aggiornamento da MyPresta.eu. |
| `actionAdminCurrenciesControllerSaveAfter` | Dopo che una valuta viene salvata nel back office. | Potrebbe essere utilizzato per rivalutare le impostazioni della valuta o attivare un aggiornamento se lo stato di una valuta cambia. |
| `actionAdminCurrenciesControllerDeleteAfter` | Dopo che una valuta viene eliminata nel back office. | Potrebbe essere utilizzato per rimuovere la valuta eliminata dall'elenco di aggiornamento del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Tassi di cambio dalla Česká národní banka (CNB)", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o all'integrazione del modulo.
