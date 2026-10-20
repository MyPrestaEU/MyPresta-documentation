---
title: "Ottimizzazione del Database - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Ottimizzazione del Database di MyPresta.eu."
sidebar:
  label: "Ottimizzazione del Database - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Database Optimization su MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/database-optimization/)
>
> ---


# Ottimizzazione del Database

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Ottimizzazione del Database. La troverai navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto a "Ottimizzazione del Database".

#### **Carrelli indesiderati**

-   **Cosa fa questa impostazione:** Questa opzione controlla se il modulo rimuoverà i vecchi carrelli abbandonati dal tuo database. Si tratta di carrelli che i clienti hanno iniziato ma per i quali non hanno mai completato un ordine.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sì":* Il modulo eliminerà periodicamente questi vecchi carrelli incompleti. Questo riduce le dimensioni del tuo database e può migliorare le prestazioni, poiché PrestaShop non deve gestire dati per migliaia di carrelli abbandonati.
    -   *Se impostato su "No":* I vecchi carrelli rimarranno nel tuo database. Sebbene ciò mantenga i dati storici, può contribuire all'ingombro del database nel tempo.
-   **Valore consigliato:** **Sì**. A meno che tu non abbia una specifica ragione commerciale per conservare tutti i dati dei carrelli abbandonati (ad esempio, per un'analisi storica molto approfondita), la loro pulizia è vantaggiosa per le prestazioni.
-   **Scenario / esempio per il commerciante:** Se noti che il tuo database sta diventando molto grande e il tuo negozio sta rallentando, abilitare questa opzione è un rapido successo per rimuovere una fonte comune di dati non necessari.

#### **Connessioni**

-   **Cosa fa questa impostazione:** Questa opzione controlla se il modulo rimuoverà i vecchi log di connessione dal tuo database. PrestaShop registra ogni connessione di un visitatore al tuo negozio, che può accumularsi rapidamente.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sì":* Il modulo eliminerà periodicamente i vecchi log di connessione. Questo riduce significativamente le dimensioni del database, poiché i log di connessione possono essere una delle tabelle più grandi in un negozio trafficato.
    -   *Se impostato su "No":* I log di connessione verranno conservati indefinitamente, portando potenzialmente a un database molto grande.
-   **Valore consigliato:** **Sì**. Per la maggior parte dei negozi, i log di connessione molto vecchi non sono critici per le operazioni quotidiane e possono essere rimossi in sicurezza per migliorare le prestazioni.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio ha un volume di traffico elevato, i log di connessione possono crescere estremamente velocemente. Abilitare questa opzione aiuta a evitare che il tuo database diventi eccessivamente grande e lento.

#### **Pagine di connessione**

-   **Cosa fa questa impostazione:** Questa opzione si rivolge specificamente ai log di connessione relativi alle singole pagine visitate. Funziona in combinazione con l'impostazione "Connessioni".
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sì":* Se anche "Connessioni" è "Sì", il modulo rimuoverà i vecchi log che dettagliano quali pagine specifiche sono state visualizzate dai visitatori.
    -   *Se impostato su "No":* Anche se "Connessioni" è "Sì", il modulo manterrà i log di connessione specifici per pagina.
-   **Valore consigliato:** **Sì**. Similmente alle connessioni generali, i log specifici per pagina possono essere molto numerosi e spesso non sono necessari per un'analisi a lungo termine se si utilizzano strumenti di analisi esterni come Google Analytics.
-   **Scenario / esempio per il commerciante:** Se ti affidi a Google Analytics per le statistiche sulle visualizzazioni di pagina, probabilmente non hai bisogno che PrestaShop memorizzi questi dati granulari indefinitamente, rendendo sicura la pulizia.

#### **Origine connessioni**

-   **Cosa fa questa impostazione:** Questa opzione si rivolge specificamente ai log di connessione relativi all'origine del visitatore (es. diretto, motore di ricerca, referral). Funziona in combinazione con l'impostazione "Connessioni".
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sì":* Se anche "Connessioni" è "Sì", il modulo rimuoverà i vecchi log che dettagliano da dove provenivano i visitatori.
    -   *Se impostato su "No":* Anche se "Connessioni" è "Sì", il modulo manterrà i log di connessione specifici per l'origine.
-   **Valore consigliato:** **Sì**. Come altri dati di connessione, questi possono spesso essere gestiti da strumenti di analisi esterni.
-   **Scenario / esempio per il commerciante:** Se il tuo team di marketing utilizza strumenti come Google Analytics o altri sistemi CRM per tracciare le fonti di traffico, i log interni di PrestaShop potrebbero essere ridondanti e possono essere puliti per risparmiare spazio nel database.

#### **Ospiti**

-   **Cosa fa questa impostazione:** Questa opzione controlla se il modulo rimuoverà i vecchi account guest inattivi dal tuo database. Si tratta di account creati per i visitatori che hanno iniziato un checkout come guest ma non lo hanno mai completato, o che hanno semplicemente navigato senza registrarsi.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sì":* Il modulo eliminerà periodicamente questi vecchi account guest. Questo aiuta a mantenere il tuo database clienti pulito e focalizzato sugli utenti attivi o registrati.
    -   *Se impostato su "No":* I vecchi account guest rimarranno nel tuo database indefinitamente.
-   **Valore consigliato:** **Sì**. A meno che tu non abbia una specifica necessità di conservare ogni singolo record guest, la loro pulizia aiuta a mantenere un database ordinato.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio ha molti visitatori che navigano ma non si registrano o non completano gli acquisti, la tabella degli ospiti può crescere in modo significativo. La pulizia di questi aiuta a mantenere i dati dei tuoi clienti gestibili.

#### **Verifica aggiornamenti**

-   **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo verificherà automaticamente la disponibilità di nuove versioni e aggiornamenti da MyPresta.eu.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Abilita":* Il modulo si connetterà periodicamente a MyPresta.eu per verificare se è disponibile una versione più recente. In tal caso, riceverai una notifica nel tuo Back Office di PrestaShop.
    -   *Se impostato su "Disabilita":* Il modulo non verificherà la disponibilità di aggiornamenti. Dovrai controllare manualmente il tuo account MyPresta.eu per nuove versioni.
-   **Valore consigliato:** **Abilita**. Questo ti assicura di essere sempre a conoscenza degli aggiornamenti disponibili, che spesso includono correzioni di bug, miglioramenti delle prestazioni e nuove funzionalità.
-   **Scenario / esempio per il commerciante:** Vuoi assicurarti che i tuoi moduli siano sempre aggiornati per sicurezza e prestazioni. Abilitare questa opzione fornisce comode notifiche.

#### **Notifiche aggiornamenti**

-   **Cosa fa questa impostazione:** Questa impostazione controlla se ricevi notifiche nel tuo Back Office di PrestaShop quando è disponibile un aggiornamento (se "Verifica aggiornamenti" è abilitato).
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Abilita":* Vedrai una notifica nel tuo Back Office quando viene rilevata una nuova versione del modulo.
    -   *Se impostato su "Disabilita":* Anche se "Verifica aggiornamenti" è abilitato e un aggiornamento è disponibile, non riceverai una notifica visibile nel Back Office.
-   **Valore consigliato:** **Abilita**. Questo funziona in combinazione con "Verifica aggiornamenti" per tenerti informato.
-   **Scenario / esempio per il commerciante:** Vuoi essere immediatamente avvisato quando un aggiornamento è pronto in modo da poter pianificare l'installazione, assicurando che il tuo negozio benefici degli ultimi miglioramenti.

#### **Pagina del modulo**

-   **Cosa fa questa impostazione:** Questa impostazione è probabilmente un'opzione di visualizzazione per la pagina del modulo stesso o per le informazioni all'interno del Back Office. (Basandosi sulla tipica struttura dei moduli MyPresta.eu, questo potrebbe controllare un link o un elemento di visualizzazione specifico relativo al modulo stesso).
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Abilita":* Probabilmente visualizza un link o una sezione relativa alle informazioni del modulo o ad altri moduli MyPresta.eu.
    -   *Se impostato su "Disabilita":* Questo link o sezione sarà nascosto.
-   **Valore consigliato:** **Abilita**. Di solito fornisce un accesso rapido al supporto o ad altre risorse utili.
-   **Scenario / esempio per il commerciante:** Vuoi un facile accesso alle risorse di MyPresta.eu direttamente dalla pagina di configurazione del tuo modulo.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Carrelli indesiderati | Sì | Rimuove i vecchi carrelli abbandonati per ridurre le dimensioni del database e migliorare le prestazioni. |
| Configurazione modulo | Connessioni | Sì | Rimuove i vecchi log di connessione dei visitatori per ridurre significativamente le dimensioni del database. |
| Configurazione modulo | Pagine di connessione | Sì | Rimuove i vecchi log delle pagine specifiche visitate dalle connessioni. |
| Configurazione modulo | Origine connessioni | Sì | Rimuove i vecchi log delle fonti di traffico per le connessioni. |
| Configurazione modulo | Ospiti | Sì | Rimuove i vecchi account guest inattivi per mantenere puliti i dati dei clienti. |
| Configurazione modulo | Verifica aggiornamenti | Abilita | Controlla automaticamente MyPresta.eu per gli aggiornamenti del modulo. |
| Configurazione modulo | Notifiche aggiornamenti | Abilita | Visualizza le notifiche del Back Office quando sono disponibili aggiornamenti del modulo. |
| Configurazione modulo | Pagina del modulo | Abilita | Controlla la visualizzazione di link/informazioni relative al modulo nella pagina di configurazione. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Dopo aver abilitato il modulo, il mio negozio non sembra più veloce. Cosa succede?**
R: L'ottimizzazione del database è un pezzo del puzzle delle prestazioni. Sebbene pulisca i dati non necessari, altri fattori come le risorse del server, l'ottimizzazione delle immagini, i moduli pesanti o i temi personalizzati non ottimizzati possono ancora rallentare il tuo negozio. Assicurati di aver anche svuotato la cache di PrestaShop (Parametri avanzati > Prestazioni) dopo la configurazione.

**D: Questo modulo eliminerà dati importanti dei clienti o ordini?**
R: No. Questo modulo è specificamente progettato per eliminare dati *indesiderati* e *inattivi*: carrelli abbandonati, vecchi log di connessione e account guest che non si sono mai convertiti. Non tocca ordini completati, account clienti attivi, dati di prodotto o altre informazioni critiche del negozio.

**D: Con quale frequenza il modulo pulisce il database? È automatico?**
R: Il modulo esegue le sue operazioni di pulizia quando la sua configurazione viene salvata o quando determinate attività in background vengono attivate da PrestaShop. Non è un pulitore continuo e in tempo reale. Il beneficio principale deriva dalla rimozione dei dati vecchi accumulati. Per una pulizia continua e programmata, potresti doverlo combinare con un cron job che attiva periodicamente la logica di pulizia del modulo (anche se questo modulo si concentra principalmente sulla pulizia una tantum o al salvataggio).

**D: Ho disabilitato "Verifica aggiornamenti" e "Notifiche aggiornamenti" ma ora voglio essere informato sugli aggiornamenti. Come li riabilito?**
R: Semplicemente torna alla pagina di configurazione del modulo (Moduli > Gestione moduli > Configura Ottimizzazione del Database) e imposta sia "Verifica aggiornamenti" che "Notifiche aggiornamenti" su "Abilita". Salva le modifiche e il modulo riprenderà a controllare e a notificarti le nuove versioni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Ottimizzazione del Database è un modulo PrestaShop semplice, progettato principalmente per eseguire operazioni di pulizia del database. Segue la struttura standard dei moduli PrestaShop, sfruttando la classe `Module` e i suoi metodi `install()` e `uninstall()` per l'installazione e la disinstallazione. La sua funzionalità principale risiede nel metodo `getContent()`, che gestisce il modulo di configurazione del Back Office e attiva la logica di ottimizzazione del database al momento dell'invio del modulo. Non introduce controller, modelli o risorse front-office personalizzati, rendendolo un'utilità leggera e mirata.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutte le operazioni sono gestite nel Back Office o tramite la classe principale del modulo.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente all'interno del metodo `getContent()` del file `dboptimization.php`.

### 4.3 Classi e modelli principali (`classes/`)

-   **Classe principale del modulo**: `dboptimization/dboptimization.php`
    -   **Nome classe**: `DbOptimization`
    -   **Classe padre**: `Module`
    -   **Responsabilità**:
        -   Gestisce l'installazione (`install()`) e la disinstallazione (`uninstall()`) del modulo.
        -   Gestisce la visualizzazione e l'invio del modulo di configurazione del Back Office (`getContent()`).
        -   Contiene la logica principale per la pulizia del database basata sulle opzioni configurate.
        -   Registra e deregistra gli hook (anche se questo modulo utilizza principalmente `displayBackOfficeHeader` per i controlli degli aggiornamenti, non per la visualizzazione front-office).
        -   Gestisce i valori di configurazione utilizzando `Configuration::get()` e `Configuration::updateValue()`.
        -   Include la logica di controllo degli aggiornamenti (`checkforupdates()`) e la visualizzazione delle notifiche.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   Nessuno. Il modulo renderizza il suo modulo di configurazione direttamente all'interno del metodo `getContent()` utilizzando `HelperForm` di PrestaShop (o una logica di rendering interna simile), piuttosto che file `.tpl` esterni.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Interagisce con le tabelle PrestaShop esistenti, principalmente:
        -   `ps_cart`: Per "Carrelli indesiderati".
        -   `ps_connections`: Per "Connessioni".
        -   `ps_connections_page`: Per "Pagine di connessione".
        -   `ps_connections_source`: Per "Origine connessioni".
        -   `ps_guest`: Per "Ospiti".
    -   I valori di configurazione sono memorizzati nella tabella `ps_configuration`:
        -   `dbopt_cart`
        -   `dbopt_connections`
        -   `dbopt_connections_page`
        -   `dbopt_connections_source`
        -   `dbopt_guest`
        -   `update_dboptimization` (per il timestamp del controllo aggiornamenti)
        -   `mypresta_updates` (impostazione globale delle notifiche di aggiornamento)
        -   `dbopt_check_updates`
        -   `dbopt_updates_notifications`
        -   `dbopt_module_page`
-   **Tabella degli hook registrati**:

| Nome Hook | File / Metodo | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Renderizza nell'intestazione delle pagine del Back Office. | Utilizzato dal modulo per iniettare notifiche di aggiornamento se `dbopt_check_updates` e `dbopt_updates_notifications` sono abilitati. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Eseguito quando un controller admin imposta i suoi media (CSS/JS). | Potenzialmente utilizzato per i controlli degli aggiornamenti o per garantire che tutte le risorse necessarie (se esistenti) siano caricate nell'admin. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto completo per il modulo Ottimizzazione del Database, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto dedicato è disponibile per assistere commercianti e sviluppatori con qualsiasi domanda o problema relativo alla funzionalità e all'integrazione del modulo.
