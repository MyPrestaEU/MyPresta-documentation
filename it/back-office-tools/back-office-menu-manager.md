---
title: "Gestore del menu del Back office - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Gestore del menu del Back office' di MyPresta.eu."
sidebar:
  label: "Gestore del menu del Back office - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Back office menu manager su MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/back-office-menu-manager/)
>
> ---


# Gestore del menu del Back office

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale per il modulo "Gestore del menu del Back office".

Questa schermata contiene tipicamente le impostazioni standard del modulo, che potrebbero includere:

-   **Abilita/Disabilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è un interruttore principale per attivare o disattivare la funzionalità del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Le funzionalità del modulo, incluse le nuove opzioni di gestione del menu, saranno attive nel tuo Back Office.
        -   *Quando disabilitato:* Il modulo smetterà di influenzare il tuo menu del Back Office e riprenderà il comportamento predefinito del menu di PrestaShop.
    -   **Valore consigliato:** **SÌ** (Abilitato) per utilizzare il modulo.
    -   **Scenario/esempio del commerciante:** Se stai testando il modulo o desideri temporaneamente tornare al menu predefinito di PrestaShop, puoi disabilitarlo qui.
-   **Ripristina impostazioni modulo:**

    -   **Cosa fa questa impostazione:** Questa opzione ti consente di ripristinare tutte le impostazioni specifiche del modulo ed eventualmente qualsiasi configurazione di menu personalizzata al loro stato predefinito.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando cliccato:* Tutte le tue disposizioni di menu personalizzate e le preferenze del modulo verranno cancellate, e il modulo si comporterà come se fosse stato appena installato per la prima volta.
    -   **Valore consigliato:** Usare con cautela. Clicca solo se desideri riavviare completamente la configurazione del tuo menu.
    -   **Scenario/esempio del commerciante:** Se hai apportato molte modifiche e vuoi ricominciare da capo, o se incontri un problema imprevisto e vuoi escludere problemi di configurazione, questo può essere un utile passaggio di risoluzione dei problemi.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo introduce una nuova sezione dedicata nel tuo Back Office di PrestaShop per gestire le schede del menu.

#### Nome schermata e posizione menu: AdminMenuTabsController

