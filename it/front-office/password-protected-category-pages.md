---
title: "Pagine di categoria protette da password - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Pagine di categoria protette da password' di MyPresta.eu."
sidebar:
  label: "Pagine di categoria protette da password - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Password protected category pages su MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/password-protected-category-pages/)
>
> ---


# Pagine di categoria protette da password

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni principali. Questa schermata fornisce opzioni generali di gestione del modulo.

-   **Cosa fa questa impostazione:** Questa sezione include tipicamente le impostazioni standard dei moduli MyPresta.eu relative agli aggiornamenti e alle licenze. Assicura che il tuo modulo sia aggiornato e correttamente licenziato.
-   **Effetto della modifica di questa impostazione:**
    *   *`mypresta_updates`*: Questa impostazione controlla se il modulo verifica automaticamente la presenza di aggiornamenti. Mantenendola abilitata ti assicura di essere avvisato delle nuove versioni.
    *   *`update_` e `updatev_`*: Queste sono impostazioni interne utilizzate dal modulo per gestire i controlli degli aggiornamenti e le informazioni sulla versione. Generalmente non è necessario interagire direttamente con queste.
-   **Valore consigliato:** Mantieni `mypresta_updates` abilitato per ricevere aggiornamenti importanti e correzioni di bug.
-   **Scenario / esempio per il commerciante:** Se vuoi assicurarti che il tuo modulo abbia sempre le ultime funzionalità e patch di sicurezza, mantieni abilitato il controllo degli aggiornamenti. Se hai un negozio altamente personalizzato e preferisci controllare manualmente gli aggiornamenti dopo test approfonditi, potresti disabilitarlo, ma questo non è generalmente consigliato per la maggior parte dei commercianti.

### 2.2 Schermata amministrativa dedicata: Password delle categorie (Back Office > Catalogo > Password delle categorie)

Questa è la schermata di gestione principale per impostare e gestire le password per le tue categorie.

-   **Nome schermata e posizione nel menu:** Puoi trovare questa schermata navigando su **Catalogo > Password delle categorie** nel menu del tuo Back Office PrestaShop.
-   **Azioni e impostazioni disponibili:**
    *   **Elenco categorie:** Questa schermata visualizza un elenco di tutte le tue categorie. Per ogni categoria, vedrai se è attualmente protetta da password e quante password le sono state assegnate.
    *   **Aggiungi/Modifica password:** Per ogni categoria, puoi cliccare su un pulsante "Modifica" o "Gestisci password" (o icona simile) per aprire un'interfaccia dedicata. Qui puoi:
        *   **Seleziona una categoria:** Scegli la categoria specifica che desideri proteggere.
        *   **Aggiungi nuova password:** Inserisci una nuova password per la categoria selezionata. Puoi aggiungere più password per una singola categoria. Questo è utile se desideri fornire codici di accesso diversi a diversi gruppi di clienti (ad es. "VIP123" per i clienti premium, "WHOLESALE456" per i partner B2B).
        *   **Elimina password:** Rimuovi le password esistenti.
        *   **Abilita/Disabilita protezione:** Potrebbe essere disponibile un interruttore o una casella di controllo per abilitare o disabilitare rapidamente la protezione con password per una categoria senza eliminare tutte le sue password.
-   **Effetto delle modifiche:**
    *   **Aggiunta di una password:** La categoria selezionata diventerà immediatamente protetta da password nel front office. I clienti dovranno inserire una delle password assegnate per visualizzare i suoi prodotti.
    *   **Eliminazione di una password:** Quella specifica password non garantirà più l'accesso. Se era l'unica password per una categoria, la categoria potrebbe diventare non protetta (a seconda della logica esatta del modulo, è più sicuro disabilitare esplicitamente la protezione se la si desidera aperta).
    *   **Disabilitazione della protezione:** La categoria diventerà nuovamente accessibile pubblicamente e i clienti vedranno i suoi prodotti senza bisogno di una password.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Vai su **Catalogo > Password delle categorie**.
    2.  Identifica la categoria che desideri proteggere.
    3.  Clicca sull'icona "Gestisci password" o "Modifica" accanto ad essa.
    4.  Nella nuova schermata, aggiungi una o più password. Ricorda che ogni password che aggiungi garantirà l'accesso.
    5.  Salva le modifiche.
    6.  Per rimuovere la protezione, elimina tutte le password per quella categoria o usa un interruttore "Abilita/Disabilita" se disponibile.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | `mypresta_updates` | Abilitato | Controlla i controlli automatici degli aggiornamenti per il modulo. Mantienilo abilitato per le ultime funzionalità e sicurezza. |
