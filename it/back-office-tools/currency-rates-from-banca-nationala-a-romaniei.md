---
title: "Tassi di cambio dalla Banca Națională a României - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tassi di cambio dalla Banca Națională a României di MyPresta.eu."
sidebar:
  label: "Tassi di cambio dalla Banca Națională a României - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Currency rates from Banca Nationala a Romaniei su MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Tassi di cambio dalla Banca Națională a României

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di feed di dati esterni, che sono standard nella maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### **Impostazioni e Opzioni**

1.  **Verifica aggiornamenti del modulo**

    -   **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo verifica periodicamente su MyPresta.eu la presenza di nuove versioni o aggiornamenti importanti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se abilitato (SÌ):* Il modulo si connetterà occasionalmente a MyPresta.eu per vedere se è disponibile una versione più recente. Se viene trovato un aggiornamento, potrebbe apparire una notifica nel tuo back office di PrestaShop, invitandoti a scaricarlo e installarlo.
        -   *Se disabilitato (NO):* Il modulo non verificherà automaticamente la presenza di aggiornamenti. Dovrai controllare manualmente il tuo account MyPresta.eu per nuove versioni.
    -   **Valore consigliato:** **SÌ**. È sempre consigliabile mantenere i moduli aggiornati per beneficiare di nuove funzionalità, correzioni di bug e miglioramenti della sicurezza.
    -   **Scenario/esempio per il commerciante:** Vuoi assicurarti che il tuo modulo per i tassi di cambio stia sempre eseguendo la versione più recente e stabile senza dover controllare costantemente manualmente. L'abilitazione di questa opzione ti avviserà quando un aggiornamento è pronto.
2.  **Aggiorna tassi di cambio**

    -   **Cosa fa questa impostazione:** Questa è la funzione principale del modulo. Quando clicchi su questo pulsante, il modulo recupererà immediatamente gli ultimi tassi di cambio dalla Banca Naţională a României (BNR) e li applicherà alle valute configurate nel tuo negozio PrestaShop.
    -   **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante si attiva un aggiornamento immediato di tutti i tassi di cambio nel tuo negozio basato sul feed BNR. Questo è un trigger manuale per il processo di aggiornamento.
    -   **Valore consigliato:** Questo è un pulsante di azione, non un'impostazione. Cliccalo ogni volta che hai bisogno di un aggiornamento immediato, o dopo aver configurato le tue valute.
    -   **Scenario/esempio per il commerciante:** È l'inizio della giornata lavorativa e vuoi assicurarti che tutti i tuoi prezzi riflettano gli ultimi tassi di cambio prima che i clienti inizino a effettuare ordini. Cliccheresti su questo pulsante.
3.  **URL Cronjob**

    -   **Cosa fa questa impostazione:** Questo campo visualizza un URL unico che puoi utilizzare per automatizzare gli aggiornamenti dei tassi di cambio. Questo URL è progettato per essere chiamato da un "cron job" sul tuo server web, che è un'attività pianificata che viene eseguita automaticamente a intervalli specifici (es. una volta al giorno, ogni ora).
    -   **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione. Copiare e impostare questo URL nello scheduler dei cron job del tuo pannello di hosting garantirà che i tuoi tassi di cambio vengano aggiornati automaticamente senza che tu debba cliccare manualmente il pulsante "Aggiorna tassi di cambio".
    -   **Valore consigliato:** Copia questo URL e configura un cron job sul tuo server per eseguirlo almeno una volta al giorno, o più frequentemente se la tua attività lo richiede.
    -   **Scenario/esempio per il commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni mattina alle 6 in punto automaticamente, anche quando non sei al computer. Copieresti questo URL e configureresti un cron job sul tuo server di hosting per eseguirlo quotidianamente alle 6 del mattino.
4.  **Valuta da aggiornare**

    -   **Cosa fa questa impostazione:** Questo elenco a discesa ti consente di selezionare quali valute specifiche nel tuo negozio PrestaShop dovrebbero essere aggiornate dal feed BNR. Il feed BNR fornisce principalmente tassi contro il RON. Il modulo convertirà quindi questi tassi nella valuta predefinita del tuo negozio e poi in altre valute selezionate.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene selezionata una valuta specifica:* Solo il tasso di cambio di quella valuta verrà aggiornato dal modulo.
        -   *Quando viene selezionato "Tutte le valute":* Il modulo tenterà di aggiornare tutte le valute attive nel tuo negozio PrestaShop utilizzando il feed BNR.
    -   **Valore consigliato:** **Tutte le valute**, a meno che tu non abbia una ragione specifica per aggiornarne solo una. Questo assicura che tutti i tuoi prezzi internazionali siano coerenti.
    -   **Scenario/esempio per il commerciante:** Il tuo negozio accetta EUR, USD e GBP. Vuoi che tutte queste valute vengano aggiornate quotidianamente in base alla conversione del feed BNR in RON e poi nella valuta predefinita del tuo negozio. Selezioneresti "Tutte le valute". Se volessi aggiornare solo EUR per qualche motivo, selezioneresti "EUR".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Verifica aggiornamenti del modulo | SÌ | Abilita i controlli automatici per nuove versioni del modulo. |