-   **Posizione menu:** Dopo aver installato il modulo, troverai una nuova voce di menu, tipicamente sotto **Parametri avanzati** o una sezione amministrativa simile, denominata qualcosa come **"Gestore menu"** o **"Menu Back Office"**. Cliccando su questa voce verrai indirizzato alla schermata `AdminMenuTabsController`.
-   **Azioni e impostazioni disponibili:**
    Questa schermata fornisce una vista a griglia (tabella) completa di tutte le schede di menu attualmente disponibili nel tuo Back Office di PrestaShop. Per ogni scheda di menu, vedrai tipicamente:

    -   **ID:** L'identificatore univoco per la scheda di menu.
    -   **Nome:** Il nome visualizzato della scheda di menu (es. "Ordini", "Prodotti", "Clienti").
    -   **Scheda padre:** A quale voce di menu principale appartiene questa scheda (es. "Ordini" è un genitore di "Ordini", "Fatture", "Note di credito").
    -   **Posizione:** L'ordine numerico della scheda all'interno del suo gruppo padre.
    -   **Interruttore Attivo/Inattivo:** Un interruttore per abilitare o disabilitare la visibilità della scheda di menu.
    -   **Azioni Modifica/Elimina:** Pulsanti per modificare i dettagli di una scheda specifica o rimuoverla (usa l'eliminazione con estrema cautela, poiché potrebbe rimuovere funzionalità di base).

    **Funzionalità chiave che puoi eseguire qui:**

    -   **Riordina voci di menu:** Di solito puoi trascinare e rilasciare le righe nella griglia o modificare manualmente il valore 'Posizione' per riordinare l'aspetto delle voci di menu.
    -   **Nascondi/Mostra voci di menu:** Usa l'interruttore attivo/inattivo per nascondere le voci di menu che non usi o che vuoi limitare a determinati ruoli del personale (se combinato con i permessi nativi di PrestaShop).
    -   **Modifica dettagli voce di menu:** Potresti essere in grado di modificare il nome visualizzato di una voce di menu, la sua icona o la sua associazione padre (anche se la modifica delle associazioni padre per le schede principali non è generalmente raccomandata senza conoscenze avanzate).
    -   **Aggiungi nuove voci di menu:** Sebbene meno comune per questo modulo specifico (che si concentra sulla gestione delle schede *esistenti*), alcune versioni avanzate potrebbero consentire l'aggiunta di collegamenti di menu personalizzati.
-   **Effetto delle modifiche:**

    -   **Nascondere una scheda:** La scheda scomparirà immediatamente dal tuo menu del Back Office per tutti gli utenti (a meno che non siano in atto specifiche sovrascritture di permessi).
    -   **Riordinare le schede:** L'ordine delle voci di menu cambierà istantaneamente nella navigazione del Back Office.
    -   **Modificare il nome di una scheda:** Il nome visualizzato nel menu del Back Office si aggiornerà.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Configurazione iniziale:** Esamina tutte le voci del tuo menu principale e le loro sotto-voci. Decidi quali il tuo team usa regolarmente, raramente o mai.
    2.  **Declutter:** Per gli elementi usati raramente o mai, usa l'interruttore "Attivo/Inattivo" per nasconderli. Questo semplifica significativamente il menu.
    3.  **Prioritizza:** Riordina gli elementi a cui si accede frequentemente in modo che siano in cima alle rispettive sezioni. Ad esempio, se trascorri la maggior parte del tuo tempo su "Ordini", assicurati che "Ordini" sia la prima sotto-voce sotto il menu principale "Ordini".
    4.  **Revisiona regolarmente:** Man mano che le operazioni del tuo negozio si evolvono o vengono installati nuovi moduli (che spesso aggiungono le proprie voci di menu), rivisita questa schermata per mantenere il tuo menu ottimizzato.

#### Nome schermata e posizione menu: index.php (adminmenu/controllers/admin/index.php)

Questo file, `index.php` all'interno di una directory del controller di amministrazione, serve tipicamente come segnaposto o punto di ingresso per la funzionalità del controller, piuttosto che come schermata autonoma con opzioni configurabili. In PrestaShop, la logica e la visualizzazione effettive per un controller di amministrazione sono gestite dalla classe principale (es. `AdminMenuTabsController.php`).

Pertanto, non interagirai direttamente con una schermata "index.php". La sua presenza fa parte della struttura interna del modulo, garantendo che `AdminMenuTabsController` funzioni correttamente. Tutte le tue interazioni avverranno tramite l'interfaccia `AdminMenuTabsController` descritta sopra.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita/Disabilita Modulo | Abilitato | Attiva/disattiva le funzionalità di gestione del menu del modulo. |
| Configurazione modulo | Ripristina impostazioni modulo | N/A (Azione) | Ripristina tutte le impostazioni del modulo e le configurazioni del menu ai valori predefiniti. Usare con cautela. |
| AdminMenuTabsController | Nome scheda (es. "Ordini") | Nome PrestaShop originale | Visualizza il nome della voce di menu. Può essere modificato. |
| AdminMenuTabsController | Scheda padre | Padre PrestaShop originale | Mostra la categoria del menu principale per questa voce. |
| AdminMenuTabsController | Posizione | Varia | Controlla l'ordine di visualizzazione della voce di menu all'interno del suo genitore. Può essere modificato tramite trascinamento o input diretto. |
| AdminMenuTabsController | Interruttore Attivo/Inattivo | Attivo | Attiva/disattiva la visibilità della voce di menu nel Back Office. |
| AdminMenuTabsController | Azioni Modifica/Elimina | N/A (Azione) | Consente la modifica dei dettagli della scheda o la rimozione (eliminare con cautela). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho nascosto una voce di menu, ma continua a essere visualizzata per alcuni utenti. Perché?**
R: Questo modulo gestisce la *visibilità* e l'*ordine* delle voci di menu. I permessi utente nativi di PrestaShop (sotto **Parametri avanzati > Team > Profili** e **Permessi**) determinano *chi può accedere a cosa*. Se un profilo utente ha un permesso esplicito per una scheda, potrebbe comunque vederla anche se l'hai contrassegnata come inattiva in questo modulo. Controlla sempre sia le impostazioni di questo modulo che i permessi di PrestaShop.

**D: Ho apportato modifiche, ma il menu non si è aggiornato. Cosa devo fare?**
R:

1.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni**. Clicca su "Svuota la cache" nell'angolo in alto a destra. Questo è spesso necessario affinché le modifiche al Back Office abbiano effetto.
2.  **Aggiorna il browser:** A volte è necessario un aggiornamento forzato del browser (Ctrl+F5 o Cmd+Shift+R) per svuotare la cache locale del browser.
3.  **Controlla lo stato del modulo:** Assicurati che il modulo "Gestore del menu del Back office" sia ancora abilitato in **Moduli > Gestione moduli**.

**D: Posso aggiungere collegamenti personalizzati completamente nuovi al menu del Back Office con questo modulo?**
R: Questo modulo si concentra principalmente sulla gestione delle schede di menu *esistenti* di PrestaShop. Sebbene alcune versioni avanzate possano offrire la creazione di collegamenti personalizzati, il suo scopo principale è quello di consentire la gestione della struttura del menu predefinita di PrestaShop. Se hai bisogno di aggiungere collegamenti personalizzati complessi, potresti richiedere un modulo più avanzato o uno sviluppo personalizzato.

**D: Ho accidentalmente eliminato una voce di menu principale di PrestaShop. Come faccio a recuperarla?**
R: L'eliminazione di voci di menu principali non è generalmente consigliata. Se l'hai fatto, il modo più sicuro per ripristinarla è:

1.  **Disabilita e riabilita il modulo:** Vai su **Moduli > Gestione moduli**, trova "Gestore del menu del Back office", disabilitalo e poi riabilitalo. Questo spesso innesca una re-inizializzazione delle voci di menu predefinite.
2.  **Ripristina le impostazioni del modulo:** Se quanto sopra non funziona, vai alla pagina di configurazione del modulo e usa l'opzione "Ripristina impostazioni modulo". Tieni presente che questo cancellerà TUTTE le tue configurazioni di menu personalizzate.
3.  **Ripristina da backup:** Come ultima risorsa, se mancano voci di menu critiche, potresti dover ripristinare il tuo database da un backup effettuato *prima* dell'eliminazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo "Gestore del menu del Back office".

### 4.1 Panoramica dell'architettura

Il modulo "Gestore del menu del Back office" estende principalmente la funzionalità principale del Back Office di PrestaShop sovrascrivendo classi helper specifiche per reintrodurre le capacità di gestione del menu. Sfrutta il pattern MVC di PrestaShop, con un controller Admin dedicato (`AdminMenuTabsController`) per fornire l'interfaccia utente per la gestione delle schede di menu. Il modulo interagisce con la tabella del database `ps_tab`, che memorizza le informazioni sulle voci di menu del Back Office. La decisione architettonica chiave è l'uso di override per modificare il comportamento principale di PrestaShop senza alterare direttamente i file principali, garantendo una migliore compatibilità e percorsi di aggiornamento.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    Questo modulo non contiene alcun controller front-office poiché la sua funzionalità è esclusivamente per il Back Office di PrestaShop.
-   **Controller Admin Back-Office**:

    -   `adminmenu/controllers/admin/AdminMenuTabs.php`

        -   **Nome classe e classe padre**: `AdminMenuTabsController` estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita**: Questo controller gestisce l'entità `Tab` (che rappresenta le voci di menu del Back Office). Crea una voce di menu dedicata nel Back Office per "Gestore menu".
        -   **Responsabilità**: Questo è il controller principale per l'interfaccia utente del modulo. Gestisce la visualizzazione dell'elenco di tutte le schede del Back Office, consentendo agli amministratori di visualizzarle, modificarle, abilitarle/disabilitarle e riordinarle. Tipicamente utilizza `HelperList` per la visualizzazione della griglia e `HelperForm` per eventuali moduli di modifica. Elabora le richieste POST per il salvataggio delle modifiche (es. aggiornamenti di posizione, attivazione/disattivazione dello stato).
    -   `adminmenu/controllers/admin/index.php`

        -   **Responsabilità**: Questo file è un segnaposto standard all'interno della struttura del controller di PrestaShop. Tipicamente contiene una semplice istruzione `die('No direct script access allowed');` per impedire l'accesso diretto alla directory e garantire che le richieste siano instradate tramite il dispatcher di PrestaShop. Non contiene alcuna logica funzionale per il modulo stesso.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo utilizza override per modificare il comportamento principale di PrestaShop.

-   `adminmenu/override/classes/helper/HelperList.php`

    -   **Nome classe e classe padre**: `HelperList` (sovrascrive la classe `HelperList` principale).
    -   **Cosa fa**: Questo override probabilmente modifica il comportamento di `HelperList` specificamente quando si rende l'elenco delle entità `Tab` nel Back Office. Questo è cruciale per riabilitare funzionalità come il riordino tramite trascinamento o visualizzazioni di colonne specifiche che sono state rimosse dall'implementazione predefinita di `HelperList` per `Tab` nelle versioni più recenti di PrestaShop. Potrebbe iniettare azioni personalizzate o modificare il modo in cui i dati vengono recuperati o visualizzati per le schede di menu.
-   `adminmenu/override/classes/helper/index.php`

    -   **Responsabilità**: Simile a `controllers/admin/index.php`, questo è un file segnaposto per impedire l'elenco o l'accesso diretto alla directory.
-   `adminmenu/override/classes/index.php`

    -   **Responsabilità**: Un altro file segnaposto per impedire l'elenco o l'accesso diretto alla directory.

### 4.4 Risorse JavaScript (`views/js/`)

L'inventario fornito indica l'assenza di file JavaScript personalizzati all'interno del modulo. Ciò suggerisce che la funzionalità di gestione del menu, incluse funzionalità come il riordino tramite trascinamento, è gestita da:

1.  JavaScript nativo di `HelperList` di PrestaShop (che l'override del modulo potrebbe riabilitare o configurare).
2.  Elaborazione lato server per gli aggiornamenti di posizione.
3.  JS inline minimo generato dalle classi `HelperList` o `HelperForm`.

Gli sviluppatori dovrebbero ispezionare l'HTML generato e le richieste di rete sulla pagina `AdminMenuTabsController` per comprendere l'esatta implementazione JS per gli elementi interattivi.

### 4.5 Fogli di stile CSS (`views/css/`)

L'inventario fornito indica l'assenza di file CSS personalizzati all'interno del modulo. Ciò implica che il modulo si basa interamente sullo stile predefinito del Back Office di PrestaShop. Qualsiasi stile personalizzato per l'interfaccia del gestore del menu sarebbe:

1.  Iniettato inline tramite template Smarty o PHP.
2.  Sfruttando le classi CSS esistenti di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

L'inventario fornito indica l'assenza di file di template Smarty personalizzati (`.tpl`) all'interno del modulo. Questo è un forte indicatore che il modulo si basa principalmente sui template predefiniti di `HelperList` e `HelperForm` di PrestaShop per il rendering della sua interfaccia Back Office.

Il `AdminMenuTabsController` istanzierebbe oggetti `HelperList` e `HelperForm`, passando loro array di configurazione, e questi helper quindi renderizzerebbero l'interfaccia utente utilizzando i template principali di PrestaShop (es. `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Questo modulo interagisce principalmente con la tabella principale esistente di PrestaShop:

    -   `ps_tab`: Questa tabella memorizza tutte le voci di menu del Back Office, inclusi i loro nomi, ID padre, posizioni e stato attivo. Il `AdminMenuTabsController` del modulo e l'override di `HelperList` leggono e scrivono direttamente in questa tabella per gestire il menu.
    -   `ps_configuration`: Tabella di configurazione standard di PrestaShop. Le impostazioni di configurazione principali del modulo (es. stato di abilitazione/disabilitazione) verrebbero memorizzate qui (es. `PS_ADMINMENU_MANAGER_ENABLED`).
-   **Tabella degli hook registrati**:
    Basandosi sulla descrizione e sulla funzionalità del modulo, non registra esplicitamente alcun hook di visualizzazione front-office o back-office (`displayHeader`, `actionValidateOrder`, ecc.) nel senso tradizionale. La sua funzionalità è ottenuta tramite:

    1.  **Registrazione del controller Admin**: Il modulo registra `AdminMenuTabsController` come nuova scheda del Back Office, rendendolo accessibile tramite il menu del Back Office.
    2.  **Override di classe**: Il meccanismo principale si basa sulla sovrascrittura di `classes/helper/HelperList.php` per modificare il modo in cui le schede di menu vengono gestite e visualizzate nel Back Office. Questo non è un "hook" ma una modifica diretta del comportamento principale.

    Pertanto, una tabella degli hook registrati non è applicabile nel senso tipico per questo modulo. Il suo impatto è sul funzionamento interno del rendering del menu del Back Office.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Gestore del menu del Back office", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
