---
title: "Delete Orders Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Delete Orders Pro di MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Delete Orders Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai reindirizzato alla pagina di configurazione principale del modulo "Delete Orders Pro". Questa schermata gestisce principalmente le impostazioni generali del modulo e i controlli degli aggiornamenti.

-   **Cosa fa questa impostazione:** Questa sezione include tipicamente le impostazioni standard dei moduli MyPresta.eu relative alle notifiche di aggiornamento e al tracciamento interno.
-   **Effetto della modifica di questa impostazione:**
    -   `mypresta_updates`, `update_`, `updatev_`: Queste impostazioni controllano se il modulo verifica la presenza di aggiornamenti da MyPresta.eu e visualizza le notifiche nel tuo back office. Abilitandole, sarai informato sulle nuove versioni e funzionalità. Disabilitandole, queste notifiche verranno interrotte.
    -   `DELETEORDERS_LAST_TAB`: Questa è un'impostazione interna che tiene traccia dell'ultima scheda o visualizzazione in cui ti trovavi all'interno dell'interfaccia di amministrazione dedicata del modulo. Aiuta il modulo a ricordare la tua ultima posizione per comodità.
-   **Valore consigliato:**
    -   Per le impostazioni relative agli aggiornamenti: **SÌ** (o Abilitato). Si consiglia sempre di mantenere abilitati i controlli degli aggiornamenti per assicurarsi di utilizzare la versione più recente, sicura e ricca di funzionalità del modulo.
    -   `DELETEORDERS_LAST_TAB`: Lascia questa impostazione così com'è; è gestita automaticamente dal modulo.
-   **Scenario/esempio del commerciante:** Mantenere abilitati i controlli degli aggiornamenti significa che riceverai una notifica direttamente nel tuo back office PrestaShop quando viene rilasciata una nuova versione di "Delete Orders Pro", assicurandoti di poter facilmente aggiornare e beneficiare di miglioramenti o correzioni di bug.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Scheda Elimina Ordini (Back Office > Ordini > Delete Orders Pro)

Questa è l'interfaccia principale dove gestirai ed eliminerai gli ordini.