| Configurazione modulo | Aggiorna tassi di cambio | N/A (Pulsante d'azione) | Attiva manualmente un aggiornamento immediato di tutti i tassi di cambio selezionati dalla BNR. |
| Configurazione modulo | URL Cronjob | N/A (Solo visualizzazione) | Fornisce l'URL per impostare un'attività pianificata automatica per gli aggiornamenti dei tassi di cambio. |
| Configurazione modulo | Valuta da aggiornare | Tutte le valute | Determina quali valute nel tuo negozio riceveranno aggiornamenti automatici dei tassi dalla BNR. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano. Cosa dovrei controllare per primo?**
R1:

1.  **Aggiornamento manuale:** Vai alla pagina di configurazione del modulo e clicca sul pulsante "Aggiorna tassi di cambio". Se questo funziona, il problema è probabilmente nella configurazione del tuo cron job.
2.  **Cron Job:** Ricontrolla che il tuo cron job sia configurato correttamente sul tuo server di hosting utilizzando l'esatto "URL Cronjob" fornito dal modulo. Assicurati che sia impostato per essere eseguito alla frequenza desiderata.
3.  **Impostazioni del modulo:** Verifica che "Tutte le valute" o le valute specifiche che desideri aggiornare siano selezionate nel menu a discesa "Valuta da aggiornare".
4.  **Valute PrestaShop:** Assicurati che le valute che ti aspetti vengano aggiornate siano attive nel tuo negozio PrestaShop (Internazionale > Valute).
5.  **Connettività del server:** Assicurati che il tuo server possa accedere a siti web esterni (in particolare il feed BNR). A volte le regole del firewall o problemi di rete possono impedirlo.

**D2: Il modulo dice che ha aggiornato, ma i prezzi nel mio front office non sembrano corretti.**
R2:

1.  **Svuota cache:** PrestaShop utilizza la cache. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo assicura che il tuo negozio visualizzi i dati più recenti.
2.  **Cache del browser:** Svuota la cache e i cookie del tuo browser, oppure prova a visualizzare il tuo negozio in una finestra di navigazione in incognito/privata per escludere problemi di caching locale.
3.  **Selezione valuta:** Assicurati di visualizzare i prezzi nella valuta corretta nel front office.

**D3: Posso aggiornare i tassi più frequentemente di una volta al giorno?**
R3: Sì, puoi. Quando configuri il tuo cron job, puoi impostarlo per essere eseguito ogni ora, ogni poche ore o a qualsiasi intervallo supportato dallo scheduler cron del tuo provider di hosting. Fai attenzione al potenziale carico del server se lo imposti per essere eseguito estremamente frequentemente (es. ogni minuto), anche se per gli aggiornamenti di valuta, questo è raramente un problema.

**D4: Cosa succede se il feed BNR è temporaneamente non disponibile?**
R4: Se il feed BNR non è disponibile, il modulo probabilmente non riuscirà a recuperare nuovi tassi. Non eliminerà o resetterà i tuoi tassi esistenti; rimarranno semplicemente invariati finché il feed non sarà di nuovo disponibile e non si verificherà un aggiornamento riuscito. Potresti vedere un messaggio di errore nei log del cron job del tuo server se l'aggiornamento fallisce.

**D5: La valuta predefinita del mio negozio non è RON. Questo modulo funzionerà comunque?**
R5: Sì, assolutamente. Il modulo è progettato per funzionare indipendentemente dalla valuta predefinita del tuo negozio. Recupera i tassi BNR (che sono tipicamente contro il RON) e poi li converte intelligentemente nella valuta predefinita del tuo negozio, e successivamente in qualsiasi altra valuta attiva che hai abilitato per l'aggiornamento.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Tassi di cambio dalla Banca Națională a României" è un modulo PrestaShop semplice, focalizzato principalmente su un singolo compito: recuperare e aggiornare i tassi di cambio. Segue una struttura di modulo PrestaShop di base, sfruttando la classe `Module` per l'installazione e la configurazione, e `ModuleFrontController` per la sua funzionalità di cron job. Non introduce classi `ObjectModel` o tabelle di database personalizzate, affidandosi invece alla classe `Currency` e alla tabella `Configuration` di PrestaShop per le impostazioni. La logica principale prevede l'analisi di un feed XML dalla BNR e l'aggiornamento dei tassi di cambio esistenti.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono progettati per essere accessibili esternamente, principalmente per l'automazione dei cron job.

-   `controllers/front/cronjob.php`
    -   **Nome classe e classe padre:** `BnrratesCronjobModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è l'endpoint dedicato per il cron job di aggiornamento automatico della valuta. Quando viene acceduto, attiva la logica principale del modulo per recuperare gli ultimi tassi di cambio dalla BNR e aggiornarli nel database di PrestaShop. Tipicamente restituisce un semplice messaggio di successo o errore, adatto per la registrazione dei cron job. Non renderizza alcun output visivo per un browser.
-   `controllers/front/index.php`
    -   **Nome classe e classe padre:** `BnrratesIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller probabilmente funge da fallback o da punto di ingresso predefinito, sebbene la sua funzione principale possa essere minima dato l'esplicito controller `cronjob.php`. In molti moduli, un controller frontale `index.php` potrebbe reindirizzare o visualizzare un semplice messaggio se acceduto direttamente senza parametri specifici. Per questo modulo, il suo utilizzo pratico è probabilmente limitato, con `cronjob.php` che gestisce l'interazione principale del front-office.

#### Controller Admin Back-Office

Il modulo non implementa alcuna classe `AdminController` personalizzata. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non introduce classi personalizzate o definizioni `ObjectModel` nella directory `classes/`. Interagisce direttamente con le classi `Currency` e `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `bnrrates/views/admin.tpl`
        -   **Scopo:** Questo template è responsabile del rendering del modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza le impostazioni come "Verifica aggiornamenti del modulo", il pulsante "Aggiorna tassi di cambio", l'"URL Cronjob" e il menu a discesa "Valuta da aggiornare".
        -   **Variabili:** Tipicamente riceverebbe variabili dal metodo `getContent()` del file principale del modulo, come i valori correnti delle impostazioni di configurazione e l'URL del cron job generato.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione pertinenti sono:
        -   `BNRRATES_MYPRESTA_UPDATES`: Memorizza il valore booleano per la verifica degli aggiornamenti del modulo.
        -   `BNRRATES_CURRENCY_TO_UPDATE`: Memorizza l'ID della valuta da aggiornare, o un valore speciale (es. `0` o `all`) per tutte le valute.
        -   `BNRRATES_LAST_UPDATE_TIME`: (Probabilmente) Memorizza un timestamp dell'ultimo aggiornamento riuscito.
        -   `BNRRATES_CRON_TOKEN`: Memorizza un token unico utilizzato nell'URL del cron job per la sicurezza.
-   **Tabella degli hook registrati**:
    Il modulo utilizza principalmente gli hook `action` per la sua funzionalità principale e potenzialmente gli hook `display` per notifiche o contenuti specifici (sebbene nessun hook di visualizzazione front-office specifico sia esplicitamente elencato nelle informazioni fornite, la descrizione del modulo menziona "Header, Colonne, Prodotto o Footer" come aree potenziali, il che implicherebbe `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter` ecc. Tuttavia, dato lo scopo del modulo, questi sarebbero probabilmente per la visualizzazione di una notifica o di uno stato, non per la funzionalità principale).

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante l'installazione del modulo | Registra la configurazione del modulo, crea le impostazioni predefinite. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce la configurazione del modulo da `ps_configuration`. |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller admin | Potenzialmente registra CSS/JS per la pagina di configurazione admin (anche se nessuno è presente in questo modulo). |
| `displayBackOfficeHeader` | Nell'intestazione del Back Office | Potenzialmente visualizza notifiche di aggiornamento o altri contenuti specifici dell'amministratore. |
| `displayHeader` | Nella sezione `<head>` del front office | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per meta tag o JS/CSS se necessario. |
| `displayLeftColumn` | Nella colonna sinistra del front office | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per visualizzare un blocco valuta. |
| `displayRightColumn` | Nella colonna destra del front office | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per visualizzare un blocco valuta. |
| `displayProductButtons` | Nella pagina del prodotto, vicino all'aggiunta al carrello | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per informazioni relative alla valuta. |
| `displayFooter` | Nel piè di pagina del front office | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per informazioni relative alla valuta. |

La logica principale di aggiornamento della valuta viene attivata accedendo al controller frontale `cronjob.php`, che non è un hook standard di PrestaShop ma un endpoint esterno.

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Tassi di cambio dalla Banca Națională a României", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