| Pagina di configurazione del modulo | `update_`, `updatev_` | (Interno) | Impostazioni interne per la gestione degli aggiornamenti. Nessuna interazione del commerciante necessaria. |
| Password delle categorie (Catalogo > Password delle categorie) | Elenco categorie | N/A | Panoramica di tutte le categorie e del loro stato di protezione con password. |
| Password delle categorie (Catalogo > Password delle categorie) | Aggiungi/Modifica password | N/A | Consente di aggiungere, modificare o eliminare password per categorie specifiche. Sono supportate più password per categoria. |
| Password delle categorie (Catalogo > Password delle categorie) | Abilita/Disabilita protezione | N/A | Attiva o disattiva la protezione con password per una categoria. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato una password, ma la categoria è ancora visibile senza di essa. Cosa c'è che non va?**
R1:

-   **Svuota la cache:** La ragione più comune è la cache. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" e "Svuota la cache" per tutte le cache).
-   **Controlla lo stato della categoria:** Assicurati che la categoria stessa sia attiva e visibile nel tuo negozio.
-   **Verifica l'inserimento della password:** Ricontrolla di aver inserito e salvato correttamente la/e password nella sezione **Catalogo > Password delle categorie**.
-   **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo gestisca questo automaticamente, se hai temi pesantemente personalizzati, a volte gli hook possono essere sovrascritti.

**D2: Posso avere più password per una categoria?**
R2: Sì! Questo modulo supporta esplicitamente un numero illimitato di password per una singola categoria. Questo è utile per dare codici di accesso diversi a gruppi diversi (ad es. password "VIP", password "Ingrosso").

**D3: Cosa succede se un cliente tenta di accedere a un prodotto direttamente da una categoria protetta tramite il suo URL?**
R3: Se un prodotto appartiene a una categoria protetta da password, l'accesso diretto alla pagina del prodotto richiederà comunque l'inserimento della password della categoria. Il modulo assicura che il contesto della categoria sia rispettato, impedendo l'accesso diretto ai prodotti all'interno di una categoria protetta senza autenticazione.

**D4: Come rimuovo la protezione con password da una categoria?**
R4: Vai su **Catalogo > Password delle categorie**. Trova la categoria che desideri sbloccare. Puoi eliminare tutte le password associate a quella categoria, oppure, se è presente un interruttore esplicito "Abilita/Disabilita" per la protezione della categoria, utilizzalo. Una volta rimosse tutte le password o disabilitata la protezione, la categoria tornerà ad essere accessibile pubblicamente.

**D5: Il modulo password non ha un bell'aspetto sul mio tema personalizzato. Come posso risolverlo?**
R5: Il modulo utilizza la templating e il CSS standard di PrestaShop. Se non ha un bell'aspetto, è probabile che si tratti di un conflitto CSS con il tuo tema personalizzato.

-   **Ispeziona elemento:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi del modulo password. Cerca regole CSS in conflitto dal tuo tema.
-   **CSS personalizzato:** Puoi aggiungere CSS personalizzato al file `custom.css` del tuo tema (o simile) per sovrascrivere lo stile predefinito del modulo e farlo corrispondere al tuo tema.
-   **Contatta il supporto:** Se non ti senti a tuo agio con il CSS, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Pagine di categoria protette da password" si integra nell'architettura MVC di PrestaShop principalmente sovrascrivendo il `CategoryController` principale per intercettare le richieste alle pagine di categoria. Utilizza un Controller Admin dedicato (`AdminCatPasswordController`) per gestire le associazioni categoria-password, memorizzandole in una tabella di database personalizzata. La visualizzazione del front-office è gestita tramite un template Smarty personalizzato per il modulo di inserimento password.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `catpswd/override/controllers/front/listing/CategoryController.php`
        -   **Nome classe:** `CategoryController` (sovrascrive il `CategoryController` principale di PrestaShop)
        -   **Classe padre:** `CategoryControllerCore`
        -   **Responsabilità:** Questa sovrascrittura è il cuore della funzionalità front-office del modulo. Intercetta le richieste alle pagine di categoria. Prima di visualizzare il contenuto effettivo della categoria, verifica se la categoria è protetta da password. Se lo è, e l'utente non ha ancora inserito la password corretta (o la sessione è scaduta), renderizza il modulo di inserimento password (`category.tpl`) invece della pagina di categoria standard. Gestisce l'invio del modulo password, convalida la password inserita e imposta una variabile di sessione in caso di autenticazione riuscita.
    -   `catpswd/override/controllers/front/listing/index.php`
        -   **Responsabilità:** Questo è un file `index.php` standard di PrestaShop all'interno di una directory di override, tipicamente utilizzato per prevenire l'elenco diretto delle directory e garantire il corretto caricamento del modulo. Non contiene una logica di controller attiva.
