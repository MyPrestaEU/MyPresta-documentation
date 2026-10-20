---
title: "Caselle di controllo aggiuntive durante la registrazione - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Caselle di controllo aggiuntive durante la registrazione' di MyPresta.eu."
sidebar:
  label: "Caselle di controllo aggiuntive durante la registrazione - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Additional checkboxes during register su MyPresta.eu](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/additional-checkboxes-during-register/)
>
> ---


# Caselle di controllo aggiuntive durante la registrazione

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili nella maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile cliccando su "Configura" dopo l'installazione.

-   **Cosa fa questa impostazione:** Questa schermata gestisce principalmente le impostazioni generali del modulo e ti consente di gestire gli aggiornamenti.
-   **Effetto della modifica di questa impostazione:**
    -   `mypresta_updates`: Questa è un'impostazione generale per i moduli MyPresta.eu per verificare la presenza di aggiornamenti.
        -   *Quando abilitato:* Il modulo controllerà periodicamente MyPresta.eu per nuove versioni, notificandoti nel Back Office se è disponibile un aggiornamento. Questo ti aiuta a mantenere il tuo modulo sicuro e aggiornato con le ultime funzionalità e correzioni di bug.
        -   *Quando disabilitato:* Il modulo non controllerà automaticamente la presenza di aggiornamenti. Dovrai controllare manualmente il tuo account MyPresta.eu per nuove versioni.
    -   `update_`: Questa impostazione è correlata alla funzionalità di controllo degli aggiornamenti.
    -   `updatev_`: Questa impostazione è correlata alla funzionalità di controllo degli aggiornamenti.
-   **Valore consigliato:** Per `mypresta_updates`, è generalmente **consigliato mantenerlo abilitato** per assicurarti di essere sempre informato sulle ultime versioni del modulo. Le altre due impostazioni sono interne e dovrebbero generalmente essere lasciate così come sono.
-   **Scenario / esempio del commerciante:** Vuoi assicurarti che il tuo negozio esegua sempre la versione più sicura e ricca di funzionalità del modulo. L'abilitazione dei controlli degli aggiornamenti significa che sarai avvisato direttamente nell'amministrazione di PrestaShop quando viene rilasciata una nuova versione, rendendo facile rimanere aggiornati.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminAddTosListController (Back Office > Moduli > Caselle di controllo aggiuntive > Elenco caselle di controllo)

Questa schermata è dove definisci e gestisci tutte le singole caselle di controllo che appariranno durante la registrazione del cliente.