-   **Nome schermata e posizione menu:** Puoi accedere a questa schermata navigando su **Ordini > Delete Orders Pro** nel menu del tuo back office PrestaShop.
-   **Azioni e impostazioni disponibili:** Questa schermata presenta una vista a griglia o a elenco dei tuoi ordini, simile all'elenco standard degli ordini di PrestaShop, ma con funzionalità aggiuntive specificamente per l'eliminazione.
    -   **Opzioni di filtro:** Probabilmente troverai filtri per restringere gli ordini che desideri eliminare (ad esempio, per stato dell'ordine, intervallo di date, cliente, ecc.). Questo è cruciale per mirare in modo sicuro a tipi specifici di ordini.
    -   **Caselle di controllo di selezione:** Ogni ordine nell'elenco avrà una casella di controllo, che ti consentirà di selezionare singoli ordini per l'eliminazione.
    -   **Azioni di massa:** Dovrebbe esserci un'opzione per selezionare più ordini (ad esempio, "Seleziona tutto" o "Seleziona ordini con stato X") e quindi eseguire un'eliminazione di massa.
    -   **Pulsante Elimina:** Un pulsante prominente (ad esempio, "Elimina ordini selezionati" o "Elimina ordini") avvierà il processo di eliminazione.
-   **Effetto delle modifiche:**
    -   Quando selezioni gli ordini e fai clic sul pulsante di eliminazione, il modulo rimuoverà permanentemente tali ordini e tutti i dati associati (dettagli dell'ordine, prodotti ordinati, messaggi del cliente relativi all'ordine, fatture, ecc.) dal tuo database PrestaShop.
    -   Questa azione è irreversibile.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Rivedi regolarmente i tuoi ordini:** Identifica quali stati degli ordini rappresentano comunemente ordini "indesiderati" (ad esempio, "Annullato", "Errore di pagamento", "In riordino" se non evasi, o stati personalizzati per ordini di test).
    2.  **Accedi a "Delete Orders Pro":** Vai su **Ordini > Delete Orders Pro**.
    3.  **Filtra gli ordini:** Utilizza i filtri disponibili per visualizzare solo gli ordini che intendi eliminare (ad esempio, filtra per stato "Annullato" e un intervallo di date precedente a 3 mesi).
    4.  **Seleziona attentamente gli ordini:** Ricontrolla gli ordini che hai filtrato e selezionali utilizzando le caselle di controllo.
    5.  **Avvia l'eliminazione:** Fai clic sul pulsante "Elimina ordini selezionati". Conferma l'azione quando richiesto.
    6.  **Esegui backup:** Prima di qualsiasi eliminazione importante, assicurati sempre di avere un backup recente del database.

#### 2.2.2 Controller Index (deleteorderspro/controllers/admin/index.php)

Questo file funge tipicamente da controller di routing o di fallback all'interno della sezione amministrativa del modulo. Nel contesto di "Delete Orders Pro", probabilmente assicura che se un utente naviga al percorso amministrativo di base del modulo senza specificare un'azione o un sub-controller particolare, venga reindirizzato all'interfaccia principale `deleteorderstab`.

-   **Nome schermata e posizione menu:** Non una schermata diretta, ma parte della navigazione interna del modulo.
-   **Azioni e impostazioni disponibili:** Nessuna impostazione configurabile direttamente dall'utente. Il suo scopo è gestire il routing interno.
-   **Effetto delle modifiche:** Nessun impatto diretto sul commerciante. Garantisce un'esperienza di navigazione fluida all'interno della sezione amministrativa del modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Nessun flusso di lavoro specifico necessario; questo opera in background.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | `mypresta_updates` | SÌ | Abilita/disabilita le notifiche di aggiornamento da MyPresta.eu. |
| | `update_` | SÌ | Flag interno per lo stato dell'aggiornamento. |
| | `updatev_` | SÌ | Flag interno per la versione dell'aggiornamento. |
| | `DELETEORDERS_LAST_TAB` | (Gestito automaticamente) | Traccia l'ultima scheda visitata nell'interfaccia di amministrazione del modulo. |
| **Scheda Elimina Ordini** | Filtri (Stato, Data, ecc.) | Varia | Restringe l'elenco degli ordini da eliminare. |
| | Caselle di selezione ordini | N/A | Consente la selezione di singoli ordini per l'eliminazione. |
| | Azione di massa: Elimina selezionati | N/A | Rimuove permanentemente gli ordini selezionati e i dati associati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho eliminato gli ordini, ma le prestazioni del mio negozio non sembrano molto più veloci. Perché?**
R: Sebbene l'eliminazione degli ordini riduca le dimensioni del database, le prestazioni sono influenzate da molti fattori (hosting, altri moduli, ottimizzazione del tema, dimensioni delle immagini). L'eliminazione degli ordini è un passo nell'ottimizzazione generale. Assicurati di aver anche svuotato la cache di PrestaShop (**Parametri Avanzati > Prestazioni**) dopo l'eliminazione.

**D: Posso recuperare gli ordini dopo averli eliminati?**
R: No. Una volta che gli ordini vengono eliminati utilizzando questo modulo, vengono rimossi permanentemente dal tuo database. Questo è il motivo per cui è fondamentale eseguire sempre il backup del database prima di eseguire qualsiasi eliminazione importante e di rivedere attentamente le tue selezioni.

**D: L'eliminazione degli ordini influirà sugli account dei miei clienti o sulle scorte dei prodotti?**
R: L'eliminazione di un ordine rimuove il record dell'ordine stesso e i dettagli associati (come i prodotti specifici ordinati all'interno di quella transazione, fatture, messaggi). NON elimina l'account cliente associato all'ordine, né di solito ripristina i livelli di stock (poiché lo stock viene solitamente regolato al momento della creazione dell'ordine o della modifica dello stato, non dell'eliminazione). Verifica sempre il comportamento del modulo in un ambiente di test se hai preoccupazioni specifiche sullo stock.

**D: Il modulo non compare nel menu del mio Back Office.**
R:

1.  **Verifica l'installazione:** Vai su **Moduli > Gestione moduli** e cerca "Delete Orders Pro". Assicurati che sia elencato come "Installato" e "Abilitato".
2.  **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache". A volte, le modifiche al menu richiedono un aggiornamento della cache.
3.  **Permessi:** Controlla i tuoi permessi utente in **Amministrazione > Permessi** per assicurarti che il tuo profilo abbia accesso alla sezione "Ordini" e a qualsiasi permesso specifico del modulo.

**D: Ricevo un errore quando cerco di eliminare gli ordini.**
R:

1.  **Controlla la modalità Debug di PrestaShop:** Abilita la modalità debug (**Parametri Avanzati > Prestazioni > Modalità debug**) per vedere se appare un messaggio di errore più dettagliato.
2.  **Log degli errori del server:** Controlla i log degli errori PHP del tuo server (spesso disponibili nel pannello di controllo del tuo hosting) per eventuali messaggi correlati.
3.  **Contatta il supporto:** Se non riesci a risolvere il problema, raccogli eventuali messaggi di errore e contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo "Delete Orders Pro".

### 4.1 Panoramica dell'architettura

Il modulo "Delete Orders Pro" segue l'architettura standard dei moduli PrestaShop, sfruttando principalmente i Controller Amministrativi del Back-Office per la sua funzionalità. Si integra nel sistema di menu di PrestaShop e utilizza il `AdminController` core di PrestaShop per il rendering degli elenchi e la gestione delle sottomissioni di moduli. Il modulo interagisce direttamente con il database per eseguire operazioni di eliminazione sulle tabelle relative agli ordini. Non introduce classi `ObjectModel` personalizzate, ma opera su entità di ordine PrestaShop esistenti.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Questo modulo non ha presenza nel front-office.
-   **Controller Amministrativi Back-Office**:

    -   `deleteorderspro/controllers/admin/deleteorderstab.php`

        -   **Nome classe**: `AdminDeleteOrdersProController` (o simile, tipicamente derivato dal nome del file e dal contesto del modulo) che estende `ModuleAdminController`.
        -   **Responsabilità**: Questo è il controller amministrativo principale per il modulo. È responsabile di:
            -   Visualizzare l'elenco degli ordini in formato griglia.
            -   Gestire il filtraggio, l'ordinamento e la paginazione degli ordini.
            -   Elaborare l'eliminazione degli ordini selezionati.
            -   Interagire con gli `Order` e gli `ObjectModel` correlati di PrestaShop per eseguire eliminazioni dal database.
            -   Renderizzare il template per l'elenco degli ordini e l'interfaccia di eliminazione.
        -   **Scheda PrestaShop**: Questo controller è registrato come nuova scheda sotto il menu "Ordini" nel back office di PrestaShop.
    -   `deleteorderspro/controllers/admin/index.php`

        -   **Nome classe**: Non una tipica classe controller; spesso un semplice reindirizzamento o file di bootstrap.
        -   **Responsabilità**: Questo file funge tipicamente da fallback o punto di ingresso. In molti moduli, se un utente naviga al percorso base `admin/nome_modulo`, questo `index.php` potrebbe reindirizzarlo al controller primario (ad esempio, `deleteorderstab`) per garantire che l'interfaccia corretta venga caricata. Previene l'accesso diretto alla directory e garantisce un routing corretto.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non sembra introdurre classi o `ObjectModel` personalizzati nella sua directory `classes/` in base all'inventario fornito. Probabilmente opera direttamente sugli `Order` e sugli `ObjectModel` correlati di PrestaShop (ad esempio, `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart`, ecc.) per garantire l'eliminazione completa di tutti i dati associati.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript è stato identificato nell'archivio del modulo. Il modulo probabilmente si basa sul JavaScript standard del back-office di PrestaShop per l'invio di moduli e le interazioni con la griglia, oppure la sua funzionalità è interamente lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS è stato identificato nell'archivio del modulo. Il modulo probabilmente eredita lo stile direttamente dal tema del back-office di PrestaShop, garantendo un aspetto e una sensazione coerenti senza stili personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

Nessun file `.tpl` è stato identificato nell'archivio del modulo. Ciò suggerisce che il modulo potrebbe utilizzare i template predefiniti `list.tpl` e `form.tpl` forniti da `AdminController` per il rendering della sua griglia e configurazione, oppure genera il suo HTML direttamente all'interno del controller.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Opera su tabelle PrestaShop esistenti relative agli ordini, incluse ma non limitate a:

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_order_return`
    -   `ps_order_slip`
    -   `ps_cart` (e `ps_cart_product` correlato)
    -   `ps_message` (per i messaggi dei clienti relativi agli ordini)
    -   `ps_product_sale` (aggiorna il conteggio delle vendite)
    -   `ps_customer_thread` (per i thread del servizio clienti relativi agli ordini)
    -   `ps_configuration` (per memorizzare le impostazioni del modulo come `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
-   **Tabella degli hook registrati**:
    Basandosi sullo scopo del modulo come strumento di amministrazione del back-office, utilizza principalmente gli hook per l'installazione, la disinstallazione e potenzialmente l'aggiunta di voci di menu. Non sembra utilizzare hook di visualizzazione del front-office.

    | Nome Hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `install()` | Durante l'installazione del modulo | Crea la nuova scheda "Delete Orders Pro" nel menu del back office di PrestaShop. Memorizza i valori di configurazione iniziali in `ps_configuration`. |
    | `uninstall()` | Durante la disinstallazione del modulo | Rimuove la scheda "Delete Orders Pro" dal menu del back office. Elimina i valori di configurazione da `ps_configuration`. |
    | `displayBackOfficeHeader` | Renderizza il contenuto nella sezione `<head>` del Back Office | Potenzialmente utilizzato per includere eventuali JS/CSS necessari per il controller amministrativo, sebbene nessuno sia stato identificato nell'inventario. |
    | `actionAdminControllerSetMedia` | Consente di aggiungere JS/CSS a specifici controller amministrativi | Utilizzato da `AdminDeleteOrdersProController` per aggiungere eventuali risorse specifiche richieste per la sua interfaccia. |

## 5. Supporto ufficiale e aggiornamenti

Per il supporto ufficiale, gli aggiornamenti e per scaricare l'ultima versione del modulo "Delete Orders Pro", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità del modulo.