-   **Controller Admin Back-Office**:

    -   `catpswd/controllers/admin/AdminCatPasswordController.php`
        -   **Nome scheda:** "Password delle categorie" (sotto il menu Catalogo)
        -   **Entità gestita:** `CatPassword` (sebbene non sia esplicitamente elencato alcun `ObjectModel`, questo controller gestisce le relazioni categoria-password, probabilmente interagendo direttamente con il database o una classe helper).
        -   **Responsabilità:** Questo controller fornisce l'interfaccia nel Back Office di PrestaShop per gli amministratori per gestire la protezione con password per le categorie. Elenca le categorie, consente di aggiungere più password a una categoria e di rimuoverle. Gestisce le operazioni CRUD per i dati categoria-password.
    -   `catpswd/controllers/admin/index.php`
        -   **Responsabilità:** Simile all'`index.php` del front-office, questo file impedisce l'elenco diretto delle directory per la directory dei controller admin.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi esplicite nella directory `classes/`. Ciò suggerisce che l'`AdminCatPasswordController` gestisce probabilmente le interazioni con il database direttamente o utilizza una semplice funzione helper all'interno del file principale del modulo (`catpswd.php`) per la gestione dei dati, piuttosto che un `ObjectModel` dedicato.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo indica l'assenza di file JavaScript specifici. L'invio e la convalida della password sono probabilmente gestiti tramite l'invio di moduli HTML standard e l'elaborazione lato server all'interno dell'override di `CategoryController`.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo indica l'assenza di file CSS specifici. Lo stile per il modulo di inserimento password è probabilmente minimale e si basa sullo stile di base del tema predefinito di PrestaShop. Gli sviluppatori che desiderano personalizzare l'aspetto dovrebbero mirare agli elementi del modulo all'interno del template `category.tpl` utilizzando il CSS personalizzato del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `catpswd/lib/searchTool/views/scripts.tpl`
        -   **Hook:** Probabilmente utilizzato in `displayHeader` o `actionAdminControllerSetMedia` (se contiene inclusioni JS/CSS per uno strumento di ricerca).
        -   **Output:** Questo template probabilmente contiene inclusioni JavaScript o CSS, possibilmente per un'utilità di ricerca utilizzata all'interno dell'interfaccia amministrativa del modulo o per la funzionalità del front-office.
-   **Template front-office (`views/templates/front/`)**:
    -   `catpswd/views/templates/front/category.tpl`
        -   **Scopo:** Questo è il template renderizzato dal `CategoryController` sovrascritto quando una categoria protetta da password viene acceduta senza autenticazione. Visualizza il modulo di inserimento password al cliente. Tipicamente include campi per la password, un pulsante di invio e messaggi per tentativi riusciti o falliti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   `ps_catpassword`: Questa tabella personalizzata viene creata dal modulo durante l'installazione. Memorizza le associazioni tra gli ID delle categorie e le rispettive password.
        -   **Colonne (previste):** `id_catpassword` (chiave primaria), `id_category` (chiave esterna a `ps_category`), `password` (la stringa della password hashata o in chiaro).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potenzialmente utilizzato per includere risorse CSS o JS globali, o per impostare meta tag relativi alla funzionalità del modulo. |
| `actionAdminControllerSetMedia` | Quando un controller admin viene caricato e i suoi media (JS/CSS) vengono impostati. | Utilizzato dal modulo per iniettare i suoi file JavaScript e CSS specifici nel Back Office per l'`AdminCatPasswordController` o altre pagine admin dove sono necessarie le risorse del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e a garantire che il modulo funzioni senza problemi.