-   **Nome schermata e posizione nel menu:** Puoi trovare questa schermata navigando su **Moduli > Caselle di controllo aggiuntive > Elenco caselle di controllo** nel menu del Back Office di PrestaShop.
-   **Azioni e impostazioni disponibili:**
    -   **Elenco delle caselle di controllo:** Questa pagina visualizza una tabella di tutte le caselle di controllo personalizzate che hai creato. Ogni riga mostra il nome della casella di controllo, se è obbligatoria, il suo stato (abilitata/disabilitata) e la sua posizione.
    -   **Aggiungi nuova casella di controllo:** Ci sarà un pulsante (es. "Aggiungi nuova casella di controllo" o un'icona più) per creare una nuova casella di controllo. Quando aggiungi/modifica una casella di controllo, tipicamente configurerai:
        -   **Nome/Etichetta:** Il testo che appare accanto alla casella di controllo (es. "Accetto l'Informativa sulla Privacy"). Questo dovrebbe essere chiaro e conciso.
        -   **Link (Opzionale):** Un URL a una pagina (es. la tua pagina dell'Informativa sulla Privacy, una pagina di termini specifici) che i clienti possono cliccare per leggere i dettagli completi. Questo è cruciale per la trasparenza.
        -   **Obbligatorio:** Un interruttore (Sì/No) per determinare se il cliente *deve* spuntare questa casella per completare la registrazione.
            -   *Quando abilitato (Sì):* I clienti non possono registrarsi senza spuntare questa casella. Questo è ideale per accordi legali essenziali.
            -   *Quando disabilitato (No):* I clienti possono registrarsi anche se non spuntano questa casella. Questo è adatto per consensi opzionali come le iscrizioni alla newsletter.
        -   **Attivo:** Un interruttore (Sì/No) per abilitare o disabilitare la visualizzazione della casella di controllo nel front office.
            -   *Quando abilitato (Sì):* La casella di controllo sarà visibile nel modulo di registrazione.
            -   *Quando disabilitato (No):* La casella di controllo sarà nascosta dal modulo di registrazione ma mantenuta nel Back Office per un uso futuro.
        -   **Posizione:** Un numero intero per controllare l'ordine in cui le caselle di controllo appaiono nel modulo di registrazione. I numeri più bassi appaiono più in alto.
    -   **Modifica/Elimina:** Ogni casella di controllo nell'elenco avrà azioni per modificarne i dettagli o eliminarla completamente.
-   **Effetto delle modifiche:**
    -   **Aggiunta di una nuova casella di controllo:** La nuova casella di controllo apparirà immediatamente nel modulo di registrazione del cliente (se attiva) e nella pagina "Le mie informazioni personali" del cliente.
    -   **Modifica di una casella di controllo:** Le modifiche all'etichetta, al link, allo stato obbligatorio o allo stato attivo verranno riflesse istantaneamente nel front office.
    -   **Eliminazione di una casella di controllo:** La casella di controllo verrà rimossa dal front office. I consensi esistenti dei clienti per questa specifica casella di controllo rimarranno registrati nella cronologia, ma non potranno essere forniti nuovi consensi.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Identifica le esigenze di consenso:** Prima di aggiungere, determina quali consensi specifici ti servono (es. Informativa sulla Privacy, Newsletter, Verifica dell'età, termini di servizio specifici).
    2.  **Crea pagine di contenuto:** Assicurati di avere pagine CMS dedicate (o link esterni) per ogni politica o termine a cui vuoi collegarti.
    3.  **Aggiungi caselle di controllo:** Vai su "Elenco caselle di controllo" e clicca su "Aggiungi nuova casella di controllo". Compila l'etichetta, il link, impostala come obbligatoria/opzionale e attivala.
    4.  **Ordina le caselle di controllo:** Usa il campo "Posizione" per disporle logicamente.
    5.  **Rivedi il Front Office:** Testa sempre il processo di registrazione nel front office del tuo negozio dopo aver apportato modifiche per assicurarti che tutto venga visualizzato e funzioni come previsto.

#### AdminAddTosHistoryController (Back Office > Moduli > Caselle di controllo aggiuntive > Cronologia)

Questa schermata fornisce un registro storico dei consensi dei clienti per ogni casella di controllo.

-   **Nome schermata e posizione nel menu:** Puoi trovare questa schermata navigando su **Moduli > Caselle di controllo aggiuntive > Cronologia** nel menu del Back Office di PrestaShop.
-   **Azioni e impostazioni disponibili:**
    -   **Tabella Cronologia Consensi:** Questa pagina visualizza un registro dettagliato di quando ogni cliente ha accettato (o non accettato) una specifica casella di controllo.
    -   **Le colonne tipicamente includono:**
        -   **Nome Cliente:** Il nome del cliente.
        -   **Nome Casella di Controllo:** L'etichetta della casella di controllo con cui hanno interagito.
        -   **Stato Consenso:** Se hanno accettato (spuntato) o rifiutato (non spuntato) la casella.
        -   **Data:** Il timestamp di quando il consenso è stato registrato.
        -   **Indirizzo IP:** L'indirizzo IP da cui è stato dato il consenso (importante per la conformità legale).
    -   **Filtro/Ricerca:** Di solito puoi filtrare questo elenco per cliente, casella di controllo o intervallo di date per trovare record di consenso specifici.
-   **Effetto delle modifiche:** Questa schermata è principalmente per la visualizzazione e l'audit. Non puoi modificare direttamente i record di consenso qui, poiché rappresentano fatti storici.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   **Audit e Conformità:** Usa questa schermata per verificare i consensi dei clienti in caso di controversie o per audit di conformità interni.
    -   **Richieste sulla Privacy dei Dati:** Se un cliente richiede di sapere quali dati detieni o a cosa ha acconsentito, questa cronologia fornisce un registro chiaro.

#### index.php (addtos/controllers/admin/index.php)

Questo file è un segnaposto e tipicamente contiene un semplice `header('Location: ../../../index.php?controller=AdminHome');` o un reindirizzamento simile per impedire l'accesso diretto alla directory. Non rappresenta una schermata configurabile per il commerciante.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Controllo Aggiornamenti MyPresta.eu | Abilitato | Ti notifica le nuove versioni del modulo per sicurezza e funzionalità. |
| **Elenco Caselle di Controllo** | Nome/Etichetta Casella di Controllo | N/A (Definito dall'utente) | Il testo visibile accanto alla casella di controllo nel modulo di registrazione. |
| **Elenco Caselle di Controllo** | Link (URL) | N/A (Definito dall'utente) | URL a una pagina di policy; fornisce dettagli per la casella di controllo. |
| **Elenco Caselle di Controllo** | Obbligatorio | No (Opzionale) | Se Sì, il cliente *deve* spuntare per registrarsi. Se No, è opzionale. |
| **Elenco Caselle di Controllo** | Attivo | Sì | Se Sì, la casella di controllo è visibile nel front office. Se No, è nascosta. |
| **Elenco Caselle di Controllo** | Posizione | N/A (Definito dall'utente) | Determina l'ordine di visualizzazione delle caselle di controllo nel modulo. |
| **Cronologia** | Nome Cliente | N/A (Sola lettura) | Mostra quale cliente ha dato il consenso. |
| **Cronologia** | Nome Casella di Controllo | N/A (Sola lettura) | Mostra quale casella di controllo è stata interagita. |
| **Cronologia** | Stato Consenso | N/A (Sola lettura) | Mostra se il cliente ha accettato o rifiutato. |
| **Cronologia** | Data | N/A (Sola lettura) | Timestamp del record di consenso. |
| **Cronologia** | Indirizzo IP | N/A (Sola lettura) | Indirizzo IP da cui è stato dato il consenso. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho aggiunto una nuova casella di controllo, ma non appare nella pagina di registrazione.**
**R1:**

-   **Controlla lo stato "Attivo":** Vai su **Moduli > Caselle di controllo aggiuntive > Elenco caselle di controllo** e assicurati che l'interruttore "Attivo" per la tua casella di controllo sia impostato su "Sì".
-   **Svuota la cache:** A volte la cache di PrestaShop può impedire la visualizzazione immediata di nuovi contenuti. Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Svuota la cache" e clicca su "Svuota la cache".
-   **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo di solito gestisca questo automaticamente, se hai apportato modifiche al tema, potrebbe essere utile controllare gli hook del modulo in **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti). Il modulo tipicamente utilizza `displayAdditionalCustomerFormFields` o hook simili.

**D2: Il testo della mia casella di controllo è troppo lungo e appare male su mobile.**
**R2:**

-   **Sii conciso:** Cerca di accorciare l'etichetta della casella di controllo alla sua essenza (es. "Accetto l'Informativa sulla Privacy" invece di "Ho letto e accetto i termini e le condizioni dell'informativa sulla privacy di questo sito web").
-   **Usa i link:** Inserisci le informazioni dettagliate in una pagina CMS separata e collegala dall'etichetta della casella di controllo. Questo mantiene il modulo pulito fornendo piena trasparenza.
-   **Personalizzazione del tema:** Se il problema persiste, il CSS del tuo tema potrebbe limitare la visualizzazione. Un webmaster può regolare il CSS per le classi `.addtos-checkbox` o simili per migliorare la reattività.

**D3: Posso tradurre le etichette delle caselle di controllo in diverse lingue?**
**R3:** Sì! Quando modifichi una casella di controllo in **Moduli > Caselle di controllo aggiuntive > Elenco caselle di controllo**, dovresti vedere un selettore di lingua accanto al campo "Nome/Etichetta" (spesso un'icona a bandiera). Clicca sulla bandiera per passare a un'altra lingua e inserisci il testo tradotto per quella lingua. Ricorda di salvare le modifiche per ogni lingua.

**D4: Cosa succede se elimino una casella di controllo? Elimina la cronologia dei consensi del cliente?**
**R4:** No, l'eliminazione di una casella di controllo dall'"Elenco caselle di controllo" la rimuoverà dal modulo di registrazione del front-office, ma **non eliminerà i record di consenso storici** che i clienti hanno precedentemente dato per quella casella di controllo. Tali record rimangono nella sezione "Cronologia" per scopi di audit e conformità. I nuovi clienti semplicemente non vedranno più quella casella di controllo.

**D5: Voglio cambiare l'ordine delle caselle di controllo nella pagina di registrazione.**
**R5:** Vai su **Moduli > Caselle di controllo aggiuntive > Elenco caselle di controllo**. Nella tabella, dovresti vedere una colonna "Posizione". Di solito puoi trascinare e rilasciare le righe per riordinarle, oppure potrebbero esserci frecce su/giù o un campo numerico modificabile per cambiare la posizione. Ricorda di salvare le modifiche se richiesto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Caselle di controllo aggiuntive durante la registrazione" segue un modello MVC (Model-View-Controller) standard di PrestaShop, estendendo principalmente `Module` per la sua funzionalità principale e `AdminController` per la gestione del Back Office. Sfrutta il sistema di hook di PrestaShop per iniettare campi personalizzati nei moduli di registrazione e identità del cliente e per registrare i dati di consenso. Il modulo introduce tabelle di database personalizzate per memorizzare le definizioni delle caselle di controllo e la cronologia dei consensi dei clienti.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non utilizza controller frontali dedicati. Tutte le interazioni del front-office (visualizzazione delle caselle di controllo, elaborazione del consenso) sono gestite direttamente tramite i controller principali dei clienti di PrestaShop, sfruttando hook specifici.
-   **Controller Admin Back-Office**:

    -   `addtos/controllers/admin/AdminAddTosHistory.php`
        -   **Nome classe e classe genitore**: `AdminAddTosHistoryController` estende `ModuleAdminController`.
        -   **Nome tab e entità gestita**: Gestisce i record storici dei consensi dei clienti. È accessibile tramite la tab "Cronologia" sotto il menu principale del modulo. Questo controller visualizza una vista `list` degli oggetti `TosHistory`, mostrando cliente, casella di controllo, stato del consenso, data e IP. Non consente la modifica o l'aggiunta di record, in quanto è un log storico.
    -   `addtos/controllers/admin/AdminAddTosList.php`
        -   **Nome classe e classe genitore**: `AdminAddTosListController` estende `ModuleAdminController`.
        -   **Nome tab e entità gestita**: Gestisce la definizione delle caselle di controllo personalizzate. È accessibile tramite la tab "Elenco caselle di controllo". Questo controller fornisce viste `list`, `add` e `edit` per gli oggetti `Tos`, consentendo agli amministratori di definire l'etichetta della casella di controllo, il link, lo stato obbligatorio, lo stato attivo e la posizione.
    -   `addtos/controllers/admin/index.php`
        -   Questo è un file segnaposto standard per impedire l'elenco delle directory. Tipicamente contiene `header('Location: ../../../index.php?controller=AdminHome');` o simili. Non ha alcun ruolo funzionale nella logica del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Le classi principali del modulo sono probabilmente definite all'interno del file `addtos.php` principale o direttamente all'interno della directory `classes/` se presente (anche se l'inventario suggerisce che potrebbero essere nel file principale).

-   `Tos` (Probabilmente definito all'interno di `addtos.php` o `classes/Tos.php`):

    -   **Tabella del database**: `ps_addtos_tos` (o simile, basato sul nome dell'entità `tos`).
    -   **Estende `ObjectModel`**: Sì.
    -   **Campi `$definition`**:
        -   `id_tos`: Chiave primaria.
        -   `name`: Campo `HTML`, `isLang` (multilingue) - l'etichetta della casella di controllo.
        -   `link`: Campo `HTML`, `isLang` (multilingue) - l'URL per maggiori informazioni.
        -   `required`: `BOOL` - se la casella di controllo è obbligatoria.
        -   `active`: `BOOL` - se la casella di controllo è attualmente visualizzata.
        -   `position`: `INT` - ordine di visualizzazione.
    -   **Metodi pubblici chiave**: Metodi `ObjectModel` standard per le operazioni CRUD.
-   `TosHistory` (Probabilmente definito all'interno di `addtos.php` o `classes/TosHistory.php`):

    -   **Tabella del database**: `ps_addtos_toshistory` (o simile, basato sul nome dell'entità `toshistory`).
    -   **Estende `ObjectModel`**: Sì.
    -   **Campi `$definition`**:
        -   `id_toshistory`: Chiave primaria.
        -   `id_customer`: `INT` - ID del cliente che ha dato il consenso.
        -   `id_tos`: `INT` - ID della casella di controllo.
        -   `accepted`: `BOOL` - `1` se accettato, `0` se rifiutato (o `NULL` se opzionale e non spuntato).
        -   `date_add`: `DATE` - timestamp del consenso.
        -   `ip_address`: `STRING` - indirizzo IP del cliente al momento del consenso.
    -   **Metodi pubblici chiave**: Principalmente per operazioni `add` e `read`, poiché i record di cronologia sono immutabili.

### 4.4 Risorse JavaScript (`views/js/`)

L'inventario indica che non sono presenti file JavaScript specifici. Ciò suggerisce che qualsiasi convalida lato client o comportamento dinamico per le caselle di controllo è gestito dal JS principale di PrestaShop, dal JS del tema, o non è una funzionalità primaria di questo modulo (basandosi sulla convalida lato server).

### 4.5 Fogli di stile CSS (`views/css/`)

L'inventario indica che non sono presenti file CSS specifici. Ciò implica che il modulo si basa sullo stile predefinito di PrestaShop per gli elementi del modulo o sul CSS del tema attivo per stilizzare le caselle di controllo. Gli sviluppatori che desiderano personalizzare l'aspetto dovrebbero mirare ai selettori di input del modulo standard o potenzialmente alle classi aggiunte dal modulo nei suoi template.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `addtos/views/templates/hook/addtos_bo.tpl`: Questo template è probabilmente utilizzato nel Back Office, possibilmente per visualizzare un blocco del modulo o informazioni all'interno di una pagina di amministrazione, o per renderizzare contenuti all'interno della pagina di configurazione del modulo (es. notifiche di aggiornamento).
-   **Template admin (`views/templates/admin/`)**: Non sono elencati template admin dedicati, suggerendo che `AdminAddTosListController` e `AdminAddTosHistoryController` si basano sui template `list.tpl` e `form.tpl` predefiniti di PrestaShop per il rendering delle loro viste.
-   **Template front-office (`views/templates/front/`)**:
    -   `addtos/views/templates/front/identity.tpl`: Questo template è probabilmente agganciato alla pagina "Le mie informazioni personali" (Identità) del cliente. Visualizzerebbe l'elenco delle caselle di controllo e lo stato attuale del consenso del cliente, consentendo potenzialmente loro di aggiornare le proprie preferenze.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_addtos_tos`: Memorizza le definizioni di ogni casella di controllo personalizzata (etichetta, link, stato obbligatorio, stato attivo, posizione).
    -   `ps_addtos_tos_lang`: Memorizza il contenuto multilingue per i campi `name` e `link` della tabella `ps_addtos_tos`.
    -   `ps_addtos_toshistory`: Memorizza i record storici dei consensi dei clienti (ID cliente, ID casella di controllo, stato accettato, timestamp, indirizzo IP).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionValidateOrder` | Dopo la convalida di un ordine. | Potenzialmente utilizzato per registrare il consenso relativo a termini specifici dell'ordine, sebbene meno comune per le caselle di controllo di registrazione. |
| `validateCustomerFormFields` | Durante la convalida dell'invio del modulo di registrazione del cliente. | Cruciale per la convalida lato server delle caselle di controllo obbligatorie. Se una casella di controllo obbligatoria non è spuntata, questo hook impedirebbe la registrazione. |
| `displayAdditionalCustomerFormFields` | Renderizza campi aggiuntivi nel modulo di registrazione del cliente. | Hook principale per visualizzare le caselle di controllo personalizzate nella pagina di registrazione del front-office. |
| `displaytermsAndConditions` | Renderizza il contenuto dei termini e delle condizioni. | Potrebbe essere utilizzato per visualizzare le caselle di controllo vicino ai T&C standard, o come alternativa. |
| `displayvalidateCustomerFormFields` | Renderizza i messaggi di convalida per i campi del modulo cliente. | Utilizzato per visualizzare messaggi di errore se una casella di controllo obbligatoria non è spuntata. |
| `additionalCustomerFormFields` | Simile a `displayAdditionalCustomerFormFields`, potenzialmente per contesti o versioni diverse. | Un altro hook per iniettare campi personalizzati nei moduli cliente. |
| `termsAndConditions` | Simile a `displaytermsAndConditions`. | Un altro hook per iniettare termini e condizioni. |
| `actionCustomerAccountAdd` | Dopo la creazione di un nuovo account cliente. | Utilizzato per registrare le scelte di consenso del cliente per tutte le caselle di controllo attive nella tabella `ps_addtos_toshistory`. |
| `displayAdminCustomers` | Renderizza il contenuto nella pagina di elenco/modifica dei clienti dell'amministrazione. | Potrebbe essere utilizzato per visualizzare un riepilogo dei consensi di un cliente direttamente nel loro profilo del Back Office. |
| `displayCustomerAccountForm` | Renderizza il contenuto nella pagina "Le mie informazioni personali" (Identità) del cliente. | Utilizzato per visualizzare le caselle di controllo e consentire ai clienti di visualizzare/aggiornare le proprie preferenze di consenso dopo la registrazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Caselle di controllo aggiuntive durante la registrazione", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e alla configurazione del modulo.
